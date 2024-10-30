+++
title = "Logs Router with Firelens"
date = 2024
weight = 2
chapter = false
pre = "<b>9.2. </b>"
+++

#### Create IAM Role for Task

To allow containers within a task to interact with S3, we need to create an IAM Role for the task. In the search bar:

- Enter `IAM`
- Select **IAM**

![9.2.1](/images/9-logs-router-with-firelens/9.2.1.png)

Next, in the left-hand menu:

- Select **Roles**.
- Click **Create role**.

![9.2.2](/images/9-logs-router-with-firelens/9.2.2.png)

On the creation page, enter and select the following information:

- Trust entity type: select **AWS Service**.
- Under **Use case**:
  - Service or use case: select **Elastic Container Service**.
  - Use case: select **Elastic Container Service Task**.
- Click **Next**.

![9.2.3](/images/9-logs-router-with-firelens/9.2.3.png)

Next, to grant write permissions to S3:

- Enter `AmazonS3FullAccess` to find the policy.
- Select **AmazonS3FullAccess**.
- Click **Next**.

![9.2.4](/images/9-logs-router-with-firelens/9.2.4.png)

Fill out the information on the final step:

- Name: `ECSTaskFullAccessToS3Role` (or any name you prefer)
- Description: `Allows ECS tasks to call AWS services on your behalf.` (add a description for easy management)

![9.2.5](/images/9-logs-router-with-firelens/9.2.5.png)

Click **Create role** to finish.

![9.2.6](/images/9-logs-router-with-firelens/9.2.6.png)

Done!

![9.2.7](/images/9-logs-router-with-firelens/9.2.7.png)
