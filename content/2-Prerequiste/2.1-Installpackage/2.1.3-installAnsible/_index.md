---
title : "Install Ansible"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.1.3 </b> "
---

#### Cài đặt Ansible trên Windows

***Bước 1:*** Cài đặt Chocolatey (nếu chưa cài đặt)
Mở PowerShell với quyền Quản trị (Run as Administrator):

Nhấn phím Windows, tìm "PowerShell", nhấp chuột phải và chọn "Run as Administrator".
Cài đặt Chocolatey:

Sao chép và dán lệnh sau vào PowerShell và nhấn Enter:

```Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))```

***Bước 2:*** Cài đặt Ansible bằng Chocolatey

Mở lại PowerShell với quyền Quản trị (nếu chưa mở).

Cài đặt Ansible bằng cách chạy lệnh sau trong PowerShell:

```choco install ansible -y```

***Bước 3:*** Kiểm tra cài đặt Ansible
Sau khi cài đặt xong, kiểm tra xem Ansible đã được cài đặt thành công hay chưa bằng cách chạy lệnh sau trong PowerShell:

```ansible --version```