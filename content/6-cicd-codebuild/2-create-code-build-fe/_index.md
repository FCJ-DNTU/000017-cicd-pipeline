+++
title = "Create Frontend CodeBuild"
date = 2024
weight = 2
chapter = false
pre = "<b>6.2.</b>"
+++

#### Create Frontend CodeBuild

- Access AWS Console and search for **CodeBuild** service in the menu

![codebuild-menu](/images/6-cicd-codebuild/6.2.1.png)

- Select **Build project**
- Click **Create project**

![create-project](/images/6-cicd-codebuild/6.2.2.png)

- Enter Project name: `aws-fcj-container-fe`
- Select **GitHub** as Source provider

![source-provider](/images/6-cicd-codebuild/6.2.3.png)

- For Connection, select **Custom**
- Choose **Personal access token**
- Click **Create a new secret**
- In the **Create secret** panel, fill in:
  - Secret name: `codebuild-github-access-token`
  - Secret description: `Access token for github`
  - GitHub personal access token: Paste the token created in previous step

![create-secret](/images/6-cicd-codebuild/6.2.4.png)

Go back to GitHub to get Repository URL:

- Copy the HTTPS URL of the repository

![github-url](/images/6-cicd-codebuild/6.2.5.png)

Return to CodeBuild:

- Select **Repository in my GitHub account**
- Paste HTTPS URL into GitHub repository field
- Source version: `refs/tags/*`

![source-config](/images/6-cicd-codebuild/6.2.6.png)

In Primary source webhook events section:

- Select **Rebuild every time a code change is pushed to the repository**
- Choose **Single build**
- Click **Add filter group**

![webhook-events](/images/6-cicd-codebuild/6.2.7.png)

- Select Event type: **PUSH**
- Enter Pattern: `^refs/tags/`

![webhook-filter](/images/6-cicd-codebuild/6.2.8.png)

Configure environment:

- Provisioning model: `On-demand`
- Environment image: `Managed image`
- Compute: **EC2**
- Operating system: **Ubuntu**
- Runtime: **Standard**
- Image: **aws/codebuild/standard:7.0**
- Image version: **Always use latest image for version**

![environment](/images/6-cicd-codebuild/6.2.9.png)

- Service role: `aws-fcj-container-fe-service-role`
- Click **Next**

Expand **Additional configuration**

![additional-config](/images/6-cicd-codebuild/6.2.10.png)

- Click **Add environment variable**
- Add environment variables according to the table:

![env-variables](/images/6-cicd-codebuild/6.2.11.png)

Configure **Buildspec**:

- Select **Use a buildspec file**
- Buildspec name: `frontend/buildspec.yml`

![buildspec](/images/6-cicd-codebuild/6.2.12.png)

Configure **Logs**:

- Select **Enable cloudwatch logs**
- Click **Create build project**

![logs](/images/6-cicd-codebuild/6.2.13.png)

#### Add role for FE CodeBuild

After creating the build project:

- Access the newly created build project
- In the **Service role** section, click on the role to navigate to IAM management

![service-role](/images/6-cicd-codebuild/6.2.14.png)

Add permissions to the role:

- Select **Add permissions**
- Choose **Attach policy**
- Search and select these policies:
  - `AmazonECS_FullAccess`
  - `CloudWatchLogsFullAccess`
  - `WriteECRRepositoryContent`
- Click **Attach policies**

![attach-policies](/images/6-cicd-codebuild/6.2.15.png)
