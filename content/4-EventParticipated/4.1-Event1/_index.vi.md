---
title: "Event 1"
date: 2026-04-07
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Kick Off AWS First Cloud AI Journey

### Mục Đích Của Sự Kiện

- Xây dựng định hướng lộ trình học tập, thực hành điện toán đám mây cho kỹ sư và sinh viên tham gia cộng đồng.
- Trang bị kiến thức nền tảng vững chắc về hệ sinh thái AWS (Global Infrastructure, IAM, Management Tools).
- Giới thiệu và hướng dẫn tích hợp trí tuệ nhân tạo (GenAI) vào vòng đời phát triển phần mềm thông qua công cụ AWS Kiro.
- Nâng cao nhận thức cốt lõi về tối ưu hóa chi phí (Cost Optimization) và kiến trúc hệ thống trên môi trường Cloud.

### Danh Sách Diễn Giả

- **Nguyen Gia Hung** - Head of Solution Architect, FCAJ

### Nội Dung Nổi Bật

#### 1. Khởi động hành trình (Prologue & Mindset)

- Giới thiệu 6 nguyên tắc cốt lõi: Builder & Troubleshooter, Teamwork, Resilience, Hands-on & Sharing, Invest in yourself, Lifelong learning.
- Mục tiêu thực tiễn: Thực hành "from scratch" và hoàn thành 5 projects thực tế để chứng minh năng lực.

#### 2. Nền tảng hạ tầng AWS

- Lợi ích của Cloud Computing: Tối ưu chi phí (Pay-as-you-go), tăng tốc độ phát triển và khả năng mở rộng quy mô toàn cầu.
- Hạ tầng toàn cầu (Global Infrastructure): Cấu trúc tầng bậc từ Data Center → Availability Zone (AZ - tối thiểu 2 AZ để dự phòng) → Region.
- Giới thiệu Edge Location (dùng cho CDN CloudFront) và Local Zone để tối ưu hóa độ trễ tại Việt Nam.

#### 3. Công cụ quản lý & Bảo mật cơ bản

- 3 phương thức tương tác chính: AWS Management Console, AWS CLI (tự động hóa qua terminal) và AWS SDK (tích hợp vào mã nguồn).
- Phân định rõ sự nguy hiểm của việc dùng Root User. Phải luôn sử dụng IAM User, thiết lập MFA và bảo mật tuyệt đối Access Key.

#### 4. Ứng dụng GenAI trên AWS - Trợ lý Kiro

- Sự dịch chuyển sang phương pháp **Spec-Driven Development**: Xác định rõ các yêu cầu (Requirement/Spec) và thiết kế trước khi để AI sinh code.
- Khả năng của Kiro IDE: Agent Hook (kích hoạt hành động tự động như sinh log/test khi lưu file), Context Management, và Property-Based Testing.
- Kiro CLI & Custom Agent: Đưa AI vào terminal với các Agent chuyên biệt (DevOps, DB) và Kiro Power (hệ sinh thái plugin kỹ năng cho AI).

#### 5. Tối ưu hóa chi phí (Cost Optimization)

- Nguyên tắc Right-sizing: Chỉ cấp phát tài nguyên đúng với nhu cầu hiện tại, không mua dư thừa như môi trường On-premise.
- Tận dụng các mô hình thanh toán: Trả trước (Reserved/Savings Plans), Tài nguyên dư thừa (Spot Instances) hoặc theo mức sử dụng thực tế (Serverless).
- Quản lý bằng công cụ: Cài đặt AWS Budgets để thiết lập cảnh báo, dùng AWS Pricing Calculator để dự toán trước dự án.

### Những Gì Học Được

#### Tư Duy Thiết Kế

- **Tư duy Builder & Troubleshooter:** Không chờ đợi "cầm tay chỉ việc", sẵn sàng đối mặt và tự khắc phục các sự cố hệ thống.
- **Spec-driven approach:** Bắt đầu bằng việc viết tài liệu kỹ thuật, kiến trúc và business rules (Steering files) rõ ràng trước khi yêu cầu AI viết code.
- **Cost-awareness:** Luôn gắn liền kiến trúc hệ thống với bài toán chi phí. Giá trị của một kỹ sư không chỉ ở việc "làm hệ thống chạy được" mà còn là "giúp doanh nghiệp tiết kiệm tiền".

