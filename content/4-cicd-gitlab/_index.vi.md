+++
title = "Triển khai CI/CD với Gitlab"
date = 2024
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

#### Tổng quan

Trong phần này, chúng ta sẽ tìm hiểu cách triển khai ứng dụng tự động sử dụng Gitlab CI/CD pipeline kết hợp với các dịch vụ AWS như ECR, ECS, CodeDeploy.

![Quy trình Pipeline](/images/4-cicd-gitlab/4.0.1.png)

#### Quy trình Pipeline

1. **Khởi động Pipeline**
   - Developer tạo tag và push code lên Gitlab repository
   - Gitlab CI/CD được trigger tự động khi developer tạo tag mới

2. **Build**
   - Code được build thành Docker image

3. **Push Image**
   - Image được đẩy lên Amazon ECR (Elastic Container Registry) hoặc DockerHub

4. **Cập nhật**
   - Cập nhật ECS Task Definition của cả Frontend và Backend

5. **Triển khai**
   - Frontend service:
     - Cập nhật revision mới của service frontend
   - Backend service:
     - Cập nhật code deploy mới của service backend

#### Nội dung

1. [Fork và Chỉnh sửa Code](1-forkandmodifycode)

2. [Cài đặt Gitlab và Runner](2-setupgitlabandrunner)

3. [Chỉnh sửa và Thêm Role](3-modifyandaddrole)

4. [Tạo Tag và Theo dõi Pipeline](4-createtagandviewpipeline)

5. [Kiểm tra Kết quả](5-checkresult)

Sau khi hoàn thành module này, bạn sẽ có khả năng:
- Thiết lập và quản lý CI/CD pipeline với Gitlab
- Tự động hóa quy trình triển khai ứng dụng
- Xử lý các vấn đề phát sinh trong quá trình triển khai
- Áp dụng các best practices trong DevOps