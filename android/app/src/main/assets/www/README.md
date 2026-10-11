# Tủ Đồ Ảo — PWA

## Bản cập nhật v8
- Thêm bộ lọc người mặc trong Tủ đồ: Tất cả, Đồ nam, Đồ nữ, Unisex.
- Khi thêm món đồ, chọn nhãn người mặc ngay trong biểu mẫu.
- Trang chi tiết cho phép đổi nhãn người mặc của từng món; thay đổi được lưu trong dữ liệu localStorage.
- Dữ liệu cũ chưa có nhãn được gán mặc định `unisex` để không làm mất hoặc ẩn món đồ.
- Nâng phiên bản cache Service Worker lên `tudoao-v8` để trình duyệt tải bản mới.

## Triển khai
Giải nén thư mục `tudoao-pwa` và triển khai toàn bộ thư mục lên hosting HTTPS. Mở lại ứng dụng; nếu vẫn thấy bản cũ, đóng ứng dụng rồi mở lại để Service Worker cập nhật.

## Lưu ý
Ứng dụng lưu dữ liệu ở trình duyệt trên thiết bị. Đây là bản PWA mẫu, chưa có đồng bộ đám mây giữa nhiều thiết bị.
