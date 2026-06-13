---
title: "Worklog Tuần 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Hiểu rõ bản chất mối đe dọa: Nắm bắt cơ chế hoạt động của các cuộc tấn công chuỗi cung ứng hiện đại (như Shai-Hulud) thông qua việc khai thác thông tin xác thực của người bảo trì và lan truyền qua các môi trường của người sử dụng gói phần mềm.
* Tiếp cận theo chuẩn Well-Architected: Áp dụng lý thuyết từ Trụ cột Bảo mật (Security Pillar) của AWS Well-Architected Framework để giảm thiểu sự phơi nhiễm trước các mối đe dọa.
* Nghiên cứu kiến trúc phòng thủ nhiều lớp (Defense in Depth): Khám phá nguyên lý kết hợp thông tin xác thực tạm thời, đặc quyền tối thiểu, quy trình phê duyệt nhiều bên và xác minh chữ ký tạo tác (Artifact Signing).
* Kiểm soát mã nguồn và phụ thuộc: Phân tích vai trò của quản lý gói tập trung để chống giả mạo tên (typosquatting), cùng lý thuyết về chứng thực nguồn gốc (provenance attestation).
* Xây dựng tư duy giám sát và phản hồi: Tìm hiểu sự khác biệt giữa quét lỗ hổng CVE tĩnh và phân tích hành vi thời gian thực đối với các gói độc hại (zero-day, sleeper packages).

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Nghiên cứu bản chất các cuộc tấn công chuỗi cung ứng: Phân tích cơ chế Shai-Hulud, Chalk/Debug, cách kẻ tấn công khai thác thông tin xác thực maintainer để phát tán mã độc <br> - Lý thuyết về rủi ro thông tin xác thực: Tại sao token npm, GitHub dài hạn là điểm yếu; nguyên lý OIDC và kiến trúc liên kết danh tính <br> - Nguyên tắc Đặc quyền Tối thiểu: Cấp quyền tối thiểu, kiểm toán và xoay vòng bí mật tự động để thu hẹp phạm vi ảnh hưởng | 08/06/2026 | 08/06/2026 | <https://aws.amazon.com/vi/blogs/security/well-architected-best-practices-for-software-supply-chain-security/> |
| 3   | - Khái niệm Phòng thủ Chiều sâu: Kiến trúc bảo mật nhiều lớp, kết hợp MFA và phê duyệt nhiều bên để chặn sự lây lan rủi ro <br> - Cơ chế Ký Tạo tác (Artifact Signing): Nguyên lý mật mã học, ràng buộc gói phần mềm với danh tính tạo ra <br> - Quy trình xác minh chữ ký: Hệ thống tự động ký (OCI), admission controllers đối chiếu chữ ký trước khi triển khai | 09/06/2026 | 09/06/2026 | <https://aws.amazon.com/vi/blogs/security/well-architected-best-practices-for-software-supply-chain-security/> |
| 4   | - Chiến lược Quản lý Phụ thuộc Tập trung: Kho lưu trữ tập trung ngăn typosquatting qua danh sách nguồn được phê duyệt <br> - Kiến trúc bảo mật vùng chứa: Mã hóa tĩnh và chính sách quản lý vòng đời bảo vệ tính toàn vẹn hình ảnh container <br> - Chứng thực Nguồn gốc (Provenance Attestation): Cơ chế npm provenance, Sigstore liên kết CI/CD với mã nguồn gốc | 10/06/2026 | 10/06/2026 | <https://aws.amazon.com/vi/blogs/security/well-architected-best-practices-for-software-supply-chain-security/> |
| 5   | - Chiến lược Quét liên tục trong SDLC: Các lớp quét từ SCA khi review code đến quét liên tục trên pipeline <br> - Phân tích Hành vi vs. Quét CVE tĩnh: Hạn chế quét CVE truyền thống; phân tích hành vi thời gian thực cho zero-day và sleeper packages <br> - Cấu trúc SBOM: Tiêu chuẩn SPDX, CycloneDX và cách dùng SBOM đánh giá blast radius khi có sự cố | 11/06/2026 | 11/06/2026 | <https://aws.amazon.com/vi/blogs/security/well-architected-best-practices-for-software-supply-chain-security/> |
| 6   | - Giám sát Tập trung (Visibility): Tổng hợp và liên kết chéo nhật ký ứng dụng, dịch vụ để phát hiện sớm hành vi dị thường <br> - Nhận diện rủi ro qua Nhật ký Kiểm toán: Mẫu sự kiện rủi ro — lệnh từ IP bất thường, Push Image bỏ qua CI/CD, Access Key không theo quy luật <br> - Pháp y kỹ thuật số (Forensics) và Tự động hóa: Đánh giá phạm vi lộ lọt và xây dựng quy tắc tự động phản ứng sự kiện bất thường | 12/06/2026 | 12/06/2026 | <https://aws.amazon.com/vi/blogs/security/well-architected-best-practices-for-software-supply-chain-security/> |

### Kết quả đạt được tuần 8:

* Tư duy kiến trúc an toàn toàn diện: Nắm vững lý thuyết thiết lập hàng rào bảo mật xuyên suốt SDLC, từ viết mã, CI/CD đến triển khai.
* Nhận diện và loại bỏ rủi ro cốt lõi: Đánh giá mức độ nguy hiểm của thông tin xác thực dài hạn và hiểu lộ trình chuyển sang danh tính ngắn hạn/tạm thời.
* Chặn đứng sự lây lan (Prevent Sprawl): Thiết kế chốt chặn (kiểm tra chữ ký mã hóa độc lập) để mã độc không vào môi trường sản xuất khi tài khoản developer bị xâm phạm.
* Năng lực ứng phó sự cố chủ động: Sử dụng SBOM để khoanh vùng blast radius nhanh chóng.
* Hiểu cách dùng nhật ký kiểm toán (CloudTrail) cho pháp y kỹ thuật số khi có sự cố lộ lọt danh tính.
