+++
title = "Delete IAM and S3 Bucket Resources"
date = 2024
weight = 4
chapter = false
pre = "<b>8.4. </b>"
+++

#### Delete IAM Resources

Now, let’s delete the created roles.
- Go to **Roles** under **IAM**.
- Enter `CustomRWECRRole`
- Select **Delete**.

![IAM](/images/Clean-up/iam-1.png)

- Enter `CustomRWECRRole`
- Select **Delete**.

![IAM](/images/Clean-up/iam-2.png)

- Deletion successful.

![IAM](/images/Clean-up/iam-3.png)

- Repeat the process above.
- Enter `ECSTaskFullAccessToS3Role`

![IAM](/images/Clean-up/iam-4.png)

- Deletion successful.

![IAM](/images/Clean-up/iam-5.png)

#### Delete S3 Bucket Resources

Delete the created S3 bucket.
- Access **S3**.
- Select the name of the created bucket.
- Choose **Empty**.

![S3](/images/Clean-up/s3-1.png)

- Enter `permanently delete`
- Select **Empty**.

![S3](/images/Clean-up/s3-2.png)

- Emptying completed.

![S3](/images/Clean-up/s3-3.png)

- Select the now-empty bucket.
- Choose **Delete**.

![S3](/images/Clean-up/s3-4.png)

- Enter `firelens-log`
- Select **Delete bucket**.

![S3](/images/Clean-up/s3-5.png)

- Bucket deletion complete.

![S3](/images/Clean-up/s3-6.png)
