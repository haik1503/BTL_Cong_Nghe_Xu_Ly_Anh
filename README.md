# NHẬN DIỆN KHUÔN MẶT CẢNH BÁO NGƯỜI LẠ VÀO VÙNG KIỂM SOÁT CỦA CAMERA 

## Giới thiệu

Đây là ứng dụng Python sử dụng OpenCV, face_recognition và giao diện Tkinter để nhận diện khuôn mặt qua camera IP (RTSP). Khi phát hiện người lạ, hệ thống sẽ:

- Phát cảnh báo âm thanh (báo động).
- Gửi ảnh cảnh báo qua Telegram.
- Tự động ghi lại video sự kiện.
- Lưu trữ và cho phép xem lại các video đã ghi.
- Giao diện trực quan, dễ sử dụng.

## Chức năng chính

- **Nhận diện khuôn mặt:** So sánh khuôn mặt xuất hiện với thư viện ảnh đã biết.
- **Cảnh báo người lạ:** Khi phát hiện người lạ, phát âm thanh cảnh báo và gửi ảnh qua Telegram.
- **Ghi & lưu video:** Tự động ghi lại video khi phát hiện người lạ, lưu file dưới dạng `.avi`.
- **Xem lại video:** Danh sách video được lưu, có thể chọn để xem lại ngay trên giao diện.
- **Giao diện người dùng:** Giao diện Tkinter thân thiện, dễ thao tác.

## Bảng công nghệ sử dụng

| Thành phần         | Công nghệ/Thư viện      | Vai trò chính                           |
|--------------------|------------------------|-----------------------------------------|
| Nhận diện khuôn mặt| face_recognition       | Phát hiện & mã hóa khuôn mặt            |
| Xử lý ảnh/video    | OpenCV                 | Đọc, ghi, xử lý khung hình & video      |
| Giao diện          | Tkinter, Pillow        | Hiển thị hình ảnh, giao diện người dùng |
| Cảnh báo âm thanh  | winsound               | Phát âm thanh báo động                  |
| Gửi cảnh báo       | requests, Telegram API | Gửi ảnh cảnh báo qua Telegram           |
| Đa luồng           | threading              | Xử lý song song các tác vụ              |

## Hướng dẫn sử dụng

1. **Cài đặt thư viện:**
    ```sh
    pip install -r requirements.txt
    ```

2. **Thêm khuôn mặt đã biết:**
    - Thêm ảnh vào thư mục `known_faces/<Tên>/`.
    - Mỗi người một thư mục con, tên thư mục là tên người.

3. **Cấu hình camera:**
    - Đảm bảo camera IP hỗ trợ RTSP, chỉnh URL trong hàm `open_camera()` .

4. **Cấu hình Telegram:**
    - Thay đổi `TELEGRAM_BOT_TOKEN` và `TELEGRAM_CHAT_ID` trong `main.py`.

5. **Chạy chương trình:**
    ```sh
    python main.py
    ```

6. **Sử dụng giao diện:**
    - Nhấn "Bắt đầu nhận diện" để khởi động camera.
    - Bật/tắt chế độ cảnh báo người lạ.
    - Xem lại video đã lưu ở khung bên phải.

## Yêu cầu

- Python 3.12
- Camera IP hỗ trợ RTSP
- Kết nối Internet để gửi Telegram

## Thư mục

- `main.py`: Chương trình chính.
- `interface.py`: Giao diện người dùng (nếu dùng).
- `known_faces/`: Thư mục chứa ảnh khuôn mặt đã biết.
- `alarm_new.wav`: Âm thanh cảnh báo.
- Các file `.avi`: Video ghi lại sự kiện.

## Hướng mở rộng trong tương lai

- Hỗ trợ nhận diện nhiều camera cùng lúc.
- Tích hợp lưu trữ đám mây cho video và ảnh cảnh báo.
- Thêm chức năng quản lý người dùng qua giao diện.
- Cải thiện tốc độ nhận diện với GPU hoặc model deep learning nâng cao.
- Thêm chức năng nhận diện hành vi bất thường.
- Tích hợp gửi cảnh báo qua nhiều nền tảng khác (Zalo, Email...).

---

**Tác giả:**  
- Nguyễn Thanh Hải