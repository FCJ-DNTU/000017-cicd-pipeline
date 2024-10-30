+++
title = "Tạo IAM Role cho ECS Task"
date = 2024
weight = 2
chapter = false
pre = "<b>9.2. </b>"
+++

#### Tạo IAM Role cho Task

Để mà các container ở trong một task có thể tương tác được với S3, thì chúng ta cần phải tạo ra một IAM Role cho task đó. Trên thanh tìm kiếm

- Nhập `IAM`
- Chọn **IAM**

![9.2.1](/images/9-logs-router-with-firelens/9.2.1.png)

Tiếp theo, ở bên thanh menu bên trái

- Chọn **Roles**.
- Ấn **Create role**.

![9.2.2](/images/9-logs-router-with-firelens/9.2.2.png)

Trong trang tạo, điền và chọn các thông tin như sau

- Trust entity type: chọn** AWS Service**.
- Trong phần **Use case**
  - Service or use case: chọn **Elastic Container Service**.
  - Use case: chọn **Elastic Container Service Task**.
- Ấn chọn **Next**

![9.2.3](/images/9-logs-router-with-firelens/9.2.3.png)

Tiếp theo, để có thể có được quyền ghi vào S3, thì chúng ta cần

- Nhập `AmazonS3FullAccess` để tìm policy.
- Chọn **AmazonS3FullAccess**.
- Ấn **Next**.

![9.2.4](/images/9-logs-router-with-firelens/9.2.4.png)

Điền các thông tin trong bước cuối

- Name: `ECSTaskFullAccessToS3Role` (bạn đặt là gì cũng được)
- Description: `Allows ECS tasks to call AWS services on you behalf.` (nhập mô tả cho dễ quản lý)

![9.2.5](/images/9-logs-router-with-firelens/9.2.5.png)

Ấn **Create role** để tạo

![9.2.6](/images/9-logs-router-with-firelens/9.2.6.png)

Xong

![9.2.7](/images/9-logs-router-with-firelens/9.2.7.png)
