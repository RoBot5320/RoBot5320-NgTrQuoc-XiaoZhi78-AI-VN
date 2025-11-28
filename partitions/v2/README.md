# Chatbot Dựa Trên MCP

(English | [中文](README.md) | [日本語](README_ja.md))

## Giới thiệu

👉 [Con người: Gắn camera cho AI vs AI: Phát hiện ngay chủ nhân ba ngày chưa gội đầu【bilibili】](https://www.bilibili.com/video/BV1bpjgzKEhd/)

👉 [Tự tay làm bạn gái AI, hướng dẫn nhập môn cho người mới【bilibili】](https://www.bilibili.com/video/BV1XnmFYLEJN/)

Chatbot XiaoZhi AI là một giao diện tương tác bằng giọng nói, tận dụng khả năng AI từ các mô hình lớn như Qwen / DeepSeek và thực hiện điều khiển đa thiết bị qua giao thức MCP.

<img src="docs/mcp-based-graph.jpg" alt="Điều khiển mọi thứ bằng MCP" width="320">

## Ghi chú phiên bản

Phiên bản v2 hiện tại không tương thích với bảng phân vùng v1, vì vậy không thể nâng cấp OTA từ v1 lên v2.  
Xem chi tiết bảng phân vùng tại: [partitions/v2/README.md](partitions/v2/README.md)

Tất cả thiết bị chạy v1 có thể nâng lên v2 bằng cách nạp firmware thủ công.

Phiên bản ổn định của v1: **1.9.2**  
Có thể chuyển sang nhánh v1 bằng lệnh: `git checkout v1`  
Nhánh v1 được duy trì đến **tháng 2/2026**

### Tính năng đã triển khai

- Wi-Fi / ML307 Cat.1 4G
- Đánh thức giọng nói ngoại tuyến (ESP-SR)
- Hỗ trợ WebSocket hoặc MQTT+UDP
- Mã hóa âm thanh OPUS
- Tương tác giọng nói dựa trên Streaming ASR + LLM + TTS
- Nhận diện người nói (3D Speaker)
- Màn hình OLED / LCD hỗ trợ emoji
- Hiển thị pin và quản lý năng lượng
- Hỗ trợ ngôn ngữ: Trung, Anh, Nhật
- Hỗ trợ ESP32-C3, ESP32-S3, ESP32-P4
- MCP phía thiết bị: loa, LED, servo, GPIO…
- MCP phía đám mây: nhà thông minh, PC, tra cứu…
- Tùy chỉnh wake word, font, emoji, nền chat qua web  
  (Công cụ Assets: https://github.com/78/xiaozhi-assets-generator)

## Phần cứng

### Breadboard DIY

Hướng dẫn chi tiết tại Feishu:

👉 ["XiaoZhi AI Chatbot Encyclopedia"](https://ccnphfhqs21z.feishu.cn/wiki/F5krwD16viZoF0kKkvDcrZNYnhb?from=from_copylink)

Breadboard demo:

![Breadboard Demo](docs/v1/wiring2.jpg)

### Hỗ trợ hơn 70 thiết bị phần cứng (liệt kê một phần)

- LiChuang ESP32-S3 Development Board
- Espressif ESP32-S3-BOX3
- M5Stack CoreS3
- M5Stack AtomS3R + Echo Base
- Magic Button 2.4
- Waveshare ESP32-S3-Touch-AMOLED-1.8
- LILYGO T-Circle-S3
- XiaGe Mini C3
- CuiCan AI Pendant
- WMnologo-Xingzhi-1.54TFT
- SenseCAP Watcher
- ESP-HI Low Cost Robot Dog

(Hình ảnh giữ nguyên)

## Phần mềm

### Nạp firmware

Người mới nên sử dụng firmware nạp trực tiếp, không cần môi trường phát triển.

Firmware mặc định kết nối server chính thức:  
https://xiaozhi.me

Hướng dẫn cho người mới:  
👉 https://ccnphfhqs21z.feishu.cn/wiki/Zpz4wXBtdimBrLk25WdcXzxcnNS

### Môi trường phát triển

- Cursor hoặc VSCode
- Cài ESP-IDF plugin, chọn SDK ≥ 5.4
- Linux biên dịch nhanh và ổn định hơn Windows
- Tuân thủ Google C++ Code Style khi đóng góp

### Tài liệu lập trình viên

- docs/custom-board.md – tạo board tùy chỉnh
- docs/mcp-usage.md – điều khiển IoT qua MCP
- docs/mcp-protocol.md – luồng MCP phía thiết bị
- docs/mqtt-udp.md – giao thức hỗn hợp
- docs/websocket.md – tài liệu WebSocket chi tiết

## Cấu hình mô hình lớn

Thiết bị XiaoZhi kết nối server chính thức có thể cấu hình tại:

https://xiaozhi.me

Video hướng dẫn (giao diện cũ):

👉 https://www.bilibili.com/video/BV1jUCUY2EKM/

## Các dự án mở rộng liên quan

- Python server: https://github.com/xinnan-tech/xiaozhi-esp32-server
- Java server: https://github.com/joey-zhou/xiaozhi-esp32-server-java
- Golang server: https://github.com/AnimeAIChat/xiaozhi-server-go

Client khác sử dụng giao thức XiaoZhi:

- Python: py-xiaozhi
- Android: xiaozhi-android-client
- Linux: xiaozhi-linux
- Bluetooth: xiaozhi-sf32
- QuecPython: solution-xiaozhiAI

## Về dự án

Dự án ESP32 mã nguồn mở theo giấy phép MIT.  
Cho phép sử dụng miễn phí, sửa đổi, thương mại hóa.

Mục tiêu: giúp người dùng hiểu rõ ứng dụng mô hình ngôn ngữ lớn vào phần cứng AI.

Thảo luận – góp ý: QQ Group **1011329060**

## Lịch sử Star

<a href="https://star-history.com/#78/xiaozhi-esp32&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=78/xiaozhi-esp32&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=78/xiaozhi-esp32&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=78/xiaozhi-esp32&type=Date" />
 </picture>
</a>