#### Kiến Trúc Kỹ Thuật

- **Thiết kế High Availability (HA) & Disaster Recovery (DR):** Hiểu cách cấu trúc ứng dụng tối thiểu trên 2 AZs để đảm bảo uptime, và dùng Multi-Region để phòng ngừa thảm họa.
- **Tối ưu trải nghiệm với Edge Computing:** Biết khi nào nên đẩy các dữ liệu tĩnh (hình ảnh, video) ra các Edge Location qua CloudFront thay vì bắt user tải trực tiếp từ Region.
- **Tự động hóa bằng Custom AI Agents:** Cách phân mảnh các tác vụ (Code Review, Security Check, DevOps) cho các Agent cụ thể thông qua MCP Server để tránh tình trạng Hallucination (ảo giác) ở AI do quá tải context.

#### Chiến Lược Hiện Đại Hóa

- **Chuyển dịch sang Serverless:** Cân nhắc thay thế hệ thống máy chủ ảo (EC2) truyền thống bằng Serverless đối với các ứng dụng có lượng truy cập biến động mạnh để tối ưu chi phí.
- **Áp dụng Well-Architected Framework:** Biến việc dùng framework này thành một thói quen để đánh giá, sinh báo cáo (report) và cải thiện hệ thống hiện tại định kỳ.

### Ứng Dụng Vào Công Việc

- **Cải thiện bảo mật cá nhân/công ty:** Lập tức thiết lập MFA cho Root User, chuyển sang dùng IAM User và xóa/xoay vòng (rotate) các Access Keys có nguy cơ lộ lọt.
- **Kiểm soát ngân sách dự án:** Cài đặt AWS Budgets và thiết lập Billing Alarm qua email/SMS để tránh tình trạng phát sinh chi phí "ngầm" do quên tắt dịch vụ.
- **Thích ứng với công cụ AI mới:** Tải và trải nghiệm Kiro IDE/CLI. Xây dựng thử một dự án nhỏ sử dụng tính năng "Spec-driven" và thử tạo "Agent Hook" tự động gen ra Changelog mỗi khi save code.
- **Review kiến trúc:** Dùng AWS Well-Architected tool trên console để quét và đánh giá thử mức độ tối ưu của một dịch vụ đang chạy trong công ty.

### Trải Nghiệm Trong Event

Tham gia vào các nội dung đầu tiên của "First Cloud AI Journey" là một trải nghiệm mở mang tầm mắt, giúp tôi định hình được cách học tập và làm việc trên môi trường Cloud kết hợp AI. Một số trải nghiệm nổi bật:

- **Học hỏi từ cộng đồng:** Sự chia sẻ nhiệt tình từ diễn giả của AWS Study Group, không chỉ dạy về kỹ thuật mà còn dạy về "mindset" làm nghề và tinh thần "no sharing, no growing".
- **Thay đổi cách nhìn về thực hành:** Các bài lab yêu cầu phải tự build "from scratch" thay vì chỉ click theo hướng dẫn có sẵn giúp tôi hiểu sâu bản chất hệ thống.
- **Kinh ngạc trước sức mạnh của Kiro:** Xem các demo về Kiro Autonomous Agent và Custom Agent giúp tôi hình dung được tương lai của lập trình viên sẽ làm việc "cùng" với AI như một đồng nghiệp thực thụ.

### Bài Học Rút Ra

- Công nghệ Cloud và GenAI đang thay đổi cực nhanh, việc tích hợp AI (như Kiro) vào quá trình phát triển không còn là lựa chọn phụ trợ mà là yếu tố bắt buộc để tăng hiệu suất.
- Làm Cloud không chỉ là biết dùng dịch vụ, mà phải biết "Cost Optimization". Kỹ năng tối ưu hóa chi phí chính là một trong những giá trị cạnh tranh lớn nhất của Cloud Engineer.
- Tinh thần "teamwork", tính bền bỉ ("resilience") và việc tự giác thực hành liên tục qua các dự án thực tế là chìa khóa duy nhất để tiến xa trên con đường trở thành chuyên gia AWS.

### Hình Ảnh Sự Kiện

![Hình Ảnh 1](/images/event1-1.png)

![Hình Ảnh 2](/images/event1-2.png)

![Hình Ảnh 3](/images/event1-3.png)
