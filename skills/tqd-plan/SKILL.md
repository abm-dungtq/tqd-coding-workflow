---
name: tqd-plan
description: "Bước 2/7 của tqd-coding-workflow, do tqd-start điều phối sau khi đã chốt hướng ở brainstorm. Biến hướng đã chốt thành kế hoạch theo phase nhỏ, mỗi phase có task và bằng chứng xong, bằng ngôn ngữ người chưa biết code đọc và duyệt được. Chưa code."
---

# tqd-plan — Viết kế hoạch theo phase (Bước 2/7)

Bước này biến **hướng đã chốt** (quyết định ở bước 1) thành một kế hoạch ngắn, chia thành các *phase*. Phase là một đoạn việc nhỏ, có mục tiêu riêng, làm xong mới sang đoạn tiếp. Bạn chưa cần hiểu code: chỉ cần đọc được "làm gì trước, làm gì sau, làm sao biết là xong".

## Mục tiêu bước này

- Có một plan theo phase, rõ ràng, đủ để người dùng đọc và duyệt ở bước 3.
- Mỗi phase là một mục tiêu độc lập, kiểm tra được bằng bằng chứng cụ thể (chạy được, thấy kết quả trên màn hình, hoặc *test* pass — test là chạy thử để xem phần vừa làm có đúng không).
- Chỉ nằm trong phạm vi đã chốt ở `tqd-brainstorm`; không thêm tính năng mới.

## Cách làm (từng bước)

Đọc lại hướng đã chốt ở bước 1. Nếu hướng chưa chốt, dừng lại và báo về người điều phối để quay lại `tqd-brainstorm`. Nếu thiếu **một** thông tin để chia việc, hỏi người dùng **một** câu, rồi mới viết plan.

1. **Chia thành các phase nhỏ.** Mỗi phase = một mục tiêu độc lập, nhỏ đủ để kiểm tra. Đặt tên bằng tiếng Việt dễ hiểu (ví dụ "Hiện danh sách việc"), không đặt tên kiểu kỹ thuật. Ít phase hơn tốt hơn: đừng thêm phase nếu không cần.

2. **Trong mỗi phase, liệt kê task cụ thể.** Task là việc nhỏ cần làm. Với mỗi task ghi: làm gì, và ở file/phần nào nếu đã biết. Nếu chưa biết tên file, mô tả bằng ngôn ngữ thường (ví dụ "màn hình chính", "nút Thêm"). Không viết code.

3. **Với mỗi phase, ghi "Làm sao biết là xong".** Bắt buộc có bằng chứng người không biết code cũng thấy được, ví dụ:
   - Chạy được / mở được ứng dụng.
   - Thấy đúng kết quả trên màn hình (nút hiện, chữ hiện, trang mở ra).
   - Test pass (chạy thử tự động, kết quả đạt).
   Không dùng câu mơ hồ như "làm xong thì xong".

4. **Sắp xếp phase theo thứ tự phụ thuộc.** Cái gì phải xong trước thì đứng trước. Ghi rõ "cần xong Phase X" nếu phase sau nằm trên phase trước. Không ghép hai việc phụ thuộc nhau vào cùng một phase nếu không kiểm tra riêng được.

5. **Viết kế hoạch ra văn bản rõ ràng.** Dùng ngôn ngữ dễ hiểu cho người không rành kỹ thuật. Gặp từ kỹ thuật thì giải thích 1 câu rồi mới dùng. Dùng mẫu ngắn này:

   ```
   # Kế hoạch: <tên ngắn của việc>

   Phạm vi (đã chốt): <1-3 câu, lấy từ brainstorm>

   ## Phase 1: <tên>
   Mục tiêu: ...
   Phụ thuộc: không / cần xong Phase ...
   Task:
   - ...
   Làm sao biết là xong:
   - ...
   ```

   Sau khi viết xong, tóm tắt 1-2 câu cho người dùng: có bao nhiêu phase, phase đầu làm gì. **Chưa hỏi duyệt** — việc duyệt thuộc bước 3.

## Khi nào xong -> báo về người điều phối

Xong khi đã có văn bản plan đầy đủ: các phase đã chia, mỗi phase có task và "làm sao biết là xong", thứ tự phụ thuộc rõ, ngôn ngữ dễ đọc. Không cần người dùng đồng ý ở bước này.

**Báo kết quả ngắn gọn về người điều phối (`tqd-start`) và dừng**: nêu số phase và phase đầu, đề nghị sang bước 3 (`tqd-plan-approval`) để trình duyệt. Không tự kích hoạt skill khác — người điều phối sẽ chuyển bước.

## Ranh giới

- **Chưa code.** Không tạo file nguồn, không sửa code, không cài đặt thư viện.
- **Không thêm tính năng** ngoài phạm vi đã chốt ở `tqd-brainstorm`. Nếu người dùng muốn thêm, nhớ họ: quay lại bước 1 để chốt lại, hoặc giữ nguyên phạm vi.
- **Giữ plan gọn, không vẽ vời.** Không viết dài, không liệt kê hàng chục phase cho việc nhỏ, không vẽ kiến trúc thừa.
- Không tự chuyển sang code. Không hỏi "duyệt chưa" ở đây — đó là việc của `tqd-plan-approval`.
