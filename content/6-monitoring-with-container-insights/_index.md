+++
title = "Application Monitoring with Container Insights (CloudWatch)"
date = 2024
weight = 6
chapter = false
pre = "<b>6. </b>"
+++

![cloudwatch_container_insights](/images/8-monitoring-with-container-insights/cloudwatch_container_insights.png)

{{% notice note %}}
To complete this section correctly, you must have successfully configured and run the CI/CD steps beforehand.
{{% /notice %}}

#### Configuring Container Insights

First, in this section, we need to configure some settings before we can use **Container Insights**. **Container Insights** is a service that allows us to monitor metrics like CPU usage, Network traffic, etc., from which we can infer user activity over a specific time period.

Combined with **CloudWatch**, we can view logs sent from containers as log groups, typically with a group name starting with **/ecs/\***. This provides an overview of applications in the system, such as their performance, alerts, or if an application encounters an error. We can also examine these logs to find the cause or investigate unusual traffic in case of system intrusion.

First, go to the ECS console, and in the right-hand menu, select **Account settings**.

![8.1](/images/8-monitoring-with-container-insights/8.1.png)

In the **Account settings** section, look for **CloudWatch Container Insights** with a **Turned off** status, then select **Update**.

![8.2](/images/8-monitoring-with-container-insights/8.2.png)

Check **Container insights** and click **Save changes**.

![8.3](/images/8-monitoring-with-container-insights/8.3.png)

![8.4](/images/8-monitoring-with-container-insights/8.4.png)

#### Observing Metrics with Performance Monitoring

Return to the **Cluster** tab, and go to your cluster.

![8.5](/images/8-monitoring-with-container-insights/8.5.png)

Open the **Metrics** tab and select **View Container Insights**.

![8.6](/images/8-monitoring-with-container-insights/8.6.png)

The **Container Insights** page will then appear.

![8.7](/images/8-monitoring-with-container-insights/8.7.png)

{{% notice note %}}
Here, you can see the metrics for the cluster we previously deployed, **FCJ-Lab-cluster**, if there’s only one cluster in the region where we created it.
{{% /notice %}}

To view information for other clusters:

- On the left selector, choose **ECS Cluster**.
- On the right selector, select the cluster we created, in this case, **FCJ-Lab-cluster**.

![8.8](/images/8-monitoring-with-container-insights/8.8.png)

We can also view charts for various resources; in this case, we'll select **ECS Tasks**.

![8.9](/images/8-monitoring-with-container-insights/8.9.png)

The chart will then display different tasks (including **fcjresbar-task-fe** and **fcjresbar-task-be**).

![8.10](/images/8-monitoring-with-container-insights/8.10.png)

To view **ECS Services**.

![8.11](/images/8-monitoring-with-container-insights/8.11.png)

This is one way to view activity charts for Clusters, Services, Tasks, etc.

#### Observing Metrics with Container Map

In this section, you can view specific **Containers**, **Tasks**, **Services**, etc., in the deployed Cluster.

Switch from **Performance Monitoring** to **Container Map**.

![8.12](/images/8-monitoring-with-container-insights/8.12.png)

Then, you'll see a new interface showing how a **Cluster** manages resources like **Services** and **Tasks**. However, metrics in a **Task** differ from those in a **Service**, as a **Service** directly manages **Tasks**; thus, **Task** metrics also belong to **Service**.

![8.13](/images/8-monitoring-with-container-insights/8.13.png)

Click on the **frontend** service to view metrics within this service.

![8.14](/images/8-monitoring-with-container-insights/8.14.png)

You can see basic metrics like **CPU utilization**, **Memory utilization**, **Network**, and **Disk utilization**.

![8.15](/images/8-monitoring-with-container-insights/8.15.png)

Now, to view a task, select **fcjresbar-task-be**.

![8.16](/images/8-monitoring-with-container-insights/8.16.png)

Thus, the Container Map provides a more detailed view of **Services** and **Tasks** within a Cluster.

Additionally, you can also use **List View**.

- Select **Resources**
- Select **FCJ-Lab-cluster**

This includes resources that were created and are currently running.

![8.17](/images/8-monitoring-with-container-insights/8.17.png)

We can observe average usage for these resources over different time intervals, from 1 hour, 3 hours, 12 hours, 1 day, 1 week, etc.

![8.18](/images/8-monitoring-with-container-insights/8.18.png)

With this, we've configured and completed Container Insights observation. AWS isn’t limited to Container Insights for system monitoring; we can also use other services or third-party solutions for this purpose.

By default, **ECS Container** sends logs to **CloudWatch**. If you look in the **Task Definition** setup in previous workshops, logs can be routed to destinations like **Amazon S3**, **Amazon EC2**, or external services. To route these logs elsewhere, we need an application running in an ECS Service alongside the application whose logs we want to send. In the next section, we will configure **FireLens** to route logs to **Amazon S3**.
