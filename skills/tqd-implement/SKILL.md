---
name: tqd-implement
description: "Bước 4/7 của tqd-coding-workflow, do tqd-start điều phối sau khi plan đã được duyệt. Viết code thật đúng theo plan đã duyệt, từng phase một, sửa ở gốc vấn đề, không để code giả hay TODO."
---

# tqd-implement — Viết code theo plan đã duyệt (Bước 4/7)

Đây là bước **viết chương trình thật**. Bạn không cần tự gõ code — trợ lý làm đúng theo kế hoạch (plan) bạn đã duyệt ở bước 3, lần lượt từng phần nhỏ.

Phase là một phần nhỏ trong kế hoạch: làm xong phần này rồi mới sang phần kế.

## Mục tiêu bước này

- Làm xong **tất cả phase** nằm trong plan đã duyệt, đúng thứ tự, không bớt không thêm.
- Code **chạy thật**: bấm/chạy được, không phải khung rỗng hay đoạn "làm sau".
- Người dùng luôn biết đang ở phase nào, vừa xong gì, sắp làm gì.
- Nếu plan thiếu hoặc sai: dừng lại hỏi, không tự ý mở rộng.

## Cách làm (từng bước)

1. **Bám đúng plan đã duyệt, từng phase một.** Mở plan vừa được duyệt. Làm phase 1, rồi 2, rồi 3... Không nhảy lung tung, không làm trước phase sau, không chèn việc ngoài plan.

2. **Trước khi gõ phím, nói ngắn cho người dùng.** 2-3 câu: phase này tên gì, sẽ sửa/tạo gì, người dùng sẽ thấy kết quả gì. Đây là thông báo, không phải hỏi duyệt lại — plan đã duyệt rồi. Mỗi lượt chỉ hỏi người dùng **một** việc, và chỉ hỏi khi thật sự cần (xem bước 5).

3. **Sửa ở gốc, làm thật, cập nhật hết chỗ liên quan.**
   - Sửa đúng chỗ gây ra vấn đề, không che giấu lỗi (ví dụ tắt cảnh báo, nuốt lỗi im lặng, viết đoạn tạm cho qua).
   - Không để code giả: hàm rỗng, chuỗi mẫu, placeholder (đoạn chờ trống), hay dòng TODO (ghi chú "làm sau").
   - Nếu đổi tên, đổi cách dùng, hay đổi một mảnh: cập nhật **hết** chỗ đang dùng nó. Cắt đoạn cũ không dùng nữa.

4. **Sau mỗi phase, tóm tắt rồi mới đi tiếp.** Nói ngắn: đã làm gì, file/màn hình nào đổi, kết quả thấy được (ví dụ nút đã bấm được, trang đã mở). Rồi mới bắt đầu phase tiếp theo. Không gom nhiều phase vào một lúc.

5. **Plan thiếu hoặc sai thì dừng lại.** Nếu phát hiện plan thiếu bước, sai, hoặc mơ hồ đến mức không biết làm gì: **dừng**, hỏi người dùng **một** câu (ví dụ: "Plan chưa nói X. Bạn muốn bổ sung vào plan hay bỏ X?"). Không tự thêm tính năng, không đoán giúp, không tự sửa plan rồi code tiếp.

## Khi nào xong -> báo về người điều phối

Xong khi **mọi phase trong phạm vi đã duyệt** đã được code thật, không còn chỗ trống, và phần vừa làm có thể chạy/bấm thử được.

Chưa xong nếu: còn phase trong plan chưa làm, còn TODO/hàm rỗng, hoặc vừa tự thêm việc ngoài plan.

Không làm bước test ở đây. Khi đã xong, nói 1-2 câu tóm tắt cho người dùng, rồi **báo kết quả về người điều phối (`tqd-start`)** và đề nghị sang bước 5 (`tqd-test`). Không tự kích hoạt skill khác — người điều phối sẽ chuyển bước.

## Ranh giới

- Không làm ngoài plan đã duyệt (không "tiện tay" thêm tính năng, viết lại lớn, hay trang trí thêm).
- Không để lại code giả, placeholder, hàm rỗng, hay TODO.
- Không tự merge (gộp vào nhánh chính) hay deploy (đưa ứng dụng lên máy thật / internet).
- Không bỏ qua bước 5-7: xong code thì báo về người điều phối để sang `tqd-test`, không tự soát code, không tự đẩy code, không tự tạo PR (lời mời gộp code — thuộc bước 7).
- Không đợi người dùng tự gõ lệnh máy hay tự viết code. Trợ lý làm; chỉ hỏi khi plan vỡ.
- Không lộ secret (mật khẩu, token, khóa API).
