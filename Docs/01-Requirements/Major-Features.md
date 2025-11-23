# BẢNG XÁC ĐỊNH MAJOR FEATURES - SNAKEAID PLATFORM

## Thông tin dự án
- **Tên dự án:** AI-Powered Platform for Snakebite First Aid and Rescue Support (SnakeAid)
- **Mục đích:** Nền tảng tích hợp hỗ trợ sơ cứu rắn cắn, nhận diện loài rắn bằng AI, theo dõi cứu hộ, tư vấn chuyên gia và giám sát sự cố

---

| # | Topic | Description | Primary Actors |
|---|-------|-------------|----------------|
| | **Major Features** | | |
| | ***Mobile/Web Application for Patient*** | | |
| 1 | Hướng dẫn sơ cứu khẩn cấp | FE-01: Chức năng cung cấp hướng dẫn từng bước khi bị rắn cắn (băng ép, cách xử lý, cảnh báo hành động cấm kỵ).<br>FE-02: Hiển thị hướng dẫn băng ép đúng cách có hình ảnh minh họa.<br>FE-03: Cảnh báo các hành động nguy hiểm cần tránh (đắp lá, rạch vết thương, hút độc...). | **Patient** |
| 2 | Gọi cứu hộ khẩn cấp (SOS) | FE-04: Nút SOS gửi vị trí GPS và gọi trực tiếp đến đường dây nóng cấp cứu.<br>FE-05: Tự động chia sẻ vị trí real-time với đội cứu hộ được phân công. | **Patient** |
| 3 | Định vị cơ sở điều trị gần nhất | FE-06: Hiển thị bản đồ các bệnh viện/trạm y tế có huyết thanh kháng nọc rắn.<br>FE-07: Tính toán khoảng cách và thời gian ước tính đến từng cơ sở.<br>FE-08: Thông tin chi tiết về loại huyết thanh có sẵn tại mỗi cơ sở (dựa trên dữ liệu admin cập nhật). | **Patient** |
| 4 | Theo dõi vết cắn và triệu chứng | FE-09: Cho phép người dùng nhập mô tả triệu chứng (đau, sưng, tê, buồn nôn...).<br>FE-10: Chụp ảnh vết cắn để theo dõi sự tiến triển theo thời gian.<br>FE-11: Lưu trữ lịch sử triệu chứng và ảnh để cung cấp cho bác sĩ hoặc chuyên gia. | **Patient** |
| 5 | Nhận diện loài rắn từ hình ảnh (AI) | FE-12: Sử dụng AI để nhận diện loài rắn từ ảnh chụp.<br>FE-13: Hiển thị kết quả: tên rắn, độc tính (có độc/không độc), mức độ nguy hiểm.<br>FE-14: Đề xuất biện pháp sơ cứu phù hợp dựa trên loài rắn được nhận diện. | **Patient** |
| 6 | Đánh giá mức độ nghiêm trọng (AI) | FE-15: Phân tích ảnh vết cắn và triệu chứng để đánh giá mức độ nguy hiểm.<br>FE-16: Cảnh báo khẩn cấp và khuyến nghị gọi cấp cứu nếu tình trạng nghiêm trọng.<br>FE-17: Phân loại mức độ: nhẹ, trung bình, nặng, nguy kịch. | **Patient** |
| 7 | Báo cáo sự cố rắn cắn / phát hiện rắn | FE-18: Gửi báo cáo vị trí GPS và hình ảnh rắn đến hệ thống.<br>FE-19: Yêu cầu đội cứu hộ rắn đến bắt/di dời rắn.<br>FE-20: Cảnh báo cộng đồng về khu vực có rắn độc xuất hiện. | **Patient** |
| 8 | Kiến thức phòng tránh rắn cắn | FE-21: Cung cấp bài viết, video về cách phòng tránh rắn cắn.<br>FE-22: FAQ - Câu hỏi thường gặp về xử lý rắn cắn.<br>FE-23: Thông tin về các loài rắn phổ biến ở từng khu vực. | **Patient** |
| 9 | Theo dõi đội cứu hộ real-time | FE-24: Hiển thị vị trí đội cứu hộ đang di chuyển trên bản đồ sau khi yêu cầu cứu hộ.<br>FE-25: Nhận thông báo khi đội cứu hộ đang trên đường đến và khi hoàn thành nhiệm vụ.<br>FE-26: Hiển thị lộ trình và thời gian dự kiến đến nơi. | **Patient** |
| 10 | Quản lý thanh toán dịch vụ | FE-27: Thanh toán phí tư vấn chuyên gia rắn trực tuyến.<br>FE-28: Thanh toán phí cứu hộ rắn trực tiếp cho đội cứu hộ qua nền tảng.<br>FE-29: Theo dõi trạng thái thanh toán và hóa đơn điện tử.<br>FE-30: Xem lịch sử giao dịch và chi tiết dịch vụ đã sử dụng. | **Patient** |
| | ***Mobile/Web Application for Snake Rescuer*** | | |
| 11 | Nhận cảnh báo cứu hộ rắn | FE-31: Nhận thông báo về phát hiện rắn hoặc yêu cầu cứu hộ kèm vị trí và hình ảnh.<br>FE-32: Xem chi tiết yêu cầu: loại rắn dự đoán, mức độ nguy hiểm, thông tin liên hệ. | **Snake Rescuer** |
| 12 | Xác nhận và phản hồi nhanh | FE-33: Xác nhận loại rắn (có độc/không độc) từ hình ảnh.<br>FE-34: Cập nhật kết quả xác minh lên hệ thống.<br>FE-35: Gửi thông tin sơ bộ cho người yêu cầu về mức độ nguy hiểm. | **Snake Rescuer** |
| 13 | Quản lý nhiệm vụ cứu hộ | FE-36: Chấp nhận hoặc từ chối yêu cầu cứu hộ.<br>FE-37: Cập nhật tiến độ (đang di chuyển, đang xử lý, đã hoàn thành).<br>FE-38: Quản lý danh sách nhiệm vụ: đang chờ, đang thực hiện, đã hoàn thành. | **Snake Rescuer** |
| 14 | Hướng dẫn an toàn bắt rắn | FE-39: Quy trình chuẩn để bắt và di dời rắn an toàn.<br>FE-40: Danh sách thiết bị cần thiết và kỹ thuật xử lý từng loài.<br>FE-41: Video hướng dẫn bắt rắn cho từng tình huống. | **Snake Rescuer** |
| 15 | Liên lạc với chuyên gia | FE-42: Trao đổi thông tin với chuyên gia rắn để nhận diện chính xác.<br>FE-43: Yêu cầu hỗ trợ từ xa khi gặp loài rắn khó xác định.<br>FE-44: Chia sẻ ảnh/video real-time với chuyên gia. | **Snake Rescuer**<br>**Snake Expert** |
| 16 | Ghi nhận và báo cáo hoạt động | FE-45: Ghi nhận chi tiết từng ca cứu hộ (vị trí, thời gian, loài rắn, kết quả).<br>FE-46: Chụp ảnh rắn sau khi bắt để lưu vào cơ sở dữ liệu.<br>FE-47: Tạo báo cáo thống kê hoạt động cứu hộ theo tháng/quý. | **Snake Rescuer** |
| 17 | Theo dõi bản đồ và điều hướng | FE-48: Cập nhật vị trí real-time của đội cứu hộ lên hệ thống.<br>FE-49: Hỗ trợ điều hướng đến vị trí của bệnh nhân.<br>FE-50: Gửi thông báo trạng thái (đang đến, đã đến, hoàn thành) cho bệnh nhân. | **Snake Rescuer**<br>**Patient** |
| 18 | Nhận diện rắn từ ảnh (AI) | FE-51: Sử dụng AI để nhận diện loài rắn từ ảnh do bệnh nhân gửi.<br>FE-52: Nhận cảnh báo về mức độ nguy hiểm trước khi đến hiện trường.<br>FE-53: Chuẩn bị thiết bị và biện pháp an toàn phù hợp. | **Snake Rescuer** |
| 19 | Quản lý doanh thu cứu hộ | FE-54: Chấp nhận yêu cầu cứu hộ có trả phí từ bệnh nhân.<br>FE-55: Theo dõi doanh thu, trạng thái thanh toán và lịch sử giao dịch.<br>FE-56: Nhận thanh toán qua nền tảng sau khi hoàn thành cứu hộ.<br>FE-57: Xem đánh giá và nhận phản hồi từ khách hàng để cải thiện ưu tiên xếp hạng. | **Snake Rescuer** |
| | ***Mobile/Web Application for Snake Expert*** | | |
| 20 | Xác minh dữ liệu nhận diện | FE-58: Xác nhận loài rắn từ hình ảnh/mô tả do hệ thống hoặc người dùng gửi.<br>FE-59: Sửa đổi kết quả AI nếu nhận diện sai.<br>FE-60: Thêm ghi chú chuyên môn về đặc điểm nhận dạng. | **Snake Expert** |
| 21 | Hỗ trợ AI nhận diện loài rắn | FE-61: Sử dụng AI để rút ngắn thời gian xác minh loài rắn.<br>FE-62: Kiểm tra và phê duyệt kết quả AI trước khi công bố.<br>FE-63: Đào tạo và cải thiện mô hình AI bằng cách xác nhận dữ liệu mới. | **Snake Expert** |
| 22 | Cập nhật hướng dẫn sơ cứu | FE-64: Cập nhật quy trình xử lý và sơ cứu theo từng loài rắn.<br>FE-65: Biên soạn hướng dẫn chi tiết về triệu chứng và cách xử lý nọc rắn.<br>FE-66: Cung cấp thông tin về liều lượng huyết thanh kháng nọc phù hợp. | **Snake Expert** |
| 23 | Tư vấn từ xa | FE-67: Hỗ trợ trực tuyến cho bệnh nhân qua chat/video call.<br>FE-68: Tư vấn cho đội cứu hộ về cách xử lý loài rắn phức tạp.<br>FE-69: Đánh giá tình trạng bệnh nhân và khuyến nghị biện pháp khẩn cấp. | **Snake Expert**<br>**Patient**<br>**Snake Rescuer** |
| 24 | Quản lý doanh thu tư vấn | FE-70: Thiết lập mức phí tư vấn trực tuyến.<br>FE-71: Nhận thanh toán qua nền tảng và xuất hóa đơn điện tử.<br>FE-72: Xem báo cáo doanh thu theo tháng/quý.<br>FE-73: Theo dõi số lượt tư vấn và đánh giá từ khách hàng. | **Snake Expert** |
| | ***Admin Web Application*** | | |
| 25 | Quản lý người dùng và phân quyền | FE-74: Tạo tài khoản cho bệnh nhân, chuyên gia và đội cứu hộ.<br>FE-75: Phân quyền truy cập theo vai trò (Patient, Rescuer, Expert, Admin).<br>FE-76: Quản lý trạng thái tài khoản (kích hoạt, khóa, xóa).<br>FE-77: Xem lịch sử hoạt động của người dùng. | **Admin** |
| 26 | Quản lý cơ sở dữ liệu loài rắn | FE-78: Thêm, sửa, xóa thông tin loài rắn (tên khoa học, tên địa phương, đặc điểm, phân bố).<br>FE-79: Upload hình ảnh rắn cho từng loài.<br>FE-80: Quản lý thông tin về hành vi, môi trường sống của rắn.<br>FE-81: Phân loại rắn theo mức độ nguy hiểm và khu vực phân bố. | **Admin** |
| 27 | Quản lý cơ sở điều trị | FE-82: Thêm thông tin bệnh viện/trạm y tế (tên, địa chỉ, tọa độ GPS).<br>FE-83: Cập nhật danh sách loại huyết thanh kháng nọc có sẵn tại mỗi cơ sở.<br>FE-84: Quản lý giờ làm việc và thông tin liên hệ khẩn cấp.<br>FE-85: Đánh dấu cơ sở có khả năng điều trị rắn độc 24/7. | **Admin** |
| 28 | Quản lý nội dung hệ thống | FE-86: Cập nhật hướng dẫn sơ cứu, thông tin về rắn, khu vực nguy hiểm.<br>FE-87: Biên tập bài viết, video giáo dục về phòng tránh rắn cắn.<br>FE-88: Quản lý FAQ và nội dung trợ giúp người dùng.<br>FE-89: Đăng tin tức cập nhật về tình hình rắn độc theo mùa. | **Admin** |
| 29 | Thống kê và báo cáo dữ liệu | FE-90: Thống kê số ca rắn cắn theo khu vực, thời gian, loài rắn.<br>FE-91: Báo cáo số lượt cứu hộ và tỷ lệ hoàn thành của đội cứu hộ.<br>FE-92: Thống kê số lượt tư vấn và đánh giá chuyên gia.<br>FE-93: Phân tích xu hướng và khu vực có nguy cơ cao.<br>FE-94: Xuất báo cáo theo tháng/quý/năm. | **Admin** |
| 30 | Cảnh báo và thông báo cộng đồng | FE-95: Gửi cảnh báo về khu vực có rắn độc xuất hiện nhiều.<br>FE-96: Đẩy thông báo hướng dẫn phòng tránh theo mùa.<br>FE-97: Cảnh báo khẩn cấp khi phát hiện loài rắn độc nguy hiểm mới.<br>FE-98: Quản lý danh sách người nhận thông báo theo khu vực. | **Admin** |
| 31 | Giám sát hoạt động trên bản đồ | FE-99: Hiển thị real-time các ca cứu hộ đang diễn ra trên bản đồ.<br>FE-100: Theo dõi vị trí đội cứu hộ và trạng thái nhiệm vụ.<br>FE-101: Xem biểu đồ nhiệt về các điểm nóng rắn cắn.<br>FE-102: Giám sát thời gian phản hồi trung bình của đội cứu hộ. | **Admin** |
| 32 | Quản lý phí dịch vụ và doanh thu | FE-103: Thiết lập mức phí cho dịch vụ cứu hộ và tư vấn chuyên gia.<br>FE-104: Theo dõi tổng doanh thu và phân chia thu nhập cho rescuer/expert.<br>FE-105: Quản lý thanh toán giữa bệnh nhân – rescuer/expert – nền tảng.<br>FE-106: Tạo báo cáo tài chính định kỳ (tháng/quý/năm).<br>FE-107: Quản lý hoa hồng nền tảng và chính sách hoàn tiền.<br>FE-108: Xử lý tranh chấp thanh toán và yêu cầu hoàn tiền. | **Admin** |

---

## Ghi chú
- **FE:** Feature (Tính năng chức năng)
- Mỗi Major Feature được chia nhỏ thành các chức năng cụ thể với mã định danh riêng (FE-01, FE-02,...)
- Primary Actors bao gồm: **Patient** (Bệnh nhân), **Snake Rescuer** (Đội cứu hộ rắn), **Snake Expert** (Chuyên gia rắn), **Admin** (Quản trị viên)
