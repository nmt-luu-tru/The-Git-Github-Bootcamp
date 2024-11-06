Dưới đây là hướng dẫn chi tiết về cách đẩy (push) mã nguồn từ repo Git cục bộ của bạn lên GitHub sau khi đã kết nối hai repo này với nhau. Phần này sẽ giải thích cách sử dụng lệnh `git push` để đưa mã nguồn từ máy tính của bạn lên repo GitHub.

---

### Tổng Quan về Các Bước Đẩy Mã Nguồn Lên GitHub

1. **Tạo repo trên GitHub** (đã hoàn thành).
2. **Kết nối repo cục bộ với repo GitHub bằng cách thêm remote** (đã hoàn thành trong phần trước).
3. **Đẩy mã nguồn từ repo cục bộ lên GitHub** (sẽ thực hiện trong phần này).

---

### Giới Thiệu về `git push`

Lệnh `git push` là lệnh của Git giúp bạn đưa các thay đổi từ repo cục bộ lên repo từ xa (trong trường hợp này là GitHub). Cấu trúc lệnh thường có dạng:

```bash
git push <remote> <branch>
```

Trong đó:
- **`<remote>`**: Tên của remote mà bạn đã cấu hình để kết nối với repo GitHub (thường là `origin`).
- **`<branch>`**: Tên nhánh mà bạn muốn đẩy lên (ví dụ: `master` hoặc `main`).

---

### Đẩy Nhánh Chính (Master/Main) Lên GitHub

Giả sử bạn đã thực hiện xong các bước tạo và kết nối repo GitHub, và bạn muốn đẩy nhánh chính (trong ví dụ này là `master`) lên GitHub. Thao tác như sau:

1. **Kiểm tra remote hiện tại**  
   Sử dụng lệnh sau để kiểm tra remote:
   ```bash
   git remote -v
   ```
   Kết quả sẽ hiển thị URL của repo GitHub mà bạn đã kết nối, xác nhận rằng repo cục bộ đã biết về repo GitHub này.

2. **Kiểm tra nhánh hiện tại và xác nhận các thay đổi đã commit**  
   Đảm bảo rằng bạn đang ở nhánh muốn đẩy lên (trong ví dụ là `master`) và tất cả các thay đổi đã được commit.

3. **Đẩy nhánh `master` lên GitHub**  
   Sử dụng lệnh:
   ```bash
   git push origin master
   ```
   Trong lệnh này:
   - `origin` là remote mà bạn đã thêm ở phần trước, liên kết với repo GitHub.
   - `master` là nhánh mà bạn đang đẩy lên GitHub.

4. **Kiểm tra trên GitHub**  
   Sau khi lệnh `git push` chạy xong, bạn có thể truy cập vào repo trên GitHub và làm mới trang để xem mã nguồn đã được đẩy lên hay chưa.

---

### Đẩy Nhiều Nhánh Lên GitHub

Giả sử bạn đã làm việc trên một nhánh phụ (ví dụ: `new-feature`) và muốn đẩy nhánh đó lên GitHub. Cách làm tương tự như khi đẩy nhánh `master`:

1. **Tạo và chuyển sang nhánh phụ**  
   ```bash
   git switch -c new-feature
   ```
   Thao tác này tạo nhánh `new-feature` và chuyển bạn sang nhánh đó.

2. **Thực hiện các thay đổi trên nhánh `new-feature` và commit chúng**  
   Ví dụ:
   ```bash
   echo "Some new feature" > feature.txt
   git add feature.txt
   git commit -m "Add new feature"
   ```

3. **Đẩy nhánh `new-feature` lên GitHub**  
   ```bash
   git push origin new-feature
   ```
   Lệnh này sẽ đẩy nhánh `new-feature` cùng với các commit mới lên GitHub.

4. **Xem lại nhánh trên GitHub**  
   Khi vào trang repo trên GitHub, bạn sẽ thấy nhánh `new-feature` mới được thêm vào cùng với các thay đổi mà bạn đã thực hiện.

---

### Tại Sao Cần Chỉ Rõ Remote và Nhánh Khi Đẩy?

Khi làm việc với Git, bạn có thể có nhiều remote và nhiều nhánh khác nhau trong repo của mình. Ví dụ, bạn có thể có các remote sau:
- `origin`: Liên kết đến repo GitHub chính.
- `backup`: Liên kết đến một server khác để sao lưu.

Bằng cách chỉ rõ remote và nhánh khi đẩy, bạn đảm bảo rằng các thay đổi được gửi đến đúng repo và nhánh mà bạn mong muốn, tránh việc đẩy nhầm dữ liệu.

---

### Mẹo Khi Đẩy Code

- **Đảm bảo mọi thay đổi đã được commit**: Chỉ các commit mới sẽ được đẩy lên GitHub. Các thay đổi chưa được commit sẽ không được gửi đi.
- **Xác thực SSH**: Để tránh việc phải nhập mật khẩu mỗi lần đẩy mã nguồn, hãy cấu hình SSH như đã hướng dẫn trong phần trước.
- **Giữ nhánh chính cập nhật**: Khi làm việc nhóm, các thành viên thường sẽ cập nhật mã nguồn trên nhánh chính (`master` hoặc `main`). Luôn đẩy các thay đổi quan trọng lên nhánh này và tạo nhánh mới để phát triển tính năng.

---

### Tóm Tắt

1. Sử dụng `git push <remote> <branch>` để đẩy mã nguồn lên GitHub.
2. `origin` là tên remote tiêu chuẩn kết nối đến repo GitHub, `master` hoặc `main` là nhánh chính thường đẩy lên GitHub.
3. Có thể đẩy nhiều nhánh lên GitHub, giúp quản lý và phát triển tính năng dễ dàng hơn.
  
Sau khi thực hiện các bước này, repo GitHub của bạn sẽ có đầy đủ mã nguồn từ repo cục bộ, giúp bạn sao lưu và chia sẻ mã nguồn một cách thuận tiện.
