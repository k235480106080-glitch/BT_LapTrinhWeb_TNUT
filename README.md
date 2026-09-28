# BÀI TẬP VỀ NHÀ MÔN LẬP TRÌNH WEB - TNUT

## Thông tin sinh viên
* **Họ và tên**: Trần Hoàng Xuân Vũ
* **Mã sinh viên**: K235480106080
* **Lớp**: K59KMT - Kĩ thuật máy tính

## Danh sách đầy đủ đường link (Public Domain & GitHub Repo)
* **GitHub Repository**: https://github.com/k235480106080-glitch/BT_LapTrinhWeb_TNUT
* **Website 1 (Gọi API Node-RED)**: http://site1.hoangvu057.id.vn
* **Website 2 (Trang thứ hai)**: http://site2.hoangvu057.id.vn
* **Quản trị CSDL (phpMyAdmin)**: http://pma.hoangvu057.id.vn

## Báo cáo minh chứng kết quả thực hiện

### 1. Trạng thái 5 Docker Container
![Docker Status](./images/01_docker_status.png)

### 2. Website 1 - Gọi API Node-RED (http://site1.hoangvu057.id.vn)
![Website 1 API](./images/02_site1_api.png)

### 3. Website 2 - Trang độc lập (http://site2.hoangvu057.id.vn)
![Website 2](./images/03_site2_web.png)

### 4. Quản trị Database phpMyAdmin (http://pma.hoangvu057.id.vn)
![phpMyAdmin](./images/04_phpmyadmin.png)


---

# 📌 MỤC 6. LÝ THUYẾT VÀ THỰC NGHIỆM XÂY DỰNG API BẰNG NODE-RED

## 6.1. KHÁI NIỆM VÀ CƠ CHẾ HOẠT ĐỘNG CỦA NODE-RED

### A. Khái niệm chung
* **Node-RED** là một công cụ lập trình trực quan dựa trên luồng (**Flow-based Programming - FBP**) được phát triển trên nền tảng **Node.js**.
* Cho phép kết nối các thiết bị phần cứng, các điểm cuối API (**Endpoints**) và các dịch vụ trực tuyến thông qua việc kéo-thả các khối chức năng (**Nodes**) và nối chúng lại với nhau (**Wires**).

### B. Cơ chế xử lý bất đồng bộ (Event-Driven)
* Tận dụng cơ chế **Non-blocking I/O** của Node.js giúp xử lý hàng nghìn yêu cầu HTTP đồng thời với hiệu năng cao và độ trễ cực thấp.
* Mọi dữ liệu luân chuyển giữa các Node được đóng gói trong một đối tượng JavaScript chuẩn gọi là **** (Message Object). Trong đó:
  * ****: Chứa nội dung dữ liệu chính (JSON, String, Buffer, Array).
  * ****: Chứa các thông tin Header của yêu cầu HTTP (Content-Type, User-Agent,...).

---

## 6.2. KIẾN TRÚC LUỒNG XỬ LÝ RESTFUL API (FLOW ARCHITECTURE)

Dịch vụ Node-RED được triển khai trong môi trường **Docker Container** (Port ), đứng sau mã nguồn **Nginx Reverse Proxy** để xử lý các yêu cầu từ Web Client.

### 📊 Bảng mô tả chi tiết các Node trong luồng API:

| TÊN NODE | THỂ LOẠI NODE | CHỨC NĂNG VÀ QUY TRÌNH XỬ LÝ LÝ THUYẾT |
| :--- | :--- | :--- |
| **** |  | Lắng nghe các HTTP Request gửi đến theo phương thức  tại tuyến đường . |
| **** |  | Sử dụng JavaScript mã hóa mảng dữ liệu JSON chứa thông tin Sinh viên TNUT (Mã SV, Họ tên, Điểm TB, Xếp loại). |
| **** |  | Thiết lập Header  và phản hồi dữ liệu về Client với mã . |

---

## 6.3. MINH CHỨNG KẾT QUẢ THỰC NGHIỆM NODE-RED

### 📸 Ảnh 1: Sơ đồ luồng (Flow Editor) cấu hình RESTful API trên giao diện Node-RED:

### 📸 Ảnh 2: Giao diện Website 1 gọi API Node-RED và hiển thị danh sách sinh viên TNUT:
