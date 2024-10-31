+++
title = "Tạo S3 Bucket cho logs"
date = 2024
weight = 1
chapter = false
pre = "<b>7.1. </b>"
+++

#### Tạo S3 Bucket

Để có thể lưu được các logs, thì sẽ cần phải tạo một S3 Bucket. Trên thanh tìm kiếm:

- Nhập `S3`.
- Chọn **Amazon S3**.

![9.1.1](/images/9-logs-router-with-firelens/9.1.1.png)

Vào **Buckets**, chọn **Create bucket**.

![9.1.2](/images/9-logs-router-with-firelens/9.1.2.png)

Bắt đầu cấu hình cho S3

- Name: đặt một cái tên bất kì, ở đây mình sẽ đặt là `firelens-logs`.
- Object Ownership: chọn **ACLs Disable (recommended)**.

![9.1.3](/images/9-logs-router-with-firelens/9.1.3.png)

Tiếp theo là mình sẽ mở Bucket ra ngoài Internet

![9.1.4](/images/9-logs-router-with-firelens/9.1.4.png)

{{% notice note %}}
Để thực hành nhanh thì trong bài này mình sẽ mở Public Access cho Bucket, nhưng khi cấu hình để làm thật thì bạn nên cấu hình cho VPC một cái **S3 Endpoint** trước và đóng Public Access cho Bucket. Cùng với đó là sử dụng **Resource-based Policy** lên Bucket đó và cho phép các **Principal** là **ECS Service**.
{{% /notice %}}

Trong **Bucket versioning**, chọn **Disable**.

![9.1.5](/images/9-logs-router-with-firelens/9.1.5.png)

Tiếp theo, trong phần **Default encryption**

- Encryption type: để mặc định.
- Bucket key: **Disable**.
- Ấn **Create bucket**.

![9.1.6](/images/9-logs-router-with-firelens/9.1.6.png)

Tạo xong thì chúng ta có thể xem kết quả ở trong console của S3

![9.1.7](/images/9-logs-router-with-firelens/9.1.7.png)
