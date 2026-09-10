---
name: tqd-ship
description: "Bước 7/7 của tqd-coding-workflow, do tqd-start điều phối sau khi đã review sạch. Đóng gói: tóm tắt thay đổi, lưu mốc commit, xin đồng ý riêng cho push và riêng cho mở Pull Request; không bao giờ tự merge hay deploy."
---

# tqd-ship — Đóng gói và mở Pull Request (Bước 7/7)

Đây là **bước cuối**. Việc của bước này là **đóng gói** những gì vừa làm thành một mốc rõ ràng, rồi — **chỉ khi bạn đồng ý** — gửi lên máy chủ chung và mở lời đề nghị để người khác xem rồi gộp vào bản chính.

Ba từ sẽ gặp: **commit** = lưu lại một mốc thay đổi trên máy bạn. **push** = đẩy code lên máy chủ chung (ví dụ GitHub). **PR / Pull Request** = đề nghị gộp thay đổi của mình vào code chính để người khác xem và đồng ý.

## Mục tiêu bước này

- Người dùng hiểu sẽ gộp những gì, bằng lời thường, trước khi lưu.
- Thay đổi đã được **commit** với lời nhắn rõ (mốc đã lưu trên máy).
- Khi người dùng đồng ý: đã **push** và đã có **PR** (kèm link) để người khác review/gộp.
- Không bao giờ tự gộp vào nhánh chính, không bao giờ tự đưa lên môi trường thật.

## Cách làm (từng bước)

1. **Tóm tắt những gì sẽ được gộp.** Đọc phần vừa làm (sau test và review). Nói với người dùng bằng tiếng Việt ngắn: đã thêm/sửa/xóa chức năng gì, file nào liên quan, còn sót việc gì không. Mỗi lượt chỉ hỏi **một** việc: "Phần tóm tắt này đúng chưa?" Chưa đúng thì sửa tóm tắt, chưa commit.

2. **Commit — lưu một mốc thay đổi.** Khi tóm tắt đã ổn: kiểm tra không có **secret** (mật khẩu, token, khóa API — giải thích: thông tin bí mật không được đưa lên máy chủ). Gom đúng file của việc này, không gom file linh tinh. Viết lời nhắn commit ngắn, rõ, nói *đã làm gì* (ví dụ: "Thêm trang danh sách việc cần làm"). Lưu mốc. Báo người dùng: đã lưu xong trên máy, chưa gửi đi đâu cả.

3. **Xin đồng ý riêng cho việc push.** Đây là hành động **chạm máy chủ chung** — cho nhiều người cùng thấy. Giải thích: bước này sẽ *push* (đẩy code lên). Hỏi một câu, ví dụ: "Bạn có muốn đẩy code lên máy chủ chung không?" **Dừng** nếu chưa có lời đồng ý rõ (có / đồng ý / OK, đẩy lên...). Không suy ra đồng ý từ im lặng hay từ việc đã duyệt plan ở bước 3. Sự đồng ý này chỉ dùng cho lần push này, không dùng lại cho việc khác.

4. **Sau khi push xong, xin đồng ý riêng cho việc mở PR.** Push và mở PR là **hai việc khác nhau, đồng ý riêng từng việc**. Khi đã push, hỏi thêm một câu: "Đã đẩy lên xong. Bạn có muốn mở Pull Request (đề nghị gộp vào bản chính) không?" Chỉ mở PR khi có lời đồng ý rõ cho riêng việc này. Khi được đồng ý: mở Pull Request với tiêu đề và mô tả ngắn tiếng Việt (gộp gì, đã test/review chưa, cần người xem chú ý gì). Đưa **link PR** và tóm tắt 3-5 dòng cho người dùng. Nếu không tạo được PR, nói rõ lỗi bằng tiếng thường; không tự lặp lại hành động chạm máy chủ.

5. **Không bao giờ tự gộp hay tự đưa lên production.** **Merge** = gộp PR vào code chính. **Deploy / production** = đưa bản đó lên chỗ người dùng thật dùng. Bước này **không làm** hai việc đó trên bất kỳ đường nào — dừng ở PR đang mở. Nếu người dùng muốn merge hay deploy, nói rõ đó là việc ngoài quy trình 7 bước này và cần làm riêng, có người chịu trách nhiệm.

## Khi nào xong -> hết quy trình

Bước này **xong** khi một trong hai việc đã xảy ra:

- Đã có **PR** (có link), hoặc
- Người dùng **chọn dừng ở commit** (đã lưu mốc trên máy, không push, hoặc push rồi nhưng không mở PR).

**Đây là bước 7/7 — hết quy trình.** Không kích hoạt skill nào nữa; báo kết quả cuối về người điều phối (`tqd-start`).

Trước khi kết thúc, tóm tắt cả bảy bước cho người dùng, mỗi ý một câu:

1. Brainstorm — đã chốt muốn làm gì.
2. Plan — đã có kế hoạch từng phần.
3. Duyệt plan — người dùng đã chấp nhận.
4. Implement — đã code theo plan đã duyệt.
5. Test — đã chạy thử phần vừa làm.
6. Review — đã soát lại.
7. Ship — đã commit; và (nếu đồng ý) đã push và có PR.

Nói kết quả cụ thể của bước 7: lời nhắn commit, đã push hay chưa, link PR hoặc lý do dừng ở máy. Nếu người dùng muốn làm việc mới, báo người dùng gọi lại `tqd-start`. Không tự bắt đầu task mới.

## Ranh giới

- Không **push** khi chưa được người dùng đồng ý rõ cho riêng việc push.
- Không **tạo PR** khi chưa được người dùng đồng ý rõ cho riêng việc mở PR. Đồng ý push không phải là đồng ý mở PR.
- Không tự **merge** vào nhánh chính, không tự **deploy** lên production — trên mọi đường, kể cả khi người dùng "giục cho nhanh".
- Không commit **secret**: mật khẩu, token, khóa API, file `.env` có bí mật, chứng chỉ. Nếu thấy, dừng, nói cho người dùng, không đưa vào mốc.
- Không thêm việc ngoài phạm vi đã duyệt. Không sửa code mới ở bước này trừ khi chặn được việc lộ secret hoặc commit nhầm file — và phải nói trước.
- Không bịa link PR. Không báo "đã gửi" khi chưa push thành công.
