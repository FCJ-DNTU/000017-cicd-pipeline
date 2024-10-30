+++
title = "Cập nhật ECS Service"
date = 2024
weight = 3
chapter = false
pre = "<b>9.3. </b>"
+++

#### Cập nhật Task Definition

Quay trở lại ECS Console

- Chọn **Task Definition**.
- Chọn task **fcjresbar-task-fe**.

![9.3.1](/images/9-logs-router-with-firelens/9.3.1.png)

Sau đó là chọn phiên bản task mới nhất, chọn **Create new revision**.

![9.3.2](/images/9-logs-router-with-firelens/9.3.2.png)

Kéo xuống một xíu, trong phần **Task Role**

- Nhập `ECS`
- Chọn **ECSTaskFullAccessToS3Role**

![9.3.3](/images/9-logs-router-with-firelens/9.3.3.png)

![9.3.4](/images/9-logs-router-with-firelens/9.3.4.png)

Tiếp tục cuộn xuống dưới

![9.3.5](/images/9-logs-router-with-firelens/9.3.5.png)

Trong phần **Log collection**, xổ xuống và chọn **Export logs to S3 via AWS Firelens**.

![9.3.6](/images/9-logs-router-with-firelens/9.3.6.png)

Tiếp theo, cấu hình cho logs driver

- Trong biến `bucket`, nhập `firelens-logs` hoặc bất kì cái tên nào mà bạn đặt cho S3 Bucket ở phần trước.
- Thêm biến `retry_limit`, nhập `2`.

![9.3.7](/images/9-logs-router-with-firelens/9.3.7.png)

Khi mà chúng ta chọn lựa chọn khác cho logs thì lúc này sẽ có một container mới được tạo phía dưới. Một số thông tin như sau:

- Image URI: `amazon/aws-for-fluent-bit:stable`
- CPU: 1; Memory hard limit: 3; Memory soft limit: 2.

![9.3.8](/images/9-logs-router-with-firelens/9.3.8.png)

Để các cấu hình của logs driver mặc định

![9.3.9](/images/9-logs-router-with-firelens/9.3.9.png)

Cuối cùng là ấn **Create** để tạo revision mới.

![9.3.10](/images/9-logs-router-with-firelens/9.3.10.png)

Thành công.

![9.3.11](/images/9-logs-router-with-firelens/9.3.11.png)

#### Cập nhật ECS Service

Quay lại service **frontend** để cập nhật phiên bản mới. Ấn chọn **Update service**.

![9.3.12](/images/9-logs-router-with-firelens/9.3.12.png)

Chọn revision mới nhất

![9.3.13](/images/9-logs-router-with-firelens/9.3.13.png)

Còn lại thì chúng ta sẽ giữ nguyên, kéo xuống ấn chọn **Create** để update service.

![9.3.14](/images/9-logs-router-with-firelens/9.3.14.png)

Sau một khoảng thời gian, thì bạn có thể thấy được là 2 containers mới đã được tạo. Một là của frontend và một là của logs router. Hiện tại thì logs đang được gửi về Log router.

![9.3.15](/images/9-logs-router-with-firelens/9.3.15.png)
