# Reflection — Lab 19

**Tên:** _<Họ Tên>_
**Cohort:** _<A20-K1 / A20-K2 / ...>_
**Path đã chạy:** _lite_

---

## Câu hỏi (≤ 200 chữ)

> Trên golden set 50 queries, mode nào thắng ở loại query nào (`exact` /
> `paraphrase` / `mixed`), và tại sao? Khi nào bạn **không** dùng hybrid
> (i.e. khi nào pure BM25 hoặc pure vector là lựa chọn đúng)?

Trên golden set 50 queries của em, hybrid (RRF) đạt Precision@10 trung bình cao
nhất: hybrid 78.6%, keyword 77.8%, semantic 73.2%. Theo từng loại query:
`exact` thì BM25 và hybrid gần như ngang nhau (đều rất cao), vì truy vấn chứa từ
khóa sát với tài liệu. `mixed` thì hybrid thắng rõ (100%), do kết hợp được tín
hiệu lexical và semantic. `paraphrase` trong run này BM25 vẫn nhỉnh hơn semantic,
cho thấy embedding model lite chưa bắt hết ngữ nghĩa tiếng Việt ở tập paraphrase.

Em không dùng hybrid khi cần hệ thống cực đơn giản hoặc chi phí/độ trễ phải tối
thiểu tuyệt đối: ví dụ search exact-match trong FAQ thì BM25 là đủ; hoặc bài toán
retrieval theo ngữ nghĩa thuần (không phụ thuộc từ khóa) thì pure vector có thể
phù hợp hơn. Hybrid phù hợp nhất khi query đa dạng và cần độ ổn định trên nhiều
kiểu truy vấn.

---

## Điều ngạc nhiên nhất khi làm lab này

_(Optional, 1–2 câu)_

---

## Bonus challenge

- [ ] Đã làm bonus (xem `bonus/`)
- [ ] Pair work với: _<tên đồng đội nếu có>_
