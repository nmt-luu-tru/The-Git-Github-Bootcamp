### Giới Thiệu Về Tree Trong Git

Trong Git, **tree** là một loại đối tượng đại diện cho **cấu trúc thư mục**. Nếu như blob lưu trữ nội dung của file mà không có tên file, thì tree giúp Git quản lý mối quan hệ giữa các file và thư mục, cũng như lưu trữ cấu trúc thư mục của một dự án.

---

#### **1. Tree Là Gì?**

Tree trong Git đại diện cho một thư mục và chứa các **tham chiếu** tới các blob (nội dung của file) và các tree khác (các thư mục con):

- **Blob**: Chứa nội dung của file.
- **Tree**: Chứa cấu trúc thư mục, liên kết các blob với tên file và các thư mục con khác.
  
**Ví dụ**: Nếu bạn có một thư mục với file `app.js`, Git sẽ có một tree đại diện cho thư mục này, với một tham chiếu đến blob của `app.js`.

---

#### **2. Cấu Trúc Của Tree**

Mỗi tree chứa danh sách các mục, mỗi mục bao gồm:

- **Loại**: Cho biết mục đó là blob (file) hay tree (thư mục con).
- **Hash**: Mã băm SHA-1 của blob hoặc tree.
- **Tên**: Tên của file hoặc thư mục.

**Ví dụ**:

Giả sử cấu trúc thư mục như sau:

```
project/
├── index.html
├── main.js
└── styles/
    ├── app.css
    └── nav.css
```

- **Tree của `project`**:
   - Gồm hai blob (đại diện cho `index.html` và `main.js`) và một tree (đại diện cho thư mục `styles`).
   - Mỗi mục được liên kết với mã hash SHA-1 của blob hoặc tree và tên của chúng.
  
---

#### **3. Tạo Tree Trong Git**

Khi bạn tạo commit, Git tự động tạo ra các tree dựa trên cấu trúc thư mục tại thời điểm commit. Các tree này không lưu trữ nội dung của file trực tiếp mà chỉ lưu trữ các tham chiếu đến blob chứa nội dung file.

---

#### **4. Truy Xuất Tree Bằng Lệnh `git cat-file`**

Bạn có thể sử dụng `git cat-file` để xem nội dung của một tree trong repository:

```bash
git cat-file -p <hash>
```

**Ví dụ**:

- **Xem Tree của Commit Gần Nhất**:

   ```bash
   git cat-file -p master^{tree}
   ```

   - Lệnh này in ra cấu trúc tree của commit mới nhất trên nhánh `master`.
   - Bạn sẽ thấy tên các file và thư mục con, kèm theo mã hash và loại (blob hoặc tree).

- **Xem Loại Đối Tượng**:

   Nếu muốn kiểm tra một hash là blob hay tree, bạn có thể sử dụng:

   ```bash
   git cat-file -t <hash>
   ```

   - **-t**: Cho biết loại đối tượng Git (blob, tree, commit).
  
---

#### **5. Tóm Tắt**

Tree trong Git là đối tượng giúp Git quản lý cấu trúc thư mục và liên kết giữa các file và thư mục con. Bằng cách sử dụng tree, Git có thể duy trì cấu trúc và theo dõi các thay đổi trong thư mục một cách hiệu quả. Tree không lưu trữ nội dung file mà chỉ chứa các tham chiếu đến blob và các tree khác.
