+++
title = "Tạo CodeBuild Backend"
date = 2024
weight = 3
chapter = false
pre = "<b>5.3.</b>"
+++

#### Tạo CodeBuild Backend

- Truy cập AWS Console và tìm dịch vụ **CodeBuild** trong menu
- Chọn **Build project**
- Chọn **Create project**
- Nhập Project name: `aws-fcj-container-be`

![create-project](/images/6-cicd-codebuild/6.3.1.png)

Cấu hình Source:

- Chọn **GitHub** làm Source provider
- Chọn **Personal access**
- Chọn **Personal access token**
- Tại Connection, chọn secret đã tạo ở bước trước
- Chọn **Repository in my GitHub account**
- Dán HTTPS URL vào ô GitHub repository (URL đã copy ở bước 6.2)
- Source version: `refs/tags/*`

![source-config](/images/6-cicd-codebuild/6.3.2.png)

Tại phần **Primary source webhook events**:

- Webhook: Chọn **Rebuild every time a code change is pushed to the repository**
- Chọn **Single build**
- Event type: **PUSH**
- Nhập HEAD_REF: `HEAD_REF`
- Nhập Pattern: `^refs/tags/`

![webhook-config](/images/6-cicd-codebuild/6.3.3.png)

Cấu hình môi trường:

- Provisioning model: `On-demand`
- Environment image: `Managed image`
- Compute: **EC2**
- Operating system: **Ubuntu**
- Runtime: **Standard**
- Image: **aws/codebuild/standard:7.0**
- Image version: **Always use latest image for version**
- Service role: **New service role**
- Role name: `codebuild-aws-fcj-container-be-service-role`

![environment](/images/6-cicd-codebuild/6.3.4.png)

Mở rộng **Additional configuration**

![additional-config](/images/6-cicd-codebuild/6.3.5.png)

- Chọn **Add environment variable**
- Thêm các biến môi trường theo bảng:

![env-variables](/images/6-cicd-codebuild/6.3.6.png)

- Nhấn **Create build project** để hoàn tất

![create-complete](/images/6-cicd-codebuild/6.3.7.png)

#### Thêm role cho BE CodeBuild

Sau khi tạo xong build project:

- Truy cập vào build project vừa tạo

![access-project](/images/6-cicd-codebuild/6.3.8.png)

- Tại phần **Service role**, nhấp vào role để chuyển đến trang quản lý IAM

![service-role](/images/6-cicd-codebuild/6.3.9.png)

Thêm quyền cho role:

- Chọn **Add permissions**
- Chọn **Attach policy**
- Tìm và chọn các policy sau:
  - `AmazonECS_FullAccess`
  - `CloudWatchLogsFullAccess`
  - `WriteECRRepositoryContent`
- Chọn **Attach policies**

![attach-policies](/images/6-cicd-codebuild/6.3.10.png)
