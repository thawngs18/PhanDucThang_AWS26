---
title : "Kiểm tra hệ thống"
date : "2025-10-10"
weight : 12
chapter : false
pre : " <b> Step 12 </b> "
---
# Step 12: Kiểm Tra Hệ Thống

---

## URL Demo Trực Tiếp

**Truy cập ứng dụng đã deploy:** [https://d3rs3evkmfvesp.cloudfront.net/](https://d3rs3evkmfvesp.cloudfront.net/)

---

## Health Check

```powershell
# Lấy API URL từ CloudFormation
$apiUrl = aws cloudformation describe-stacks --stack-name CloudNexus-Backend --query "Stacks[0].Outputs[?OutputKey=='ApiUrl'].OutputValue" --output text

# Test health endpoint
curl -s "$apiUrl/api/health"
```

**Kết quả mong đợi:**
```json
{"status":"ok"}
```

---

## Kiểm Tra Frontend

Mở trên trình duyệt: [https://d3rs3evkmfvesp.cloudfront.net/](https://d3rs3evkmfvesp.cloudfront.net/)

**Xác minh:**
- React app load hoàn toàn
- ReactFlow canvas hiển thị
- Terminal interface nhìn thấy được
- Dark mode theme active

---

## Test AI Generation

```powershell
$body = '{"prompt":"simple web server with database"}'
curl -s -X POST "$apiUrl/api/ai/generate" -H "Content-Type: application/json" -d $body
```

**Kết quả mong đợi:** JSON topology với nodes và edges

---

## Hướng Dẫn Chụp Ảnh Xác Minh

📸 **Ảnh 1: Frontend Load Thành Công**

**Cách chụp:**
1. Mở [https://d3rs3evkmfvesp.cloudfront.net/](https://d3rs3evkmfvesp.cloudfront.net/) trên trình duyệt
2. Đợi page load hoàn toàn
3. Chụp ảnh interface đầy đủ

**Cần xác minh:**
- ReactFlow canvas hiển thị bên trái
- Terminal interface bên phải
- Dark theme được áp dụng
- Không có lỗi loading

---

📸 **Ảnh 2: API Health Check Response**

**Cách chụp:**
1. Chạy lệnh curl cho health check
2. Chụp ảnh terminal hiển thị JSON response

**Kết quả mong đợi:** `{"status":"ok"}`

---

📸 **Ảnh 3: CloudWatch Lambda Logs**

**Cách chụp:**
1. Vào AWS Console → CloudWatch → Log groups
2. Tìm `/aws/lambda/CloudNexus-Backend`
3. Chụp ảnh các log events gần đây

**Cần xác minh:**
- INIT_START event
- Lambda handler invoked
- Không có error logs

---

## Lambda Metrics

```powershell
aws cloudwatch get-metric-statistics `
  --namespace AWS/Lambda `
  --metric-name Invocations `
  --dimensions Name=FunctionName,Value=CloudNexus-BackendHandler `
  --start-time 2025-01-01T00:00:00Z `
  --end-time 2025-12-31T23:59:59Z `
  --period 3600 `
  --statistics Sum
```

| Metric | Giá trị | Ý nghĩa |
|--------|---------|----------|
| Invocations | > 0 | Lambda đang được gọi |
| Duration | ~60ms | Xử lý request |
| Errors | 0 | Không có lỗi |
