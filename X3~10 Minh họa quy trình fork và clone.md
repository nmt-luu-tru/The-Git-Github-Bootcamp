
Trong video này, tôi sẽ minh họa quy trình fork và clone, cho thấy cách thức làm việc với các kho lưu trữ trên GitHub. Khi bạn fork một kho lưu trữ, bạn sẽ có một bản sao của nó trên tài khoản GitHub của mình, cho phép bạn thực hiện các thay đổi mà không ảnh hưởng đến kho lưu trữ gốc.

#### **1. Khái Niệm Forking**

- **Fork**: Khi bạn fork một kho lưu trữ, GitHub sẽ tạo một bản sao của kho lưu trữ đó trong tài khoản của bạn. Điều này cho phép bạn có quyền truy cập đầy đủ để thực hiện các thay đổi, thêm cộng tác viên và xóa nhánh mà không làm ảnh hưởng đến kho lưu trữ gốc.

#### **2. Quy Trình Fork và Clone**

1. **Fork Kho Lưu Trữ**:
   - Tôi sẽ bắt đầu với kho lưu trữ 2048, một trò chơi HTML đơn giản. Tôi nhấn vào nút **Fork** trên GitHub để tạo bản sao của kho lưu trữ này trong tài khoản của mình.

2. **Cloning**:
   - Sau khi fork xong, tôi có thể sao chép URL của kho lưu trữ forked và sử dụng lệnh `git clone` để sao chép kho lưu trữ đó về máy tính của mình. 
   - ```bash
     git clone <URL>
     ```

3. **Thực Hiện Thay Đổi**:
   - Tôi có thể thực hiện các thay đổi trong mã nguồn mà không làm ảnh hưởng đến kho lưu trữ gốc. Ví dụ, tôi có thể thay đổi tiêu đề trang hoặc các thuộc tính CSS.

4. **Commit Thay Đổi**:
   - Sau khi thực hiện các thay đổi, tôi thêm các tệp đã thay đổi vào giai đoạn commit và thực hiện commit.
   - ```bash
     git add .
     git commit -m "Thay đổi màu sắc giao diện"
     ```

5. **Push Lên GitHub**:
   - Cuối cùng, tôi có thể đẩy những thay đổi của mình lên kho lưu trữ forked.
   - ```bash
     git push origin master
     ```

#### **3. Lợi Ích của Forking**

- **Tự Do Thực Hiện Thay Đổi**: Bạn có thể thực hiện bất kỳ thay đổi nào mà không lo lắng về việc làm hỏng kho lưu trữ gốc.
- **Cộng Tác Với Người Khác**: Bạn có thể thêm các cộng tác viên vào kho lưu trữ forked của mình để làm việc cùng nhau.

#### **4. Kết Luận**

Quy trình fork và clone rất quan trọng trong việc phát triển phần mềm, đặc biệt là trong các dự án mã nguồn mở. Nó cho phép các lập trình viên thử nghiệm và thực hiện các thay đổi mà không cần quyền truy cập trực tiếp vào kho lưu trữ gốc. Trong video tiếp theo, tôi sẽ nói về cách sử dụng quy trình này để đóng góp vào các dự án mã nguồn mở hoặc làm việc cùng nhau trong một nhóm.
