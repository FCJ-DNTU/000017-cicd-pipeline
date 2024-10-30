+++
title = "Triển khai CI/CD với Github Action"
date = 2024
weight = 5
chapter = false
pre = "<b>5. </b>"
+++

#### Tổng quan
Trong phần này, chúng ta sẽ tìm hiểu cách triển khai ứng dụng tự động sử dụng Github Action kết hợp với các dịch vụ AWS như ECR, ECS, CodeDeploy.

![Quy trình Pipeline](/images/4-cicd-gitlab/4.0.2.png)

#### Quy trình Pipeline

1. **Khởi động Pipeline**
   - Developer tạo tag và push code lên Github repository
   - Github Action được trigger tự động khi developer tạo tag mới

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

1. [Clone template Github](1-clone-project)
2. [Tạo mới một project và push code lên Github](2-new-project-push-code)
3. [Tạo access key và secret key](3-accesskey-secretkey)
4. [Kiểm tra kết quả](4-result)