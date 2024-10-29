+++
title = "Cấu hình Quyền và IAM Role"
date = 2024
weight = 3
chapter = false
pre = "<b>4.3. </b>"
+++

#### Thiết lập Quyền Sudo cho GitLab Runner

{{% notice note %}}
GitLab Runner cần quyền sudo để thực thi các tác vụ CI/CD như build, test và deploy. Phần này sẽ hướng dẫn cách cấu hình quyền sudo cho GitLab Runner.
{{% /notice %}}

1. Mở File Cấu hình Sudo
![Visudo Command](/images/4-cicd-gitlab/4.3.1.png)

Thực thi lệnh:
```bash
sudo visudo
```

2. Cập nhật Quyền Sudo
![Update Sudo](/images/4-cicd-gitlab/4.3.2.png)

Thêm dòng sau vào file:
```bash
gitlab-runner ALL=(ALL) NOPASSWD:ALL
```

{{% notice tip %}}
Sau khi thêm, nhấn `Ctrl + X` để thoát, `Y` để xác nhận lưu và `Enter` để hoàn tất.
{{% /notice %}}

#### Cấu hình IAM Role

1. Truy cập EC2 Instance
![EC2 Access](/images/4-cicd-gitlab/4.3.3.png)

Các bước thực hiện:
- Mở EC2 Console
- Chọn instance đang chạy
- Vào mục Security
- Chọn Modify IAM role

2. Kiểm tra Role Hiện Tại
![Check Role](/images/4-cicd-gitlab/4.3.4.png)

Xác nhận IAM Role `CustomRWECRRole` đã được gán cho EC2.

3. Truy cập IAM Role
![Access IAM](/images/4-cicd-gitlab/4.3.5.png)

Điều hướng trong IAM Console:
- Chọn tab Roles
- Tìm `CustomRWECRRole`
- Nhấn vào role để xem chi tiết

4. Bổ sung Policy
![Add Policy](/images/4-cicd-gitlab/4.3.6.png)

Thêm quyền mới:
- Policy cần thêm: `AmazonEC2FullAccess`
- Gán vào role `CustomRWECRRole`

{{% notice warning %}}
Việc gán `AmazonEC2FullAccess` cần được cân nhắc kỹ trong môi trường production. Nên tuân theo nguyên tắc least privilege và chỉ cấp những quyền thực sự cần thiết.
{{% /notice %}}