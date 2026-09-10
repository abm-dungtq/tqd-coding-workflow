---
name: tqd-test
description: "Bước 5/7 của tqd-coding-workflow, do tqd-start điều phối sau khi code xong. Chạy test thật hoặc mở lên bấm thử để xem phần vừa làm có chạy đúng không, rồi báo về người điều phối kết quả pass hay còn lỗi."
---

# tqd-test — Chạy thử phần vừa làm (Bước 5/7)

Đây là bước **chạy thử** sau khi đã code. Bạn không cần biết lập trình: mục đích chỉ là xem phần vừa thay đổi có làm đúng việc hay không, bằng **bằng chứng thật** (kết quả chạy), không phải đoán.

## Mục tiêu bước này

- Có bằng chứng phần vừa làm **chạy đúng**.
- Nếu là sửa lỗi: tái hiện lỗi trước, sửa, rồi chắc lỗi **không còn**.
- Nếu fail: quay lại code để sửa, rồi test lại — chưa sang soát code.
- Chỉ khi test/chạy thử **pass** mới chuyển bước 6.

## Cách làm (từng bước)

1. **Giải thích 1 câu, rồi làm.** *Test* là chạy thử để kiểm tra code làm đúng việc — giống thử bật đèn xem nó sáng thật, không chỉ nhìn dây điện. Mỗi lượt chỉ yêu cầu người dùng **một** việc.

2. **Nếu dự án đã có bộ test** (bộ test = tập kiểm tra sẵn, máy tự chạy và báo đúng/sai): chỉ chạy **phần liên quan đến thay đổi**. Đọc kết quả: *pass* = tốt; *fail* / *error* = chưa xong. Không cần chạy hết cả bộ nếu chỉ đổi một phần nhỏ.

3. **Nếu chưa có test sẵn: mở lên bấm thử phần vừa làm.** Chạy đúng đường vừa thay đổi (ví dụ mở trang, bấm nút, nhập thử) và xem kết quả có đúng như plan mong đợi không. Đây là *smoke test* — thử nhanh xem có "bốc khói" chỗ nào không.

4. **Nếu là sửa lỗi:** làm lại đúng thao tác từng gây lỗi, chắc chắn lỗi đã hết. Nếu tiện, giữ lại một bài test nhỏ cho lỗi đó (chạy trước khi sửa thì fail, sau khi sửa thì pass) để sau này lỡ hỏng lại thì biết ngay.

5. **Nói kết quả bằng tiếng thường.** Ví dụ: "Đã bấm thử nút Lưu, ghi chú hiện ra đúng." hoặc "Còn lỗi: trang trắng khi mở." Không giấu fail, không nói "chắc là được".

## Khi nào xong -> báo về người điều phối

Xong khi phần vừa thay đổi đã **chạy thật** và cho kết quả đúng (test pass, hoặc bấm thử ra đúng).

Nếu **pass**: nói 1-2 câu kết quả cho người dùng, rồi **báo về người điều phối (`tqd-start`)** và đề nghị sang bước 6 (`tqd-code-review` — đọc kỹ xem có lỗi, điểm yếu, hoặc vô tình phá cái cũ).

Nếu còn **lỗi**: **không** đề nghị sang review. Báo về người điều phối là còn lỗi, cần quay lại `tqd-implement` (bước 4 ở trên), sửa xong rồi test lại ở đây. Không tự kích hoạt skill khác — người điều phối sẽ chuyển bước.

## Ranh giới

- Không báo "xong" khi chưa thực sự chạy.
- Không viết test giấy / test giả / test chỉ để "có test". Test thật phải **chạy thật**.
- Không đoán "chắc là đúng"; không bỏ qua fail.
- Không đề nghị sang `tqd-code-review` hay `tqd-ship` khi test còn fail.
- Không tự ý viết thêm tính năng trong lúc test; chỉ kiểm tra phần vừa thay đổi.
- Không tự kích hoạt skill khác, chỉ báo về người điều phối.
