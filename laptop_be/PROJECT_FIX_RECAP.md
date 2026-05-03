# TỔNG KẾT QUÁ TRÌNH SỬA LỖI DỰ ÁN SHOP LAPTOP AHP-AI

## 1. Các lỗi nghiêm trọng trong file hướng dẫn cũ (`Đọc tôi.txt`)
*   **Sai tên thư mục môi trường ảo:** Hướng dẫn cũ yêu cầu chạy `python -m venv .env`. 
    *   *Hậu quả:* `.env` là file cấu hình hệ thống, việc đặt trùng tên thư mục khiến việc quản lý biến môi trường bị lỗi hoàn toàn.
    *   *Khắc phục:* Đổi tên thư mục môi trường ảo thành `.venv`.
*   **Thiếu thư viện cài đặt:** File cũ không nhắc đến `flask-cors` và `requests`.
    *   *Hậu quả:* Backend bị sập ngay khi vừa khởi động (ModuleNotFoundError).
*   **Thiếu bước nạp dữ liệu Admin:** Hướng dẫn cũ không giải thích cơ chế bảo mật Bearer Token.
    *   *Hậu quả:* Người dùng không thể nạp dữ liệu từ Excel vì bị chặn bởi lớp bảo mật Admin.
*   **Cấu hình Database không rõ ràng:** Không nhắc đến việc phải tạo database tên `T2C1` dẫn đến lỗi kết nối SQL.

## 2. Các hạng mục đã được Fix (Recap)

### A. Hạ tầng & Kết nối
1.  **Sửa lỗi Database Name:** Phát hiện database bị đặt tên nhầm thành `'T2C1 '` (thừa dấu cách). Đã thực hiện đổi tên về chuẩn `'T2C1'`.
2.  **Cấu hình .env:** Cập nhật file `.env` chuẩn để kết nối đồng bộ giữa Backend và PostgreSQL.
3.  **Bảo mật:** Tạo thành công tài khoản Admin (`admin@gmail.com`) để phục vụ việc nạp và quản lý dữ liệu.

### B. Xử lý Dữ liệu (Backend)
1.  **Vượt rào nạp dữ liệu:** Xử lý thành công việc nạp file Excel qua API (vốn bị lỗi Content-Type: None trên Postman).
2.  **Sửa lỗi Procedure SQL:** Sửa lại thủ tục `sp_import_laptop_data` để xử lý các dòng dữ liệu trùng lặp trong Excel (tránh lỗi CardinalityViolation).
3.  **Chuẩn hóa dữ liệu:**
    *   Tự động nạp danh sách Hãng (Brands) từ Excel.
    *   Tự động quy đổi giá từ Euro sang VNĐ (x25.000) để bộ lọc trên web hoạt động chính xác.

### C. Giao diện (Frontend)
1.  **Cài đặt & Khởi chạy:** Thực hiện `npm install` và cấu hình server Vite chạy ở cổng `5173`.
2.  **Kết nối API:** Đảm bảo Frontend gọi đúng các endpoint `/api/form-options` và `/api/recommendations/run`.

## 3. Trạng thái hiện tại
*   **Database:** Đầy đủ 662 laptop, 19 hãng sản xuất.
*   **Backend:** Đang chạy ổn định tại cổng 5000.
*   **Frontend:** Đang chạy ổn định tại cổng 5173.

---
*Tổng kết bởi Antigravity AI - 25/04/2026*
