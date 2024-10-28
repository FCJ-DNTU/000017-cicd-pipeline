+++
title = "Sự chuẩn bị"
date = 2024
weight = 2
chapter = false
pre = "<b>2. </b>"
+++

#### Cấu hình cơ sở hạ tầng

Trước khi tham gia vào workshop triển khai CI/CD trên ECS, bạn nên hoàn thành hai workshop sau để nắm vững hạ tầng AWS cũng như quy trình triển khai Container trên ECS:

- [Deploy Application on Docker Container](https://fcj-dntu.github.io/000015-deploy-app-docker).
- [Deploy applications on Amazon Elastic Container Service](https://fcj-dntu.github.io/000016-deploy-app-ecs/).

Hoàn thành hai workshop này sẽ giúp bạn thiết lập các thành phần cần thiết để chuẩn bị cho thiết lập CI/CD trên ECS, bao gồm:

- Hạ tầng mạng VPC
- Database Instance trên Amazon RDS
- Image đã được đẩy lên Docker Hub hoặc Amazon ECR
- Amazon Cloud Map cho dịch vụ khám phá
- ECS Cluster chứa các container của ứng dụng
- Application Load Balancer để phân phối tải
- Ứng dụng đã được triển khai dưới dạng Container trên ECS

Với các thành phần hạ tầng này đã sẵn sàng, chúng ta sẽ tiến hành bước tiếp theo để thiết lập quy trình CI/CD tự động trên ECS, giúp hoàn thiện vòng đời triển khai ứng dụng của bạn.
