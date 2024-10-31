+++
title = "Kiểm tra kết quả"
date = 2024
weight = 5
chapter = false
pre = "<b>5.5. </b>"
+++

#### Kiểm tra kết quả triển khai

Kiểm tra kết quả build trên GitHub:

- Truy cập vào GitHub repository để xem tổng quan kết quả build

![github-overview](/images/6-cicd-codebuild/6.5.1.png)

Kiểm tra Frontend Build:

- Truy cập vào Frontend Build project
- Xem chi tiết quá trình build trong phần **Build logs**

![frontend-logs](/images/6-cicd-codebuild/6.5.2.png)

Kiểm tra Backend Build:

- Tương tự, kiểm tra logs của Backend trong phần **Build logs**

![backend-logs](/images/6-cicd-codebuild/6.5.3.png)

Xác nhận cấu hình ECS:

- Truy cập ECS Task definition
- Kiểm tra cấu hình của cả Frontend và Backend

![task-definition-1](/images/6-cicd-codebuild/6.5.4.png)
![task-definition-2](/images/6-cicd-codebuild/6.5.5.png)

Kiểm tra chi tiết triển khai:

- Xem xét phần **Configuration and networking**

![config-network](/images/6-cicd-codebuild/6.5.6.png)

- Kiểm tra thông tin **Deployment**

![deployment](/images/6-cicd-codebuild/6.5.7.png)

Kiểm tra ứng dụng:

- Truy cập vào ứng dụng để xác nhận hoạt động

![application](/images/6-cicd-codebuild/6.5.8.png)
