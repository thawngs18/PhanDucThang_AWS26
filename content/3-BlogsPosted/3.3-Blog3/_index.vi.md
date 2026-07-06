---
title: "Blog 3"
date: 2026-07-06
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---


# AWS DevOps Agent Sử Dụng Multi-Agent Reasoning Để Tìm Nguyên Nhân Gốc Rễ

![AWS DevOps Agent Sử Dụng Multi-Agent Reasoning](/images/aws-devops-agent.png)

Chắc hẳn ai cũng từng trải qua cảnh này: Nửa đêm hệ thống báo lỗi, API trả về 500, bạn lao vào check log các container và thấy ngay một cái Exception quen quen. Dựa vào kinh nghiệm, bạn lập tức chốt luôn nguyên nhân, fix vội rồi deploy lại. Nhưng rốt cuộc, server vẫn sập.

Hiện tượng này gọi là "Confirmation Bias". Khi gặp sự cố, chúng ta thường có xu hướng bám lấy giả thuyết đầu tiên xuất hiện trong đầu, tìm được một bằng chứng ủng hộ là dừng lại ngay, khiến nguyên nhân gốc rễ thực sự bị bỏ sót.

Để giải quyết, AWS đã giới thiệu AWS DevOps Agent – một AI áp dụng kiến trúc "multi-agent reasoning". Nó không mò mẫm log một cách mù quáng, mà hoạt động bài bản như một SRE thực thụ.

## 1. Bí Quyết Cốt Lõi: Nắm Rõ Bản Đồ Hệ Thống (Topology Graph)

Trước khi bắt tay vào fix lỗi, AI không lao vào đọc log ngay. Việc điều tra hiệu quả bắt buộc phải xuất phát từ việc hiểu rõ bối cảnh kiến trúc của toàn bộ hệ thống.

AWS DevOps Agent tự động vẽ ra một bản đồ động (Topology Graph). Bản đồ này thể hiện rõ:
- Mối liên hệ giữa các service, database và các tài nguyên hạ tầng.
- Luồng giao tiếp thực tế của hệ thống khi đang chạy (runtime).
- Sự liên kết chặt chẽ với các pipeline CI/CD (như GitLab CI/CD, GitHub Actions) để biết chính xác đoạn code nào vừa được deploy.

Nếu không có nền tảng này, AI (và cả con người) sẽ chỉ ngụp lặn giữa một biển dữ liệu giám sát.

## 2. Vòng Đời 4 Bước Xử Lý Sự Cố Của AI Đa Đặc Vụ

Thay vì làm tất cả trong một bước, AWS DevOps Agent chia quy trình xử lý thành 4 giai đoạn chuyên biệt:

**Bước 1: Phân loại (Triage) – Ưu tiên tốc độ**
Khi hệ thống có biến, hàng tá cảnh báo từ CloudWatch, Grafana hay PagerDuty có thể đổ về cùng lúc. Agent lập tức phân tích và gom nhóm các tín hiệu báo lỗi liên quan lại với nhau thành một sự cố duy nhất. Việc này giúp giảm thiểu độ nhiễu, giúp anh em dev không bị "ngợp" và tập trung vào vấn đề cốt lõi. Tất nhiên, dev vẫn có toàn quyền kiểm soát: nếu thấy AI gom nhóm sai, bạn hoàn toàn có thể tách chúng ra để điều tra độc lập.

**Bước 2: Điều tra (Investigation) – Nghệ thuật tự phản biện**
Đây là lúc Agent thể hiện sức mạnh suy luận khác biệt hoàn toàn so với các AI truyền thống. Thay vì chỉ đi theo một hướng, Agent tạo ra nhiều giả thuyết cạnh tranh cùng một lúc. Nó sẽ đào bới dữ liệu để không chỉ tìm bằng chứng ủng hộ, mà còn chủ động tìm bằng chứng phản bác các giả thuyết đó.

Ví dụ: Nếu nó nghi ngờ lỗi do đợt cập nhật code gần nhất, nhưng phát hiện ra thay đổi đó chỉ là sửa định dạng log, nó sẽ tự động loại bỏ giả thuyết này và tập trung vào các nguyên nhân khác (như cạn kiệt connection pool của database). Nó chỉ chốt Root Cause khi bằng chứng đưa ra là không thể chối cãi.

**Bước 3: Giảm thiểu (Mitigation) – An toàn là trên hết**
Xác định được lỗi rồi, sửa thế nào cho an toàn? Agent sẽ tự động sinh ra một kế hoạch khắc phục cực kỳ chi tiết. Kế hoạch bao gồm: các bước thực hiện, tiêu chí xác nhận thành công, và quan trọng nhất là kịch bản khôi phục (rollback) để đảo ngược tình thế nếu có biến.

Điểm đáng tiền: Agent KHÔNG tự ý can thiệp vào hệ thống (không có quyền write). Nó chỉ đóng vai trò cố vấn, đưa ra đề xuất. Quyền quyết định nhấn nút thực thi vẫn nằm trong tay bạn.

**Bước 4: Phòng ngừa (Prevention) – Biến thụ động thành chủ động**
Hệ thống AI không chỉ giải quyết sự cố bề nổi mà còn nhóm các lỗi trong quá khứ lại để tìm ra quy luật chung. Nhờ phân tích chéo, nó có thể phát hiện ra rằng hàng loạt các lỗi timeout hay API phản hồi chậm thực chất đều bắt nguồn từ một cấu hình sai ở database.

Từ đó, Agent đề xuất các giải pháp mang tính kiến trúc: tinh chỉnh lại hạ tầng, viết thêm test case, hoặc thêm các rào chắn kiểm tra vào luồng CI/CD để ngăn lỗi này vĩnh viễn không lặp lại.

---
**Tóm tắt:** AWS DevOps Agent đang thay đổi cách ta vận hành hệ thống. Bằng cách ủy thác việc rà soát log, vẽ bản đồ kiến trúc và đối chiếu bằng chứng cho AI, các kỹ sư Backend và DevOps có thể thoát khỏi những đêm thức trắng dò lỗi thủ công. Bạn sẽ bước vào quá trình fix bug với một tâm thế tự tin hơn, bởi mọi giả thuyết đều đã được kiểm chứng bằng data thực tế, kèm theo một lối thoát hiểm an toàn.

**Tài liệu tham khảo:** [How AWS DevOps Agent uses multi-agent reasoning to find root causes](https://aws.amazon.com/blogs/devops/how-aws-devops-agent-uses-multi-agent-reasoning-to-find-root-causes/)

---
