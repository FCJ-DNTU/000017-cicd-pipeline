+++
title = "Triển khai CI/CD với CodeBuild"
date = 2024
weight = 5
chapter = false
pre = "<b>5. </b>"
+++

#### Tổng quan
Trong phần này, chúng ta sẽ tìm hiểu cách triển khai ứng dụng tự động sử dụng CodeBuild kết hợp với các dịch vụ AWS như ECR, ECS, CodeDeploy.

![Quy trình Pipeline](/images/4-cicd-gitlab/4.0.3.png)

#### Quy trình Pipeline

1. **Khởi động Pipeline**
   - Developer tạo tag và push code lên Github repository
   - CodeBuild được trigger tự động khi developer tạo tag mới

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

1. [Github repository](1-github)

2. [Create CodeBuild Frontend](2-create-code-build-fe)

3. [Create CodeBuild Backend](3-create-code-build-be)

4. [Create tag](4-create-tag)

5. [Check result](5-result)

Sau khi hoàn thành module này, bạn sẽ có khả năng:
- Thiết lập và quản lý CI/CD pipeline với CodeBuild trigger bởi Github Repository
- Tự động hóa quy trình triển khai ứng dụng
- Xử lý các vấn đề phát sinh trong quá trình triển khai
- Áp dụng các best practices trong DevOps