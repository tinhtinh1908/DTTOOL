# Devices — Xiaomi / Redmi China

Mỗi mã model có một file `<MODEL>.json`. `index.json` liệt kê file và SHA-256. Snapshot ngày 2026-10-31 gồm 128 mã model, bao phủ 113 codename có bản ROM China HyperOS 2, 3 hoặc 4 ghi nhận trong HyperOS.fans trước hoặc đúng ngày này, gồm điện thoại và máy tính bảng. Phạm vi đối chiếu dựa trên các nguồn đã ghi nhận, không bao gồm thiết bị chưa được nguồn công bố.

## Nhận diện

`model` là mã chứng nhận/model, ví dụ `2410DPN6CC`; `codenames` là tên dùng trong ROM, ví dụ `haotian`. Hai loại mã khác nhau; một codename có thể có nhiều biến thể. `market` luôn `CN`; không thay bằng mã POCO/Global/India.

`hyperos` liệt kê phiên bản lớn có bằng chứng ROM China, không phải cam kết nâng cấp tương lai. `sources.roms` ghi snapshot dữ liệu gốc [HyperOS.fans](https://hyperos.fans/zh/devices/), đường dẫn codename và ROM làm bằng chứng. Mi 11 Pro dùng chung firmware `star` với Ultra; alias ghi rõ trong file.

HyperOS.fans không cung cấp đầy đủ mã chứng nhận model: nguồn này xác minh codename/ROM; mã model được đối chiếu riêng với MobileModels. Các mã dạng `Mxxxxx` giữ nguyên cách ghi của nguồn, không tự đổi thành mã chứng nhận có hậu tố `C`.

## Thông số

`specs` chỉ phục vụ tab Thông tin: kích thước, loại, độ phân giải và tần số quét màn hình; camera chính/siêu rộng/tele/trước; loại RAM và bộ nhớ; Wi-Fi, Bluetooth, USB; dung lượng và loại pin. Tên công nghệ giữ tiếng Anh chuẩn.

Dung lượng RAM/bộ nhớ thực tế phải đọc từ máy đang cắm, không gán dung lượng một SKU cho mọi máy cùng model. Máy gập chỉ mô tả màn hình chính khi xác minh được.

Thiếu bằng chứng hoặc mâu thuẫn: bỏ trường khỏi `specs`, ghi ở `missing_fields`/`conflicts`. `None` nghĩa là nguồn xác nhận không có camera đó; trường bị bỏ trống nghĩa là chưa xác minh. Không coi thiếu thông số là lỗi kết nối hoặc chặn cài đặt. Không suy ra thành phần pin từ tên thương mại “Jinshajiang”. Một số model mới còn thiếu trường; không phải mọi file đã đủ thông số.

## Nguồn và ghi công

- [KHwang9883/MobileModels](https://github.com/KHwang9883/MobileModels): mã model, codename, tên và chú thích RAM/UFS theo mã. Nguồn CC BY-NC-SA 4.0; phần nhận diện chuyển đổi giữ điều kiện đó. Giấy phép đầy đủ trong `licenses/MobileModels-CC-BY-NC-SA-4.0.txt`.
- [HegeKen/HyperData](https://github.com/HegeKen/HyperData): dữ liệu gốc HyperOS.fans để đối chiếu codename và ROM China. Nguồn GPL-3.0; bản giấy phép trong `licenses/HyperData-GPL-3.0.txt`. Chỉ trích dữ kiện ROM cần đối chiếu, không sao chép mã chương trình.
- [Fatty911/crawl_phones](https://github.com/Fatty911/crawl_phones): dữ kiện China từ ZOL/PConline/CNMO, snapshot `6c36718cc2e972233b70fbfd2d82ec67e483ad0c`.
- [bytecharts/device_specs_gsmarena](https://github.com/bytecharts/device_specs_gsmarena): dữ kiện phần cứng chọn lọc. Đối chiếu mã kèm tên tương thích, bản China chỉ rõ hoặc họ máy chỉ có mã China trong snapshot nhận diện. Không suy đoán chỉ từ codename/tên gần giống; nguồn có thể gán nhầm mã.
- Bảng sản phẩm China của ZOL và tin ra mắt từ IT之家: URL trong từng file. Chỉ trích dữ kiện cho các trường trên, không kèm bài viết, ảnh, giá bán hay đánh giá.

Các nguồn phần cứng không có giấy phép tái phân phối rõ trong repository đã kiểm tra; công khai không đồng nghĩa giấy phép thương mại tự do. Thông báo này không cấp quyền đối với nội dung bên thứ ba. Commit/SHA-256 ghi trong index và từng file; không có sự bảo chứng của Xiaomi hoặc tác giả nguồn.

## Cập nhật

Sửa đúng file model, giữ `market: CN`, cập nhật nguồn và `field_sources`, tính lại SHA-256 trong index. Không đổi tên file thành codename; không thêm serial/IMEI, trạng thái root, bootloader hoặc ngày kích hoạt.

Trong source DT TOOL, chạy `app/scripts/update-device-catalog.cjs --from <đường-dẫn-Devices>` để kiểm tra toàn bộ file, checksum/schema rồi thay snapshot offline. Không có `--from` thì dùng đúng commit repository đã ghim trong snapshot. Công cụ cập nhật không chạy khi đổi tab/cắm điện thoại.
