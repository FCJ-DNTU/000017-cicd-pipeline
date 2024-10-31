+++
title = "GitHub Setup"
date = 2024
weight = 1
chapter = false
pre = "<b>5.1. </b>"
+++

#### Fork GitHub Repository

Access the GitHub repository [aws-fcj-container-app-codebuild](https://github.com/FromSunNews/aws-fcj-container-app-codebuild).

- Click **fork**.

![fork-repo](/images/6-cicd-codebuild/6.1.1.png)

- Repository name: `aws-fcj-container-app-codebuild`
- Select **Copy the master branch only**
- Click **Create fork**

![fork-repo](/images/6-cicd-codebuild/6.1.2.png)

Set the version for the newly created GitHub repository

Navigate to the following path: **aws-fcj-container-app-codebuild/frontend/src/components/**

- Select **Menu.jsx**
- Click **Edit**
- Change the version to `Dashboard v1.0.3`

![fork-repo](/images/6-cicd-codebuild/6.1.3.png)

#### Create Personal Access Token

- Click **Settings**

![fork-repo](/images/6-cicd-codebuild/6.1.4.png)

- Click **Developer settings**

![fork-repo](/images/6-cicd-codebuild/6.1.5.png)

- Select **Personal access tokens**
- Choose **Tokens (classic)**
- Click **Generate new token**
- Select **Generate new token classic**

![fork-repo](/images/6-cicd-codebuild/6.1.6.png)

- Note: `access by code build`
- Select repo

![fork-repo](/images/6-cicd-codebuild/6.1.7.png)

- Select **project**
- Click **Generate token**

![fork-repo](/images/6-cicd-codebuild/6.1.8.png)
{{% notice warning %}}
**Lưu ý quan trọng về Token:**

- Copy token ngay lập tức sau khi tạo
- Lưu token vào một nơi an toàn (ví dụ: notepad, password manager)
- Token sẽ chỉ hiển thị một lần duy nhất
- Nếu bạn quên lưu token, bạn sẽ cần tạo token mới
  {{% /notice %}}
