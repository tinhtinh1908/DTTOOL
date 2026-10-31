# DT TOOL — danh sách lệnh

OS3 và OS4 có hai file riêng:

| File | Nội dung |
|---|---|
| `adb.json` | Tên hiển thị → lệnh Android, không thêm `adb shell` |
| `apps.json` | Tên hiển thị → package, tool tự chọn gỡ hoặc tắt |

`apps.json` đã gộp 89 package duy nhất từ danh sách người dùng. Không còn chia `go.json` và `tat.json`.

Tool bỏ qua package không có hoặc đã tắt, giữ bàn phím đang dùng và thành phần lõi. Với package còn hoạt động, tool gỡ cho user 0 và giữ dữ liệu (`-k`). Nếu Android báo rõ lỗi chặn gỡ, tool thử `disable-user`. Cả hai đường đều đọc lại trạng thái; lỗi ADB hoặc kết quả chưa xác nhận không được coi là thành công và không tự chuyển thao tác.

Danh sách là lựa chọn của người dùng, không phải chứng nhận mọi package đều vô hại khi gỡ. Không tự thực thi khi tải/cập nhật danh sách; Auto setup chỉ chạy khi người dùng khởi động tác vụ.
