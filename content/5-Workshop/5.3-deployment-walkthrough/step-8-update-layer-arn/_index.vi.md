---
title : "Cập nhật Layer ARN trong CDK"
date : "2025-10-10"
weight : 8
chapter : false
pre : " <b> Step 8 </b> "
---
# Step 8: Cập Nhật Layer ARN trong CDK

---

## Mục Đích

Cập nhật Lambda Layer ARN trong CDK stack với version number mới được publish.

---

## Các Lệnh

Mở file backend stack:

```powershell
notepad C:\Users\ADMIN\Desktop\BC\DEMO\infrastructure\stacks\backend_stack.py
```

Tìm dòng này:

```python
layer_arn = 'arn:aws:lambda:ap-southeast-1:<ACCOUNT_ID>:layer:CloudNexus-PythonDeps:1'
```

Cập nhật số version ở cuối (VD: `:1`, `:2`, `:3`, `:4`) tùy vào lần publish layer.

---

## Hướng Dẫn Chụp Ảnh Xác Minh

📸 **Ảnh 1: Layer ARN trong Code**

**Cách chụp:**
1. Mở `backend_stack.py` trong editor
2. Tìm dòng `layer_arn`
3. Chụp ảnh hiển thị ARN với số version đúng

**Cần xác minh:**
- ARN kết thúc bằng `:1` (hoặc số version phù hợp)
- Account ID đúng

**Kết quả mong đợi:** Code hiển thị Layer ARN với version khớp với layer đã publish
