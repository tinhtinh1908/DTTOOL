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

Tên ở bên trái hiển thị trong tool. Giá trị bên phải là lệnh hoặc package. File quyết định thao tác: `go.json` để gỡ, `tat.json` để tắt.

Thêm mục bằng dấu phẩy giữa các dòng; dòng cuối không có dấu phẩy. Không cần ID, type, trường thời gian chờ hay cấu trúc lồng nhau.

Sửa file trong đúng thư mục OS, bấm **Commit changes**, rồi **Cập nhật** trong tool. Tool chỉ chạy các mục người dùng chọn và bấm Chạy.

Lệnh từ repo được quản lý và ẩn nội dung trong giao diện/nhật ký. Lệnh người dùng tự thêm được lưu riêng trên PC, hiển thị rõ và không gửi lên repo. Repo này công khai; việc ẩn chỉ là cách hiển thị trong ứng dụng.
