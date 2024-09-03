---
title : "Introductions"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

**Terraform** và **Ansible** là hai công cụ mạnh mẽ và phổ biến được sử dụng để tự động hóa quy trình triển khai hạ tầng và ứng dụng.

Terraform

- Terraform là một công cụ Infrastructure as Code (IaC) do HashiCorp phát triển, cho phép người dùng định nghĩa, xem trước và áp dụng các thay đổi hạ tầng trên nhiều nhà cung cấp dịch vụ đám mây khác nhau như AWS, Azure, Google Cloud Platform, và nhiều hơn nữa. Terraform sử dụng một ngôn ngữ khai báo có tên là HashiCorp Configuration Language (HCL) để mô tả hạ tầng dưới dạng mã.

- Bằng cách sử dụng Terraform, chúng ta có thể tự động hóa việc tạo và quản lý các tài nguyên hạ tầng như máy ảo, mạng, bộ nhớ, và các dịch vụ khác, giúp đảm bảo rằng môi trường hạ tầng luôn nhất quán và có thể tái tạo được.

Ansible

- Ansible là một công cụ tự động hóa mã nguồn mở do Red Hat phát triển, được sử dụng để cấu hình hệ thống, triển khai phần mềm và điều phối các tác vụ khác trên hạ tầng CNTT.
- Ansible hoạt động theo mô hình "agentless" (không cần cài đặt agent trên các máy chủ đích) và sử dụng SSH để kết nối và thực thi các tác vụ trên máy chủ từ xa.

- Với Ansible, chúng ta có thể tự động hóa việc cài đặt và cấu hình phần mềm, triển khai ứng dụng và thực hiện các tác vụ quản lý hệ thống khác thông qua các playbook - các tệp YAML mô tả các tác vụ cần thực hiện.
