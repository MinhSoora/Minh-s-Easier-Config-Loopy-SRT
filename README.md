# Minh's Easier Config Loopy SRT

Trình tạo file `config.ini` trực quan cho [Loopy SRT Stats Monitor](https://github.com/loopy750/SRT-Stats-Monitor) — công cụ tự động chuyển scene trong OBS Studio khi luồng SRT/RTMP mất kết nối, dùng phổ biến trong livestream IRL.

Đây là một trang HTML tĩnh, chạy hoàn toàn trên trình duyệt (không server, không cần cài đặt, không gửi dữ liệu đi đâu cả). Thay vì tự tay sửa từng dòng trong `config.ini`, bạn điền form và trang sẽ sinh ra file đúng định dạng.

## Cách dùng

1. Mở file `minhs-easier-config-loopy-srt.html` bằng trình duyệt bất kỳ (double-click là chạy, không cần internet sau khi tải trang lần đầu).
2. Đi qua từng mục ở thanh bên trái, điền thông tin theo đúng thiết lập OBS / máy chủ của bạn. Mỗi trường đều có tên gốc trong `config.ini` và một dòng giải thích ngắn bên dưới.
3. Panel bên phải (hoặc nút **Xem config.ini** trên điện thoại) hiển thị file `config.ini` được sinh ra theo thời gian thực.
4. Bấm **Tải config.ini** để tải file, hoặc **Sao chép** để dán trực tiếp vào file có sẵn.
5. Đặt file vào `Documents\Loopy SRT Monitor\config.ini`, ghi đè lên file mẫu `config.default.ini`.

Chưa biết bắt đầu từ đâu? Vào tab **Hướng dẫn cài đặt** trong trang — có quy trình 7 bước và phần hỏi-đáp.

## Các mục trong trang

| Mục | Tương ứng section trong `config.ini` | Bắt buộc? |
|---|---|---|
| Cấu hình chung | `[config]` | Có |
| WebSocket & OBS | `[config]` (phần WebSocket) + `[obs-websocket-http]` | Có |
| SRT Live Server | `[srt-live-server]` | Chỉ nếu dùng SLS |
| NGINX RTMP | `[nginx-rtmp-module]` | Chỉ nếu dùng NGINX |
| Datarhei Restreamer | `[datarhei-restreamer]` | Chỉ nếu dùng Restreamer |
| Đa camera | `[multi-camera-switch]` | Tuỳ chọn |
| Bitrate thấp | `[low-bitrate]` | Tuỳ chọn |
| Nâng cao | `[advanced]` + `[undocumented]` | Tuỳ chọn |

Bạn chỉ cần bật **một** trong ba nguồn phát (SLS / NGINX / Restreamer) nếu có dùng máy chủ trung chuyển riêng; nếu OBS nhận SRT trực tiếp thì bỏ qua cả ba, chỉ cần đúng tên Media Source ở mục Cấu hình chung.

## Ghi chú

- Trang không lưu dữ liệu lại giữa các lần mở — đóng trình duyệt là mất, nên tải file `config.ini` về máy trước khi đóng.
- Mật khẩu WebSocket và mật khẩu Restreamer chỉ tồn tại trong bộ nhớ trình duyệt của bạn, không gửi đi bất cứ đâu.
- Tài liệu chính thức: [github.com/loopy750/SRT-Stats-Monitor](https://github.com/loopy750/SRT-Stats-Monitor).

## File trong bộ này

- `minhs-easier-config-loopy-srt.html` — trang công cụ chính, mở bằng trình duyệt.
- `README.md` — file này.
