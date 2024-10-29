+++
title = "Cài đặt và đăng ký GitLab Runner"
date = 2024
weight = 2
chapter = false
pre = "<b>4.2. </b>"
+++

{{% notice note %}}
Trong bài này, chúng ta sẽ thực hiện cài đặt và cấu hình GitLab Runner - một agent quan trọng để thực thi các CI/CD jobs trong GitLab.
{{% /notice %}}

#### Cài đặt GitLab Runner

1. Chuẩn bị môi trường
![Create Config Directory](/images/4-cicd-gitlab/4.2.1.png)

Tạo thư mục và file cấu hình:
```bash
sudo mkdir -p /tools && vi tools/setup.sh
```

2. Cài đặt Runner
![Install GitLab Runner](/images/4-cicd-gitlab/4.2.2.png)

Thêm nội dung sau vào file setup.sh:
```bash
#!/bin/bash
# Cập nhật package list
apt update -y

# Cài đặt GitLab Runner
curl -L "https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh" | sudo bash
apt install gitlab-runner

# Kiểm tra version
gitlab-runner --version
```

3. Xác nhận cài đặt
![Check Version](/images/4-cicd-gitlab/4.2.3.png)

Kiểm tra version để đảm bảo cài đặt thành công:
```bash
gitlab-runner --version
```

#### Thiết lập Runner Backend

1. Chuyển đổi user
![Switch User](/images/4-cicd-gitlab/4.2.4.png)

```bash
sudo -i
su gitlab-runner
cd
```

2. Truy cập GitLab Settings
![Access Settings](/images/4-cicd-gitlab/4.2.5.png)

Điều hướng đến Runner settings:
- Settings → CI/CD → Runners
- Nhấn "New project runner"

3. Thiết lập Runner Backend
![Configure Runner](/images/4-cicd-gitlab/4.2.6.png)

Cấu hình thông tin:
- Tag: `fcj-lab-runner-be`
- Chọn "Run untagged jobs"
- Nhấn "Create runner"

{{% notice tip %}}
Tag giúp xác định loại jobs mà runner sẽ xử lý. Ví dụ: backend jobs, frontend jobs.
{{% /notice %}}

4. Đăng ký Runner
![Register Runner](/images/4-cicd-gitlab/4.2.8.png)

```bash
# Đăng ký runner với token
gitlab-runner register --url https://gitlab.com --token [your-token]

# Nhập các thông tin khi được hỏi
- URL: https://gitlab.com
- Name: fcj-lab-runner-be
- Executor: shell
```

5. Khởi động Runner
![Start Runner](/images/4-cicd-gitlab/4.2.9.png)

```bash
# Chạy trong background
nohup gitlab-runner run > start-runner-be.txt 2>&1 &

# Kiểm tra log
tail -f start-runner-be.txt
```

#### Thiết lập Runner Frontend

{{% notice note %}}
Để xử lý các jobs một cách hiệu quả, chúng ta cần tạo runner riêng cho frontend.
{{% /notice %}}

1. Tạo Runner Frontend
![Frontend Runner](/images/4-cicd-gitlab/4.2.11.png)

Lặp lại các bước trên với thông tin:
- Tag: `fcj-lab-runner-fe`
- Name: `fcj-lab-runner-fe`
- Các cấu hình khác giữ nguyên

2. Xác nhận Runners
![Verify Runners](/images/4-cicd-gitlab/4.2.12.png)

Kiểm tra danh sách runners:
- Backend: #42138335 (fcj-lab-runner-be)
- Frontend: #42138385 (fcj-lab-runner-fe)