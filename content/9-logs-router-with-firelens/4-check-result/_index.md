+++
title = "Logs Router with Firelens"
date = 2024
weight = 4
chapter = false
pre = "<b>9.4. </b>"
+++

#### Checking Logs in S3 Bucket

Go back to the Bucket that we created. Upon opening it, you should see a new folder named `fluent-bit-logs`.

![9.4.1](/images/9-logs-router-with-firelens/9.4.1.png)

Continue by expanding inside, go to the folder representing the hour, and navigate into any of the folders where you will see log files by the minute.

![9.4.2](/images/9-logs-router-with-firelens/9.4.2.png)

On average, each log file is about 2.7 KB in size.

![9.4.3](/images/9-logs-router-with-firelens/9.4.3.png)

After some time, you should notice additional folders (logs) being created gradually.

![9.4.4](/images/9-logs-router-with-firelens/9.4.4.png)

With this, we have successfully transferred logs to the S3 Bucket. Congratulations on completing this workshop successfully!
