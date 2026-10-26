# 📱 Hệ Thống Điểm Danh Sinh Viên Bằng Mã QR (Student Attendance Management System)

> Dự án thuộc khuôn khổ học phần Kiến trúc Hướng Dịch Vụ (SOA) / Đồ án môn học.

## 🌟 Tổng Quan Dự Án
Hệ thống hỗ trợ giảng viên tạo mã QR động cho từng buổi học, sinh viên dùng điện thoại thông minh quét mã QR để thực hiện điểm danh nhanh chóng, chống gian lận vị trí/thời gian và tự động đồng bộ dữ liệu về hệ thống tập trung.

---

## 🛠️ Công Nghệ Sử Dụng (Tech Stack)
* **Backend:** Node.js, Express, thư viện `qrcode` (Tạo và giải mã QR).
* **Frontend/Client (Dự kiến):** Web App / Mobile App quét mã QR.
* **Database / Store:** In-Memory Storage (`Map`, `Set`) mô phỏng luồng dữ liệu hoặc Database quan hệ.

---

## 🚀 Các Tính Năng Chính (Planned Features)
1. **Tạo QR Buổi Học (Generate QR):** Giảng viên tạo mã QR tương ứng với `classId`, `sessionId`, kèm thời gian sống (TTL) của mã.
2. **Quét & Xác Thực (Verify & Check-in):** Sinh viên dùng điện thoại quét mã $\rightarrow$ Gửi Payload lên Server $\rightarrow$ Server đối chiếu dữ liệu gốc, chống giả mạo (`Anti-tampering`) và ghi nhận trạng thái `checkedIn`.
3. **Quản Lý Lịch Sử (Logs & Reports):** Xuất danh sách sinh viên đã điểm danh theo thời gian thực.

---

## 📂 Cấu Trúc Thư Mục Dự Kiến
```text
student-attendance-qr/
│
├── backend/            # Chứa API Service (Node.js/Express)
│   ├── src/
│   │   ├── controllers/
│   │   ├── routes/
│   │   ├── services/
│   │   └── config/
│   └── server.js
│
├── docs/               # Tài liệu thiết kế, sơ đồ luồng (Sequence Diagram)
└── README.md