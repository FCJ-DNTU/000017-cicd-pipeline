+++
title = "Thiết lập Github"
date = 2024
weight = 1
chapter = false
pre = "<b>5.1. </b>"
+++

#### Fork github repository

Truy cập vào github [aws-fcj-container-app-codebuild](https://github.com/FromSunNews/aws-fcj-container-app-codebuild).

- Chọn **fork**.

![fork-repo](/images/6-cicd-codebuild/6.1.1.png)

- Repository name: `aws-fcj-container-app-codebuild`.
- Chọn **Copy the master branch only**.
- Chọn **Create fork**.

![fork-repo](/images/6-cicd-codebuild/6.1.2.png)

Đặt tên cho version github vừa tạo

Vào path như sau: \***\*aws-fcj-container-app-codebuild/frontend/src
/components/**

- Chọn **Menu.jsx**.
- Chọn **Edit**.
- Đổi version `Dashboard v1.0.3`

![fork-repo](/images/6-cicd-codebuild/6.1.3.png)

#### Tạo quyền truy cập cá nhân

- Chọn **Settings**.

![fork-repo](/images/6-cicd-codebuild/6.1.4.png)

- Chọn **Developer settings**.

![fork-repo](/images/6-cicd-codebuild/6.1.5.png)

- Chọn **Personal access tokens**.
- Chọn **Tokens (classic)**.
- Chọn **Generate new token**.
- Chọn **Generate new token classic **.

![fork-repo](/images/6-cicd-codebuild/6.1.6.png)

- Note: `access by code build`.
- Chọn repo

![fork-repo](/images/6-cicd-codebuild/6.1.7.png)

- Chọn **project**
- Chọn **Generate token**.

![fork-repo](/images/6-cicd-codebuild/6.1.8.png)

{{% notice warning %}}
**Lưu ý quan trọng về Token:**

- Copy token ngay lập tức sau khi tạo
- Lưu token vào một nơi an toàn (ví dụ: notepad, password manager)
- Token sẽ chỉ hiển thị một lần duy nhất
- Nếu bạn quên lưu token, bạn sẽ cần tạo token mới
  {{% /notice %}}
