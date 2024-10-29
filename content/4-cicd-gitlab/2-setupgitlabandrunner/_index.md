+++
title = "Install and Register GitLab Runner"
date = 2024
weight = 2
chapter = false
pre = "<b>4.2. </b>"
+++

{{% notice note %}}
In this section, we will install and configure GitLab Runner - an essential agent for executing CI/CD jobs in GitLab.
{{% /notice %}}

#### Install GitLab Runner

1. Prepare Environment
![Create Config Directory](/images/4-cicd-gitlab/4.2.1.png)

Create directory and configuration file:
```bash
sudo mkdir -p /tools && vi tools/setup.sh
```

2. Install Runner
![Install GitLab Runner](/images/4-cicd-gitlab/4.2.2.png)

Add the following content to setup.sh:
```bash
#!/bin/bash
# Update package list
apt update -y

# Install GitLab Runner
curl -L "https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh" | sudo bash
apt install gitlab-runner

# Check version
gitlab-runner --version
```

3. Verify Installation
![Check Version](/images/4-cicd-gitlab/4.2.3.png)

Check version to ensure successful installation:
```bash
gitlab-runner --version
```

#### Configure Backend Runner

1. Switch User
![Switch User](/images/4-cicd-gitlab/4.2.4.png)

```bash
sudo -i
su gitlab-runner
cd
```

2. Access GitLab Settings
![Access Settings](/images/4-cicd-gitlab/4.2.5.png)

Navigate to Runner settings:
- Settings → CI/CD → Runners
- Click "New project runner"

3. Configure Backend Runner
![Configure Runner](/images/4-cicd-gitlab/4.2.6.png)

Set up configuration:
- Tag: `fcj-lab-runner-be`
- Select "Run untagged jobs"
- Click "Create runner"

{{% notice tip %}}
Tags help identify which types of jobs the runner will process. For example: backend jobs, frontend jobs.
{{% /notice %}}

4. Register Runner
![Register Runner](/images/4-cicd-gitlab/4.2.8.png)

```bash
# Register runner with token
gitlab-runner register --url https://gitlab.com --token [your-token]

# Enter information when prompted
- URL: https://gitlab.com
- Name: fcj-lab-runner-be
- Executor: shell
```

5. Start Runner
![Start Runner](/images/4-cicd-gitlab/4.2.9.png)

```bash
# Run in background
nohup gitlab-runner run > start-runner-be.txt 2>&1 &

# Check logs
tail -f start-runner-be.txt
```

#### Configure Frontend Runner

{{% notice note %}}
To handle jobs efficiently, we need to create a separate runner for frontend tasks.
{{% /notice %}}

1. Create Frontend Runner
![Frontend Runner](/images/4-cicd-gitlab/4.2.11.png)

Repeat the above steps with these details:
- Tag: `fcj-lab-runner-fe`
- Name: `fcj-lab-runner-fe`
- Keep other configurations the same

2. Verify Runners
![Verify Runners](/images/4-cicd-gitlab/4.2.12.png)

Check runners list:
- Backend: #42138335 (fcj-lab-runner-be)
- Frontend: #42138385 (fcj-lab-runner-fe)