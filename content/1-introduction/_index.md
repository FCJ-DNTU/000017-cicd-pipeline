+++
title = "Introduction"
date = 2024
weight = 1
chapter = false
pre = "<b>1. </b>"
+++

#### Overview

After deploying a Service in a Cluster, we can modify configurations such as the number of Tasks, Container modifications, and adjustments to CPU and Memory in the Task Definition Revision.

![Image](/images/1-introduction/1.1.png?width=20pc)

ECS provides 3 methods to implement these changes:

1. **Rolling update**
- Executed by ECS, using the service scheduler to update the new version of the Container.
- Configured through two values:
  - **Minimum healthy percent**: The minimum percentage of Tasks that should remain in the RUNNING state.
  - **Maximum percent**: The maximum percentage of Tasks that can be in the RUNNING or PENDING state.

2. **Blue/Green**
- Executed by CodeDeploy, maintaining two versions: production (BLUE) and test (GREEN).
- Traffic gradually shifts from BLUE to GREEN using one of the following methods:
  - **Canary**: Divides traffic into 2 parts, for example:
    - CodeDeployDefault.ECSCanary10Percent5Minutes: 10% initially, 90% after 5 minutes
    - CodeDeployDefault.ECSCanary10Percent15Minutes: 10% initially, 90% after 15 minutes
  - **Linear**: Evenly distributes traffic, for example:
    - CodeDeployDefault.ECSLinear10PercentEvery1Minutes: 10% every 1 minute
    - CodeDeployDefault.ECSLinear10PercentEvery3Minutes: 10% every 3 minutes
  - **All-at-once**: Shifts all traffic simultaneously

3. **External**
- Uses a third-party deployment controller, based on Service/Task APIs.