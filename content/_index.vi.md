+++
title = "Triển khai CI/CD với ECS Container"
date = 2024
weight = 1
chapter = false
+++

# Triển khai CI/CD với ECS Container

#### Tổng Quan

Chào mừng bạn đến với workshop tiếp theo trong chuỗi Triển khai ứng dụng trên **Amazon Elastic Container Service (ECS)**. Trong phần này, chúng ta sẽ thiết lập CI/CD cho các container đã tạo ở phần trước, sử dụng dịch vụ ECS trên AWS.

**CI/CD (Continuous Integration/Continuous Deployment)** là quy trình tự động hóa mà các kỹ sư DevOps thường xuyên áp dụng để tăng hiệu quả làm việc. Thay vì phải thực hiện thủ công các bước triển khai mỗi khi có thay đổi trong mã nguồn – một quy trình tốn nhiều thời gian và dễ gây nhàm chán – CI/CD tự động hóa toàn bộ quy trình, giúp mọi thay đổi từ source code nhanh chóng được cập nhật trên ứng dụng. Đây là một công cụ vô cùng hữu ích, giúp giảm thiểu lỗi phát sinh và tăng tính nhất quán trong quá trình phát triển.

Ngoài ra, chúng ta sẽ tận dụng các công cụ giám sát của AWS để theo dõi liên tục ứng dụng, giúp phát hiện kịp thời và xử lý nhanh chóng nếu có lỗi xảy ra. Những công cụ này sẽ đảm bảo ứng dụng luôn hoạt động ổn định và hiệu suất cao, mang lại trải nghiệm tốt nhất cho người dùng.

#### Nội dung chính

1. [Giới thiệu](1-introduction/)
2. [Các bước chuẩn bị](2-preparation/)
3. [Triển khai CI/CD với Gitlab](3-cicd-gitlab/)
4. [Triển khai CI/CD với Github](4-cicd-github/)
5. [Triển khai CI/CD với Github và CodeBuild](5-cicd-codebuild/)
6. [Giám sát với Container insights](6-monitoring-with-container-insights/)
7. [Kiểm tra logs router với Firelens](7-logs-router-with-firelens/)
8. [Dọn dẹp tài nguyên](8-clean-up/)