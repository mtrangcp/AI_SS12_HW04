# Bài 3: Sinh Test Case và dữ liệu kiểm thử tự động (Mock Data)

---

## 1. Prompt 1

Tiếp tục với dự án eKYC Spring Boot, hãy đóng vai là một Senior QA/Software Tester. Dựa trên các đặc tả yêu cầu và mã nguồn API 'Đăng ký mở tài khoản cơ bản' từ Bài tập 03, hãy thiết kế một danh sách các kịch bản kiểm thử (Test Case Matrix) chi tiết dưới dạng bảng Markdown.

Bảng danh sách cần có các cột: Test Case ID, Chức năng, Phân loại, Mô tả kịch bản, Dữ liệu kiểm thử đầu vào (Input), Kết quả mong đợi (Expected Result), Mã lỗi HTTP mong đợi.

Hãy bao phủ đầy đủ các phân loại sau cho các trường fullName, email, phone, citizenId:

Positive Test Case: Đăng ký thành công với dữ liệu hoàn toàn hợp lệ.

Negative Test Case: Dữ liệu lỗi (để trống, sai định dạng email, sai định dạng SĐT, số CCCD không đủ/vượt quá 12 số, hoặc email/CCCD bị trùng lặp).

Boundary Test Case: Kiểm tra các trường hợp biên về độ dài ký tự.

## 2. Prompt 2

Bây giờ, tôi cần chuẩn bị dữ liệu để kiểm thử hiệu năng và kiểm thử diện rộng. Hãy tự động tạo một file dữ liệu giả lập đặt tên là mock_customers.csv và lưu trực tiếp vào thư mục gốc của dự án này.

Yêu cầu về dữ liệu:

Số lượng: Sinh chính xác 50 dòng dữ liệu (không viết ngắn gọn hay dùng dấu ba chấm).

Định dạng: File CSV gồm các cột: fullName, phone, email, citizenId.

Tính thực tế: Toàn bộ dữ liệu phải khớp với thực tế tại Việt Nam (Họ tên tiếng Việt có dấu ngẫu nhiên, số điện thoại bắt đầu bằng các đầu số nhà mạng VN như 090, 091, 032, 098..., số CCCD là chuỗi đúng 12 chữ số ngẫu nhiên).

Hãy tự động tạo và ghi file này vào không gian làm việc của tôi.

## 3. Prompt 3

Tuyệt vời, file CSV đã được tạo. Bước tiếp theo, hãy đóng vai là một Developer viết Unit Test. Bạn hãy tự động tạo một file kiểm thử tên là AccountServiceTest.java đặt vào đúng cấu trúc thư mục src/test/java/com/abcbank/ekyc/service/AccountServiceTest.java.

Yêu cầu kỹ thuật cho mã nguồn:

Sử dụng khung kiểm thử JUnit 5 (@ExtendWith(MockitoExtension.class)) và Mockito để mock tầng AccountRepository.

Viết tối thiểu 3 phương thức test bao phủ các luồng logic của AccountServiceImpl:

registerAccount_Success: Test luồng đăng ký thành công, verify repository có gọi hàm save().

registerAccount_ThrowsException_WhenEmailExists: Test luồng ném ra DuplicateResourceException khi email đã tồn tại.

registerAccount_ThrowsException_WhenCitizenIdExists: Test luồng ném ra DuplicateResourceException khi số CCCD đã tồn tại.

Mã nguồn phải có JavaDoc giải thích mục đích từng hàm test và có comment tiếng Việt rõ ràng. Hãy tự động ghi trực tiếp file test này vào dự án cho tôi.

## 4. Prompt 4

Dự án đã có đầy đủ mã nguồn và file test. Hãy mở Terminal của hệ thống ngầm và chạy lệnh Maven kiểm thử (mvn test) để kiểm tra xem các class Unit Test chúng ta vừa viết có vượt qua (Pass) hết hay không. Hãy hiển thị kết quả log chạy test ra màn hình chat này cho tôi xem.
