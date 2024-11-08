### Hiểu Về Commit trong Git

Commit trong Git là một đối tượng (object) quan trọng nhất, đóng vai trò ghi lại trạng thái của dự án tại một thời điểm nhất định. Mỗi commit chứa tham chiếu tới một **tree** (đại diện cho cấu trúc thư mục và nội dung file tại thời điểm đó) và thường là tham chiếu tới commit cha của nó, tạo thành một **chuỗi lịch sử** của dự án.

---

#### **1. Cấu Trúc Của Commit**

Mỗi commit trong Git chứa:

- **Tree**: Tham chiếu tới một đối tượng tree, là ảnh chụp nhanh của toàn bộ cấu trúc thư mục và file.
- **Parent (Cha)**: Tham chiếu tới commit trước đó. Mỗi commit lưu trữ mã băm SHA-1 của commit cha, tạo thành một chuỗi các commit.
- **Thông tin tác giả và ngày tháng**: Bao gồm tên tác giả, email, và thời gian commit.
- **Thông điệp commit**: Mô tả ngắn gọn về các thay đổi.

---

#### **2. Commit Và Cách Git Lưu Trữ Thông Tin**

Khi bạn thực hiện lệnh `git commit`, Git tạo một commit mới, lưu trữ thông tin như sau:

- **Mã băm**: Commit mới sẽ có mã băm SHA-1 duy nhất dựa trên toàn bộ nội dung commit.
- **Cấu trúc thư mục**: Commit chứa tham chiếu tới một tree, đại diện cho snapshot của toàn bộ dự án tại thời điểm đó.
- **Lịch sử**: Nếu commit không phải là commit đầu tiên, nó sẽ tham chiếu tới commit cha, tạo thành một chuỗi commit.

---

#### **3. Sử Dụng `git cat-file` Để Kiểm Tra Commit**

Bạn có thể kiểm tra nội dung của một commit bằng lệnh `git cat-file`:

```bash
git cat-file -p <commit_hash>
```

**Ví dụ**: 

```bash
git cat-file -p 79DD6
```

Kết quả sẽ hiển thị nội dung chi tiết của commit, bao gồm tham chiếu tới **tree**, commit cha (nếu có), thông tin tác giả, và thông điệp commit.

---

#### **4. Commit, Tree, Và Blob**

Sơ đồ cấu trúc commit trong Git:

- **Commit**:
  - Tham chiếu tới **tree** (ảnh chụp của toàn bộ cấu trúc thư mục).
  - Tham chiếu tới **commit cha** để duy trì lịch sử.
- **Tree**:
  - Chứa các blob (nội dung file) và các tree khác (thư mục con).
  - Mỗi file trong tree có tên file và mã hash của blob.
- **Blob**:
  - Chỉ lưu trữ nội dung của file, không bao gồm tên file.

---

#### **5. Hoạt Động Của Commit Trong Git**

Khi chuyển nhánh hoặc kiểm tra một commit cụ thể, Git sử dụng:

- **Tree của commit**: Để khôi phục cấu trúc thư mục và nội dung file.
- **Blob**: Để tái tạo nội dung của từng file.

Git có thể khôi phục trạng thái dự án tại bất kỳ thời điểm nào bằng cách lấy **tree** từ commit và sử dụng các blob trong tree đó.

---

#### **6. Tóm Tắt**

Commit trong Git lưu trữ trạng thái của dự án, bao gồm cấu trúc thư mục và nội dung file. Mỗi commit chứa:

- Tham chiếu tới một tree (cấu trúc thư mục).
- Tham chiếu tới commit cha.
- Thông tin tác giả và thông điệp commit.

Commit cùng với tree và blob là nền tảng của Git, giúp Git quản lý phiên bản và lịch sử thay đổi.
