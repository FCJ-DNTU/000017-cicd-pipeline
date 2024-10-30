+++
title = "Create S3 Bucket to store logs"
date = 2024
weight = 1
chapter = false
pre = "<b>9.1. </b>"
+++

#### Creating an S3 Bucket

To store the logs, we’ll need to create an S3 Bucket. In the search bar:

- Enter `S3`.
- Select **Amazon S3**.

![9.1.1](/images/9-logs-router-with-firelens/9.1.1.png)

Go to **Buckets**, then select **Create bucket**.

![9.1.2](/images/9-logs-router-with-firelens/9.1.2.png)

Start configuring the S3 bucket:

- Name: give it any name; here, we'll name it `firelens-logs`.
- Object Ownership: select **ACLs Disable (recommended)**.

![9.1.3](/images/9-logs-router-with-firelens/9.1.3.png)

Next, we’ll make the Bucket accessible over the Internet.

![9.1.4](/images/9-logs-router-with-firelens/9.1.4.png)

{{% notice note %}}
To expedite the practice, we’ll make this Bucket publicly accessible in this tutorial. However, for a real-world setup, you should configure an **S3 Endpoint** for your VPC and disable public access for the Bucket. Additionally, apply a **Resource-based Policy** on the Bucket and permit **ECS Service** as a **Principal**.
{{% /notice %}}

In **Bucket versioning**, select **Disable**.

![9.1.5](/images/9-logs-router-with-firelens/9.1.5.png)

Next, in the **Default encryption** section:

- Encryption type: leave it as default.
- Bucket key: **Disable**.
- Click **Create bucket**.

![9.1.6](/images/9-logs-router-with-firelens/9.1.6.png)

Once created, you can view the result in the S3 console.

![9.1.7](/images/9-logs-router-with-firelens/9.1.7.png)
