# SHIN AIOS v2 — Demo 5 màn hình (chỉ thêm code mới)

## Phạm vi
- **Tổng quan:** sử dụng nguyên trạng màn hình và logic hiện có.
- **Tiến độ:** xem, tìm, lọc công trường, thêm/sửa/xóa WBS, tăng tiến độ 10%, lọc KPI.
- **Vật tư 4 bên:** xem, tìm, lọc, thêm/sửa/xóa phiếu, đánh dấu xác nhận demo của bốn vai trò.
- **Nhật ký:** xem, tìm, lọc, thêm/sửa/xóa nhật ký thi công, ghi chú HSE.
- **Cài đặt:** sử dụng nguyên trạng Settings Sheet hiện có (theme, palette, font, rail, bottom nav).

## Chạy thử
1. Giải nén ZIP.
2. Mở `preview_shin_aios_v2_demo.html` trên trình duyệt, hoặc chạy `python3 -m http.server 5500` trong thư mục giải nén rồi truy cập `http://localhost:5500/preview_shin_aios_v2_demo.html`.
3. Thử 5 tab: Hôm nay, Nhật ký, Tiến độ, Vật tư 4B, Cài đặt.
4. Nhấn nút tia sét trên Header để vào Trung tâm Phê duyệt gốc.
5. Dữ liệu ba màn hình mới lưu trong localStorage, khóa `shin_v2_complete_demo_20261103`. Có nút xuất JSON và reset demo (bấm 2 lần trong 5 giây).

## Tệp mới
- `css_demo_v2.html`: CSS bổ sung, dùng tokens của SHIN.
- `js_demo_v2.html`: mã mở rộng và dữ liệu demo, không sửa code gốc.
- `preview_shin_aios_v2_demo.html`: **bản sao dựng để chạy thử** từ preview gốc, có chèn hai add-on mới. Không thay thế `preview.html` trong repo.

## Nguyên tắc bảo toàn
**Không sửa, xóa hoặc ghi đè bất kỳ file code cũ nào.** Tích hợp điều hướng chỉ thực hiện trong runtime của bản preview. Không tự động thay đổi `Index.html`, `Code.gs`, `js_shin_core.html` hoặc các file hiện hữu. Để triển khai GAS, cần bổ sung entrypoint mới hoặc xin phép sửa điểm include; không tự ý sửa.

## Giới hạn và kiểm thử
- Dữ liệu là mô phỏng, không đồng bộ giữa thiết bị, không phải xác nhận pháp lý, chưa có GPS/ảnh thực tế.
- Tổng quan và Cài đặt vẫn là code gốc; mức độ đáp ứng quy chuẩn UI/UX ở hai màn hình này phụ thuộc bản gốc.
- Đã kiểm tra cú pháp JavaScript (`node --check`). **Chưa kiểm thử trực quan trình duyệt tự động** vì môi trường không có executable Chromium; cần kiểm tra 320/360/390/414px và đủ 15 tiêu chí SHIN trước nghiệm thu.
- Không push lên GitHub. Khi push: fetch/pull, tạo branch mới, chỉ commit file mới, fetch lại, kiểm tra conflict và xin xác nhận nếu có conflict.