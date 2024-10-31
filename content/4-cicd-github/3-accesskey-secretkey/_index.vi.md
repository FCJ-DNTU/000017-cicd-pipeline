+++
title = "Tạo Access key và Secret key"
date = 2024
weight = 3
chapter = false
pre = "<b>4.3. </b>"
+++

#### Tạo access key trong AWS IAM

Đầu tiên là vào AWS, gõ từ khóa **IAM** để tạo access key trong đó.
- Chọn **Users** nếu bạn sử dụng tài khoản user để triển khai bài Workshop này.
- Sau đó chọn vào user mà bạn đang sử dụng.

![Github](/images/5-cicd-github/5.3.1.png)

- Ở trong user của mình, bạn click chọn **Security credentials**
- Kéo xuống phần **Access keys** và chọn **Create access key**

![Github](/images/5-cicd-github/5.3.2.png)

- Bên trong phần **Create access key** chọn **Third-party service**.
- Và click **Next**

![Github](/images/5-cicd-github/5.3.3.png)

- Tiếp theo là nhập tag value `access key for github action`
- Chọn **Create access key**

![Github](/images/5-cicd-github/5.3.4.png)

- Access key đã được tạo, các bạn cần lưu nó lại bằng file hoặc bất kì nơi đâu để có thể dùng nó cho mục đích tiếp theo.

![Github](/images/5-cicd-github/5.3.5.png)

#### Tạo secret key trong Github

Tạo secret key cho github để có thể dùng các giá trị này gán vào các biến ở trong CI/CD để nó được hoạt động đúng cách.
- Vào phần **Settings** của repository bạn đã tạo từ phần trước.
- Chọn **Secrets and variables** và **Actions** như hướng dẫn.
- Chọn **New repository secret** để tạo secret.

![Github](/images/5-cicd-github/5.3.6.png)

- Thêm các giá trị như hình sau đây vào:
  - `AWS_ACCESS_KEY_ID` gán giá trị access key vừa tạo trong aws vào.
  - `AWS_SECRET_ACCESS_KEY` gán giá trị secret key vừa tạo trong aws vào.
  - `AWS_REGION` gán giá trị bằng region bạn đang sử dụng.
  - `AWS_ACCOUNT_NUMBER` gán số account của bạn đang sử dụng.
  - `CI_PROJECT_BE_NAME` gán giá trị bằng tên repository ở trên ECR của backend.
  - `CI_PROJECT_FE_NAME` gán giá trị bằng tên repository ở trên ECR của frontend.
  - `CLUSTER_NAME` gán giá trị bằng tên Cluster ECS.
  - `TASK_NAME_BE` gán giá trị bằng tên task definition của backend.
  - `TASK_NAME_FE` gán giá trị bằng tên task definition của frontend.
  - `SERVICE_NAME_BE` gán giá trị bằng tên Sevice name của backend.
  - `SERVICE_NAME_FE` gán giá trị bằng tên Sevice name của frontend.
  - `AWS_APPLICATION_NAME` gán giá trị bằng tên Application ở trong CodeDeploy của backend.
  - `AWS_DEPLOYMENT_GROUP_NAME` gán giá trị bằng tên Deployment group ở trong Application của backend.

![Github](/images/5-cicd-github/5.3.7.png)

{{% notice tip %}}
Vì repository đang sử dụng ECR để chứa images, nếu bạn muốn sử dụng một nơi lưu trữ khác như Docker Hub, cần phải thêm các secret key để đăng nhập vào Docker Hub và chỉnh lại các biến trong file cấu hình để phù hợp với Docker Hub.
{{% /notice %}}