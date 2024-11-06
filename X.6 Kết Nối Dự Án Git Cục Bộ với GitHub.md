### Kết Nối Dự Án Git Cục Bộ với GitHub

Để đẩy mã từ dự án Git cục bộ của bạn lên GitHub, có hai tùy chọn bạn có thể sử dụng. Dưới đây là cách làm của cả hai tùy chọn.

---

### Tùy Chọn 1: Đã Có Dự Án Git Cục Bộ Sẵn

1. **Tạo Kho Rỗng Trên GitHub:**
   - Truy cập vào [GitHub](https://github.com) và đăng nhập.
   - Nhấn **New repository** từ trang chủ (hoặc vào dấu `+` ở góc trên cùng và chọn **New repository**).
   - Đặt tên cho kho (repository) của bạn và chọn **Public** hoặc **Private**. Sau đó nhấn **Create repository**.

2. **Kết Nối Repo Cục Bộ Với GitHub:**
   - Từ kho cục bộ của bạn, mở Terminal và chạy lệnh sau để thêm GitHub làm remote:
     ```bash
     git remote add origin <URL_GitHub>
     ```
   - Trong đó `<URL_GitHub>` là URL của repo bạn vừa tạo trên GitHub (ví dụ: `https://github.com/username/repo.git`).

3. **Đẩy Dự Án Lên GitHub:**
   - Chạy lệnh:
     ```bash
     git push -u origin main
     ```
   - Thao tác này sẽ đẩy toàn bộ lịch sử và các tập tin từ dự án cục bộ của bạn lên GitHub.

---

### Tùy Chọn 2: Bắt Đầu Từ GitHub Và Clone Về Máy

1. **Tạo Kho Rỗng Trên GitHub:**
   - Làm tương tự như bước trên để tạo một repository rỗng trên GitHub.

2. **Clone Kho Về Máy Cục Bộ:**
   - Sử dụng lệnh `git clone` với URL của repo vừa tạo trên GitHub:
     ```bash
     git clone <URL_GitHub>
     ```
   - Thao tác này sẽ tải toàn bộ repo rỗng về máy của bạn, tạo thư mục và tự động kết nối với GitHub.

3. **Làm Việc Với Dự Án:**
   - Di chuyển vào thư mục vừa clone:
     ```bash
     cd <tên_thư_mục>
     ```
   - Bắt đầu làm việc và sử dụng các lệnh Git như thường lệ (`git add`, `git commit`, ...) để lưu thay đổi.

4. **Đẩy Thay Đổi Lên GitHub:**
   - Khi đã có thay đổi, dùng lệnh `git push` để đẩy mã nguồn lên GitHub:
     ```bash
     git push -u origin main
     ```

---

### Ghi Chú Thêm

- Nếu repo đã được clone từ GitHub, bạn không cần phải thực hiện kết nối với remote (`git remote add`) vì nó đã được tự động liên kết.
- **Tập tin README** và **.gitignore** có thể thêm khi tạo repo, nhưng bạn cũng có thể tạo thủ công sau khi đã clone về.

Việc sử dụng GitHub giúp bạn sao lưu mã, làm việc nhóm, và quản lý lịch sử phát triển dự án một cách hiệu quả.
