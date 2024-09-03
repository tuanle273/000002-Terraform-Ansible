---
title : "Cài đặt Terraform"
date : "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2.1.2 </b> "
---


Cài đặt Terraform trên Windows
Bạn có thể cài đặt Terraform trên Windows một cách dễ dàng bằng cách sử dụng Chocolatey, một trình quản lý gói phổ biến cho Windows. Dưới đây là các bước hướng dẫn chi tiết:

***Bước 1:*** Cài đặt Chocolatey
Nếu bạn chưa cài đặt Chocolatey, hãy làm theo các bước sau:

Mở PowerShell với quyền Quản trị:

Tìm kiếm "PowerShell" trong menu Start, nhấp chuột phải và chọn "Run as Administrator".
Cài đặt Chocolatey:

Sao chép và dán lệnh sau vào PowerShell và nhấn Enter:
powershell
Copy code

``` Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1')) ```

Chờ cho quá trình cài đặt hoàn tất.


***Bước 2:*** Cài đặt Terraform bằng Chocolatey
Cài đặt Terraform:

Mở PowerShell với quyền Quản trị (nếu chưa mở).
Chạy lệnh sau để cài đặt Terraform:

```choco install terraform -y```

Kiểm tra cài đặt:

Sau khi quá trình cài đặt hoàn tất, bạn có thể kiểm tra phiên bản Terraform đã được cài đặt bằng lệnh:

```terraform --version```

***Bước 3:*** Terraform đã được cài đặt thành công
Nếu Terraform đã được cài đặt thành công, bạn sẽ thấy phiên bản của Terraform hiển thị trong PowerShell.

Terraform v1.5.0