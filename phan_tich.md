### **1\. Phân tích lỗi tư duy của Nam**

* **Sai lầm 1: Dùng Rich Text (.docx) cho quản lý mã nguồn (Git Version Control)**  
  * *Bản chất:* File `.docx` thực chất là một gói nén ZIP chứa cấu trúc mã XML phức tạp (Binary/Rich Text). Git không thể đọc và so sánh theo từng dòng (`line-by-line diff`). Khi hai người cùng sửa, Git chỉ thấy file nhị phân thay đổi toàn bộ, gây ra xung đột (Conflict) nặng nề. Hơn nữa, GitHub không thể render file Word trực tiếp trên trình duyệt như Markdown.  
* **Sai lầm 2: Chủ quan về độ an toàn và dung lượng lưu trữ**  
  * *Bản chất:* File Rich Text nặng hơn nhiều và cực kỳ dễ hỏng cấu trúc. Nếu file Word bị mất hoặc lệch dù chỉ 1 byte do lỗi đường truyền mạng khi tải lên GitHub, toàn bộ tệp sẽ bị hỏng hoàn toàn (không thể mở được). Ngược lại, Markdown là **Plain Text**, siêu nhẹ, dễ đọc, và nếu bị lỗi mạng mất 1 byte thì chỉ mất đúng ký tự đó, các phần còn lại hoàn toàn giữ nguyên vẹn.

  