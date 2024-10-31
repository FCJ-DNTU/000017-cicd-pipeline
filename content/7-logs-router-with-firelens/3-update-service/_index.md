+++
title = "Update ECS Service"
date = 2024
weight = 3
chapter = false
pre = "<b>7.3. </b>"
+++

#### Update Task Definition

Go back to the ECS Console:

- Select **Task Definition**.
- Choose the task **fcjresbar-task-fe**.

![9.3.1](/images/9-logs-router-with-firelens/9.3.1.png)

Next, select the latest task version, and choose **Create new revision**.

![9.3.2](/images/9-logs-router-with-firelens/9.3.2.png)

Scroll down to the **Task Role** section:

- Enter `ECS`
- Select **ECSTaskFullAccessToS3Role**.

![9.3.3](/images/9-logs-router-with-firelens/9.3.3.png)
![9.3.4](/images/9-logs-router-with-firelens/9.3.4.png)

Continue scrolling down.

![9.3.5](/images/9-logs-router-with-firelens/9.3.5.png)

In the **Log collection** section, expand and select **Export logs to S3 via AWS Firelens**.

![9.3.6](/images/9-logs-router-with-firelens/9.3.6.png)

Next, configure the log driver:

- In the `bucket` variable, enter `firelens-logs` or any other name you assigned to the S3 Bucket in the previous step.
- Add the variable `retry_limit` and set it to `2`.

![9.3.7](/images/9-logs-router-with-firelens/9.3.7.png)

When selecting different log options, a new container will be created below. Some details:

- Image URI: `amazon/aws-for-fluent-bit:stable`
- CPU: 1; Memory hard limit: 3; Memory soft limit: 2.

![9.3.8](/images/9-logs-router-with-firelens/9.3.8.png)

Leave the log driver configuration settings as default.

![9.3.9](/images/9-logs-router-with-firelens/9.3.9.png)

Finally, click **Create** to create the new revision.

![9.3.10](/images/9-logs-router-with-firelens/9.3.10.png)

Success!

![9.3.11](/images/9-logs-router-with-firelens/9.3.11.png)

#### Update ECS Service

Return to the **frontend** service to update to the latest version. Click **Update service**.

![9.3.12](/images/9-logs-router-with-firelens/9.3.12.png)

Select the latest revision.

![9.3.13](/images/9-logs-router-with-firelens/9.3.13.png)

Leave the rest unchanged, scroll down, and click **Create** to update the service.

![9.3.14](/images/9-logs-router-with-firelens/9.3.14.png)

After a short time, you should see that two new containers have been created—one for the frontend and one for the log router. Logs are now being sent to the log router.

![9.3.15](/images/9-logs-router-with-firelens/9.3.15.png)
