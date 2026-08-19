# Reflection — Lab 19

**Tên:** Đinh Xuân Huy
**Cohort:** A20
**Path đã chạy:** lite

---

## Câu hỏi (≤ 200 chữ)

> Trên golden set 50 queries, mode nào thắng ở loại query nào (`exact` /
> `paraphrase` / `mixed`), và tại sao? Khi nào bạn **không** dùng hybrid
> (i.e. khi nào pure BM25 hoặc pure vector là lựa chọn đúng)?

- **Exact queries:** Pure BM25 thắng hoặc tương đương vì đối sánh từ khóa chính xác (mã lỗi, tên riêng, thuật ngữ kỹ thuật) mà không phụ thuộc vào biểu diễn ngữ nghĩa.
- **Paraphrase queries:** Semantic (vector search) vượt trội nhờ khả năng nắm bắt ý định và ngữ cảnh người dùng khi từ ngữ được diễn đạt lại.
- **Mixed queries & Tổng thể:** Hybrid Search (kết hợp BM25 + Vector qua RRF k=60) đạt Precision@10 cao nhất và ổn định nhất, tận dụng điểm mạnh của cả hai.
- **Khi không dùng Hybrid:** Không dùng khi hệ thống yêu cầu độ trễ cực thấp/tiết kiệm tài nguyên CPU/RAM (pure BM25 nhanh và nhẹ hơn), hoặc khi tìm kiếm dữ liệu đặc thù như mã sản phẩm, SKU, số điện thoại (chỉ cần pure BM25). Ngược lại, với dữ liệu đa ngôn ngữ/ý định trừu tượng không có từ khóa cứng, pure vector là lựa chọn tối ưu.

---

## Điều ngạc nhiên nhất khi làm lab này

RRF (Reciprocal Rank Fusion) cực kỳ đơn giản nhưng lại dung hòa hiệu quả hai không gian điểm số hoàn toàn khác biệt của BM25 và Vector Cosine Similarity mà không cần chuẩn hóa phức tạp.

---

## Bonus challenge

- [ ] Đã làm bonus (xem `bonus/`)
- [ ] Pair work với:
