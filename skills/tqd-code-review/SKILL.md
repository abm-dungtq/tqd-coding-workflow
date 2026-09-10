---
name: tqd-code-review
description: "Bước 6/7 của tqd-coding-workflow, do tqd-start điều phối sau khi test đã pass. Đọc phần vừa đổi bằng mắt người kiểm tra: bắt lỗi còn sót, regression, và soát secret; rồi báo về người điều phối là sạch hay còn vấn đề chặn."
---

# tqd-code-review — Soát lại code (Bước 6/7)

Bước này là **kiểm tra**, không phải viết thêm tính năng. Nhìn lại phần vừa đổi bằng mắt người kiểm tra: đúng chưa, sạch chưa, có làm hỏng chỗ khác không. Người dùng không cần đọc file kỹ thuật — trợ lý soát rồi nói bằng tiếng thường.

## Mục tiêu bước này

- Chắc phần vừa làm vẫn đúng ý đã duyệt, không sót lỗi nghiêm trọng.
- Không làm hỏng tính năng cũ. *Regression* là sửa chỗ này mà vô tình hỏng chỗ khác.
- Code dễ đọc, dễ bảo trì; không lộ *secret* (token, mật khẩu, khóa API) trong code.

## Cách làm (từng bước)

1. **Đọc lại những gì đã thay đổi** với con mắt "người kiểm tra", không phải người vừa viết. Chỉ xem phần vừa dựng ở bước implement. Tóm tắt cho người dùng bằng 1-2 câu tiếng thường; mỗi lượt chỉ hỏi họ **một** việc (nếu cần hỏi).

2. **Kiểm tra ba việc này:**
   - Có làm hỏng tính năng cũ không (regression)?
   - Có đúng ý đã duyệt ở plan không, hay đã lệch/thêm ngoài phạm vi?
   - Có lộ secret, hoặc còn code giả / TODO / đoạn tạm sót lại không?

3. **Nói rõ kết quả bằng tiếng thường.** Ví dụ: "Soát xong, ổn, không đụng tính năng cũ." hoặc "Có vấn đề: chỗ này còn quên xử lý khi bỏ trống ô nhập." Nếu thấy vấn đề chặn, nói rõ đó là gì.

## Khi nào xong -> báo về người điều phối

Xong khi đã soát phần vừa đổi và kết luận rõ: **sạch** (không vấn đề chặn) hay **còn vấn đề chặn**.

Nếu **sạch**: tóm tắt 1-2 câu cho người dùng, rồi **báo về người điều phối (`tqd-start`)** và đề nghị sang bước 7 (`tqd-ship`).

Nếu **còn lỗi**: **không** đề nghị sang ship. Báo về người điều phối là còn vấn đề chặn, cần quay lại `tqd-implement` (rồi test lại) như bước 4. Không tự kích hoạt skill khác — người điều phối sẽ chuyển bước.

## Ranh giới

- Không bỏ qua vấn đề nghiêm trọng để cho "xong".
- Không tự đổi phạm vi code (không thêm tính năng, không "sửa luôn cho đẹp" ngoài plan đã duyệt).
- Không sửa code ngay trong bước này — sửa thuộc `tqd-implement`.
- Không ship, không đẩy code, không mở Pull Request (kéo code lên chỗ dùng chung) — việc đó thuộc `tqd-ship`.
- Không bắt người dùng đọc diff hay file kỹ thuật.
- Không tự kích hoạt skill khác, chỉ báo về người điều phối.
