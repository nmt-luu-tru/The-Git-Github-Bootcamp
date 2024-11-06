### Hướng Dẫn Đăng Ký GitHub và Thiết Lập SSH Key

#### 1. Đăng Ký Tài Khoản GitHub

1. **Truy cập GitHub:** Mở trang [GitHub](https://github.com) và nhấp vào **Sign up**.
2. **Điền Thông Tin:** Tạo tên người dùng, địa chỉ email, và mật khẩu.
3. **Xác Nhận Email:** Hãy dùng email thật, vì GitHub sẽ yêu cầu xác minh.
4. **Cấu hình Email Cục Bộ:** Đảm bảo email trên GitHub giống với email bạn đã cấu hình trên Git (nếu trước đó bạn đã dùng `git config user.email`), điều này giúp GitHub nhận diện bạn khi bạn đẩy mã nguồn.

#### 2. Thiết Lập SSH Key

SSH Key giúp xác thực mà không cần nhập mật khẩu mỗi lần tương tác với GitHub từ dòng lệnh.

##### Kiểm Tra SSH Key

Chạy lệnh sau để kiểm tra xem bạn đã có SSH Key chưa:
   ```bash
   ls -al ~/.ssh
   ```
Nếu bạn thấy các tệp như `id_rsa.pub` hoặc `id_ed25519.pub`, nghĩa là bạn đã có SSH Key. Nếu không có, bạn cần tạo mới.

##### Tạo SSH Key Mới

1. **Tạo SSH Key:** Sao chép và chạy lệnh sau, thay `<email@example.com>` bằng email của bạn:
   ```bash
   ssh-keygen -t ed25519 -C "<email@example.com>"
   ```
   - **Lưu tên và vị trí tệp:** Nhấn Enter để sử dụng tên và đường dẫn mặc định, hoặc đặt tên riêng nếu muốn.
   - **Nhập mật khẩu:** Bạn có thể đặt mật khẩu hoặc để trống.

2. **Thêm SSH Key vào SSH Agent:**
   - Chạy lệnh sau:
     ```bash
     eval "$(ssh-agent -s)"
     ```
   - Nếu dùng macOS, tạo và mở tệp `config` trong thư mục `~/.ssh` và thêm nội dung sau:
     ```plaintext
     Host *
       AddKeysToAgent yes
       IdentityFile ~/.ssh/id_ed25519
     ```

3. **Thêm SSH Key vào Agent:**
   ```bash
   ssh-add ~/.ssh/id_ed25519
   ```

#### 3. Thêm SSH Key Vào GitHub

1. **Sao Chép Public Key:** Chạy lệnh sau để sao chép public key vào clipboard:
   ```bash
   pbcopy < ~/.ssh/id_ed25519.pub
   ```
2. **Thêm Vào GitHub:**
   - Vào GitHub, vào **Settings** > **SSH and GPG keys** > **New SSH key**.
   - Dán key đã sao chép vào và đặt tên.

Sau khi hoàn thành, bạn sẽ không cần nhập thông tin đăng nhập mỗi khi tương tác với GitHub.
