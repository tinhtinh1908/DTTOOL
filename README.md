# DT TOOL — danh sách lệnh

OS3 và OS4 dùng các thư mục độc lập. Mỗi thư mục có ba file JSON gọn:

| File | Nội dung |
|---|---|
| `adb.json` | Tên hiển thị → lệnh Android |
| `go.json` | Tên hiển thị → package cần gỡ |
| `tat.json` | Tên hiển thị → package cần tắt |

Các file hiện để `{}`, chưa có lệnh nào.

## Ví dụ adb.json

```json
{
  "Đọc mã máy": "getprop ro.product.model",
  "Cho phép sửa cài đặt": "appops set com.android.shell WRITE_SETTINGS allow"
}
```

Không thêm tiền tố `adb shell`. Lệnh cần JAR/APK chỉ chạy được khi tài nguyên đó đã có sẵn; danh sách này không tự đẩy file.

## Ví dụ go.json hoặc tat.json

```json
{
  "Tên ứng dụng A": "com.example.appa",
  "Tên ứng dụng B": "com.example.appb"
}
```

