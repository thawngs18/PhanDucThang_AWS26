---
title: "Worklog Tuần 10"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

* Nâng cấp tính năng mô phỏng tấn công với khả năng áp dụng biện pháp phòng thủ và chạy lại kịch bản (Re-run Attack).
* Cải thiện trải nghiệm người dùng thông qua giao diện hacker overlay trực quan với animation và tooltip thông minh.
* Tối ưu logic xử lý phía Frontend và Backend để đảm bảo luồng mô phỏng hoạt động ổn định.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Xây dựng hàm `reRunWithDefense` trong `useStore.js` để chạy lại mô phỏng với defense measures <br> - Bổ sung endpoint `/api/simulation/run-with-defense` trong `main.py` xử lý yêu cầu kèm phòng thủ <br> - Viết `SIMULATION_WITH_DEFENSE_PROMPT` trong `ai_service.py` để AI phân tích tấn công bị chặn | 22/06/2026 | 22/06/2026 | <https://fastapi.tiangolo.com/tutorial/> |
| 3   | - Thiết kế thành phần `HackerOverlay` với icon Shield động khi attack bị blocked, Skull khi đang tấn công <br> - Thêm animation pulse và blur effect tạo hiệu ứng hacker terminal chân thực <br> - Hiển thị step progress (Step X/Y) và target node ID trong overlay <br> - Tích hợp hiển thị `blocking_detail` khi attack bị chặn bởi phòng thủ | 23/06/2026 | 23/06/2026 | <https://react.dev/reference/react/memo> |
| 4   | - Viết hàm `resolveAnimationSteps` trong `useStore.js` parse attack path từ AI thành các bước animation riêng biệt <br> - Xây dựng `formatResultBody` định dạng kết quả mô phỏng thành text block có indentation <br> - Lập trình `normalize_node` trong `main.py` xử lý đa dạng format AI response (flat và nested) <br> - Bổ sung type mapping trong `normalize_node` chuyển node types từ AI về đúng format frontend | 24/06/2026 | 24/06/2026 | <https://developer.mozilla.org/en-US/docs/Web/JavaScript> |
| 5   | - Thiết kế và triển khai defense tooltip hover trong `CustomNode.jsx`: ATTACK ATTEMPT (đỏ) vs HOW IT WAS BLOCKED (xanh) <br> - Cải thiện `CanvasFlow.jsx` với tính năng xóa edges bằng phím Delete/Backspace khi được chọn <br> - Triển khai thuật toán smart handle positioning trong `onNodeDrag` tự động điều chỉnh connection points | 25/06/2026 | 25/06/2026 | <https://reactflow.dev/docs/api/edge-common-props/> |
| 6   | - Xử lý edge cases: animation state được reset đúng sau hoàn thành hoặc lỗi <br> - Fix logic `reRunWithDefense`: đóng modal hiện tại trước khi bắt đầu animation mới <br> - Thêm validation cho node type mapping xử lý type không mong đợi từ AI <br> - Đảm bảo edge styling (color, width) reset về default sau simulation | 26/06/2026 | 26/06/2026 | <https://zustand.docspm.invalid/> |

### Kết quả đạt được tuần 10:

* Tính năng Re-run Attack với Defense Measures hoạt động hoàn chỉnh — người dùng áp dụng phòng thủ và xem kịch bản tấn công bị chặn tại điểm nào.
* Giao diện Hacker Overlay mang lại trải nghiệm hacker terminal chân thực với animation pulse, icon động và hiển thị từng bước tấn công.
* Defense Tooltip giúp người dùng hiểu rõ cơ chế tấn công/phòng thủ qua giao diện so sánh trực quan.
* Toàn bộ luồng simulation từ gửi topology đến AI → animate các bước → hiển thị kết quả hoạt động ổn định.
