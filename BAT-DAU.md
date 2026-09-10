# Bắt đầu nhanh — tqd-coding-workflow

Gói kỹ năng tiếng Việt giúp **người chưa biết code** đi hết một task phần mềm qua 7 bước.
Trợ lý sẽ dẫn bạn từng bước, mỗi lượt chỉ hỏi/làm một việc.

## Cài đặt

Gói là một file ZIP độc lập: `tqd-coding-workflow-vi.zip`. Giải nén rồi cài theo host của bạn.

- **OMP**: đặt thư mục `tqd-coding-workflow/` vào thư mục skill (ví dụ `~/.omp/agent/skills/`) hoặc nạp động bằng `--plugin-dir`.
- **Claude Code**: thêm làm plugin (thư mục có `.claude-plugin/plugin.json`), rồi dùng `--plugin-dir` hoặc cài qua marketplace của bạn.
- **Codex**: cài làm plugin skill (thư mục có `plugin.json`), skill sẽ hiện trong catalog với tiền tố `$tqd-coding-workflow:`.

Kiểm tra: host phải thấy 8 skill — `tqd-start` và 7 bước `tqd-*`.

## Dùng như thế nào

Chỉ cần nói với trợ lý, ví dụ:

> "Tôi muốn làm một trang web to-do list nhỏ." — rồi gọi `tqd-start`.

Trợ lý (người điều phối `tqd-start`) sẽ lần lượt dẫn qua bảy bước:

1. **tqd-brainstorm** — hỏi để hiểu bạn muốn gì, so sánh vài cách làm.
2. **tqd-plan** — viết kế hoạch chia thành các phase nhỏ.
3. **tqd-plan-approval** — đưa kế hoạch cho bạn **đọc và duyệt**. Bạn có thể sửa.
4. **tqd-implement** — code đúng theo kế hoạch đã duyệt.
5. **tqd-test** — chạy thử để chắc phần vừa làm chạy đúng.
6. **tqd-code-review** — soát lại lỗi và chất lượng.
7. **tqd-ship** — đóng gói và mở Pull Request (khi bạn đồng ý).

Mỗi bước làm xong sẽ **báo về người điều phối**, rồi người điều phối chuyển sang bước kế — bạn không phải tự gọi từng skill.

## Điều quan trọng

- Ở **bước 3**, trợ lý sẽ **dừng lại chờ bạn duyệt** trước khi code. Đọc kỹ, sửa nếu cần, rồi nói "duyệt" (hoặc "OK, làm đi").
- Ở **bước 7**, việc đẩy code lên và tạo PR chỉ xảy ra khi bạn đồng ý — và đồng ý **đẩy lên** với đồng ý **mở PR** là hai lần hỏi riêng. Trợ lý không bao giờ tự merge hay deploy.
- Tất cả skill đều bắt đầu bằng `tqd-`. Gói này độc lập, không phụ thuộc AgentKit hay namespace `ak:`.
