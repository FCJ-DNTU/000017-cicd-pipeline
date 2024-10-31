+++
title = "Theo dõi ứng dụng với Container Insights (CloudWatch)"
date = 2024
weight = 6
chapter = false
pre = "<b>6. </b>"
+++

![cloudwatch_container_insights](/images/8-monitoring-with-container-insights/cloudwatch_container_insights.png)

{{% notice note %}}
Để làm được đúng phần này thì bạn phải làm thành công các bước cấu hình CI/CD và chạy CI/CD trước đó.
{{% /notice %}}

#### Cấu hình Container Insights

Trước tiên, trong phần này thì chúng ta sẽ phải cấu hình một số thứ trước khi có thể dùng được **Container Insights**. **Container Insights** là một dịch vụ mà cho phép chúng ta có thể quan sát được các thông số như mức sử dụng CPU, Network, ... từ đó có thể suy ra được lượng người dùng trong một khoảng thời gian nào đó.

Kết hợp với **CloudWatch** thì chúng ta có thể xem được các logs được gửi từ trong Container dưới dạng các groups, thông thường thì tên group sẽ bắt đầu với tiền tố là **/ecs/\***. Khi đó thì chúng ta sẽ có cái nhìn tổng quát hơn về các ứng dụng trong hệ thống, như là đang chạy như thế nào, có cảnh báo gì không, hay là khi có một ứng dụng nào đó bị lỗi thì chúng ta có thể đọc các logs đó để tìm ra nguyên nhân, hoặc cũng có thể điều tra được các traffic bất thường khi hệ thống bị xâm nhập.

Đầu tiên, vào trong trang console của ECS, ở menu bên phải, chọn **Account settings**

![8.1](/images/8-monitoring-with-container-insights/8.1.png)

Trong phần **Account settings** thì mình sẽ để ý tới mục **CloudWatch Container Insights** có trạng thái **Turned off**, giờ thì chọn **Update**.

![8.2](/images/8-monitoring-with-container-insights/8.2.png)

Tích chọn **Container insights** và ấn **Save changes**

![8.3](/images/8-monitoring-with-container-insights/8.3.png)

![8.4](/images/8-monitoring-with-container-insights/8.4.png)

#### Quan sát các thông số với Performance Monitoring

Quay trở lại với tab **Cluster**, vào trong cluster của chúng ta

![8.5](/images/8-monitoring-with-container-insights/8.5.png)

Mở tab **Metrics** và chọn **View Container Insights**

![8.6](/images/8-monitoring-with-container-insights/8.6.png)

Sau đó thì trang **Container Insights** sẽ hiện ra

![8.7](/images/8-monitoring-with-container-insights/8.7.png)

{{% notice note %}}
Trong này thì chúng ta có thể thấy được các thông số của cluster mà chúng ta đã tiển khai ở trước đó **FCJ-Lab-cluster** nếu như trong region mà chúng ta tạo chỉ có một cluster ở trong đó.
{{% /notice %}}

Để xem được các thông tin khác, cluster khác thì

- Ở thanh chọn bên trái, chọn **ECS Cluster**
- Ở thanh chọn bên phải, chọn cluster mà chúng ta đã tạo, trong bài này là **FCJ-Lab-cluster**

![8.8](/images/8-monitoring-with-container-insights/8.8.png)

Chúng ta còn có thể xem các biểu đồ của một số tài nguyên khác, trong này thì chúng ta sẽ chọn **ECS Tasks**

![8.9](/images/8-monitoring-with-container-insights/8.9.png)

Khi đó biểu đồ sẽ hiện theo các tasks khác nhau (gồm **fcjresbar-task-fe** và **fcjresbar-task-be**)

![8.10](/images/8-monitoring-with-container-insights/8.10.png)

Xem theo **ECS Services**

![8.11](/images/8-monitoring-with-container-insights/8.11.png)

Đây là một cách để mà chúng ta có thể xem được các biểu đồ hoạt động của các Clusters, Services, Tasks, ...

#### Quan sát các thông số với Container Map

Ở trong phần này thì chúng ta có thể xem được trong Cluster mà chúng ta đã triển khai thì có những **Containers** nào, **Tasks** nào, **Services** nào, ... một cách cụ thể hơn.

Thay đổi **Performance Monitoring** thành **Container Map**

![8.12](/images/8-monitoring-with-container-insights/8.12.png)

Sau đó chúng ta sẽ thấy được giao diện mới, trong này, bạn có thể thấy được là một **Cluster** nó sẽ quản lý các tài nguyên có liên quan như **Services**, **Tasks**. Nhưng các thông số trong một **Task** sẽ khác với các thông số trong một **Service**, vì **Service** sẽ quản lý trực tiếp các **Task**, nên các thông số thuộc **Task** cũng sẽ thuộc **Service**.

![8.13](/images/8-monitoring-with-container-insights/8.13.png)

Ấn vào **frontend** service để xem các thông số ở trong service này.

![8.14](/images/8-monitoring-with-container-insights/8.14.png)

Chúng ta có thể thấy các thông số cơ bản như: **CPU utilization**, **Memory utilization**, **Network**, **Disk utilization**.

![8.15](/images/8-monitoring-with-container-insights/8.15.png)

Giờ thì xem thử một task, chọn **fcjresbar-task-be**.

![8.16](/images/8-monitoring-with-container-insights/8.16.png)

Như vậy, với Container Map thì giúp chúng ta có một cái nhìn cụ thể hơn về các **Services**, **Tasks** ở trong một Cluster.

Ngoài ra thì chúng ta cũng có thể xem được với **List View**.

- Chọn **Resources**
- Chọn **FCJ-Lab-cluster**

Bao gồm các resource mà mình đã tạo, cũng như là đang chạy.

![8.17](/images/8-monitoring-with-container-insights/8.17.png)

Chúng ta có thể xem trung bình mức sử dụng của các Resources này trong các khoảng thời gian khác nhau, từ 1 giờ, 3 giờ, 12 giờ, 1 ngày, 1 tuần, ...

![8.18](/images/8-monitoring-with-container-insights/8.18.png)

Nhưng vậy thì chúng ta đã cấu hình và thực hành xong phần quan sát với Container Insights, nhưng AWS không chỉ giới hạn dịch vụ quan sát, theo dõi hệ thống trong Container Insights mà chúng ta cũng có thể dùng các dịch vụ khác hoặc các dịch vụ bên thứ 3 để làm việc đó.

Theo mặc định thì **ECS Container** sẽ chuyển logs về cho **CloudWatch**, nếu như bạn để ý trong phần cấu hình **Task Definition** ở các workshop 16 trước đó và chúng ta có thể định tuyến các logs này tới các đích khác như **Amazon S3**, **Amazon EC2** hoặc là các dịch vụ bên ngoài. Để mà có thể chuyển được các logs này tới một đích khác, thì chúng ta sẽ cần tới một ứng dụng chạy trong một ECS Service cùng với ứng dụng mà chúng ta muốn logs, trong phần sau chúng ta sẽ cấu hình **Firelens** đê chuyển logs tới **Amazon S3**.
