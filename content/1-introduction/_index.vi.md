+++
title = "Giới thiệu"
date = 2024
weight = 1
chapter = false
pre = "<b>1. </b>"
+++


#### Github Action CI/CD

**GitHub Actions** là dịch vụ tự động hóa tích hợp trên GitHub, giúp tự động hóa quy trình phát triển phần mềm từ kiểm tra mã nguồn đến triển khai ứng dụng, dễ dàng thiết lập CI/CD (Continuous Integration/Continuous Deployment).

1. Continuous Integration (CI)
- Xây dựng và Kiểm tra Tự động: Tự động xây dựng và kiểm tra mã mỗi khi có thay đổi, giúp phát hiện lỗi sớm.
- Workflows: Định nghĩa các workflow để tự động thực hiện kiểm tra, xây dựng và phát hành mã khi có sự kiện như pull request hoặc commit mới.
2. Continuous Deployment (CD)
- Triển khai Tự động: Hỗ trợ triển khai ứng dụng tự động lên các môi trường như staging hoặc production khi mã được chấp nhận.
- Tích hợp Dịch vụ: Dễ dàng tích hợp với các dịch vụ như AWS, Azure và Google Cloud.
3. Tính Năng Nổi Bật
- Khả Năng Tùy Biến: Tạo các action tùy chỉnh hoặc sử dụng action từ GitHub Marketplace.
- Giao Diện Thân Thiện: Dễ dàng thiết lập và quản lý workflows mà không cần kiến thức sâu về scripting.
- Quản lý Tài Nguyên: Theo dõi trạng thái workflow và cung cấp thông tin chi tiết về quá trình kiểm tra và triển khai.
4. Lợi Ích
- Tiết Kiệm Thời Gian: Giảm thiểu công việc lặp đi lặp lại cho nhà phát triển.
- Nâng Cao Chất Lượng Mã: Cải thiện chất lượng phần mềm nhờ kiểm tra và triển khai thường xuyên.
- Khả Năng Linh Hoạt: Dễ dàng điều chỉnh quy trình CI/CD để phù hợp với nhu cầu dự án.

#### Gitlab CI/CD

**GitLab CI/CD** là thành phần quan trọng của GitLab, cho phép tự động hóa quy trình phát triển phần mềm thông qua tích hợp liên tục (CI) và triển khai liên tục (CD).

1. Continuous Integration (CI)
- Tự động Xây dựng và Kiểm tra: Tự động hóa xây dựng mã và kiểm tra khi có thay đổi, giúp phát hiện lỗi sớm.
- Cấu hình trong .gitlab-ci.yml: Cấu hình CI/CD được định nghĩa trong file này, dễ dàng thiết lập pipeline.
2. Continuous Deployment (CD)
- Triển khai Tự động: Hỗ trợ triển khai ứng dụng lên môi trường staging và production sau khi kiểm tra thành công.
- Quản lý Phiên Bản: Theo dõi và dễ dàng rollback khi cần.
3. Tính Năng Nổi Bật
- GitLab Runners: Thành phần thực thi job trong pipeline, có thể sử dụng runners của GitLab hoặc tự tạo.
- Hỗ Trợ Đa Nền Tảng: Tích hợp với nhiều dịch vụ như AWS, Google Cloud, Azure.
- Giao Diện Trực Quan: Dễ dàng theo dõi tiến trình pipeline và log qua giao diện người dùng.
4. Lợi Ích
- Tiết Kiệm Thời Gian: Giảm công sức cho công việc lặp lại.
- Cải Thiện Chất Lượng Mã: Kiểm tra liên tục giúp phát hiện lỗi nhanh chóng.
- Tính Linh Hoạt và Tùy Biến: Tùy chỉnh quy trình theo nhu cầu dự án.
5. Tích Hợp với DevOps
- Hỗ trợ quy trình DevOps, tạo ra vòng đời phát triển nhanh chóng và cải thiện sự cộng tác giữa các nhóm.

#### AWS CodePipeline CI/CD

**AWS CodePipeline** là dịch vụ CI/CD quản lý hoàn toàn trên AWS, cho phép tự động hóa quy trình xây dựng, kiểm tra và triển khai mã ứng dụng. Nó tối ưu hóa quy trình phát triển phần mềm từ mã nguồn đến sản xuất.

