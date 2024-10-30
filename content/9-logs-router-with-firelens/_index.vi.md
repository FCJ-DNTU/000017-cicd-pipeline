+++
title = "Định tuyến logs với Firelens"
date = 2024
weight = 9
chapter = false
pre = "<b>9. </b>"
+++

![logs_router_with_firelens](/images/9-logs-router-with-firelens/logs_router_with_firelens.png)

#### Nội dung

Trong phần này, thì chúng ta sẽ cùng cấu hình Firelens để mà có thể định tuyến các logs tới các đích khác để chúng ta có thể làm được một số các công việc như là:

- Phân tích logs.
- Theo dõi các hành vi đáng ngờ.
- Theo dõi lượng truy cập.
- Quan sát mức sử dụng tài nguyên.
- Và nhiều tác vụ khác.

Các công việc trên có thể sẽ đòi hỏi nhiều công cụ khác hơn, vì thế mà chúng ta mới cần phải "chuyển" các logs tới nguồn khác để làm được việc đó.

Trong phần này chúng ta sẽ cấu hình Firelens trong ECS để có thể chuyển được logs của **frontend** Service tới S3 Bucket và kiểm tra kết quả.

1. [Tạo S3 Bucket](1-create-s3-bucket)
2. [Tạo IAM Role cho Task](2-create-iam-role-for-task)
3. [Triển khai Service với Task Definition mới](3-update-service)
4. [Kiểm tra kết quả](4-check-result)
