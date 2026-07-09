---
title : "Demo Workshop & Video"
date : "2025-10-10"
weight : 4
chapter : false
pre : " <b> 5.4 </b> "
---
# 5.4. Demo Workshop & Video

---

## Demo Trực Tiếp

**Trải nghiệm Cloud Nexus ngay:** [https://d3rs3evkmfvesp.cloudfront.net/](https://d3rs3evkmfvesp.cloudfront.net/)

![Cloud Nexus Demo Trực Tiếp](https://d3rs3evkmfvesp.cloudfront.net/)

---

## Video Demo

> **Video Demo:** [Cloud Nexus Workshop Demo Video](youtube.com/watch?v=j0-aYoJ2xpY&feature=youtu.be)

*Video trình diễn đầy đủ nền tảng Cloud Nexus bao gồm:*
- *Tạo network topology*
- *Quét lỗ hổng bảo mật bằng AI*
- *Mô phỏng đường đi tấn công*
- *Khuyến nghị phòng thủ*

---

## Các Tính Năng Demo

### Tính Năng 1: Trình Chỉnh Sửa Topology Trực Quan

Trình chỉnh sửa dựa trên ReactFlow cho phép người dùng kéo và thả các thành phần mạng lên canvas.

**Các bước demo:**
1. Mở ứng dụng tại [https://d3rs3evkmfvesp.cloudfront.net/](https://d3rs3evkmfvesp.cloudfront.net/)
2. Chọn loại node từ panel bên trái (Server, Database, Firewall, v.v.)
3. Kéo và thả lên canvas
4. Kết nối các node bằng cách kéo từ handle này sang handle khác

**Kết quả mong đợi:** Các node xuất hiện trên canvas với các cạnh kết nối

---

### Tính Năng 2: Tạo Topology Bằng AI

Gõ lệnh trong terminal để tạo network topology bằng AI.

**Các bước demo:**
1. Click vào panel terminal
2. Gõ: `generate a secure web application with load balancer`
3. Nhấn Enter
4. Quan sát AI tạo topology

**Kết quả mong đợi:** Các node mạng và edges xuất hiện tự động trên canvas

---

### Tính Năng 3: Quét Lỗ Hổng Bảo Mật

Quét topology hiện tại để tìm các lỗ hổng bảo mật tiềm ẩn.

**Các bước demo:**
1. Tạo hoặc tạo một network topology
2. Gõ: `scan` trong terminal
3. Xem panel attack scenarios

**Kết quả mong đợi:** Danh sách các kịch bản tấn công tiềm năng với mức độ nghiêm trọng

---

### Tính Năng 4: Mô Phỏng Tấn Công

Mô phỏng các đường đi tấn công và xem chúng được hiển thị trên canvas.

**Các bước demo:**
1. Chạy vulnerability scan trước
2. Chọn một attack scenario từ panel
3. Click "Simulate Attack"
4. Quan sát đường đi tấn công hoạt hình

**Kết quả mong đợi:** Đường đi tấn công hoạt hình highlight tuyến đường từ attacker đến target

---

### Tính Năng 5: Khuyến Nghị Phòng Thủ

Nhận khuyến nghị từ AI để bảo mật mạng.

**Các bước demo:**
1. Sau khi mô phỏng, xem các khuyến nghị
2. Thêm các defense node (Firewall, WAF, IDS) vào topology
3. Chạy mô phỏng lại để thấy bảo mật cải thiện

**Kết quả mong đợi:** Các đường đi tấn công bị chặn hoặc giảm thiểu bởi các defense node

---

## Hướng Dẫn Chụp Ảnh Xác Minh

📸 **Ảnh 1: Giao Diện Ứng Dụng Đầy Đủ**

**Cách chụp:**
1. Mở [https://d3rs3evkmfvesp.cloudfront.net/](https://d3rs3evkmfvesp.cloudfront.net/)
2. Đợi page load hoàn toàn
3. Chụp ảnh toàn bộ interface

**Cần xác minh:**
- Panel trái: Các loại node có sẵn
- Giữa: Canvas ReactFlow với lưới
- Panel phải: Giao diện terminal
- Dưới: Panel attack scenarios (nếu hiển thị)

---

📸 **Ảnh 2: Topology Đã Tạo**

**Cách chụp:**
1. Tạo một topology đơn giản với 3+ nodes
2. Chụp ảnh các nodes được kết nối bằng edges

---

📸 **Ảnh 3: Phản Hồi AI trong Terminal**

**Cách chụp:**
1. Gõ `help` trong terminal
2. Chụp ảnh các lệnh có sẵn

---

## Xác Minh Kiến Trúc

| Thành phần | URL | Trạng thái |
|-----------|-----|-----------|
| Frontend (CloudFront) | https://d3rs3evkmfvesp.cloudfront.net/ | ✅ Đã deploy |
| API Gateway | https://\<id\>.execute-api.ap-southeast-1.amazonaws.com/prod/ | ✅ Đã deploy |
| Lambda | CloudNexus-BackendHandler | ✅ Đã deploy |
| S3 | cloudnexus-frontend-\<suffix\> | ✅ Đã deploy |

---

## Checklist Kiểm Tra

| Test | Command | Kết quả mong đợi |
|------|---------|-----------------|
| Health Check | `curl <api-url>/api/health` | `{"status":"ok"}` |
| Generate | `generate simple network` | Topology JSON |
| Scan | `scan` | Attack scenarios |
| Validate | POST `/api/topology/validate` | Validation result |
