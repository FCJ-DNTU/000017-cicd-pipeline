+++
title = "Logs Router with Firelens"
date = 2024
weight = 9
chapter = false
pre = "<b>9. </b>"
+++

![logs_router_with_firelens](/images/9-logs-router-with-firelens/logs_router_with_firelens.png)

#### Overview

In this section, we’ll configure FireLens to route logs to different destinations, enabling us to accomplish tasks such as:

- Log analysis.
- Monitoring suspicious activities.
- Tracking access levels.
- Observing resource utilization.
- And various other tasks.

These tasks may require additional tools, which is why routing logs to an external source becomes essential.

Here, we’ll configure FireLens within ECS to route logs from the **frontend** Service to an S3 Bucket and then check the results.

1. [Create an S3 Bucket](1-create-s3-bucket)
2. [Create an IAM Role for the Task](2-create-iam-role-for-task)
3. [Deploy the Service with a New Task Definition](3-update-service)
4. [Verify the Results](4-check-result)
