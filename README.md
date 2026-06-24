# Welcome Board — Bảng chào mừng khách / đoàn

Bảng chào mừng hiển thị toàn màn hình (1920×1080) cho khách, đoàn kiểm tra, đoàn công tác, sinh viên thực tập… Tự chỉnh trực tiếp trên trình duyệt, không cần cài đặt gì.

🔗 **Demo:** https://<tên-github>.github.io/<tên-repo>/

---

## Tính năng

- **Chỉnh trực tiếp** — bấm nút **✎ Chỉnh sửa** (góc dưới phải) để thêm/bớt đơn vị, thêm/bớt người, sửa tên, chức vụ, vai trò.
- **Nhiều đơn vị / đoàn** — mỗi đơn vị là một khối có tiêu đề riêng.
- **3 kiểu thẻ** tự thích ứng:
  - Có vai trò → hiện huy hiệu (Trưởng Đoàn, Thành Viên…)
  - Chỉ chức vụ → thẻ gọn, căn hai đầu
  - Chỉ tên đơn vị (không có người) → hiện tên lớn, căn giữa
- **Tùy biến hiển thị** bằng công tắc gạt: hiện/ẩn chức vụ, hiện/ẩn vai trò, chức vụ xuống dòng hay căn sang phải.
- **Cỡ chữ & kiểu chữ** — Be Vietnam Pro, Montserrat, Playfair Display, Lora; phóng 70%–160%.
- **Màu chủ đạo** — 6 màu chọn sẵn, áp cho cả bảng hoặc **riêng từng người**.
- **Nhập từ Excel** — chọn file `.xlsx`, tự gom nhóm theo Tên công ty và lọc theo cột Ngày tháng.
- **Xuất PNG 1920×1080** — tải ảnh đúng độ phân giải để chiếu lên màn hình/TV.
- **Tự lưu** — mọi chỉnh sửa lưu trong trình duyệt, mở lại vẫn còn.

---

## Cách dùng

1. Mở link demo (hoặc mở `index.html` bằng trình duyệt).
2. Bấm **✎ Chỉnh sửa** để nhập danh sách, hoặc **📄 Chọn file Excel…** để nạp từ file.
3. Tinh chỉnh hiển thị (cỡ chữ, màu, kiểu chữ…) trong panel.
4. Bấm **⬇ Tải PNG 1920×1080** để xuất ảnh.

### Định dạng file Excel

File cần có hàng tiêu đề với các cột (tiếng Việt hoặc Anh đều nhận):

| Tên Công ty | Họ và tên khách | Chức vụ | Ngày tháng |
|-------------|-----------------|---------|------------|
| Company name | Guest's full name | Position | Date |

- Người được gom theo **Tên Công ty** thành từng khối.
- Cột **Ngày tháng** dùng để lọc — chọn ngày trong panel để hiện đúng nhóm hôm đó.

---

## Triển khai (GitHub Pages)

1. Đưa `index.html` lên nhánh `main`.
2. Vào **Settings → Pages → Source: Deploy from a branch → main / root → Save**.
3. Đợi khoảng 1 phút, truy cập `https://<tên-github>.github.io/<tên-repo>/`.

> **Lưu ý:** Xuất PNG cần có mạng (tải font lần đầu để nhúng vào ảnh).

---

## Ghi chú kỹ thuật

- Một file HTML tĩnh duy nhất — không backend, không build.
- Dữ liệu lưu bằng `localStorage` trên máy người dùng.
- Đọc Excel bằng [SheetJS](https://sheetjs.com/), xuất ảnh bằng [html-to-image](https://github.com/bubkoo/html-to-image).
