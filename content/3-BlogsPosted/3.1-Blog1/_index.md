---
title: "Well-Architected Best Practices for Software Supply Chain Security"
date: 2026-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

**Title:** Well-Architected Best Practices for Software Supply Chain Security

**Link:** https://aws.amazon.com/blogs/security/well-architected-best-practices-for-software-supply-chain-security/

**Summary:** Tổng hợp 5 best practices cốt lõi theo AWS Well-Architected Security Pillar để tăng cường phòng thủ chuỗi cung ứng phần mềm, đặc biệt trước các cuộc tấn công qua npm Registry như Shai-Hulud.

---

# 1. TỔNG QUAN / OVERVIEW

Gần đây, các cuộc tấn công chuỗi cung ứng phần mềm (Software Supply Chain Attacks) thông qua npm Registry như Shai-Hulud, Chalk/Debug, tea.xyz, và axios đang gia tăng. Kẻ tấn công thường chiếm quyền tài khoản maintainer hoặc lợi dụng lỗ hổng trong môi trường CI/CD để chèn mã độc. Bài viết này tổng hợp 5 best practices cốt lõi từ AWS Security Blog, căn cứ theo AWS Well-Architected Framework – Security Pillar, giúp giảm thiểu rủi ro và giới hạn thiệt hại khi sự cố xảy ra.

Recently, software supply chain attacks through npm Registry—such as Shai-Hulud, Chalk/Debug, tea.xyz, and axios—have been increasing. Attackers often compromise maintainer accounts or exploit CI/CD environment misconfigurations to inject malicious code. This report summarizes 5 core best practices from the AWS Security Blog, based on the AWS Well-Architected Framework – Security Pillar, to reduce risk and limit damage when incidents occur.

---

# 2. CÁC BEST PRACTICES / BEST PRACTICES

## 2.1. LOẠI BỎ LONG-TERM CREDENTIALS & ÁP DỤNG LEAST PRIVILEGE
## 2.1. REMOVE LONG-TERM CREDENTIALS & APPLY LEAST PRIVILEGE

Mã độc thường quét secret như npm token, GitHub token, và IAM Access Key trên máy dev và pipeline CI/CD. Việc loại bỏ long-lived credentials giảm thiểu phạm vi ảnh hưởng nếu hệ thống bị xâm phạm.

Malware typically scans for secrets such as npm tokens, GitHub tokens, and IAM access keys on developer machines and CI/CD pipelines. Removing long-lived credentials reduces the scope of exposure if a system is compromised.

**Đề xuất chính / Key recommendations:**

- Dùng `aws login` để lấy short-lived credentials thay vì lưu cứng key. / Use `aws login` to obtain short-lived credentials instead of hardcoding keys.
- CI/CD: áp dụng OIDC (GitHub Actions, GitLab CI…) để cấp quyền tạm theo từng job. / CI/CD: use OIDC to issue temporary, job-scoped permissions.
- Nếu bắt buộc dùng third-party credentials, lưu vào AWS Secrets Manager, giới hạn quyền truy cập, bật rotation và audit logging. / If third-party credentials are required, store them in AWS Secrets Manager with restricted access, automatic rotation, and audit logging.
- Phát hiện hành vi bất thường bằng Amazon GuardDuty và AWS CloudTrail, ví dụ `sts:AssumeRole` từ IP lạ. / Detect anomalies with GuardDuty and CloudTrail, such as `sts:AssumeRole` from unusual IPs.

---

## 2.2. PHÒNG THỦ NHIỀU LỚP (DEFENSE IN DEPTH) & KÝ XÁC THỰC
## 2.2. DEFENSE IN DEPTH & ARTIFACT SIGNING

Một tài khoản bị lộ không nên dẫn đến “dấu chấm hết” cho toàn hệ thống. Defense in depth tạo nhiều lớp bảo vệ để ngăn mã độc lan rộng sau khi xâm phạm ban đầu.

A single compromised account should not result in full system compromise. Defense in depth creates multiple protective layers to contain malware spread after initial breach.

**Đề xuất chính / Key recommendations:**

- Bắt buộc MFA và phân chia trách nhiệm (separation of duties) giữa developer và vai trò nhạy cảm. / Enforce MFA and separation of duties between developers and sensitive roles.
- Áp dụng multi-approval trong pipeline trước khi deploy Production. / Apply multi-approval gates before production deployment.
- Dùng AWS Signer để ký artifact; kết hợp Amazon ECR managed signing và admission controller trên EKS (Kyverno) để chặn image không rõ nguồn gốc. / Use AWS Signer for artifact signing; combine with Amazon ECR managed signing and Kyverno admission control to block unsigned images.
- Chỉ vai trò CI/CD mới có quyền `signer:StartSigningJob`; developer credential không nên có quyền signing. / Only CI/CD roles should have signing permissions.

