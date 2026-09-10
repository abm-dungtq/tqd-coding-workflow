---
name: tqd-brainstorm
description: "Bước 1/7 của tqd-coding-workflow, do tqd-start điều phối. Làm rõ ý tưởng khi người dùng còn mơ hồ chưa chốt muốn gì: hỏi để hiểu kết quả cuối, ràng buộc, so sánh 2-3 hướng, gợi ý cách đơn giản nhất, rồi chốt hướng trước khi viết plan. Chưa viết plan, chưa code."
---

# tqd-brainstorm — Làm rõ ý tưởng (Bước 1/7)

Đây là bước đầu tiên: **chưa viết kế hoạch, chưa code**. Bạn chỉ cần hiểu người dùng (chưa biết code) thực sự muốn **thấy gì khi xong**, rồi chốt **một hướng làm** đủ rõ để sang bước plan (plan = bản kế hoạch chia nhỏ việc).

## Mục tiêu bước này

- Chốt **làm cái gì**: kết quả cuối người dùng muốn thấy, bấm, hoặc dùng được.
- Chốt **hướng nào**: dùng một cách làm, không để 2-3 hướng treo.
- Gom đủ 4 ý để viết plan: kết quả mong muốn, ràng buộc, không làm gì, bằng chứng hoàn thành.
- Nói bằng tiếng thường; gặp từ kỹ thuật thì giải thích 1 câu rồi mới dùng.

## Cách làm (từng bước)

Mỗi lượt chỉ hỏi người dùng **một** việc. Không hỏi dồn.

1. **Hỏi lại mục tiêu cuối.** Một câu: "Khi xong, bạn muốn thấy gì?" Nếu họ đã kể tính năng hoặc lỗi, lặp lại bằng 1 câu ngắn để họ gật đầu / sửa. Chưa hỏi công nghệ.

2. **Hỏi ràng buộc quan trọng.** Ràng buộc = điều kiện bắt buộc phải theo. Chỉ hỏi cái chưa biết, mỗi lượt một câu, theo thứ tự:
   - Gấp không (hôm nay / tuần này / không gấp)?
   - Đã có sẵn cái gì (trang, app, file, máy chủ)?
   - Muốn chạy ở đâu (trình duyệt, điện thoại, máy tính)?
   Bỏ qua câu nào người dùng đã trả lời.

3. **Nếu có 2-3 hướng làm khả thi**, liệt kê ngắn. Không đưa quá 3 hướng. Mỗi hướng gồm:
   - 1 câu: làm theo cách này là gì (tiếng thường)
   - 1 câu ưu
   - 1 câu nhược
   - 1 câu: nên chọn khi nào
   Nếu chỉ 1 hướng hợp lệ: nói rõ vì sao, không bịa thêm hướng.

4. **Gợi ý hướng đơn giản nhất** vẫn đạt mục tiêu. KISS = ưu tiên cách ngắn, dễ hiểu, ít phần hơn. Nói 1 câu vì sao gợi ý hướng đó, rồi hỏi chốt: "Bạn chọn hướng này hay hướng khác?" **Chờ câu trả lời.** Không tự chốt.

5. **Chỉ hỏi khi thực sự thiếu.** Nếu mục tiêu, ràng buộc và hướng đã rõ: **không hỏi thêm**. Tóm tắt 4 ý rồi đi tiếp:
   - Kết quả mong muốn
   - Ràng buộc
   - Không làm gì (việc nằm ngoài, người dùng không nhờ)
   - Bằng chứng hoàn thành = dấu hiệu để biết là xong (ví dụ: "mở trang ra, bấm nút X, thấy Y")

Sau khi người dùng chốt (hoặc yêu cầu đã rõ), giữ 4 ý đó trong hội thoại — đây là đầu vào cho `tqd-plan`. Không thêm chi tiết kỹ thuật lúc này.

## Khi nào xong -> báo về người điều phối

Xong khi **đã chốt hướng**: người dùng đã chọn hoặc xác nhận một cách làm, và 4 ý (kết quả, ràng buộc, không làm gì, bằng chứng xong) đã được nói rõ.

Chưa xong nếu: vẫn chưa biết "xong thì thấy gì", còn 2 hướng song song, hoặc người dùng chưa trả lời câu hỏi chốt.

Khi đã chốt, **báo kết quả ngắn gọn về người điều phối (`tqd-start`) và dừng**: nêu hướng đã chốt và 4 ý, đề nghị sang bước 2 (`tqd-plan`). Không tự nhảy sang bước khác — người điều phối sẽ kích hoạt bước kế tiếp.

## Ranh giới

- Không code, không tạo/sửa file, không cài đặt, không chạy lệnh.
- Không quyết định chi tiết kỹ thuật sâu (tên file, thư viện, kiến trúc) — để `tqd-plan`.
- Không tự bịa yêu cầu người dùng không nói. Thiếu thì hỏi, không đoán.
- Không nhảy sang plan khi chưa chốt hướng; không tự kích hoạt skill khác, chỉ báo về người điều phối.
- Không hỏi dồn; không dùng namespace `ak:`.
