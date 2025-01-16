+++
title = "Kiểm tra kết quả"
date = 2024
weight = 5
chapter = false
pre = "<b>3.5. </b>"
+++

#### Kiểm tra kết quả ECR

 - Truy cập ECR
 - Chọn repository của backend
![Kết quả ECR](/images/4-cicd-gitlab/4.5.1.png)
  - Truy cập ECR
  - Chọn repository của frontend
![Kết quả ECR](/images/4-cicd-gitlab/4.5.2.png)

#### Kiểm tra kết quả Task Definition
  - Chọn tab "Task Definitions"
  - Chọn task của frontend
![Kết quả Task Definition](/images/4-cicd-gitlab/4.5.3.png)
  - Chọn tab "Task Definitions"
  - Chọn task của backend
![Kết quả Task Definition](/images/4-cicd-gitlab/4.5.4.png)

#### Kiểm tra kết quả Sevice
  - Truy cập ECS
  - Chọn service của frontend
  - Review revision của service
![Kết quả Service](/images/4-cicd-gitlab/4.5.5.png)
  - Truy cập ECS
  - Chọn service của backend
  - Review Deployment của service
![Kết quả Service](/images/4-cicd-gitlab/4.5.6.png)

#### Kiểm tra website
  - Truy cập website
  - Kiểm tra Dashboard đã chuyển sang version mới
![Kết quả Website](/images/4-cicd-gitlab/4.5.7.png)
