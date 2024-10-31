+++
title = "Configure Permissions and IAM Role"
date = 2024
weight = 3
chapter = false
pre = "<b>3.3. </b>"
+++

#### Configure Sudo Permissions for GitLab Runner

{{% notice note %}}
GitLab Runner needs sudo privileges to execute CI/CD tasks such as build, test, and deploy. This section will guide you through configuring sudo permissions for GitLab Runner.
{{% /notice %}}

1. Open Sudo Configuration File
![Visudo Command](/images/4-cicd-gitlab/4.3.1.png)

Execute the command:
```bash
sudo visudo
```

2. Update Sudo Permissions
![Update Sudo](/images/4-cicd-gitlab/4.3.2.png)

Add the following line to the file:
```bash
gitlab-runner ALL=(ALL) NOPASSWD:ALL
```

{{% notice tip %}}
After adding, press `Ctrl + X` to exit, `Y` to confirm saving, and `Enter` to complete.
{{% /notice %}}

#### Configure IAM Role

1. Access EC2 Instance
![EC2 Access](/images/4-cicd-gitlab/4.3.3.png)

Steps to follow:
- Open EC2 Console
- Select the running instance
- Go to Security tab
- Choose Modify IAM role

2. Check Current Role
![Check Role](/images/4-cicd-gitlab/4.3.4.png)

Verify that the `CustomRWECRRole` IAM Role is assigned to the EC2.

3. Access IAM Role
![Access IAM](/images/4-cicd-gitlab/4.3.5.png)

Navigate in IAM Console:
- Select Roles tab
- Find `CustomRWECRRole`
- Click on the role to view details

4. Add Policy
![Add Policy](/images/4-cicd-gitlab/4.3.6.png)

Add new permissions:
- Policy to add: `AmazonEC2FullAccess`
- Attach to `CustomRWECRRole`

{{% notice warning %}}
Assigning `AmazonEC2FullAccess` should be carefully considered in a production environment. Follow the principle of least privilege and only grant necessary permissions.
{{% /notice %}}