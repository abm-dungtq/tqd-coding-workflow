# Người điều phối kích hoạt bước kế theo từng host

Gói `tqd-coding-workflow` chạy trên nhiều host. **Chỉ người điều phối (`tqd-start`) kích hoạt các bước con.** Dùng đúng cơ chế skill-native của host đang chạy — **không** đọc file SKILL.md của bước con bằng đường dẫn tương đối, và **không** in một câu lệnh ra cho người dùng tự gõ.

| Host | Cách kích hoạt bước con (ví dụ `tqd-brainstorm`) |
|------|--------------------------------------------------|
| **OMP** | Đọc tài nguyên `skill://tqd-brainstorm`. |
| **Claude Code** (plugin) | Gọi công cụ Skill với `tqd-coding-workflow:tqd-brainstorm`. |
| **Codex** (plugin) | Chọn `$tqd-coding-workflow:tqd-brainstorm` trong catalog skill và nạp toàn bộ body. |
| **Cài lẻ (loose skill)** | Dùng định danh đã đăng ký không có namespace: `tqd-brainstorm`. |

Quy tắc chung:

- Mỗi lần chuyển bước, **người điều phối** kích hoạt skill của bước kế tiếp bằng bảng trên, rồi chờ bước đó báo kết quả về. Bước con không tự kích hoạt bước khác.
- Nếu host báo không tìm thấy skill bước con, **dừng lại và báo rõ** cho người dùng (lỗi cài đặt gói), không tự bịa ra kết quả.
- Các skill trong gói đều có tiền tố `tqd-`. Không dùng namespace `ak:`.
