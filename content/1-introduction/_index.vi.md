+++
title = "Introduce"
date = 2024
weight = 1
chapter = false
pre = "<b>1. </b>"
+++

#### Tổng quan

Sau khi triển khai Service trong Cluster, ta có thể thay đổi cấu hình như số lượng Tasks, sửa đổi Containers, điều chỉnh CPU và Memory trong Task Definition Revision.

![Image](/images/1-introduction/1.1.png?width=20pc)

ECS cung cấp 3 phương pháp để thực hiện những thay đổi này:

1. **Rolling update**
- Do ECS thực hiện, sử dụng service scheduler để cập nhật phiên bản mới của Container.
- Cấu hình thông qua hai giá trị:
  - **Minimum healthy percent**: Tỷ lệ tối thiểu của Tasks cần duy trì ở trạng thái RUNNING.
  - **Maximum percent**: Tỷ lệ tối đa của Tasks ở trạng thái RUNNING hoặc PENDING.

2. **Blue/Green**
- Do CodeDeploy thực hiện, duy trì hai phiên bản: production (BLUE) và test (GREEN).
- Lưu lượng dữ liệu chuyển dần từ BLUE sang GREEN theo một trong các cách:
  - **Canary**: Chia lưu lượng thành 2 phần, ví dụ:
    - CodeDeployDefault.ECSCanary10Percent5Minutes: 10% đầu, 90% sau 5 phút
    - CodeDeployDefault.ECSCanary10Percent15Minutes: 10% đầu, 90% sau 15 phút
  - **Linear**: Chia đều lưu lượng, ví dụ:
    - CodeDeployDefault.ECSLinear10PercentEvery1Minutes: 10% mỗi 1 phút
    - CodeDeployDefault.ECSLinear10PercentEvery3Minutes: 10% mỗi 3 phút
  - **All-at-once**: Chuyển toàn bộ lưu lượng cùng lúc

3. **External**
- Sử dụng deployment controller từ bên thứ ba, dựa trên Service/Task APIs.