1. Continuous Integration (CI) với **AWS CodeBuild**: 
- AWS CodeBuild tự động biên dịch mã nguồn, chạy kiểm tra và tạo artifact cho việc triển khai, mà không cần quản lý hạ tầng.
- Tính năng nổi bật:
  - Tích hợp Mã Nguồn: Hỗ trợ lấy mã từ AWS CodeCommit, GitHub, Bitbucket, v.v.
  - Hỗ trợ Nhiều Ngôn Ngữ: Tùy chỉnh môi trường xây dựng cho nhiều ngôn ngữ lập trình.
  - Quy mô Tự Động: Mở rộng quy trình xây dựng theo yêu cầu để tiết kiệm chi phí.
2. Continuous Deployment (CD) với **AWS CodeDeploy**
- AWS CodeDeploy tự động hóa quá trình triển khai ứng dụng lên các môi trường như Amazon EC2, AWS Lambda.
- Tính năng nổi bật:
  - Triển khai Mượt Mà: Hỗ trợ phương pháp blue/green và rolling deployment để giảm downtime.
  - Theo Dõi Triển Khai: Theo dõi quá trình triển khai và có khả năng rollback khi có lỗi.
  - Tích hợp với AWS: Kết hợp dễ dàng với Amazon ECS, AWS Lambda, và Amazon EC2.
3. Tích Hợp trong **AWS CodePipeline**
- Xây dựng Pipeline: Kết hợp CodeBuild và CodeDeploy để định nghĩa quy trình CI/CD hoàn chỉnh từ lấy mã, xây dựng, kiểm tra đến triển khai.
- Quản lý Quy Trình Tự Động: Tự động hóa và quản lý quy trình CI/CD hiệu quả, đảm bảo mọi thay đổi mã nguồn được kiểm tra và triển khai ngay lập tức, giảm thiểu rủi ro và nâng cao hiệu suất.

#### Monitoring

1. Monitoring với CloudWatch Container Insights

CloudWatch Container Insights là một tính năng trong AWS CloudWatch, cung cấp khả năng giám sát và phân tích các container đang chạy trên Amazon ECS (Elastic Container Service) và EKS (Elastic Kubernetes Service). Dưới đây là một số điểm nổi bật của Container Insights:

- Giám sát Hiệu Suất: Container Insights cho phép bạn theo dõi các chỉ số hiệu suất quan trọng như CPU, bộ nhớ, và mạng cho từng container, giúp phát hiện sớm các vấn đề và tối ưu hóa hiệu suất ứng dụng.
- Thống Kê Tình Trạng Container: Bạn có thể xem thông tin chi tiết về tình trạng hoạt động của các container, bao gồm trạng thái của chúng (chạy, dừng, lỗi) và các thông số khác như thời gian chạy và số lượng bản sao.
- Tích Hợp Với AWS: Container Insights có thể dễ dàng tích hợp với các dịch vụ khác của AWS, cho phép bạn xây dựng các giải pháp giám sát toàn diện và tạo báo cáo tùy chỉnh dựa trên các chỉ số container.
- Dashboard Trực Quan: AWS cung cấp các dashboard trực quan cho phép bạn theo dõi tình trạng và hiệu suất của container một cách dễ dàng, cùng với khả năng thiết lập cảnh báo khi có sự cố xảy ra.

2. Logs Router với FireLens

FireLens là một tính năng trong AWS giúp bạn quản lý và định tuyến log từ các container đến các dịch vụ lưu trữ log khác nhau. Dưới đây là một số điểm nổi bật của FireLens:

- Định Tuyến Log Linh Hoạt: FireLens cho phép bạn dễ dàng định tuyến log từ các container đến nhiều mục tiêu khác nhau, bao gồm Amazon CloudWatch Logs, Amazon S3, Elasticsearch, và nhiều dịch vụ khác. Điều này giúp bạn dễ dàng quản lý và phân tích log.
- Tính Năng Tùy Chỉnh: Bạn có thể tùy chỉnh cách thức log được định tuyến, định dạng và xử lý log, giúp bạn tạo ra các giải pháp quản lý log phù hợp với nhu cầu cụ thể của ứng dụng.
- Hỗ Trợ Đa Nền Tảng: FireLens hỗ trợ cả Amazon ECS và EKS, cho phép bạn dễ dàng tích hợp vào các ứng dụng containerized trên nhiều nền tảng khác nhau.
- Tối Ưu Hóa Hiệu Suất: Bằng cách sử dụng FireLens, bạn có thể giảm tải cho các container, vì các tác vụ ghi log và định tuyến được xử lý riêng biệt, giúp cải thiện hiệu suất của ứng dụng.