+++
title = "Tạo CodeBuild Frontend"
date = 2024
weight = 2
chapter = false
pre = "<b>5.2.</b>"
+++

#### Tạo CodeBuild Frontend

- Truy cập AWS Console và tìm dịch vụ **CodeBuild** trong menu

![codebuild-menu](/images/6-cicd-codebuild/6.2.1.png)

- Chọn **Build project**
- Chọn **Create project**

![create-project](/images/6-cicd-codebuild/6.2.2.png)

- Nhập Project name: `aws-fcj-container-fe`
- Chọn **GitHub** làm Source provider

![source-provider](/images/6-cicd-codebuild/6.2.3.png)

- Tại Connection, chọn **Custom**
- Chọn **Personal access token**
- Chọn **Create a new secret**
- Trong bảng **Create secret**, điền các thông tin:
  - Secret name: `codebuild-github-access-token`
  - Secret description: `Access token for github`
  - GitHub personal access token: Dán token GitHub đã tạo ở bước trước

![create-secret](/images/6-cicd-codebuild/6.2.4.png)

Quay lại GitHub để lấy URL Repository:

- Copy HTTPS URL của repository

![github-url](/images/6-cicd-codebuild/6.2.5.png)

Quay lại CodeBuild:

- Chọn **Repository in my GitHub account**
- Dán HTTPS URL vào ô GitHub repository
- Source version: `refs/tags/*`

![source-config](/images/6-cicd-codebuild/6.2.6.png)

Tại phần Primary source webhook events:

- Chọn **Rebuild every time a code change is pushed to the repository**
- Chọn **Single build**
- Nhấn **Add filter group**

![webhook-events](/images/6-cicd-codebuild/6.2.7.png)

- Chọn Event type: **PUSH**
- Nhập Pattern: `^refs/tags/`

![webhook-filter](/images/6-cicd-codebuild/6.2.8.png)

Cấu hình môi trường:

- Provisioning model: `On-demand`
- Environment image: `Managed image`
- Compute: **EC2**
- Operating system: **Ubuntu**
- Runtime: **Standard**
- Image: **aws/codebuild/standard:7.0**
- Image version: **Always use latest image for version**

![environment](/images/6-cicd-codebuild/6.2.9.png)

- Service role: `aws-fcj-container-fe-service-role`
- Chọn **Next**

Mở rộng **Additional configuration**

![additional-config](/images/6-cicd-codebuild/6.2.10.png)

- Chọn **Add environment variable**
- Thêm các biến môi trường theo bảng:

![env-variables](/images/6-cicd-codebuild/6.2.11.png)

Cấu hình **Buildspec**:

- Chọn **Use a buildspec file**
- Buildspec name: `frontend/buildspec.yml`

![buildspec](/images/6-cicd-codebuild/6.2.12.png)

Cấu hình **Logs**:

- Chọn **Enable cloudwatch logs**
- Chọn **Create build project**

![logs](/images/6-cicd-codebuild/6.2.13.png)

#### Thêm role cho FE CodeBuild

Sau khi tạo build project:

- Truy cập vào build project vừa tạo
- Tại phần **Service role**, nhấp vào role để chuyển đến trang quản lý IAM

![service-role](/images/6-cicd-codebuild/6.2.14.png)

Thêm quyền cho role:

- Chọn **Add permissions**
- Chọn **Attach policy**
- Tìm và chọn các policy sau:
  - `AmazonECS_FullAccess`
  - `CloudWatchLogsFullAccess`
  - `WriteECRRepositoryContent`
- Chọn **Attach policies**

![attach-policies](/images/6-cicd-codebuild/6.2.15.png)
