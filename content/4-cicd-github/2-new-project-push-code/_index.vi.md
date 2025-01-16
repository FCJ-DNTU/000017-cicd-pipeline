+++
title = "Tạo một project mới và push code"
date = 2024
weight = 2
chapter = false
pre = "<b>4.2. </b>"
+++

#### Tạo mới repository

Repository này sẽ là nơi để bạn chạy Github Action.

- Đầu tiên là vào tài khoản Github của bạn.
- Click vào ảnh đại diện và chọn **Your repositories**

![Github](/images/5-cicd-github/5.2.1.png)

- Sau khi vào trang Repositories, chọn **New** để tạo mới.

![Github](/images/5-cicd-github/5.2.2.png)

- Nhập tên cho repository của bạn: `aws-fcj-container-app`
- Chọn **Public** nếu bạn muốn cho mọi người có thể truy cập.

![Github](/images/5-cicd-github/5.2.3.png)

- Hoàn thành tạo một repository trong Github của bạn, và các dòng lệnh dưới đây là để hướng dẫn push code cũng như tạo file.

![Github](/images/5-cicd-github/5.2.4.png)

#### Push code lên Github

- Dùng lệnh sau để add origin của repository của bạn vào.

```
git remote set-url origin "Your path"
```

![Github](/images/5-cicd-github/5.2.5.png)

- Lệnh dùng để tạo nhánh và đẩy code lên nhánh.

```
git branch -M "Your branch"
git push -u origin "Your branch"
```

![Github](/images/5-cicd-github/5.2.6.png)

- Kiểm tra xem code đã được push lên chưa.

![Github](/images/5-cicd-github/5.2.7.png)
