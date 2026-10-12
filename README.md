# NAS Cam TV — bản phát hành

Ứng dụng Android TV để xem camera trên TV:

- Camera của Synology Surveillance Station: đăng nhập bằng QuickConnect ID hoặc địa chỉ IP của NAS
- Camera RTSP/ONVIF kết nối thẳng, không cần NAS
- Overlay camera ở góc màn hình trong lúc đang xem app khác, mở bằng giọng nói hoặc phím tắt trên remote

Repo này chỉ chứa tệp APK để cài đặt và cập nhật, không chứa mã nguồn.

## Cài lần đầu

1. Tải `NasCamTV-x.y.z.apk` ở [bản phát hành mới nhất](https://github.com/vonamhai/nascamtv-releases/releases/latest).
2. Cài lên TV bằng một trong hai cách:
   - Bật gỡ lỗi ADB trên TV, rồi chạy `adb connect <IP của TV>` và `adb install NasCamTV-x.y.z.apk`
   - Chép APK vào USB hoặc gửi qua app Send Files to TV, rồi mở bằng trình quản lý tệp trên TV
     (TV sẽ hỏi quyền cài ứng dụng không rõ nguồn gốc cho trình quản lý tệp đó)

Cần Android TV hoặc Google TV chạy Android 6.0 trở lên.

## Cập nhật

App tự kiểm tra bản mới khoảng 6 giờ một lần. Khi có bản mới, nút ở đầu danh sách camera đổi thành
**Cập nhật x.y.z**: chọn nút đó, app tải APK từ đây rồi mở trình cài đặt của TV.

Lần cập nhật đầu tiên, TV hỏi quyền cài ứng dụng không rõ nguồn gốc cho NAS Cam TV, chỉ cần bật một lần.
Tài khoản và camera đã lưu được giữ nguyên sau khi cập nhật.