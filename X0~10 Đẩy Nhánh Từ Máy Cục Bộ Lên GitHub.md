Để làm rõ mối quan hệ giữa các nhánh trên máy cục bộ của bạn và các nhánh trên GitHub, dưới đây là hướng dẫn chi tiết về cách đẩy (push) nhánh từ máy cục bộ lên GitHub, với một số tình huống có thể gặp khi làm việc với nhiều nhánh.

---

### Khởi Tạo và Kết Nối Kho Lưu Trữ (Repo) Mới

1. **Tạo Repo Mới trên GitHub**:
   - Đầu tiên, tạo một repo mới trên GitHub, đặt tên, ví dụ là `pushme`.
   - Sao chép URL kết nối với repo vừa tạo.

2. **Khởi Tạo Repo Cục Bộ**:
   - Trên máy tính của bạn, dùng lệnh `git init` để tạo một repo Git trống.
   - Tạo một file mới và commit nó:
     ```bash
     touch candy.txt
     git add .
     git commit -m "create candy file"
     ```

3. **Thêm Remote**:
   - Thêm URL của GitHub repo đã tạo vào repo cục bộ bằng lệnh:
     ```bash
     git remote add origin <URL_GitHub_repo>
     ```
   - Bây giờ, repo của bạn đã biết về GitHub repo qua `origin`.

---

### Đẩy Nhánh Từ Máy Cục Bộ Lên GitHub

4. **Đẩy Nhánh Lên GitHub**:
   - Giả sử nhánh cục bộ là `master`, bạn có thể đẩy nhánh này lên nhánh `master` trên GitHub:
     ```bash
     git push origin master
     ```
   - Nếu trên GitHub chưa có nhánh `master`, lệnh này sẽ tự động tạo nhánh `master` trên GitHub và liên kết nó với nhánh `master` trên máy bạn.

5. **Cập Nhật Thay Đổi Trên Cùng Một Nhánh**:
   - Nếu thực hiện thay đổi trên nhánh `master`, ví dụ thêm file `flowers.txt`:
     ```bash
     touch flowers.txt
     git add .
     git commit -m "create flowers file"
     git push origin master
     ```
   - Thao tác này sẽ cập nhật nhánh `master` trên GitHub với thay đổi mới từ nhánh `master` của máy bạn.

---

### Đẩy Nhánh Cục Bộ Lên Nhánh Khác trên GitHub

6. **Đẩy Nhánh Cục Bộ Lên Nhánh Khác trên GitHub**:
   - Giả sử bạn tạo một nhánh mới tên `cats`:
     ```bash
     git switch -c cats
     touch cats.txt
     git add .
     git commit -m "create cats file"
     ```
   - Khi bạn đẩy nhánh `cats` lên GitHub, Git sẽ tạo một nhánh `cats` mới trên GitHub:
     ```bash
     git push origin cats
     ```
   - Nếu muốn đẩy nhánh `cats` cục bộ lên nhánh `master` trên GitHub (không phổ biến nhưng có thể thực hiện):
     ```bash
     git push origin cats:master
     ```
   - Lệnh trên sẽ lấy nội dung của nhánh `cats` trên máy cục bộ và cập nhật nhánh `master` trên GitHub với nội dung từ nhánh này.

### Kết Luận

- **Liên Kết Các Nhánh**: Thông thường, bạn sẽ đẩy nhánh `master` cục bộ lên nhánh `master` trên GitHub, và nhánh `cats` lên nhánh `cats`, giúp giữ sự nhất quán giữa cục bộ và GitHub.
- **Đẩy Các Nhánh Khác Nhau**: Bạn có thể đẩy bất kỳ nhánh nào của cục bộ lên nhánh bất kỳ trên GitHub, nhưng hãy chắc chắn rằng bạn hiểu rõ về các nhánh để tránh nhầm lẫn.
- **Thực Hành và Kiểm Tra**: Hãy thực hành tạo và đẩy các nhánh để hiểu rõ hơn về cách chúng hoạt động và mối quan hệ giữa các nhánh cục bộ và nhánh GitHub.

Hy vọng rằng điều này giúp bạn hiểu rõ hơn về quy trình đẩy nhánh và cách quản lý các nhánh giữa cục bộ và GitHub.
