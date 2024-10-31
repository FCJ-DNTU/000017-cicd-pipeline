+++
title = "Xóa tài nguyên RDS, EC2 and Load Balancer"
date = 2024
weight = 2
chapter = false
pre = "<b>8.2. </b>"
+++

#### Xóa tài nguyên RDS

Đầu tiên sẽ là xóa RDS instance.
- Truy cập vào RDS và chọn **Database**.
- Chọn vào instance mình đã tạo.
- Xổ **Action** và chọn **Delete**.

![RDS](/images/Clean-up/rds-1.png)

- Chọn vào ô giống như hình.
- Nhập `Delete me`
- Chọn **Delete**

![RDS](/images/Clean-up/rds-2.png)

- Đợi khoảng 10 đến 15 phút để RDS instance được xóa hoàn toàn.

![RDS](/images/Clean-up/rds-3.png)

Sau khi RDS được xóa xong, mình sẽ xóa tới Subnet groups.
- Chọn Subnet group đang có.
- Chọn **Delete**.

![RDS](/images/Clean-up/rds-4.png)

- Chọn **Delete**.

![RDS](/images/Clean-up/rds-5.png)

- Xóa thành công.

![RDS](/images/Clean-up/rds-6.png)

#### Xóa tài nguyên EC2

Truy cập vào EC2 để xóa các instance.
- Chọn instance đã tạo.
- Trong **Instance state** chọn **Terminate instance**.

![EC2](/images/Clean-up/ec2-1.png)

- Chọn **Terminate**.

![EC2](/images/Clean-up/ec2-2.png)

- Đợi khoản 5p để xóa thành công.

![EC2](/images/Clean-up/ec2-3.png)

#### Xóa tài nguyên Load Balance

Xóa Load Balancers trước.
- Truy cập vào Load Balance mình đã tạo.
- Chọn **Delete load balancer**.

![LB](/images/Clean-up/lb-1.png)

- Nhập `confirm`
- Chọn **Delete**.

![LB](/images/Clean-up/lb-2.png)

- Hoàn tất xóa Load Balancer

![LB](/images/Clean-up/lb-3.png)

Tiếp theo là xóa target group.
- Vào target group mình đã tạo.
- Xổ **Action** và chọn **Delete**.

![LB](/images/Clean-up/lb-4.png)

- Chọn **Yes, delete**.

![LB](/images/Clean-up/lb-5.png)

- Hoành thành xóa target group.

![LB](/images/Clean-up/lb-6.png)
