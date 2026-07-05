---
title: "Event 4"
date: 2026-05-27
weight: 1
chapter: false
pre: " <b> 4.4. </b> "
---

# FCAJ Community Day - June 2026

### Event Objectives

- Chia sẻ các kiến thức, kinh nghiệm và góc nhìn thực tế nhất từ môi trường doanh nghiệp về việc ứng dụng Cloud và AI.
- Giới thiệu các giải pháp AI đột phá đang được ứng dụng để giải quyết các bài toán vận hành, DevOps, chăm sóc khách hàng và quản lý nhân sự (HR).
- Trình diễn trực tiếp (Live Demo) cách triển khai các hệ thống AI Agents thực tế trên nền tảng AWS và các kiến trúc bảo mật kết nối.

### Speakers

- **Steve Tran** – Founder, Cloud Thinker
- **Hieu Nghi & Kiet** – Renova Cloud / Student Video Group
- **Trung Dang** – Founder & CEO, R AI
- **Bao & Nguyen Nguyen** – Cloud Engineer, Cloud Kinetics
- **Truong (Wayne) & Minh Anh** – AI Solution / Solution Architect, Noventiq
- **Toan Nguyen** – AWS Security Builder

### Key Highlights

#### AI trong Vận Hành Hạ Tầng (Cloud Thinker)

- Việc vận hành hệ thống lớn tốn rất nhiều công sức, con người phải đối mặt với các "món nợ công nghệ" và hệ thống phức tạp.
- Giới thiệu nền tảng AI Operations: So sánh sự khác biệt giữa Single-agent và Multi-agent.
- AI không thay thế kỹ sư giỏi mà hỗ trợ tối đa việc incident investigation (điều tra sự cố), code review, FinOps (tối ưu chi phí) và Security.

#### Giải pháp Voice AI cho Tiếng Việt (R AI)

- Giải quyết hạn chế của mô hình Speech-to-Speech cho tiếng Việt (do là ngôn ngữ low-resource).
- Quy trình chuẩn: Speech-to-Text → LLM (để xử lý ngữ cảnh/Prompt) → Text-to-Speech.
- AI có thể nhận diện giới tính (anh/chị), hiểu ngữ cảnh ngắt lời, và ứng dụng tool calling (như tự động khóa thẻ ngân hàng qua tổng đài).

#### DevOps Agent (Cloud Kinetics)

- Giải quyết bài toán Fragmented Telemetry (log/trace phân tán nhiều nơi) khiến kỹ sư tốn thời gian tìm lỗi.
- DevOps Agent tự động phân loại sự cố, đưa ra giả thuyết, điều tra root cause và đề xuất Mitigation Plan thay vì tự động thực thi (đảm bảo an toàn).

#### Amazon Q trong Quản trị Nhân Sự - HR (Noventiq)

- HR đang mất nhiều thời gian sàng lọc CV thủ công, dễ bỏ sót nhân tài và ảnh hưởng đến dự án.
- Amazon Q giúp tự động hóa tạo Job Description (JD), đọc và trích xuất thông tin CV, chấm điểm ứng viên, và tạo báo cáo trực quan mà vẫn giữ tính bảo mật dữ liệu.

#### Bảo Mật Kết Nối AI và MCP Server (Security)

- Kết nối các AI agents với ứng dụng bên thứ 3 (MCP Server) qua Public Internet rất dễ gặp rủi ro bảo mật (DDoS, Man-in-the-middle).
- Giải pháp đưa ra là sử dụng Private VPC Connection, thông qua AWS ALB và Route 53 Resolver để giữ luồng dữ liệu 100% trong nội bộ.

### Key Takeaways

#### Design Mindset

- **Business-first & Thực chiến:** Mọi giải pháp AI đều phải đi từ nỗi đau (pain point) thực tế của doanh nghiệp thay vì chỉ phô diễn công nghệ.
- **Copilot thay vì Autopilot:** AI đóng vai trò như một người trợ lý hỗ trợ, quyền ra quyết định (approval) và thực thi (execute) cuối cùng luôn cần Human-in-the-loop.

#### Technical Architecture

- **Multi-agent Architecture:** Hiểu được cách phân chia các Agent nhỏ với context window ngắn hơn để giải quyết chuyên biệt từng tác vụ.
- **Architecture Security:** Nhận thức rõ tầm quan trọng của việc cô lập (isolate) các MCP Server trong Private Subnet khi tích hợp hệ thống AI vào workflow nội bộ.

#### Modernization Strategy

- Khi áp dụng AI cho doanh nghiệp, cần đánh giá chi phí (như data transfer, hạ tầng VPC) để đảm bảo tính khả thi về mặt tài chính.
- Áp dụng dần dần (Phased approach), thử nghiệm ở môi trường Development hoặc cho các tác vụ mang tính chất hỗ trợ trước khi đưa vào các môi trường quan trọng.

### Applying to Work

- **Tự động hóa Incident Management:** Nghiên cứu áp dụng DevOps Agent hoặc các workflow AI để hỗ trợ đọc log, phân tích nguyên nhân gốc rễ, giúp giảm thiểu MTTD (Mean Time To Detect) và MTTR (Mean Time To Recovery).
- **Ứng dụng cho phòng ban Non-Tech:** Khảo sát đưa Amazon Q hoặc các công cụ tự động hóa vào team HR, Admin để hỗ trợ đọc tài liệu, screening ứng viên.
- **Thiết kế lại trải nghiệm Voice Chatbot:** Lưu ý thêm về context ngắt lời và văn hóa xưng hô (giới tính) nếu sau này phát triển các voice bot phục vụ thị trường nội địa.
- **Rà soát lại Security:** Cập nhật kiến trúc mạng, rà soát đưa các API/Server đang tương tác với AI Public vào hạ tầng Private VPC.

### Event Experience

Sự kiện là một trải nghiệm mở mang tầm mắt thực sự, giúp tôi nhận ra AI hiện nay không chỉ xoay quanh Chatbot tạo văn bản thông thường, mà đang thọc sâu vào các ngóc ngách vận hành cốt lõi (Cloud Infrastructure, DevOps, HR).

- Các Live Demo trực tiếp ngay trên sân khấu (Voice Agent gọi đặt câu hỏi sản phẩm, DevOps Agent bắn request sập tải hệ thống để phân tích, Amazon Q chấm điểm CV) mang tính thuyết phục rất cao.
- Có cơ hội kết nối với những con người rất tâm huyết và giàu kinh nghiệm, học hỏi tư duy xây dựng startup từ những bước đi ban đầu cho đến khi phục vụ Enterprise.

### Lessons Learned

- Dù công nghệ AI (như Agent) phát triển nhanh và mạnh, hệ thống càng lớn thì con người (các kỹ sư chuyên sâu) càng đóng vai trò định hướng quyết định. AI đóng vai trò khuếch đại năng lực chứ không thay thế hoàn toàn kỹ năng của kỹ sư.
- Đối với ngôn ngữ có ít tài nguyên như tiếng Việt, việc đi đường vòng (Speech to Text → LLM → Text to Speech) kết hợp với data huấn luyện vùng miền là giải pháp khôn ngoan nhất.
- Làm AI cho Enterprise đồng nghĩa với việc bạn phải thay đổi quy trình (process) của doanh nghiệp, và Security luôn luôn phải là yếu tố thiết kế được cân nhắc ngay từ ngày đầu.

### Event Photos

![Event 4-1](/images/event4/image-1.png)
![Event 4-2](/images/event4/image-2.png)
![Event 4-3](/images/event4/image-3.png)
