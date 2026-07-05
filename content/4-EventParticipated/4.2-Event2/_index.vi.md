---
title: "Event 2"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

# FCAJ Community Day - Conference Call

### Mục Đích Của Sự Kiện

- Chia sẻ kiến thức chuyên sâu và best practices về việc tích hợp AI vào sản phẩm thực tế (từ Prompt Engineering đến Multi-Agent Systems).
- Giải mã bản chất kỹ thuật của các mô hình ngôn ngữ lớn (LLMs) và cách quản lý độ rủi ro, tính ngẫu nhiên trong môi trường production.
- Hướng dẫn tối ưu hóa hạ tầng đám mây (Cloud Infrastructure) với Amazon CloudFront để đảm bảo bảo mật, hiệu suất và tối ưu chi phí.
- Truyền cảm hứng qua các case study thực tế từ môi trường Enterprise (Ngân hàng/Startup) đến các cuộc thi Hackathon (LotusHacks).

### Danh Sách Diễn Giả

- **Tinh Truong** – Platform Engineer, GoTymeX
- **Pham Ng Hai Anh** – AWS Community Builder, G-AsiaPacific Vietnam
- **Nguyen Tuan Thinh** – DevOps Engineer, FCAJ
- **Team VIB** – GenAI Engineer, VIB, Participants, LotusHacks 2026
- **Duc Dao** – Solution Architect, Cloud Kinetics
- **Vy Lam** – Senior Business Systems Analyst, VPBank

### Nội Dung Nổi Bật

#### Làm chủ AI thông qua Context (Ngữ cảnh)

- Nguyên nhân AI thất bại thường không phải do model yếu, mà do input thiếu ngữ cảnh. AI không thể "đọc suy nghĩ" của con người.
- Framework 4 yếu tố cho Prompt chuẩn: Goal (Mục tiêu) → Relevant Info (Thông tin liên quan) → Constraints (Ràng buộc) → Success criteria (Tiêu chí thành công).
- Sự tiến hóa của AI: Từ Prompt (câu hỏi đơn lẻ) → Context (kèm tài liệu) → Memory (Second Brain - ghi nhớ và học hỏi theo thời gian).

#### Bản chất không xác định (Non-Determinism) của LLM

- Cài đặt Temperature = 0 không đảm bảo kết quả giống nhau 100% (Deterministic) như mọi người vẫn nghĩ.
- Nguyên nhân kỹ thuật: Do kiến trúc GPU xử lý số thực (floating-point) song song và cơ chế batching request của các nhà cung cấp API (OpenAI, Anthropic,...).
- Cách khắc phục: Sử dụng temp = 0.1 để tránh model bị kẹt trong vòng lặp (loop), sử dụng structured outputs (JSON) và thiết kế hệ thống có khả năng xử lý các kết quả không đồng nhất.

#### Hệ thống AI Đa tác vụ cấp Doanh nghiệp (Enterprise-Grade Multi-Agent)

- Single Agent (AI đơn lẻ) sẽ thất bại với các bài toán phức tạp (như chấm điểm tín dụng Startup) do giới hạn context, pha loãng chuyên môn và thiếu cơ chế kiểm tra chéo (Checks & Balances).
- Multi-Agent Paradigm: Xây dựng một "hội đồng ảo" (Virtual Committee) gồm nhiều Agent chuyên biệt (Tài chính, Thị trường, Nhân sự, Rủi ro, Tuân thủ) làm việc song song và phản biện lẫn nhau.
- Enterprise-Grade Thinking: Đưa AI vào production đòi hỏi 6 trụ cột: Security (Auth, mã hóa), Data Governance, Network (VPC, Zero-trust), Operations, Human Factors, và Compliance.

#### Tối ưu hạ tầng mạng với Amazon CloudFront

- Giải quyết bài toán chi phí CDN khó đoán: Giới thiệu các gói Fixed-Price bao gồm CDN, WAF, DDoS, DNS và Storage.
- Bảo mật tại Edge (Biên): Chống DDoS (volumetric attack) hiệu quả hơn ELB, tích hợp Mutual TLS, Origin Access Control (OAC) để ẩn (cloak) Origin server.
- Tối ưu hiệu suất: HTTP/3 (QUIC) multiplexing, nén dữ liệu tại Edge, và Edge Computing (CloudFront Functions, Lambda@Edge) giúp giảm tải cho Origin.

#### Xây dựng sản phẩm từ Idea đến Reality (Kinh nghiệm Hackathon)

- Hành trình 36h xây dựng UTMorpho (Ứng dụng chuyển đổi wireframe thành code).
- Thách thức thực tế: Hiện tượng AI Overgeneration, giới hạn Token, và sự cạn kiệt thể lực (burnout).
- Bài học: Ý tưởng thực tế sinh ra từ sự thất vọng thực tế. Làm việc nhóm và sự đồng bộ (Team Sync) quan trọng hơn số lượng tính năng.

