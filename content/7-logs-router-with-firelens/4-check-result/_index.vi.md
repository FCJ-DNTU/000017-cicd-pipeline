+++
title = "Kiểm tra logs"
date = 2024
weight = 4
chapter = false
pre = "<b>7.4. </b>"
+++

#### Kiểm tra logs trong S3 Bucket

Vào lại trong Bucket mà chúng ta đã tạo, khi mở vào trong thì bạn có thể thấy được là đã có một thư mục mới đã được tạo, tên là `fluent-bit-logs`.

![9.4.1](/images/9-logs-router-with-firelens/9.4.1.png)

Tiếp tục ấn xổ vào bên trong, tới thư mục đại diện cho giờ, truy cập tiếp vào một thư mục nào đó thì chúng ta sẽ thấy các file log theo phút.

![9.4.2](/images/9-logs-router-with-firelens/9.4.2.png)

Trung bình thì mỗi file log này sẽ có dung lượng là 2.7 KB

![9.4.3](/images/9-logs-router-with-firelens/9.4.3.png)

Chờ một khoảng thời gian thì các folder (logs) đang dần được tăng thêm.

![9.4.4](/images/9-logs-router-with-firelens/9.4.4.png)

Như vậy thì chúng ta đã chuyển logs sang S3 Bucket thành công. Nếu như bạn đã làm được tới đây thì xin chúc mừng bạn đã làm thành công bài workshop này.
