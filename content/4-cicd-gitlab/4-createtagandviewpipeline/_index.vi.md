+++
title = "Thêm biến và chạy Pipeline"
date = 2024
weight = 4
chapter = false
pre = "<b>4.4. </b>"
+++

#### Thêm biến vào Gitlab
Truy cập CI/CD Variables
![Truy cập CI/CD Settings](/images/4-cicd-gitlab/4.4.3.png)

- Vào mục "Settings" trong menu bên trái
- Chọn "CI/CD" từ danh sách
- Mở rộng phần "Variables"

Thiết lập các biến môi trường
![Thiết lập Variables](/images/4-cicd-gitlab/4.4.4.png)

Thêm các biến sau vào project:
- CLUSTER_NAME: Tên ECS Cluster nơi chứa service frontend và backend
- SERVICE_NAME_FE: Tên ECS Service của frontend cần update trong Cluster
- SERVICE_NAME_BE: Tên ECS Service của backend cần update trong Cluster
- REGION: Region AWS đang sử dụng (vd: ap-southeast-1)
- AWS_APPLICATION_NAME: Tên ứng dụng trong CodeDeploy
- AWS_DEPLOYMENT_GROUP_NAME: Tên deployment group trong CodeDeploy
- ACCOUNT_NUMBER: AWS Account ID
- CI_PROJECT_BE_NAME: Tên project backend trong ECR
- CI_PROJECT_FE_NAME: Tên project frontend trong ECR
- TASK_NAME_FE: Tên Task Definition của frontend
- TASK_NAME_BE: Tên Task Definition của backend

{{% notice tip %}}
Đảm bảo tất cả các biến được đặt ở chế độ Protected và Masked để bảo vệ thông tin nhạy cảm.
{{% /notice %}}

#### Tạo tag

Truy cập Phần Tags
![Truy cập Tags](/images/4-cicd-gitlab/4.4.1.png)

- Nhấp vào "Code" ở thanh bên trái
- Chọn "Tags" từ menu con
- Nhấn nút "New tag" ở góc phải phía trên

Tạo Tag Mới
![Tạo Tag](/images/4-cicd-gitlab/4.4.2.png)

Điền các thông tin cần thiết:
- Nhập tên tag (ví dụ: "v1.0.1") vào trường Tag name
- Chọn "main" từ danh sách Create from
- Tùy chọn thêm message để mô tả tag
- Nhấn nút "Create tag" để hoàn tất

{{% notice tip %}}
Tags thường được sử dụng để đánh dấu các điểm phát hành trong mã của bạn. Sử dụng semantic versioning (ví dụ: v1.0.0) để quản lý phiên bản tốt hơn.
{{% /notice %}}

#### Xem Pipeline
au khi tạo tag, GitLab sẽ tự động kích hoạt pipeline để triển khai ứng dụng. Để xem quá trình thực thi:

Truy cập CI/CD Pipelines
![Truy cập CI/CD Pipelines](/images/4-cicd-gitlab/4.4.5.png)

- Nhấp vào "Build" ở thanh bên trái
- Chọn "Pipelines" từ menu con
- Chọn pipeline cần xem

Xem Tổng Quan Pipeline
![Xem Pipeline](/images/4-cicd-gitlab/4.4.6.png)

- Pipeline được kích hoạt cho tag "v1.0.1"
- Chọn "Job dependencies" để xem luồng công việc
- Bật "Show dependencies" để hiển thị mối quan hệ giữa các job
- Pipeline gồm 3 giai đoạn chính:
  + Build: Tạo Docker image cho cả frontend và backend
  + Push: Đẩy image lên container registry
  + Deploy: Triển khai ứng dụng lên môi trường

Xem Chi Tiết Job
![Chi Tiết Job](/images/4-cicd-gitlab/4.4.7.png)

- Mỗi job sẽ hiển thị log chi tiết quá trình thực thi
- Ví dụ với job deploy-backend:
  + Thực hiện login vào ECR
  + Chạy script deploy-backend.sh
  + Hiển thị deploymentId của quá trình triển khai
  + Kết quả thành công/thất bại của job

{{% notice tip %}}
  Màu xanh cho biết job thực thi thành công. Có thể click vào từng job để xem log chi tiết. Theo dõi thời gian thực thi và trạng thái của từng job.
{{% /notice %}}