+++
title = "Delete resources in RDS, EC2 and Load Balancer"
date = 2024
weight = 2
chapter = false
pre = "<b>8.2. </b>"
+++

#### Delete RDS Resources

First, delete the RDS instance.
- Go to **RDS** and select **Database**.
- Select the instance you created.
- Expand **Action** and select **Delete**.

![RDS](/images/Clean-up/rds-1.png)

- Check the box as shown.
- Enter `Delete me`
- Select **Delete**

![RDS](/images/Clean-up/rds-2.png)

- Wait about 10 to 15 minutes for the RDS instance to be completely deleted.

![RDS](/images/Clean-up/rds-3.png)

After the RDS instance is deleted, proceed to delete the Subnet groups.
- Select the existing Subnet group.
- Choose **Delete**.

![RDS](/images/Clean-up/rds-4.png)

- Select **Delete**.

![RDS](/images/Clean-up/rds-5.png)

- Deletion successful.

![RDS](/images/Clean-up/rds-6.png)

#### Delete EC2 Resources

Go to **EC2** to delete the instances.
- Select the instance you created.
- Under **Instance state**, choose **Terminate instance**.

![EC2](/images/Clean-up/ec2-1.png)

- Select **Terminate**.

![EC2](/images/Clean-up/ec2-2.png)

- Wait about 5 minutes for successful deletion.

![EC2](/images/Clean-up/ec2-3.png)

#### Delete Load Balancer Resources

Start by deleting the Load Balancers.
- Go to the Load Balancer you created.
- Select **Delete load balancer**.

![LB](/images/Clean-up/lb-1.png)

- Enter `confirm`
- Select **Delete**.

![LB](/images/Clean-up/lb-2.png)

- Load Balancer deletion complete.

![LB](/images/Clean-up/lb-3.png)

Next, delete the target group.
- Go to the target group you created.
- Expand **Action** and select **Delete**.

![LB](/images/Clean-up/lb-4.png)

- Choose **Yes, delete**.

![LB](/images/Clean-up/lb-5.png)

- Target group deletion complete.

![LB](/images/Clean-up/lb-6.png)
