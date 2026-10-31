# Devices

Máy Xiaomi/Redmi nội địa China có ROM HyperOS 2–4, đối chiếu đến 2026-10-31. **122 file tên máy, 128 mã model.**


Cấu trúc:

- `name`: tên máy.
- `models`: mã model để nhận diện chính xác.
- `codenames`: codename để kiểm tra đúng thiết bị.
- `specs`: thông số dùng trong tab Thông tin.
- `variants`: chỉ xuất hiện khi các mã model cùng tên có thông số khác nhau; phần này bổ sung vào thông số chung của đúng mã.
- `conflicts`: chỉ xuất hiện khi có trường chưa xác định do nguồn mâu thuẫn.

Các khóa thông số: `display_size`, `display_type`, `resolution`, `refresh_rate`, `ram`, `storage`, `camera_main`, `camera_ultrawide`, `camera_tele`, `camera_front`, `wifi`, `bluetooth`, `usb`, `battery`, `battery_chemistry`.

Giá trị `""` là chưa xác minh, để trống cho người dùng tự điền; không xóa khóa. `None` là nguồn xác nhận không có camera đó. `battery_chemistry` dành cho loại pin, ví dụ `Li-Po` hoặc `Si/C Li-Ion`. RAM/bộ nhớ ở đây là loại LPDDR/UFS/eMMC; dung lượng thực tế vẫn đọc từ máy đang cắm. Không lấy thông số Global để điền cho China. Máy gập mô tả màn hình chính khi xác minh được.

`index.json` chỉ liệt kê file và ngày cập nhật. Không cần tự tính checksum khi sửa. Tool cập nhật từ commit Git đã ghim hoặc nhập thư mục bằng `app/scripts/update-device-catalog.cjs --from <Devices>`; dùng snapshot offline khi chạy.

## Nguồn

- [HyperOS.fans / HegeKen/HyperData](https://hyperos.fans/zh/devices/): đối chiếu codename và ROM China, snapshot `56fea64c4a7ccd97fb6d6daf7ac51c671bfc7728`. Không phải nguồn đầy đủ mã chứng nhận model. Nguồn công bố GPL-3.0; giấy phép trong `licenses/HyperData-GPL-3.0.txt`.
- [KHwang9883/MobileModels](https://github.com/KHwang9883/MobileModels): mã model, codename và chú thích RAM/UFS theo mã, snapshot `2618dbf1fb9a79b451d7423b08592653e660e3f1`. Phần nhận diện chuyển đổi giữ giấy phép CC BY-NC-SA 4.0; bản đầy đủ trong `licenses/MobileModels-CC-BY-NC-SA-4.0.txt`.
- [Fatty911/crawl_phones](https://github.com/Fatty911/crawl_phones), snapshot `6c36718cc2e972233b70fbfd2d82ec67e483ad0c`; [bytecharts/device_specs_gsmarena](https://github.com/bytecharts/device_specs_gsmarena), snapshot `8be80e6dca116988484fb968add3d7a50e5f844b`; bảng sản phẩm China của ZOL và tin ra mắt từ IT之家: chỉ trích dữ kiện phần cứng, không kèm bài viết, ảnh hoặc giá. Các repository phần cứng không công bố giấy phép tái phân phối rõ trong bản đã kiểm tra; việc công khai không cấp quyền thương mại với nội dung bên thứ ba.

[Nguồn chi tiết từng mã và bằng chứng ROM trước khi tối giản](https://github.com/tinhtinh1908/DTTOOL/tree/18c090d8fc6278ca2e311f59be01d8f761b3357a/Devices) vẫn được giữ trong lịch sử Git. Bản tối giản bỏ thông tin nguồn lặp, danh sách trường thiếu và metadata dài; giữ nguyên các thông số đã có và khác biệt giữa biến thể. Không có sự bảo chứng từ Xiaomi hoặc tác giả nguồn.