---

## 2.3. QUẢN LÝ DEPENDENCY TẬP TRUNG
## 2.3. CENTRALIZED DEPENDENCY MANAGEMENT

Centralizing dependency management giúp xác minh và phê duyệt package trước khi sử dụng, đồng thời nhanh chóng kiểm kê khi có sự cố.

Centralizing dependency management helps validate and approve packages before use, and enables rapid impact assessment during incidents.

**Đề xuất chính / Key recommendations:**

- Dùng AWS CodeArtifact để quản lý package nội bộ, định nghĩa upstream an toàn, chặn typosquatting. / Use AWS CodeArtifact with approved upstream sources to block typosquatting.
- Khuyến khích kiểm tra npm provenance attestation để xác minh package được build từ đúng mã nguồn và CI/CD. / Check npm provenance attestations to verify the package was built from the intended source and CI/CD workflow.
- Với container image, kết hợp Amazon ECR + AWS KMS + lifecycle policies + Amazon Inspector. / For container images, combine Amazon ECR with AWS KMS, lifecycle policies, and Amazon Inspector.

---

## 2.4. QUÉT TỰ ĐỘNG VÀ LIÊN TỤC TRONG SDLC
## 2.4. AUTOMATED & CONTINUOUS SCANNING THROUGHOUT SDLC

Scanner CVE truyền thống không đủ trước mã độc zero-day chưa được gán mã. Cần tích hợp phân tích hành vi và cộng đồng để phát hiện sớm sleeper packages.

Traditional CVE scanners are insufficient against zero-day malicious packages without assigned identifiers. Behavioral analysis and community collaboration are needed to detect sleeper packages early.

**Đề xuất chính / Key recommendations:**

- Tích hợp Amazon Inspector vào CI/CD để quét first-party code, third-party dependencies, và IaC. / Integrate Amazon Inspector into CI/CD to scan first-party code, third-party dependencies, and IaC.
- Dùng phân tích hành vi để phát hiện sleeper packages trước khi bị gán MAL-ID. / Use behavioral analysis to detect sleeper packages before formal MAL-ID assignment.
- Luôn xuất và lưu SBOMs (SPDX/CycloneDX) để nhanh chóng đánh giá phạm vi thiệt hại khi có sự cố. / Generate and store SBOMs to rapidly assess blast radius during incidents.

---

## 2.5. TĂNG CƯỜNG LOGGING & MONITORING
## 2.5. ENHANCED LOGGING & MONITORING

Visibility toàn bộ hoạt động là yếu tố then chốt để phát hiện sớm hành vi bất thường.

Full activity visibility is critical for early anomaly detection.

**Đề xuất chính / Key recommendations:**

- Bật AWS CloudTrail để audit toàn bộ API call. / Enable AWS CloudTrail for full API audit.
- Giám sát các event như `ecr:PutImage` từ máy dev bypass CI/CD, `secretsmanager:GetSecretValue` từ nguồn lạ, hay `iam:CreateAccessKey` kèm hoạt động ngay sau đó. / Monitor events such as `ecr:PutImage` from developer workstations bypassing CI/CD, unusual `secretsmanager:GetSecretValue`, or `iam:CreateAccessKey` followed by immediate activity.
- Kết hợp Amazon GuardDuty, AWS Security Hub, AWS Config, và EventBridge để phát hiện và kích hoạt phản hồi tự động. / Combine GuardDuty, Security Hub, Config, and EventBridge for detection and automated response.

---

# 3. TỔNG KẾT / CONCLUSION

Bảo mật chuỗi cung ứng phần mềm không chỉ dừng lại ở việc viết code an toàn, mà là một chiến lược toàn diện: xây dựng kiến trúc nhiều lớp (defense in depth), triệt tiêu đặc quyền dài hạn, duy trì kiểm soát và giám sát tuyệt đối đối với mọi artifact trước khi đưa vào hệ thống vận hành.

Software supply chain security is not just about writing secure code; it is an end-to-end strategy: build defense-in-depth architecture, eliminate long-term privileges, and maintain absolute control and monitoring over every artifact before it reaches production.

---

...Image...

...Link...

...Guide...
