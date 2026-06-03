# Báo cáo tìm hiểu công cụ kiểm thử Apache JMeter

## 1. Mục tiêu

Tìm hiểu và thực hành sử dụng Apache JMeter để thực hiện kiểm thử tải (Load Testing) cho một website thực tế, từ đó đánh giá khả năng đáp ứng của hệ thống khi có nhiều người dùng truy cập đồng thời.

## 2. Giới thiệu về Apache JMeter

Apache JMeter là công cụ mã nguồn mở được phát triển bởi Apache Software Foundation, dùng để kiểm thử hiệu năng và khả năng chịu tải của các ứng dụng web, API và nhiều loại dịch vụ mạng khác.

JMeter cho phép mô phỏng nhiều người dùng truy cập cùng lúc vào hệ thống, giúp đánh giá tốc độ phản hồi, khả năng xử lý yêu cầu và độ ổn định của ứng dụng.

## 3. Các thành phần chính của JMeter

### Test Plan

Là nơi chứa toàn bộ cấu hình và kịch bản kiểm thử.

### Thread Group

Mô phỏng số lượng người dùng ảo tham gia kiểm thử.

### HTTP Request

Gửi yêu cầu HTTP đến website hoặc API cần kiểm thử.

### Listener

Hiển thị kết quả kiểm thử dưới nhiều dạng khác nhau như:

* View Results Tree
* Summary Report
* Aggregate Report

### Assertion

Kiểm tra phản hồi của hệ thống có đáp ứng điều kiện mong đợi hay không.

## 4. Kịch bản kiểm thử thực hiện

Website được kiểm thử:

http://canvas.phenikaa-uni.edu.vn/

Thông số kiểm thử:

* Number of Threads (Users): 100
* Ramp-Up Period: 10 giây
* Loop Count: 5
* Protocol: HTTPS
* Method: GET
* Path: /

Các Listener sử dụng:

* View Results Tree
* Summary Report
* Aggregate Report

## 5. Các bước thực hiện

1. Cài đặt Java Development Kit (JDK).
2. Tải và khởi động Apache JMeter.
3. Tạo Test Plan mới.
4. Thêm Thread Group.
5. Thêm HTTP Request.
6. Cấu hình website cần kiểm thử.
7. Thêm các Listener để theo dõi kết quả.
8. Thực hiện chạy kiểm thử.
9. Phân tích các chỉ số thu được.

## 6. Kết quả kiểm thử

Sau khi thực hiện kiểm thử với 100 người dùng đồng thời, hệ thống ghi nhận:

* Tổng số request: 100
* Request thành công: 98
* Request thất bại: 2
* Tỷ lệ lỗi: 2%

Một số request gặp lỗi:

Non HTTP response code: org.apache.http.NoHttpResponseException

Nguyên nhân:

Máy chủ không phản hồi một số yêu cầu khi số lượng kết nối đồng thời tăng cao.

Các chỉ số hiệu năng được theo dõi thông qua:

* Samples
* Average Response Time
* Minimum Response Time
* Maximum Response Time
* Error Percentage
* Throughput

## 7. Nhận xét và đánh giá

Qua quá trình thực hành có thể thấy Apache JMeter là công cụ mạnh mẽ và dễ sử dụng trong việc kiểm thử hiệu năng hệ thống.

Kết quả thử nghiệm cho thấy website Canvas của Phenikaa University xử lý thành công phần lớn các yêu cầu truy cập đồng thời. Tuy nhiên vẫn xuất hiện một số lỗi phản hồi khi tải tăng lên mức 100 người dùng, cho thấy hệ thống có thể gặp giới hạn tài nguyên hoặc giới hạn kết nối trong một số thời điểm.

JMeter giúp xác định các điểm nghẽn hiệu năng, hỗ trợ quá trình tối ưu hệ thống và đảm bảo chất lượng dịch vụ trước khi triển khai thực tế.

## 8. Kết luận

Apache JMeter là công cụ phù hợp để thực hiện kiểm thử tải và đánh giá hiệu năng cho website cũng như API. Thông qua bài thực hành, đã nắm được cách tạo kịch bản kiểm thử, cấu hình Thread Group, gửi HTTP Request và phân tích kết quả thông qua các báo cáo của JMeter.

## 9. Tài liệu tham khảo

1. Video hướng dẫn JMeter:
   https://www.youtube.com/watch?v=NTyY8wKSvik

2. Apache JMeter Official Website:
   https://jmeter.apache.org/

3. Apache JMeter User Manual:
   https://jmeter.apache.org/usermanual/