### Những Gì Học Được

#### Tư Duy Thiết Kế Hệ Thống AI

- **Context Quality > Context Quantity:** Không phải cứ nhồi nhét tài liệu vào AI là tốt, cần đưa đúng dữ liệu (relevant evidence).
- **Multi-Agent vs Single Agent:** Hiểu rõ khi nào dùng AI đơn (công việc tuyến tính, rủi ro thấp) và khi nào cần AI đa tác vụ (quyết định quan trọng, cần chuyên môn sâu đa ngành).
- **Xây dựng hệ thống bao dung với rủi ro:** Luôn coi output của LLM là xác suất (probabilistic) chứ không phải tuyệt đối (deterministic).

#### Kiến Trúc & Hạ Tầng Kỹ Thuật

- **Bảo mật sâu (Defense in Depth):** Ẩn hoàn toàn server xử lý phía sau CloudFront và VPC, chỉ cho phép traffic đi qua các lớp kiểm tra (WAF, OAC).
- **Guardrails cho AI:** Áp dụng kiểm soát nghiêm ngặt 3 lớp: Input (PII, Prompt Injection), Processing (Token budget, Timeout) và Output (Hallucination, Bias).

#### Chiến Lược Triển Khai Thực Tế

- **Phased approach cho Enterprise AI:** Từ Local/CrewAI → AgentCore → Docker/ECR → Lambda/API Gateway. Không đi tắt bỏ qua bước security.
- **Đo lường ROI:** Chuyển đổi quy trình bằng AI (ví dụ: Credit Scoring) không chỉ tiết kiệm giờ làm (giảm 95% chi phí quyết định) mà còn tăng tỷ lệ duyệt hồ sơ.

### Ứng Dụng Vào Công Việc

- **Cải thiện cách giao tiếp với AI:** Xây dựng template prompt cho team phát triển phần mềm theo framework: Goal - Context - Constraints - Format.
- **Quản lý độ ổn định của AI:** Thử nghiệm mức temperature = 0.1 thay vì 0 trong các tác vụ trích xuất dữ liệu JSON để tránh lỗi lặp từ; thiết kế thêm logic fallback/retry trong code.
- **Review lại kiến trúc hạ tầng:** Đánh giá việc áp dụng CloudFront và WAF cho các project hiện tại, xem xét sử dụng tính năng nén HTTP và Origin Access Control để tối ưu chi phí truyền tải và bảo mật.
- **Áp dụng Multi-Agent:** Thử nghiệm chia nhỏ các prompt/task phức tạp thành nhiều vai trò (Reviewer, Coder, Tester) giao tiếp với nhau thay vì gom vào một prompt khổng lồ.

### Trải Nghiệm Trong Event

- Tham gia sự kiện là một trải nghiệm mở rộng tầm mắt, kết nối hoàn hảo giữa tầng tư duy (Context/AI behavior), tầng ứng dụng (Multi-agent/Hackathon) và tầng hạ tầng (CloudFront/AWS services).
- **Học hỏi từ các chuyên gia:** Các bài nói chuyện không chỉ dừng ở lý thuyết bề nổi mà đi rất sâu vào bản chất (ví dụ như bài phân tích lỗi toán học floating-point của GPU làm ảnh hưởng đến tính deterministic của LLM).
- **Trải nghiệm thực tế:** Hiểu được khoảng cách giữa một "bản nháp" (POC AI) và một hệ thống "sẵn sàng cho doanh nghiệp" (Enterprise-ready).
- **Kết nối và trao đổi:** Nhận ra rằng các kỹ sư dù làm việc ở ngân hàng lớn hay thi đấu hackathon đều đối mặt với những vấn đề chung như: Token limit, Hallucination, và quản trị chi phí Cloud.

### Bài Học Rút Ra

- **Enterprise AI is not about making things work, it's about making them work securely, reliably, and at scale:** AI tạo sinh rất dễ để làm demo, nhưng đưa vào môi trường doanh nghiệp cần một tư duy kiến trúc khắt khe (Guardrails, VPC, Auditability).
- Trong kỷ nguyên GenAI, Kỹ sư ngữ cảnh (Context Engineering) và thiết kế hệ thống lưu trữ bộ nhớ cho AI (Second Brain) sẽ là những kỹ năng cốt lõi.
- Dù AI có phát triển đến đâu, một hạ tầng mạng (Foundation) vững chắc, bảo mật và tối ưu chi phí (như CloudFront) vẫn là trụ cột không thể thiếu để phân phối ứng dụng đến người dùng cuối.

### Hình Ảnh Sự Kiện

![Event 2-1](/images/event2/image-1.png)
![Event 2-2](/images/event2/image-2.png)
![Event 2-3](/images/event2/image-3.png)
