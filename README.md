<h1 align="center">Hệ Thống Tư Vấn Mua Laptop (AHP & AI) 💻</h1>

<p align="center">
  Một ứng dụng web thông minh giúp người dùng lựa chọn laptop phù hợp nhất dựa trên thuật toán <strong>Analytic Hierarchy Process (AHP)</strong> kết hợp với <strong>Trí tuệ Nhân tạo (AI)</strong>.
</p>

## ✨ Tính Năng Nổi Bật

- **Tư vấn thông minh:** Sử dụng thuật toán phân tích đa tiêu chí AHP (Giá cả, Cấu hình, Nhu cầu di chuyển, Gaming...) để tìm ra laptop tốt nhất.
- **Chấm điểm AI:** Tích hợp mô hình AI để đánh giá độ phù hợp của từng chiếc laptop với nhu cầu cá nhân hóa của người dùng.
- **Giao diện hiện đại:** Trải nghiệm người dùng mượt mà, trực quan, tốc độ phản hồi nhanh.
- **Hệ thống Quản trị (Admin):** API đầy đủ chức năng quản lý Laptop, Thương hiệu, tính năng và hỗ trợ nạp dữ liệu hàng loạt từ file Excel.

## 🛠 Công Nghệ Sử Dụng

**Frontend (Giao Diện):**
- React / JavaScript (Vite)
- Tailwind CSS
- Axios xử lý API
- 🌐 Deploy tự động trên **Vercel**

**Backend (Hệ Thống & AI):**
- Python 3 / Flask
- SQLAlchemy ORM
- Thuật toán AHP, Machine Learning (Numpy, Pandas, Scikit-Learn)
- 🌐 Deploy trên **Render**

**Cơ Sở Dữ Liệu:**
- PostgreSQL
- 🌐 Cloud Database tại **Neon.tech**

## 📂 Cấu Trúc Dự Án

- `laptop-frontend/`: Toàn bộ mã nguồn giao diện người dùng.
- `laptop_be/`: Mã nguồn Backend API & xử lý các thuật toán lõi.
- `DB.sql`: Script khởi tạo các bảng cơ sở dữ liệu.
- `*.docx`: Các file tài liệu mô tả Chức năng API, Luồng xử lý, và cơ chế Train AI.

## 🚀 Live Demo (Đang Hoạt Động)

Hệ thống hoàn chỉnh hiện đang được đưa lên nền tảng Cloud:
- **Frontend (Giao diện người dùng):** 🔗 [https://analytic-hierarchy-process-one.vercel.app/](https://analytic-hierarchy-process-one.vercel.app/)
- **Backend (API Endpoint):** 🔗 [https://laptop-db.onrender.com](https://laptop-db.onrender.com)

## 💻 Hướng Dẫn Cài Đặt (Chạy Local)

### 1. Cài đặt Backend
```bash
cd laptop_be
python -m venv .venv

# Kích hoạt môi trường ảo (Windows)
.\.venv\Scripts\activate

# Cài đặt thư viện
pip install -r requirements.txt
```
Tạo file `.env` để cấu hình chuỗi kết nối Database `DATABASE_URL` và khởi tạo CSDL:
```bash
python init_db.py
python import_db.py

# Khởi chạy server
flask run
```

### 2. Cài đặt Frontend
Mở một terminal mới:
```bash
cd laptop-frontend
npm install

# Khởi chạy giao diện
npm run dev
```

---
<p align="center">
  <i>Được phát triển và đóng góp bởi nhóm phát triển tài năng! 🚀</i>
</p>
