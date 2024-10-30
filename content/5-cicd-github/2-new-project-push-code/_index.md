+++
title = "Create a New Project and Push Code"
date = 2024
weight = 2
chapter = false
pre = "<b>5.2. </b>"
+++

#### Create a New Repository

This repository will be where you run GitHub Actions.

- First, log into your GitHub account.
- Click on your profile picture and select **Your repositories**.

![Github](/images/5-cicd-github/5.2.1.png)

- Once on the Repositories page, select **New** to create a new one.

![Github](/images/5-cicd-github/5.2.2.png)

- Enter a name for your repository: `aws-fcj-container-app`
- Choose **Public** if you want it to be accessible to everyone.

![Github](/images/5-cicd-github/5.2.3.png)

- Complete the setup to create a repository on your GitHub account. The following commands are provided to help you push code and create files.

![Github](/images/5-cicd-github/5.2.4.png)

#### Push Code to GitHub

- Use the following command to add the origin for your repository.

```
git remote set-url origin "Your path"
```

![Github](/images/5-cicd-github/5.2.5.png)

- Use these commands to create a branch and push code to it.

```
git branch -M "Your branch"
git push -u origin "Your branch"
```

![Github](/images/5-cicd-github/5.2.6.png)

- Check if the code has been successfully pushed.

![Github](/images/5-cicd-github/5.2.7.png)
