### Hướng Dẫn Đẩy Git Tags Lên Remote Repository

Khi làm việc với Git, việc đẩy các tag lên remote không tự động diễn ra khi bạn push như bình thường. Bạn cần chỉ định rõ ràng nếu muốn đẩy tag lên remote. Có hai cách để đẩy tag lên remote: đẩy từng tag hoặc đẩy tất cả các tag mới cùng một lúc. Dưới đây là hướng dẫn chi tiết.

---

#### **1. Mặc Định Khi Push Không Bao Gồm Tag**

Khi bạn chạy lệnh `git push` để đẩy thay đổi lên remote, các tag sẽ không được đẩy lên theo mặc định. Nếu muốn đẩy tag, bạn phải chỉ định rõ ràng.

---

#### **2. Cách Đẩy Một Tag Cụ Thể**

Nếu bạn muốn đẩy một tag riêng lẻ lên remote, bạn có thể sử dụng lệnh sau:

```bash
git push <tên_remote> <tên_tag>
```

**Ví dụ:**

Giả sử bạn có một tag tên là `mytag` và muốn đẩy nó lên remote tên là `origin`:

```bash
git push origin mytag
```

Lệnh này sẽ đẩy tag `mytag` lên remote `origin`. Tag sẽ xuất hiện trên GitHub hoặc dịch vụ Git khác mà bạn đang sử dụng.

---

#### **3. Cách Đẩy Tất Cả Các Tag Lên Remote**

Để đẩy tất cả các tag mới mà bạn đã tạo trong repository, bạn có thể sử dụng tùy chọn `--tags`.

```bash
git push <tên_remote> --tags
```

**Ví dụ:**

Nếu bạn muốn đẩy tất cả các tag lên remote tên là `origin`:

```bash
git push origin --tags
```

Lệnh này sẽ đẩy toàn bộ các tag trong repository của bạn lên remote `origin`.

---

#### **4. Tạo và Thiết Lập Remote Khác (Ví Dụ)**

Trong một số trường hợp, nếu bạn cần đẩy nội dung đến một remote mới, bạn có thể thiết lập một remote khác.

**Bước 1:** Thêm remote mới với tên `my_remote`:

```bash
git remote add my_remote <URL_repo_mới>
```

**Bước 2:** Đẩy lên remote mới `my_remote` với nhánh `master`:

```bash
git push my_remote master
```

**Bước 3:** Đẩy tất cả các tag lên remote mới `my_remote`:

```bash
git push my_remote --tags
```

---

#### **5. Kết Luận**

- **Mặc định**, Git không đẩy tag khi bạn push thay đổi. Bạn phải chỉ định rõ ràng tag cần đẩy.
- **Đẩy từng tag**: Sử dụng lệnh `git push <tên_remote> <tên_tag>` nếu bạn chỉ muốn đẩy một tag cụ thể.
- **Đẩy tất cả tag**: Sử dụng `--tags` nếu bạn muốn đẩy tất cả các tag mới.

Việc đẩy tag lên remote giúp đảm bảo rằng các phiên bản và mốc quan trọng của dự án được lưu trữ và chia sẻ đầy đủ với các thành viên khác. Tags là một công cụ mạnh mẽ và thường được sử dụng nhiều trong các dự án lớn và mã nguồn mở, đặc biệt khi kết hợp với Semantic Versioning.
