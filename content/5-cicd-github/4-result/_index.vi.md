+++
title = "Kiểm tra kết quả"
date = 2024
weight = 4
chapter = false
pre = "<b>5.4. </b>"
+++

#### Tạo tag

Để chạy lại các thay đổi ở trong code đã cấu hình, chúng ta cần phải tạo tag để cho Github Action chạy tự động và sẽ triển khai lại một images với version mới ở trong repository và tự động deploy lên ECS.

- Vào lại Github đã được push code cũng như là gán các secret key.
- Chọn **Tags** để tạo.

![Github](/images/5-cicd-github/5.4.1.png)

- Chọn **Releases**.
- Chọn **Create a new release**.

![Github](/images/5-cicd-github/5.4.2.png)

- Chọn **Choose a tag**.
- Nhập `v1.0.2`
- Chọn **Create new tag** để tạo.

![Github](/images/5-cicd-github/5.4.3.png)

- Chọn **Publish release** để hoàn tất tạo tag.

![Github](/images/5-cicd-github/5.4.4.png)

#### Kiểm tra quá trình Actions

- Chọn **Actions** để xem trạng thái các workflow.
- Chọn workflow mới nhất được tạo.

![Github](/images/5-cicd-github/5.4.5.png)

- Kiểm tra quá trình xem có bị lỗi hay không.

![Github](/images/5-cicd-github/5.4.6.png)

![Github](/images/5-cicd-github/5.4.7.png)

#### Kiểm tra bên trong AWS console

Vào bên trong AWS console để kiểm tra xem các quá trình triển khai CI/CD đã tạo được những tài nguyên mới chưa.

- Kiểm tra images của backend.

![Github](/images/5-cicd-github/5.4.8.png)

- Kiểm tra images của frontend.

![Github](/images/5-cicd-github/5.4.9.png)

- Kiểm tra task definition của backend.

![Github](/images/5-cicd-github/5.4.10.png)

- Kiểm tra task definition của frontend.

![Github](/images/5-cicd-github/5.4.11.png)

- Kiểm tra trong service của frontend đã được update task definition mới nhất.

![Github](/images/5-cicd-github/5.4.12.png)

- Kiểm tra Deployment trong phần CodeDeploy của service backend.

![Github](/images/5-cicd-github/5.4.13.png)

#### Kiểm tra Application

- Vào lại DNS của Load Balancer kiểm tra lại Application đã được biến đổi phần code mà mình đã đổi từ những phần trước. 

![Github](/images/5-cicd-github/5.4.14.png)
