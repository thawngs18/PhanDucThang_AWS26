---
title: "Các bài blog đã đăng"
date: 2026-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Tại đây sẽ là phần liệt kê, giới thiệu các blogs mà các bạn đã đăng trên [AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj).

###  [Blog 1 - Bảo Mật Chuỗi Cung Ứng Phần Mềm Theo Chuẩn AWS Well-Architected](3.1-Blog1/)
Blog này thảo luận về bảo mật chuỗi cung ứng phần mềm dựa trên **AWS Well-Architected Security Pillar**, đề cập đến **5 best practices cốt lõi** từ AWS Security Blog. Các chủ đề chính bao gồm loại bỏ long-term credentials và áp dụng least privilege, phòng thủ nhiều lớp với AWS Signer và Amazon ECR managed signing, quản lý dependency tập trung qua AWS CodeArtifact để giảm thiểu rủi ro typosquatting, quét tự động liên tục với Amazon Inspector để phát hiện sớm sleeper packages, và giám sát nâng cao với AWS CloudTrail, GuardDuty và EventBridge để phát hiện mối đe dọa và kích hoạt phản hồi tự động.

###  [Blog 2 - Xây Dựng Quản Lý Khóa Blockchain An Toàn Và Có Thể Kiểm Chứng Trên AWS Nitro Enclaves Với Turnkey](3.2-Blog2/)
Blog này giới thiệu giải pháp quản lý khóa blockchain an toàn từ Turnkey dựa trên **AWS Nitro Enclaves**, kết hợp mật mã học và cô lập phần cứng để xử lý khóa hoàn toàn trong môi trường enclave. Các điểm cốt lõi bao gồm thách thức trong kiến trúc quản lý khóa hiện tại, cơ chế cô lập của Nitro Enclaves không có lưu trữ vĩnh viễn và không có quyền truy cập tương tác, quy trình khởi tạo và lưu trữ dữ liệu mật mã với mô hình HD Wallet và mã hóa đối xứng bằng Quorum Key, kiến trúc phân tách giữa phân vùng quản lý bên ngoài và phân vùng tính toán bên trong với 5 bước xử lý khép kín, cùng cơ chế xác thực từ xa bằng Remote Attestation và Reproducible Builds với QuorumOS.

###  [Blog 3 - AWS DevOps Agent Sử Dụng Multi-Agent Reasoning Để Tìm Nguyên Nhân Gốc Rễ](3.3-Blog3/)
Blog này giải thích cách AWS DevOps Agent giải quyết confirmation bias trong điều tra sự cố bằng kiến trúc **multi-agent reasoning**. Các điểm cốt lõi bao gồm Topology Graph làm nền tảng bản đồ hệ thống động thể hiện mối liên hệ giữa các service, database, luồng runtime và lineage CI/CD, vòng đời 4 bước xử lý sự cố với các agent chuyên biệt Triage, Investigation, Mitigation và Prevention, cách Investigation tạo nhiều giả thuyết cạnh tranh đồng thời và xác thực bằng bằng chứng ủng hộ lẫn phản bác trước khi kết luận root cause, Mitigation sinh kế hoạch khắc phục an toàn có rollback mà không tự thực thi thay đổi, cùng Prevention nhóm lỗi quá khứ để rút ra quy luật chung và đề xuất cải tiến kiến trúc ngăn lỗi tái diễn.
