+++
title = "Fork and Modify Repository"
date = 2024
weight = 1
chapter = false
pre = "<b>4.1. </b>"
+++

{{% notice note %}}
In this section, we will learn how to fork an existing repository and make changes to the forked repository. This is the first step to begin the CI/CD process.
{{% /notice %}}

#### Fork Repository

Fork Repository allows you to create an independent copy of the original repository in your GitLab account. This enables you to freely make changes without affecting the original repository.

1. Initialize Fork
![Fork Button](/images/4-cicd-gitlab/4.1.1.png)

- Access the original repository at [aws-fcj-container-app](https://gitlab.com/fcj-lab/aws-fcj-container-app)
- Locate and click the "Fork" button in the top right corner

2. Configure Fork
![Fork Configuration](/images/4-cicd-gitlab/4.1.2.png)

Set up basic parameters:
- Project name: Keep as aws-fcj-container-app
- Project URL: Select appropriate namespace
- Project slug: Leave as default
- Branches: Select All branches to copy everything
- Visibility: Choose Public for open access
- Complete by clicking Fork project

{{% notice tip %}}
Selecting All branches gives you the complete development history of the project, useful for tracking changes and developing new features.
{{% /notice %}}

3. Verify Fork
![Fork Result](/images/4-cicd-gitlab/4.1.3.png)

Check the following elements:
- Fork success message appears
- Directory structure is fully copied
- Commit and branch information is preserved

#### Modify Source Code

1. Locate File
![Navigate to File](/images/4-cicd-gitlab/4.1.4.png)

Access the file to modify:
- Path: frontend/src/components/Menu.jsx
- Select Edit then Edit single file

2. Update Content
![Edit Content](/images/4-cicd-gitlab/4.1.5.png)

Make changes:
- Locate the section to modify
- Update text from Dashboard to Dashboard v1.0.1

3. Commit Changes
![Commit Changes](/images/4-cicd-gitlab/4.1.6.png)

Save the changes:
- Write a descriptive commit message
- Confirm target branch is main
- Confirm with Commit changes

{{% notice tip %}}
Commit messages should follow the format: type(scope): message
Example: feat(frontend): update dashboard title to v1.0.1
This helps in tracking and managing project changes effectively.
{{% /notice %}}