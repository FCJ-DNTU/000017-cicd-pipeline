+++
title = "Fork và Chỉnh sửa Repository"
date = 2024
weight = 1
chapter = false
pre = "<b>3.1. </b>"
+++

{{% notice note %}}
Trong phần này, chúng ta sẽ học cách fork một repository có sẵn và thực hiện các thay đổi trên repository đã fork. Điều này là bước đầu tiên để bắt đầu quá trình CI/CD.
{{% /notice %}}

#### Fork Repository

Fork Repository cho phép bạn tạo một bản sao độc lập của repository gốc trong tài khoản GitLab của mình. Điều này giúp bạn có thể tự do thực hiện các thay đổi mà không ảnh hưởng đến repository gốc.

1. Khởi tạo Fork
![Fork Button](/images/4-cicd-gitlab/4.1.1.png)

- Truy cập repository gốc tại [aws-fcj-container-app](https://gitlab.com/awsfirstcloudjourney/aws-fcj-container-app)
- Tìm và nhấn nút "Fork" ở góc trên bên phải

2. Cấu hình Fork
![Fork Configuration](/images/4-cicd-gitlab/4.1.2.png)

Thiết lập các thông số cơ bản:
- Project name: Giữ nguyên aws-fcj-container-app
- Project URL: Chọn namespace phù hợp
- Project slug: Để mặc định
- Branches: Chọn All branches để sao chép toàn bộ
- Visibility: Chọn Public để mọi người có thể truy cập
- Hoàn tất bằng cách nhấn Fork project

{{% notice tip %}}
Việc chọn All branches giúp bạn có được toàn bộ lịch sử phát triển của project, hữu ích cho việc theo dõi các thay đổi và phát triển tính năng mới.
{{% /notice %}}

3. Xác nhận Fork
![Fork Result](/images/4-cicd-gitlab/4.1.3.png)

Kiểm tra các yếu tố sau:
- Thông báo fork thành công xuất hiện
- Cấu trúc thư mục được sao chép đầy đủ
- Thông tin về commits và branches được giữ nguyên

#### Chỉnh sửa Source Code

1. Định vị File
![Navigate to File](/images/4-cicd-gitlab/4.1.4.png)

Truy cập file cần sửa:
- Đường dẫn: frontend/src/components/Menu.jsx
- Chọn Edit rồi Edit single file

2. Cập nhật Nội dung
![Edit Content](/images/4-cicd-gitlab/4.1.5.png)

Thực hiện chỉnh sửa:
- Xác định vị trí cần thay đổi
- Cập nhật text từ Dashboard thành Dashboard v1.0.1

3. Commit Thay đổi
![Commit Changes](/images/4-cicd-gitlab/4.1.6.png)

Lưu các thay đổi:
- Viết commit message mô tả rõ ràng
- Xác nhận branch đích là main
- Xác nhận bằng Commit changes

{{% notice tip %}}
Commit message nên tuân theo format: type(scope): message
Ví dụ: feat(frontend): update dashboard title to v1.0.1
Điều này giúp dễ dàng theo dõi và quản lý các thay đổi trong project.
{{% /notice %}}
