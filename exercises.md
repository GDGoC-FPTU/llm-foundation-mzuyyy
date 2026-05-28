# Ngày 1 — Bài Tập & Phản Ánh
## Nền Tảng LLM API | Phiếu Thực Hành

**Thời lượng:** 1:30 giờ  
**Cấu trúc:** Lập trình cốt lõi (60 phút) → Bài tập mở rộng (30 phút)

---

## Phần 1 — Lập Trình Cốt Lõi (0:00–1:00)

Chạy các ví dụ trong Google Colab tại: https://colab.research.google.com/drive/172zCiXpLr1FEXMRCAbmZoqTrKiSkUERm?usp=sharing

Triển khai tất cả TODO trong `template.py`. Chạy `pytest tests/` để kiểm tra tiến độ.

**Điểm kiểm tra:** Sau khi hoàn thành 4 nhiệm vụ, chạy:
```bash
python template.py
```
Bạn sẽ thấy output so sánh phản hồi của GPT-4o và GPT-4o-mini.

---

## Phần 2 — Bài Tập Mở Rộng (1:00–1:30)

### Bài tập 2.1 — Độ Nhạy Của Temperature
Gọi `call_openai` với các giá trị temperature 0.0, 0.5, 1.0 và 1.5 sử dụng prompt **"Hãy kể cho tôi một sự thật thú vị về Việt Nam."**

**Bạn nhận thấy quy luật gì qua bốn phản hồi?** (2–3 câu)
> Temperature thấp (0.0) thường cho câu trả lời rất chặt chẽ, lặp lại các sự thật phổ biến và ít biến thể.
> Khi tăng lên 0.5 → 1.0 → 1.5, câu trả lời trở nên đa dạng hơn, sáng tạo hơn, có thể cung cấp nhiều chi tiết bất ngờ hoặc cách diễn đạt khác nhau.

**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**
> Đối với chatbot hỗ trợ khách hàng, tôi sẽ đặt temperature thấp, khoảng 0.0–0.3, vì cần phản hồi ổn định, đáng tin cậy và giảm rủi ro trả lời sai hoặc quá sáng tạo.

---

### Bài tập 2.2 — Đánh Đổi Chi Phí
Xem xét kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người thực hiện 3 lần gọi API, mỗi lần trung bình ~350 token.

**Ước tính xem GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này:**
> GPT-4o: 5 + 20 = 25 USD / 1M token. 
> GPT-4o-mini: 0.150 + 0.600 = 0.75 USD / 1M token
> Do đó GPT-4o đắt hơn GPT-4o-mini khoảng:
 25 / 0.75 ≈ 33.3 lần

**Mô tả một trường hợp mà chi phí cao hơn của GPT-4o là xứng đáng, và một trường hợp GPT-4o-mini là lựa chọn tốt hơn:**
> GPT-4o xứng đáng khi cần chất lượng cao, suy luận phức tạp hoặc tạo nội dung sáng tạo trong những tình huống quan trọng, ví dụ đối thoại tư vấn chuyên sâu, phân tích dữ liệu hoặc xử lý ngôn ngữ tự nhiên phức tạp. GPT-4o-mini là lựa chọn tốt hơn khi cần xử lý khối lượng lớn, trả lời FAQ, hoặc dịch vụ hỗ trợ cơ bản, nơi chi phí thấp và tốc độ nhanh quan trọng hơn mức độ tinh vi tối đa.

---

### Bài tập 2.3 — Trải Nghiệm Người Dùng với Streaming
**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì non-streaming lại phù hợp hơn?** (1 đoạn văn)
> Streaming quan trọng nhất khi người dùng tương tác trực tiếp với chatbot và cần phản hồi nhanh, đặc biệt với các câu trả lời dài hoặc thời gian chờ cảm nhận được. Non-streaming phù hợp hơn khi đầu ra ngắn, xử lý batch hoặc khi cần kết quả hoàn chỉnh trước khi tiếp tục bước tiếp theo, vì nó đơn giản hơn và đủ tốt cho nhiều tình huống không yêu cầu hiển thị nội dung từng phần.


## Danh Sách Kiểm Tra Nộp Bài
- [ ] Tất cả tests pass: `pytest tests/ -v`
- [ ] `call_openai` đã triển khai và kiểm thử
- [ ] `call_openai_mini` đã triển khai và kiểm thử
- [ ] `compare_models` đã triển khai và kiểm thử
- [ ] `streaming_chatbot` đã triển khai và kiểm thử
- [ ] `retry_with_backoff` đã triển khai và kiểm thử
- [ ] `batch_compare` đã triển khai và kiểm thử
- [ ] `format_comparison_table` đã triển khai và kiểm thử
- [ ] `exercises.md` đã điền đầy đủ
- [ ] Sao chép bài làm vào folder `solution` và đặt tên theo quy định 
