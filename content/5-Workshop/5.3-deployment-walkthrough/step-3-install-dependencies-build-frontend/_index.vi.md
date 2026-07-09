---
title : "Cài Dependencies & Build Frontend"
date : "2025-10-10"
weight : 3
chapter : false
pre : " <b> Step 3 </b> "
---
# Step 3: Cài Dependencies & Build Frontend

---

## Các Lệnh

```powershell
cd C:\Users\ADMIN\Desktop\BC\DEMO
npm install
```

---

## Kết Quả Mong Đợi

```
up to date, audited 300+ packages in 5s
```

---

## Build Frontend

```powershell
npm run build
```

---

## Build Output

```
dist/ generated successfully:
  index.html
  assets/index-xxxx.js
  assets/index-xxxx.css
```

---

## Xác Minh Build

```powershell
Test-Path dist/index.html
# → True
```

---

## Hướng Dẫn Chụp Ảnh Xác Minh

📸 **Ảnh 1: npm install hoàn thành**

**Cách chụp:**
1. Chạy `npm install` trong thư mục DEMO
2. Chụp ảnh terminal hiển thị cài đặt thành công

**Kết quả mong đợi:** Thông báo "audited XXX packages"

---

📸 **Ảnh 2: npm run build hoàn thành**

**Cách chụp:**
1. Chạy `npm run build`
2. Chụp ảnh output hiển thị thư mục dist/ được tạo

**Kết quả mong đợi:** Build output với thư mục `dist/` chứa `index.html`
