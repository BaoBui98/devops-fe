docker-compose -f docker-compose.prod.yml pull
docker-compose -f docker-compose.prod.yml up -d

sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

# 1. Cài đặt Docker bản mới nhất từ kho của Amazon Linux

sudo dnf install docker -y

# 2. Kích hoạt dịch vụ Docker chạy nền

sudo systemctl start docker

# 3. Cấu hình để Docker tự động bật mỗi khi máy ảo EC2 khởi động lại

sudo systemctl enable docker

# 4. Cấp quyền cho user ec2-user để sau này gõ lệnh docker không cần gõ chữ "sudo" phía trước

sudo usermod -aG docker ec2-user
