# IoT based health monitoring system
## Introduction
<p>
IoT Patient Monitoring System là mã Arduino dành cho bo mạch Arduino UNO kết hợp với module ESP8266. Dự án này được thiết kế để giám sát các chỉ số sức khỏe quan trọng, bao gồm nhịp tim (BPM) từ cảm biến nhịp tim (Pulse Sensor) và nhiệt độ cơ thể từ cảm biến DS18B20. Các thông số này được hiển thị trên màn hình LCD 16x2 để người dùng dễ dàng theo dõi.
<p>
Hệ thống cũng tích hợp buzzer cảnh báo, giúp phát ra âm thanh khi phát hiện các giá trị vượt ngưỡng an toàn. Dữ liệu nhịp tim và nhiệt độ được gửi lên cloud thông qua ESP8266 để giám sát từ xa hoặc lưu trữ.
<p>
Dự án được thiết kế với các tính năng chính như:

- Hiển thị thông số sức khỏe theo thời gian thực trên màn hình LCD.
- Phát cảnh báo bằng buzzer khi phát hiện tình trạng bất thường.
- Gửi dữ liệu nhịp tim và nhiệt độ lên server qua ESP8266 để sử dụng trong các ứng dụng IoT. 
<p>
Sản phẩm được hướng dẫn chi tiết cách làm và cách sử dụng ở phía bên dưới

## HOW DOES IT WORK?
<p>
Hệ thống theo dõi sức khỏe sử dụng Arduino, cảm biến mạch và cảm biến nhiệt độ được thiết kế để theo dõi dữ liệu sức khỏe theo thời gian thực như nhịp tim và nhiệt độ cơ thể. Cảm biến xung, được kết nối với chân đầu vào tương tự trên Arduino, phát hiện nhịp tim bằng cách ghi lại những thay đổi trong lưu lượng máu, trong khi cảm biến nhiệt độ (như LM35 hoặc DS18B20) đo nhiệt độ cơ thể. Arduino đọc dữ liệu từ cả hai cảm biến, cho phép hệ thống giám sát các dấu hiệu quan trọng này một cách chính xác.
<p>
Sau đó, mô-đun WiFi ESP8266 được sử dụng để truyền dữ liệu này tới nền tảng đám mây, cụ thể là ThingSpeak, được biết đến vì tính đơn giản trong các ứng dụng IoT. ThingSpeak cho phép lưu trữ, phân tích và trực quan hóa dữ liệu sức khỏe trong thời gian thực, giúp dễ dàng truy cập thông tin thông qua bảng điều khiển web. Người dùng có thể theo dõi xu hướng sức khỏe của mình theo thời gian, khiến hệ thống này trở nên lý tưởng để theo dõi sức khỏe từ xa. Thiết lập này đặc biệt có giá trị đối với người chăm sóc hoặc nhân viên y tế, những người cần truy cập liên tục vào thông tin quan trọng của bệnh nhân vì dữ liệu có thể được kiểm tra từ bất kỳ thiết bị nào có truy cập Internet. Bằng cách tích hợp lưu trữ đám mây với Arduino, hệ thống này cung cấp giải pháp hiệu quả, chi phí thấp để theo dõi sức khỏe và ghi dữ liệu được cá nhân hóa.

# Requirements
## Hardware

 - Arduino UNO R3
 - KIT WiFi NodeMcu ESP8266 V3 Cp2102
 - Màn hình LCD 2x16 (I2C Module)
 - Pulse Sensor
 - Buzzer 5V 
 - LM35
 - Cảm biến ECG
   
## Circuit Diagram
Lưu ý: 
 - Output của ECG cắm cổng analog nào cũng được (tất cả các chân này đều là chân ADC và có thể đọc tín hiệu analog từ cảm biến ECG)
 - Chân SDA và SCL trên esp8266 phải được cắm đúng với chân A4 và A5 trên Arduino uno R3 vì chỉ có 2 chân này mới có chức năng kép là analog và hỗ trợ I2C
<p>
 Sơ đồ mạch của Arduino uno R3 và cảm biến ECG
 
![image](anh.png)
 
 Sơ đồ mạch của Arduino uno R3 và màn hình LCD
 
![image](anh2.jpg)


## Library
 - LiquidCrystal (Để hiển thị thông tin trên màn hình LCD 16x2).
 - SoftwareSerial (Để giao tiếp giữa Arduino và module ESP8266).
 - Analog (Để giao tiếp với cảm biến LM35 qua giao thức Analog).
 - ADC (Để đọc dữ liệu nhiệt độ từ cảm biến LM35).
 - PulseSensorPlayground (Để đọc và xử lý tín hiệu từ Pulse Sensor).
 - ESP8266WiFi (Để thiết lập kết nối WiFi với module ESP8266).
  
# Support
Nếu bạn gặp lỗi hoặc có câu hỏi nào cần được hỗ trợ thì liên lạc với tôi và tôi sẽ hỗ trợ ngay khi có thể.
