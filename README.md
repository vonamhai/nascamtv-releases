# TV Camera Overlay — bản phát hành

Ứng dụng Android TV để xem camera trên TV (tên cũ: NAS Cam TV):

- Camera của Synology Surveillance Station: đăng nhập bằng QuickConnect ID hoặc địa chỉ IP của NAS
- Camera RTSP/ONVIF kết nối thẳng, không cần NAS; quét mạng để tìm camera
- Overlay camera ở góc màn hình trong lúc đang xem app khác, mở bằng giọng nói hoặc phím tắt trên remote
  (gán nút bằng app miễn phí tvQuickActions); bố cục 2–4 camera cùng lúc trong một overlay
- Giao diện 11 ngôn ngữ, theo ngôn ngữ của TV (ngôn ngữ chưa có thì dùng tiếng Anh)

Repo này chỉ chứa tệp APK để cài đặt và cập nhật, không chứa mã nguồn.

## Cài lần đầu

1. Tải `TVCameraOverlay-x.y.z.apk` ở [bản phát hành mới nhất](https://github.com/vonamhai/nascamtv-releases/releases/latest).
2. Cài lên TV bằng một trong hai cách:
   - Bật gỡ lỗi ADB trên TV, rồi chạy `adb connect <IP của TV>` và `adb install TVCameraOverlay-x.y.z.apk`
   - Chép APK vào USB hoặc gửi qua app Send Files to TV, rồi mở bằng trình quản lý tệp trên TV
     (TV sẽ hỏi quyền cài ứng dụng không rõ nguồn gốc cho trình quản lý tệp đó)

Cần Android TV hoặc Google TV chạy Android 6.0 trở lên.

## Cập nhật

App tự kiểm tra bản mới khoảng 6 giờ một lần. Khi có bản mới, nút **Cập nhật** trên thanh trên cùng (màn hình
chọn nguồn và danh sách camera) đổi thành **Cập nhật x.y.z**: chọn nút đó, app tải APK từ đây rồi mở trình cài
đặt của TV.

Lần cập nhật đầu tiên, TV hỏi quyền cài ứng dụng không rõ nguồn gốc cho TV Camera Overlay, chỉ cần bật một lần.
Tài khoản và camera đã lưu được giữ nguyên sau khi cập nhật.

## Chuyển từ NAS Cam TV

TV Camera Overlay (từ bản 2.0.0) dùng gói mới `com.tvcameraoverlay` nên Android coi là app khác. NAS Cam TV
(1.3.1 trở xuống) vẫn báo có bản mới nhưng tải xong báo "APK không phải NAS Cam TV", không tự cập nhật được.
Chuyển sang bằng tay, một lần:

1. Cài TV Camera Overlay như mục **Cài lần đầu**. Hai app chạy song song, dữ liệu không tự chuyển sang.
2. Trong TV Camera Overlay: đăng nhập NAS, thêm lại camera RTSP/ONVIF, cấp quyền overlay và micro.
3. Gán lại phím tắt trên remote vì phím tắt cũ vẫn mở app cũ: app hướng dẫn dùng tvQuickActions
   (Overlay › Gán nút remote), Button Mapper hay app gán nút khác cũng được. Lệnh tự động hoá có
   `-p com.nascam.tv` đổi thành `-p com.tvcameraoverlay`; link `nascam://…` vẫn dùng được.
4. Gỡ NAS Cam TV.
