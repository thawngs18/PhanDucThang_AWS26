---
title: "Blog 1"
date: 2026-07-06
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---


# CÁC BEST PRACTICES BẢO MẬT CHUỖI CUNG ỨNG PHẦN MỀM THEO CHUẨN AWS WELL-ARCHITECTED

![Bảo Mật Chuỗi Cung Ứng Phần Mềm](/images/supply-chain-security.png)

Thời gian gần đây, các cuộc tấn công chuỗi cung ứng phần mềm (Software Supply Chain Attacks) qua npm Registry (vụ Shai-Hulud, tea.xyz, axios...) đang bùng nổ. Kẻ tấn công thường chiếm quyền tài khoản maintainer hoặc lợi dụng lỗ hổng cấu hình trong môi trường CI/CD để chèn mã độc.

Dựa trên **AWS Well-Architected Security Pillar**, dưới đây là **5 Best Practices cốt lõi** từ AWS Security Blog giúp anh em siết chặt phòng thủ:

## 1. Loại Bỏ Long-Term Credentials & Áp Dụng Least Privilege

Mã độc luôn tìm cách quét secret (npm token, IAM Access Keys) trên máy dev và CI/CD.

**Với Developer:** Dùng lệnh `aws login` để lấy short-lived credentials thay vì lưu cứng key.

**Với CI/CD:** Sử dụng OIDC (OpenID Connect) với GitHub Actions/GitLab CI để cấp quyền tạm thời theo từng job. Nếu dùng bên thứ ba, hãy lưu vào AWS Secrets Manager và tự động rotate key.

## 2. Phòng Thủ Nhiều Lớp (Defense in Depth) & Ký Xác Thực

Một tài khoản bị lộ không nên là "dấu chấm hết" cho toàn hệ thống.

- Bắt buộc bật MFA và áp dụng cơ chế multi-approval trước khi deploy Production.
- Dùng AWS Signer để ký xác thực artifact. Kết hợp Amazon ECR managed signing (tự động ký container image) và admission controller trên EKS (như Kyverno) để chặn các image không rõ nguồn gốc.

## 3. Quản Lý Dependency Tập Trung

Thay vì pull trực tiếp từ internet, hãy dùng AWS CodeArtifact để quản lý package nội bộ và định nghĩa upstream an toàn, chặn đứng nguy cơ Typosquatting.

Kiểm tra npm provenance attestation để xác minh package thực sự được build từ đúng mã nguồn và luồng CI/CD của tác giả.

## 4. Quét (Scanning) Tự Động và Liên Tục

Công cụ quét CVE truyền thống sẽ bất lực trước mã độc Zero-day chưa được công bố.

- Tích hợp Amazon Inspector vào luồng CI/CD. Inspector dùng phân tích hành vi để phát hiện sớm các "sleeper packages" (mã độc ngủ đông) trước khi chúng bị gán mã MAL-ID.
- Luôn xuất và lưu trữ SBOMs (Software Bills of Materials) để kiểm soát và cô lập thiệt hại nhanh nhất khi có sự cố.

## 5. Tăng Cường Logging & Monitoring

Bật AWS CloudTrail để audit toàn bộ API Call. Giám sát kỹ các hành vi lạ như `sts:AssumeRole` từ IP lạ, hoặc `ecr:PutImage` đẩy trực tiếp từ máy dev mà không qua CI/CD.

Kết hợp Amazon GuardDuty và EventBridge để phát hiện và kích hoạt phản hồi tự động (Automation Response).

---

**Tóm tắt:** Bảo mật chuỗi cung ứng phần mềm trên Cloud không chỉ dừng lại ở việc viết code an toàn, mà nó là một chiến lược toàn diện: xây dựng kiến trúc nhiều lớp (defense in depth), triệt tiêu đặc quyền dài hạn và duy trì sự kiểm soát, giám sát tuyệt đối đối với mọi artifact trước khi đưa vào hệ thống vận hành.

**Tài liệu tham khảo:** [Well-Architected Best Practices for Software Supply Chain Security](https://aws.amazon.com/blogs/security/well-architected-best-practices-for-software-supply-chain-security/)

**Bài đăng cộng đồng:** [Facebook](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2179514172813543/?rdid=amgNjd5p5RIQ4i5L#)

---
