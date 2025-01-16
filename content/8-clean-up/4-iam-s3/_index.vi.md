+++
title = "Xóa tài nguyên IAM và S3 bucket"
date = 2024
weight = 4
chapter = false
pre = "<b>8.4. </b>"
+++

#### Xóa tài nguyên IAM

Bây giờ mình sẽ xóa các Role đã tạo.
- Truy cập vào **Role** ở trong **IAM**.
- Nhập `CustomRWECRRole`
- Chọn **Delete**.

![IAM](/images/Clean-up/iam-1.png)

- Nhập `CustomRWECRRole`
- Chọn **Delete**.

![IAM](/images/Clean-up/iam-2.png)

- Xóa thành công.

![IAM](/images/Clean-up/iam-3.png)

- Mình sẽ làm tương tự như ở trên.
- Nhập `ECSTaskFullAccessToS3Role`

![IAM](/images/Clean-up/iam-4.png)

- Xóa thành công.

![IAM](/images/Clean-up/iam-5.png)

#### Xóa tài nguyên S3 bucket

Xóa file S3 Bucket đã tạo.
- Truy cập vào S3 bucket.
- Chọn vào tên file mình đã tạo.
- Chọn **Empty**

![S3](/images/Clean-up/s3-1.png)

- Nhập `permanently delete`
- Chọn **Empty**.

![S3](/images/Clean-up/s3-2.png)

- Hoàn thành Empty.

![S3](/images/Clean-up/s3-3.png)

- Chọn lại file vừa Empty.
- Chọn **Delete**

![S3](/images/Clean-up/s3-4.png)

- Nhập `firelens-log`
- Chọn **Delete bucket**.

![S3](/images/Clean-up/s3-5.png)

- Hoàn thành xóa bucket.

![S3](/images/Clean-up/s3-6.png)