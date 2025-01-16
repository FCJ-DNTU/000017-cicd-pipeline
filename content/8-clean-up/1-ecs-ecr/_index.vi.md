+++
title = "Xóa tài nguyên trong ECS và ECR"
date = 2024
weight = 1
chapter = false
pre = "<b>8.1. </b>"
+++

#### Xóa tài nguyên ECS

Đầu tiên cần xóa 2 service là backend và frontend trước.
- Vào AWS console và tìm kiếm **ECS**.
- Chọn **Cluster** đã tạo và kéo xuống phần **Service**.
- Chọn 2 service đang chạy và chọn **Delete service**.

![ECS](/images/Clean-up/ecs-1.png)

- Chọn **Force delete**.
- Nhập `delete`
- CHọn **Delete**.

![ECS](/images/Clean-up/ecs-2.png)

- Hoàn thành xóa Service.

![ECS](/images/Clean-up/ecs-3.png)

Tiếp theo là tới xóa **Task definitions**.
- Vào **Task definitions** và chọn tất cả các revision.
- Xổ **Action** và chọn **Deregister**.

![ECS](/images/Clean-up/ecs-4.png)

- Chọn **Deregister**.

![ECS](/images/Clean-up/ecs-5.png)

- Làm bên frontend cũng giống như các bước của Backend.

![ECS](/images/Clean-up/ecs-6.png)

![ECS](/images/Clean-up/ecs-7.png)

- Hoàn thành xóa Task definitions.

![ECS](/images/Clean-up/ecs-8.png)

Xóa ECS Cluser
- Vào lại Cluser và chọn **Delete cluster**.

![ECS](/images/Clean-up/ecs-9.png)

- Nhập `delete FCJ-Lab-cluster`
- Chọn **Delete**.

![ECS](/images/Clean-up/ecs-10.png)

- Đợi một lúc để xóa Cluster được hoàn tất.

![ECS](/images/Clean-up/ecs-11.png)

#### Xóa tài nguyên ECR

Đầu tiên là xóa Images trước.
- Vào trong repository ở trên ECR.
- Chọn image hiện có và chọn **Delete**.

![ECR](/images/Clean-up/ecr-1.png)

- Nhập `delete`
- Chọn **Delete**.

![ECR](/images/Clean-up/ecr-2.png)

- Xóa image thành công.

![ECR](/images/Clean-up/ecr-3.png)

Tiếp theo là xóa repository ở trên ECR
- Chọn vào repository cần xóa.
- Chọn **Delete**.

![ECR](/images/Clean-up/ecr-4.png)

- Chọn **Delete**.
- Xóa thành công repository.

![ECR](/images/Clean-up/ecr-5.png)

{{% notice note %}}
Làm tương tự với repository còn lại của ECR.
{{% /notice %}}