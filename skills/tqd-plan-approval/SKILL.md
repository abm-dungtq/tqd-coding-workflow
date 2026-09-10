---
name: tqd-plan-approval
description: "Bước 3/7 của tqd-coding-workflow, do tqd-start điều phối sau khi đã có plan. Cổng duyệt trước khi code: trình plan bằng ngôn ngữ dễ hiểu, DỪNG LẠI cho người dùng đọc, duyệt hoặc sửa; tuyệt đối không code trước khi có đồng ý rõ ràng."
---

# tqd-plan-approval — Cổng duyệt kế hoạch (Bước 3/7)

Đây là **cổng chặn** trước khi viết code: đưa kế hoạch (plan: bản viết ở bước 2, nói sẽ làm gì) cho người **chưa biết code** đọc, hiểu, và **duyệt**.
Chưa có lời nói duyệt = **chưa được code**. Bước này quan trọng nhất cho người mới — dừng lại và chờ.

## Mục tiêu bước này

- Người dùng hiểu sẽ làm gì, không làm gì, và thứ tự các phase (phase: một đoạn nhỏ trong kế hoạch, xong đoạn này mới sang đoạn sau).
- Có **sự đồng ý rõ ràng bằng lời nói** của người dùng về đúng bản plan vừa trình.
- Nếu chưa ưng ý: sửa plan rồi trình duyệt lại, không bỏ qua, không tự chốt.
- Trợ lý **dừng lượt này** sau khi trình plan — không tự code, không đoán là đã duyệt.

## Cách làm (từng bước)

1. **Trình plan bằng ngôn ngữ dễ hiểu.**
   Nếu chưa có plan (chưa qua `tqd-plan`), đừng tự bịa. Báo về người điều phối rằng cần kế hoạch trước.
   Nếu đã có plan, dịch sang tiếng Việt đơn giản. Tóm tắt ngắn, đúng thứ tự:
   - Làm gì, cho ai dùng, xong sẽ thấy gì.
   - Thứ tự các phase: mỗi phase **một câu**, đúng thứ tự sẽ code.
   - Phần **không** làm trong lần này (nếu plan có ghi).
   Giải thích mỗi từ kỹ thuật bằng 1 câu trước khi dùng. Không dán hết file kỹ thuật. Mỗi lượt chỉ hỏi người dùng **một** việc.

2. **Nói rõ việc người dùng cần làm.**
   Sau phần tóm tắt, chỉ nói **một** câu (không hỏi thêm điều khác):
   > Hãy đọc kỹ. Nếu ưng ý, trả lời **duyệt** (hoặc "OK, làm đi") để bắt đầu code. Nếu muốn đổi, nói rõ chỗ nào chưa ưng.
   Không thêm nút, lệnh, hay hướng dẫn cài đặt host.

3. **DỪNG LẠI và chờ người dùng trả lời.**
   Kết thúc lượt ngay sau bước 2. **Không** viết code, **không** tạo/sửa file, **không** cài thư viện, **không** chạy lệnh, **không** "chuẩn bị sẵn" phần code.
   Nếu người dùng hỏi thêm về plan: trả lời ngắn, rồi hỏi lại đúng một câu ở bước 2, và **chờ tiếp**.
   Không chuyển sang bước code trong cùng lượt với lời mời duyệt. Chưa có câu trả lời duyệt = chưa được đi tiếp.

4. **Nếu người dùng muốn sửa: báo về người điều phối để quay lại `tqd-plan`.**
   Sửa = chưa ưng, thêm, bớt, đổi thứ tự, đổi phạm vi, hoặc "ok nhưng đổi X".
   Chưa xong bước 3. Không sửa plan một mình rồi tự coi như đã duyệt.
   Báo cho người điều phối (`tqd-start`) là người dùng muốn sửa; người điều phối sẽ kích hoạt lại `tqd-plan`. Khi plan mới xong, quay lại skill này, trình lại từ đầu (bản mới), rồi chờ duyệt tiếp.

5. **Chỉ khi người dùng nói duyệt mới sang bước code.**
   Chấp nhận khi lời nói **rõ ràng đồng ý bắt đầu code**, ví dụ: "duyệt", "OK làm đi", "làm đi", "đồng ý", "bắt đầu code".
   Sau khi đã hỏi rõ ở bước 2, câu ngắn "OK" / "ok" **đứng một mình** (không kèm điều kiện) cũng tính là duyệt.
   **Chưa đủ:** im lặng, khen chung ("hay"), hỏi thêm, duyệt mỗi một phần, "làm luôn" khi chưa đọc tóm tắt, hoặc "ok nhưng..." (về bước 4).
   Nếu mơ hồ: hỏi lại **một** câu — "Bạn duyệt plan này để bắt đầu code chưa?" — rồi chờ.

## Khi nào xong -> báo về người điều phối

**Xong** chỉ khi người dùng **đã duyệt** đúng bản plan vừa trình.

- Nếu **chưa duyệt** hoặc đang **chờ trả lời**: ở lại đây, không đi tiếp.
- Nếu **muốn sửa**: chưa xong bước này. Báo người điều phối để quay lại `tqd-plan`, không sang code.
- Nếu **đã duyệt**: nói 1 câu "Plan đã duyệt, sắp code đúng theo plan này." Rồi **báo về người điều phối (`tqd-start`)** là đã duyệt, đề nghị sang bước 4 (`tqd-implement`). Không tự kích hoạt bước code — người điều phối sẽ chuyển bước.

## Ranh giới

- **Không code trước duyệt.** Không tạo file, không cài gói, không chạy lệnh "cho nhanh".
- **Không tự suy diễn đã duyệt.** Chỉ lời nói rõ ràng mới được. Im lặng không phải duyệt.
- **Không bỏ qua bước này**, dù task rất nhỏ hay người dùng giống như muốn "làm luôn".
- **Không đổi plan sau duyệt** rồi vẫn đi code. Plan đổi = trình duyệt lại.
- **Không hỏi nhiều việc một lúc.** Sau khi trình, chỉ đợi duyệt hoặc chờ sửa.
- Không tự kích hoạt skill khác, chỉ báo về người điều phối. Không in câu lệnh đặc thù của một host cho người dùng tự gõ.
