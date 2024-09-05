---
title: "Triển khai ứng dụng"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

1. Chuẩn bị file cài đặt cơ bản:

`terraform init`

2. main.tf với nội dung:

```yaml
provider "aws" {
region = "ap-southeast-1"
}

resource "tls_private_key" "key" {
algorithm = "RSA"
}

resource "aws_key_pair" "key_pair" {
key_name   = "ansible-key"
public_key = tls_private_key.key.public_key_openssh
}

resource "local_sensitive_file" "private_key" {
filename        = "${path.module}/ansible.pem"
content         = tls_private_key.key.private_key_pem
file_permission = "0400"
}

resource "aws_security_group" "allow_ssh" {
ingress {
from_port   = 22
to_port     = 22
protocol    = "tcp"
cidr_blocks = ["0.0.0.0/0"]
}

ingress {
from_port   = 80
to_port     = 80
protocol    = "tcp"
cidr_blocks = ["0.0.0.0/0"]
}

egress {
from_port   = 0
to_port     = 0
protocol    = "-1"
cidr_blocks = ["0.0.0.0/0"]
}
}


resource "aws_instance" "ansible_server" {
ami                    = "ami-0d07675d294f17973"
instance_type          = "t2.micro"
vpc_security_group_ids = [aws_security_group.allow_ssh.id]
key_name               = aws_key_pair.key_pair.key_name

provisioner "remote-exec" {
inline = [
"sudo yum update -y",
"sudo yum install -y software-properties-common",
"sudo yum-add-repository --yes --update ppa:ansible/ansible",
"sudo yum install -y ansible"
]

connection {
type        = "ssh"
user        = "ec2-user"
private_key = tls_private_key.key.private_key_pem
host        = self.public_ip
}
}
provisioner "local-exec" {
command = "ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -u ec2-user --key-file ansible.pem -T 300 -i '${self.public_ip},', playbook.yaml"
}


tags = {
Name = "Nginx Server"
}
}
```

3. Thêm file playbook.yaml với nội dung:

```yaml
- name: Install and Configure Nginx
  hosts: all
  become: true
  tasks:
    - name: Install Nginx
      yum:
        name: nginx
        state: present
      # Sử dụng 'apt' nếu hệ thống của bạn là Debian/Ubuntu
      # apt:
      #   name: nginx
      #   state: present
      when: ansible_os_family == "RedHat"
    - name: Ensure /var/www/html directory exists
      file:
        path: /usr/share/nginx/html
        state: directory
        mode: "0755"

    - name: Add index page
      template:
        src: index.html
        dest: /usr/share/nginx/html/index.html

    - name: Start and enable Nginx service
      service:
        name: nginx
        state: started
        enabled: true
```

4. Chạy câu lệnh dưới đây để tạo resource EC2 và triển khai web đơn giản bằng ansible

```command
terraform plan

terraform apply
```

![terraform](/images/2.prerequisite/terraform1.png)

5. Vào IP public của EC2, web đã được triển khai thành công

![terraform](/images/2.prerequisite/terraform2.png)
![terraform](/images/2.prerequisite/terraform3.png)
