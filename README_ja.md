# ⭐ MCP Dựa Trên Chatbot

(Tiếng Việt | 中文 | English)

## 1. Giới thiệu

👉 Con người: Gắn camera cho AI vs AI: Phát hiện ngay chủ nhân 3 ngày chưa gội đầu【bilibili】  
👉 Tự tay làm “bạn gái AI”, hướng dẫn nhập môn cho người mới【bilibili】

Chatbot XiaoZhi AI là cổng tương tác bằng giọng nói, tận dụng sức mạnh từ các mô hình lớn như Qwen / DeepSeek, đồng thời hỗ trợ điều khiển đa thiết bị thông qua giao thức MCP.

<img src="docs/mcp-based-graph.jpg" alt="Điều khiển mọi thứ bằng MCP" width="320">

## 2. Ghi chú phiên bản

- Phiên bản v2 hiện tại không tương thích với bảng phân vùng (partition table) của v1, do đó không thể nâng cấp từ v1 lên v2 qua OTA.  
- Chi tiết bảng phân vùng xem tại: `partitions/v2/README.md`

- Tất cả thiết bị đang chạy v1 đều có thể nâng cấp lên v2 bằng cách nạp firmware thủ công.

- Phiên bản ổn định cuối của v1 là **1.9.2**  
- Có thể chuyển về v1 bằng lệnh: `git checkout v1`  
- Nhánh v1 sẽ được duy trì đến **tháng 2 năm 2026**.

## 3. Các tính năng đã được triển khai

- Wi-Fi / ML307 Cat.1 4G  
- Đánh thức bằng giọng nói ngoại tuyến (offline wake word) – sử dụng **ESP-SR**  
- Hỗ trợ 2 giao thức giao tiếp: **WebSocket** hoặc **MQTT + UDP**  
- Sử dụng mã hóa âm thanh **OPUS**  
- Tương tác giọng nói dựa trên mô hình **ASR + LLM + TTS streaming**  
- Nhận diện người nói (định danh người đang nói) – **3D Speaker**  
- Hỗ trợ hiển thị trên màn hình **OLED / LCD**, bao gồm biểu cảm emoji  
- Hiển thị pin và quản lý năng lượng  
- Hỗ trợ đa ngôn ngữ: **Tiếng Trung, Tiếng Anh, Tiếng Nhật**  
- Hỗ trợ nền tảng chip: **ESP32-C3, ESP32-S3, ESP32-P4**  
- **MCP phía thiết bị**: điều khiển âm lượng, độ sáng, servo, hành động, GPIO…  
- **MCP phía đám mây**: mở rộng khả năng của mô hình lớn (điều khiển nhà thông minh, thao tác desktop PC, tìm kiếm kiến thức, gửi email…)  
- Hỗ trợ tùy chỉnh: wake word, font, emoji, hình nền chat thông qua trình chỉnh sửa web  
  (Custom Assets Generator)

## 4. Phần cứng

### 4.1 Thực hành DIY với breadboard

Xem hướng dẫn trên tài liệu Feishu:

👉 “Bách khoa toàn thư XiaoZhi AI Chatbot”

Ví dụ Breadboard:  
(hình ảnh giữ nguyên trong thư mục `docs/v1/wiring2.jpg`)

### 4.2 Hỗ trợ hơn 70 loại phần cứng mã nguồn mở (liệt kê một phần)

- Lichuang ESP32-S3 Development Board  
- Espressif ESP32-S3-BOX3  
- M5Stack CoreS3  
- M5Stack AtomS3R + Echo Base  
- Magic Button 2.4  
- Waveshare ESP32-S3-Touch-AMOLED-1.8  
- LILYGO T-Circle-S3  
- Xmini C3  
- CuiCan AI Pendant  
- Xingzhi 1.54TFT  
- SenseCAP Watcher  
- ESP-HI Robot Chó Giá Rẻ  

(hình ảnh giữ nguyên)

## 5. Phần mềm

### 5.1 Nạp firmware

Người mới được khuyến nghị sử dụng firmware có thể nạp trực tiếp mà không cần thiết lập môi trường phát triển.

- Firmware mặc định kết nối đến server chính thức:  
  👉 https://xiaozhi.me  

- Người dùng cá nhân có thể đăng ký tài khoản để sử dụng mô hình **Qwen real-time** miễn phí.  

- Hướng dẫn nạp firmware cho người mới:  
  👉 (Giữ nguyên link Feishu / tài liệu gốc nếu có)

### 5.2 Môi trường phát triển

- Sử dụng **Cursor** hoặc **VSCode**  
- Cài plugin **ESP-IDF**, chọn SDK **5.4 trở lên**  
- **Linux** tốt hơn Windows vì compile nhanh và ít lỗi driver  
- Dự án sử dụng **Google C++ Code Style**, cần tuân thủ khi đóng góp code

### 5.3 Tài liệu dành cho lập trình viên

- Hướng dẫn tạo bo mạch tùy chỉnh  
- Hướng dẫn sử dụng MCP trong IoT  
- Luồng giao tiếp MCP  
- Tài liệu giao thức hỗn hợp **MQTT + UDP**  
- Tài liệu giao thức **WebSocket** chi tiết  

## 6. Cấu hình mô hình AI lớn

Nếu bạn đã sở hữu thiết bị XiaoZhi và đã kết nối với server chính thức, bạn có thể cấu hình tại:

👉 https://xiaozhi.me  

Video hướng dẫn giao diện cũ:  
👉 https://www.bilibili.com/video/BV1jUCUY2EKM/

## 7. Các dự án mã nguồn mở liên quan

### Triển khai server trên máy tính cá nhân

- Python server: https://github.com/xinnan-tech/xiaozhi-esp32-server  
- Java server: https://github.com/joey-zhou/xiaozhi-esp32-server-java  
- Golang server: https://github.com/AnimeAIChat/xiaozhi-server-go  

### Các client khác dùng giao thức XiaoZhi

- Python client  
- Android client  
- Linux client (100ask)  
- Firmware Bluetooth (Sichuan)  
- QuecPython firmware  

## 8. Về dự án

Đây là dự án ESP32 mã nguồn mở, được phát hành theo giấy phép **MIT**.  
Mọi người đều có thể sử dụng miễn phí, bao gồm cả mục đích thương mại.

Mục tiêu của dự án là giúp người dùng hiểu rõ hơn về phát triển phần cứng AI và cách ứng dụng mô hình ngôn ngữ lớn vào các thiết bị thực tế.

Nếu bạn có góp ý hoặc đề xuất, hãy tạo Issues hoặc tham gia nhóm QQ: **1011329060**

## 9. Lịch sử Star

(hình và mã nhúng giữ nguyên)

<a href="https://star-history.com/#78/xiaozhi-esp32&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=78/xiaozhi-esp32&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=78/xiaozhi-esp32&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=78/xiaozhi-esp32&type=Date" />
 </picture>
</a>
