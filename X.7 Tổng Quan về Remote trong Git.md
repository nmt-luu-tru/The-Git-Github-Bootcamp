Dưới đây là hướng dẫn chi tiết từng bước để bạn có thể kết nối repo Git cục bộ trên máy tính của mình với một repo trống vừa tạo trên GitHub. Việc này giúp bạn có thể đưa mã nguồn từ máy tính của mình lên GitHub để dễ dàng lưu trữ, sao lưu và chia sẻ với người khác.

---

### Tổng Quan về Remote trong Git

Một "remote" trong Git đơn giản là một liên kết URL đến một repo Git được lưu trữ ở một nơi khác (thường là trên GitHub). Khi bạn thiết lập một remote, bạn đang bảo Git nhớ URL đó để có thể đẩy (push) hoặc kéo (pull) mã nguồn giữa repo cục bộ và repo từ xa.

---

### Bước 1: Kiểm Tra Remote Hiện Có Trong Repo Cục Bộ

Trước khi bắt đầu, bạn nên kiểm tra xem repo cục bộ của mình đã có remote nào chưa bằng cách dùng lệnh sau trong terminal hoặc command prompt:

```bash
git remote -v
```

- Nếu repo của bạn chưa có remote, lệnh này sẽ không trả về kết quả nào.
- Nếu repo của bạn đã có remote, bạn sẽ thấy một danh sách các remote hiện có cùng với URL của chúng.

> **Ví dụ:** Nếu bạn đã từng clone (sao chép) một repo từ GitHub, remote mặc định là `origin`, liên kết với URL của repo mà bạn đã clone.

---

### Bước 2: Thêm Remote Mới để Kết Nối Repo Cục Bộ với Repo GitHub

Nếu bạn chưa có remote hoặc repo cục bộ không được kết nối với repo trên GitHub, bạn cần thiết lập một remote mới. Để thực hiện việc này, bạn làm theo các bước sau:

1. **Tạo một repo trống trên GitHub**  
   - Đăng nhập vào GitHub, sau đó nhấp vào nút **New** (nút xanh) hoặc chọn **New repository** từ biểu tượng dấu + ở góc trên bên phải.
   - Đặt tên cho repo, chọn quyền truy cập (Public hoặc Private), và nhấn **Create repository**.
   - Bạn sẽ thấy trang repo mới với URL của nó, thường có dạng `https://github.com/tentaikhoan/tên_repo.git`.

2. **Thêm Remote vào Repo Cục Bộ**  
   - Đảm bảo bạn đã vào thư mục chứa repo cục bộ của mình.
   - Sử dụng lệnh sau để thêm remote:

     ```bash
     git remote add origin <URL_GitHub>
     ```

     Trong đó:
     - `origin` là tên mặc định thường được dùng để gọi remote. Bạn có thể đặt tên khác, nhưng `origin` là cách gọi tiêu chuẩn và dễ nhớ.
     - `<URL_GitHub>` là URL của repo bạn vừa tạo trên GitHub.

   - Ví dụ, nếu bạn thấy URL trên GitHub là `https://github.com/tentaikhoan/github-demo.git`, bạn sẽ chạy lệnh sau:

     ```bash
     git remote add origin https://github.com/tentaikhoan/github-demo.git
     ```

3. **Kiểm Tra Remote Mới**  
   - Để đảm bảo remote đã được thiết lập thành công, bạn chạy lại lệnh sau:

     ```bash
     git remote -v
     ```

   - Nếu thiết lập đúng, bạn sẽ thấy tên remote `origin` cùng với URL của repo GitHub mà bạn đã kết nối.

---

### Tại Sao `origin` Lại Thường Được Sử Dụng Là Tên Remote?

`origin` là tên mặc định mà Git thường sử dụng cho remote đầu tiên kết nối với một repo từ xa, và đây là một quy ước phổ biến. Khi bạn nhìn thấy `origin`, bạn sẽ biết ngay đó là remote chính kết nối đến GitHub hoặc một dịch vụ lưu trữ tương tự.

> **Lưu ý:** Bạn hoàn toàn có thể sử dụng một tên khác thay vì `origin`, nhưng nên dùng `origin` cho dễ hiểu và dễ quản lý khi làm việc với nhiều remote.

---

### Một Số Lệnh Remote Khác

1. **Đổi Tên Remote**  
   Nếu bạn muốn đổi tên remote từ `origin` sang một tên khác, bạn có thể sử dụng lệnh:

   ```bash
   git remote rename origin <tên_mới>
   ```

   Ví dụ:

   ```bash
   git remote rename origin main_repo
   ```

2. **Xóa Remote**  
   Nếu bạn muốn xóa một remote khỏi repo, dùng lệnh:

   ```bash
   git remote remove <tên_remote>
   ```

   Ví dụ, để xóa remote `origin`:

   ```bash
   git remote remove origin
   ```

---

### Bước Kế Tiếp: Đẩy Mã Nguồn Lên GitHub

Sau khi thiết lập remote thành công, bước tiếp theo là đẩy (push) mã nguồn từ repo cục bộ lên repo GitHub. Ở phần tiếp theo, bạn sẽ được hướng dẫn cách thực hiện thao tác này.

> **Nhắc nhở:** Luôn đảm bảo bạn đang dùng đúng URL của repo trên GitHub của mình, và không nên dùng URL của người khác vì bạn sẽ không có quyền đẩy mã nguồn lên repo của họ.

---

### Tóm Tắt

- **Remote** là một liên kết URL đến một repo từ xa.
- `git remote add origin <URL_GitHub>` là lệnh để thêm remote `origin` với URL đến repo GitHub của bạn.
- Bạn có thể kiểm tra remote hiện có bằng lệnh `git remote -v`.
  
Bây giờ, repo cục bộ của bạn đã biết đến URL của repo GitHub và bạn đã thiết lập kết nối thành công. Trong bước tiếp theo, bạn sẽ đẩy mã nguồn của mình lên GitHub thông qua remote `origin`.
