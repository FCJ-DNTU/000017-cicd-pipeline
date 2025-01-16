+++
title = "Create Backend CodeBuild"
date = 2024
weight = 3
chapter = false
pre = "<b>5.3.</b>"
+++

#### Create Backend CodeBuild

- Access AWS Console and search for **CodeBuild** in the menu
- Select **Build project**
- Click **Create project**
- Enter Project name: `aws-fcj-container-be`

![create-project](/images/6-cicd-codebuild/6.3.1.png)

Configure Source:

- Select **GitHub** as Source provider
- Choose **Personal access**
- Select **Personal access token**
- For Connection, choose the secret created earlier
- Select **Repository in my GitHub account**
- Paste the HTTPS URL into GitHub repository field (URL copied from step 6.2)
- Source version: `refs/tags/*`

![source-config](/images/6-cicd-codebuild/6.3.2.png)

In the **Primary source webhook events** section:

- Webhook: Select **Rebuild every time a code change is pushed to the repository**
- Choose **Single build**
- Event type: **PUSH**
- Enter HEAD_REF: `HEAD_REF`
- Enter Pattern: `^refs/tags/`

![webhook-config](/images/6-cicd-codebuild/6.3.3.png)

Configure environment:

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

Expand **Additional configuration**

![additional-config](/images/6-cicd-codebuild/6.3.5.png)

- Click **Add environment variable**
- Add environment variables according to the table:

![env-variables](/images/6-cicd-codebuild/6.3.6.png)

- Click **Create build project** to complete

![create-complete](/images/6-cicd-codebuild/6.3.7.png)

#### Add role for BE CodeBuild

After creating the build project:

- Access the newly created build project

![access-project](/images/6-cicd-codebuild/6.3.8.png)

- In the **Service role** section, click on the role to navigate to IAM management

![service-role](/images/6-cicd-codebuild/6.3.9.png)

Add permissions to the role:

- Select **Add permissions**
- Choose **Attach policy**
- Search and select these policies:
  - `AmazonECS_FullAccess`
  - `CloudWatchLogsFullAccess`
  - `WriteECRRepositoryContent`
- Click **Attach policies**

![attach-policies](/images/6-cicd-codebuild/6.3.10.png)
