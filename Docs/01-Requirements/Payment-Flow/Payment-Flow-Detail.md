# LUỒNG TIỀN CHI TIẾT - HỆ THỐNG SNAKEAID

## Thông tin tài liệu
- **Tên dự án:** AI-Powered Platform for Snakebite First Aid and Rescue Support (SnakeAid)
- **Mục đích:** Làm rõ luồng tiền giữa các bên: Patient, Rescuer, Expert, và Platform
- **Ngày tạo:** 14/12/2025
- **Phiên bản:** 1.0

---

## 📌 TỔNG QUAN LUỒNG TIỀN

Hệ thống SnakeAid có **3 luồng thanh toán chính**:

1. **Patient → Platform → Rescuer** (Dịch vụ cứu hộ rắn)
2. **Patient → Platform → Expert** (Tư vấn chuyên gia trực tiếp)
3. **Platform → Expert** hoặc **Rescuer → Expert** (Hỗ trợ khẩn cấp cho Rescuer)

---

## 💰 CHI TIẾT CÁC LUỒNG THANH TOÁN

### 1. LUỒNG TIỀN: DỊCH VỤ CỨU HỘ RẮN

**Kịch bản:** Patient phát hiện rắn trong nhà → Yêu cầu đội cứu hộ đến bắt rắn → Rescuer thực hiện → Thanh toán

#### 1.1. Quy trình thanh toán

```
┌──────────┐                  ┌──────────┐                  ┌──────────┐
│          │   1. Yêu cầu     │          │   2. Chấp nhận   │          │
│ PATIENT  │─────────────────>│ PLATFORM │<─────────────────│ RESCUER  │
│          │                  │          │                  │          │
└────┬─────┘                  └────┬─────┘                  └────┬─────┘
     │                             │                             │
     │ 3. Rescuer hoàn thành       │                             │
     │    cứu hộ                   │                             │
     │                             │                             │
     │ 4. Patient thanh toán       │                             │
     │    (100% phí dịch vụ)       │                             │
     ├────────────────────────────>│                             │
     │                             │                             │
     │                             │ 5. Platform phân chia:      │
     │                             │    - 85% → Rescuer          │
     │                             │    - 10% → Platform         │
     │                             │    - 5% → Quỹ bảo hiểm     │
     │                             ├────────────────────────────>│
     │                             │                             │
     │ 6. Nhận hóa đơn             │                             │
     │<────────────────────────────┤                             │
     │                             │                             │
     │                             │ 7. Rescuer nhận thông báo   │
     │                             │    thanh toán thành công    │
     │                             │<────────────────────────────┤
     │                             │                             │
```

#### 1.2. Phân chia doanh thu chi tiết

**Ví dụ cụ thể:**
- Phí cứu hộ rắn: **500,000 VNĐ**

| Bên nhận | Tỷ lệ | Số tiền | Mục đích |
|----------|-------|---------|----------|
| **Rescuer** | 85% | 425,000 VNĐ | Thu nhập từ dịch vụ cứu hộ |
| **Platform (Admin)** | 10% | 50,000 VNĐ | Phí vận hành hệ thống, bảo trì server, marketing |
| **Quỹ bảo hiểm** | 5% | 25,000 VNĐ | Bảo hiểm tai nạn cho Rescuer khi thực hiện nhiệm vụ |
| **TỔNG** | 100% | 500,000 VNĐ | |

**Ghi chú:**
- Patient trả **100%** phí dịch vụ (500,000 VNĐ) qua cổng thanh toán
- Thanh toán sau khi Rescuer hoàn thành cứu hộ
- Phí cứu hộ có thể thay đổi tùy theo:
  - Loài rắn (rắn độc cao hơn)
  - Khu vực (xa trung tâm cao hơn)
  - Mức độ nguy hiểm
  - Thời gian (ban đêm/ngày lễ có thể cao hơn)

#### 1.3. Phương thức thanh toán

Patient có thể thanh toán qua:
- **Ví điện tử:** Momo, VNPay, ZaloPay
- **Thẻ tín dụng/ghi nợ:** Visa, Mastercard, JCB
- **Chuyển khoản ngân hàng:** Internet Banking
- **Tiền mặt:** (Trong một số trường hợp đặc biệt, thanh toán trực tiếp cho Rescuer - Platform vẫn ghi nhận giao dịch)

#### 1.4. Thời điểm thanh toán

```
Timeline:
┌────────────┐     ┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│ T0: Yêu    │────>│ T1: Rescuer  │────>│ T2: Hoàn     │────>│ T3: Thanh    │
│ cầu cứu hộ │     │ chấp nhận    │     │ thành cứu hộ │     │ toán ngay    │
└────────────┘     └──────────────┘     └──────────────┘     └──────────────┘
                                                                      │
                                                                      ▼
                                                         ┌──────────────────────┐
                                                         │ T4: Rescuer nhận     │
                                                         │ tiền trong 5-10 phút │
                                                         └──────────────────────┘
```

**Lưu ý:**
- Thanh toán **KHÔNG trả trước** để tránh trường hợp Rescuer không đến
- Patient phải thanh toán ngay sau khi Rescuer đánh dấu "Hoàn thành"
- Nếu Patient không thanh toán trong 24h → Hệ thống tự động nhắc nhở
- Nếu Patient không thanh toán trong 72h → Khóa tài khoản cho đến khi thanh toán

#### 1.5. Tính năng liên quan

| Mã tính năng | Mô tả | Vai trò |
|--------------|-------|---------|
| **FE-28** (Patient) | Thanh toán phí cứu hộ rắn trực tiếp cho đội cứu hộ qua nền tảng | Patient |
| **FE-29** (Patient) | Theo dõi trạng thái thanh toán và hóa đơn điện tử | Patient |
| **FE-30** (Patient) | Xem lịch sử giao dịch và chi tiết dịch vụ đã sử dụng | Patient |
| **FE-25** (Rescuer) | Theo dõi doanh thu, trạng thái thanh toán và lịch sử giao dịch | Rescuer |
| **FE-26** (Rescuer) | Nhận thanh toán qua nền tảng sau khi hoàn thành cứu hộ | Rescuer |
| **FE-32** (Admin) | Quản lý thanh toán giữa bệnh nhân – rescuer/expert – nền tảng | Admin |
| **FE-33** (Admin) | Tạo báo cáo tài chính định kỳ (tháng/quý/năm) | Admin |

---

### 2. LUỒNG TIỀN: TƯ VẤN CHUYÊN GIA

**Kịch bản:** Patient muốn tư vấn về rắn cắn hoặc phòng ngừa → Đặt lịch với Expert → Tư vấn qua chat/video call → Thanh toán

#### 2.1. Quy trình thanh toán

```
┌──────────┐                  ┌──────────┐                  ┌──────────┐
│          │   1. Đặt lịch    │          │   2. Xác nhận    │          │
│ PATIENT  │─────────────────>│ PLATFORM │<─────────────────│  EXPERT  │
│          │                  │          │                  │          │
└────┬─────┘                  └────┬─────┘                  └────┬─────┘
     │                             │                             │
     │ 3. Thanh toán TRƯỚC         │                             │
     │    (escrow - giữ tiền)      │                             │
     ├────────────────────────────>│                             │
     │                             │                             │
     │                        Tiền được giữ                      │
     │                        trong tài khoản                    │
     │                        tạm thời (escrow)                  │
     │                             │                             │
     │ 4. Bắt đầu tư vấn           │                             │
     │<───────────────────────────────────────────────────────>│
     │                             │                             │
     │ 5. Expert hoàn thành        │                             │
     │    tư vấn                   │<────────────────────────────┤
     │                             │                             │
     │                             │ 6. Platform chuyển tiền:    │
     │                             │    - 90% → Expert           │
     │                             │    - 10% → Platform         │
     │                             ├────────────────────────────>│
     │                             │                             │
     │ 7. Nhận hóa đơn điện tử     │                             │
     │<────────────────────────────┤                             │
     │                             │                             │
```

#### 2.2. Phân chia doanh thu chi tiết

**Ví dụ cụ thể:**
- Phí tư vấn chuyên gia: **300,000 VNĐ** (30 phút tư vấn)

| Bên nhận | Tỷ lệ | Số tiền | Mục đích |
|----------|-------|---------|----------|
| **Expert** | 90% | 270,000 VNĐ | Thu nhập từ tư vấn chuyên môn |
| **Platform (Admin)** | 10% | 30,000 VNĐ | Phí vận hành hệ thống, cổng thanh toán, video call |
| **TỔNG** | 100% | 300,000 VNĐ | |

**Ghi chú:**
- Patient trả **100%** phí tư vấn (300,000 VNĐ) qua cổng thanh toán
- Thanh toán **TRƯỚC** khi tư vấn (escrow - giữ tiền tạm thời)
- Sau khi Expert hoàn thành → Tiền được chuyển từ escrow sang tài khoản Expert
- Phí tư vấn do Expert tự thiết lập (FE-13)
- Phí có thể thay đổi tùy theo:
  - Kinh nghiệm của Expert
  - Loại tư vấn (khẩn cấp cao hơn)
  - Thời gian tư vấn (15 phút, 30 phút, 60 phút)

#### 2.3. Cơ chế Escrow (Giữ tiền tạm thời)

**Tại sao cần escrow?**
- Đảm bảo Patient đã thanh toán trước khi Expert bắt đầu tư vấn
- Bảo vệ cả hai bên:
  - Expert: Chắc chắn sẽ nhận được tiền sau khi hoàn thành
  - Patient: Tiền chỉ được chuyển cho Expert sau khi tư vấn xong

**Quy trình escrow:**

```
┌─────────────────────────────────────────────────────────────┐
│                    TÀI KHOẢN ESCROW                         │
│                    (Platform quản lý)                        │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  [Bước 1] Patient thanh toán → Tiền vào escrow             │
│            ▼                                                │
│  [Giữ tiền] Tiền nằm trong escrow trong suốt buổi tư vấn   │
│            ▼                                                │
│  [Bước 2] Expert hoàn thành tư vấn                         │
│            ▼                                                │
│  [Chuyển tiền] Escrow → Tài khoản Expert (90%)             │
│                       → Platform (10%)                      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**Trường hợp đặc biệt:**
- Nếu Expert không tham gia đúng giờ (quá 15 phút) → Tự động hoàn tiền cho Patient
- Nếu Patient hủy trong vòng 2h trước giờ hẹn → Mất 20% phí (phí hủy)
- Nếu có tranh chấp → Admin can thiệp xem lại lịch sử chat/video để quyết định

#### 2.4. Thời điểm thanh toán

```
Timeline:
┌────────────┐     ┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│ T0: Đặt    │────>│ T1: Thanh    │────>│ T2: Bắt đầu  │────>│ T3: Hoàn     │
│ lịch tư vấn│     │ toán TRƯỚC   │     │ tư vấn       │     │ thành tư vấn │
└────────────┘     └──────────────┘     └──────────────┘     └──────────────┘
                           │                                         │
                           ▼                                         ▼
                    Tiền vào ESCROW                        Tiền chuyển cho Expert
                    (giữ tạm thời)                         (trong 5-10 phút)
```

#### 2.5. Tính năng liên quan

| Mã tính năng | Mô tả | Vai trò |
|--------------|-------|---------|
| **FE-27** (Patient) | Thanh toán phí tư vấn chuyên gia rắn trực tuyến | Patient |
| **FE-29** (Patient) | Theo dõi trạng thái thanh toán và hóa đơn điện tử | Patient |
| **FE-30** (Patient) | Xem lịch sử giao dịch và chi tiết dịch vụ đã sử dụng | Patient |
| **FE-13** (Expert) | Thiết lập mức phí tư vấn trực tuyến | Expert |
| **FE-14** (Expert) | Nhận thanh toán qua nền tảng và xuất hóa đơn điện tử | Expert |
| **FE-15** (Expert) | Xem báo cáo doanh thu theo tháng/quý | Expert |
| **FE-16** (Expert) | Theo dõi số lượt tư vấn và đánh giá từ khách hàng | Expert |

---

### 3. LUỒNG TIỀN: HỖ TRỢ KHẨN CẤP (RESCUER ↔ EXPERT)

**Kịch bản:** Rescuer đang ở hiện trường, gặp loài rắn khó nhận diện → Yêu cầu Expert hỗ trợ từ xa → Expert tư vấn ngay

#### 3.1. Quy trình thanh toán (2 phương án)

**PHƯƠNG ÁN 1: Platform trả phí (không tính vào khách hàng)**

```
┌──────────┐                  ┌──────────┐                  ┌──────────┐
│          │   1. Yêu cầu hỗ  │          │   2. Kết nối    │          │
│ RESCUER  │────trợ khẩn cấp─>│ PLATFORM │────ngay lập tức─>│  EXPERT  │
│          │                  │          │                  │          │
└────┬─────┘                  └────┬─────┘                  └────┬─────┘
     │                             │                             │
     │ 3. Tư vấn qua               │                             │
     │    chat/video call          │                             │
     │<───────────────────────────────────────────────────────>│
     │                             │                             │
     │                             │ 4. Sau khi tư vấn xong      │
     │                             │    Platform trả phí Expert  │
     │                             ├────────────────────────────>│
     │                             │    (50,000 - 100,000 VNĐ)  │
     │                             │                             │
     │                             │ 5. Rescuer KHÔNG mất tiền   │
     │                             │    Patient KHÔNG mất tiền   │
     │                             │                             │
```

**Phí hỗ trợ khẩn cấp:**
- 50,000 VNĐ cho tư vấn < 10 phút
- 100,000 VNĐ cho tư vấn 10-20 phút
- Platform chịu chi phí để đảm bảo Rescuer làm việc an toàn

---

**PHƯƠNG ÁN 2: Rescuer chia sẻ phí cứu hộ cho Expert**

```
┌──────────┐                  ┌──────────┐                  ┌──────────┐
│          │   1. Yêu cầu hỗ  │          │   2. Kết nối    │          │
│ RESCUER  │────trợ khẩn cấp─>│ PLATFORM │────ngay lập tức─>│  EXPERT  │
│          │                  │          │                  │          │
└────┬─────┘                  └────┬─────┘                  └────┬─────┘
     │                             │                             │
     │ 3. Tư vấn qua               │                             │
     │    chat/video call          │                             │
     │<───────────────────────────────────────────────────────>│
     │                             │                             │
     │ 4. Sau khi hoàn thành       │                             │
     │    cứu hộ, phân chia:       │                             │
     │    - 75% → Rescuer          │                             │
     │    - 10% → Expert           │                             │
     │    - 10% → Platform         │                             │
     │    - 5% → Quỹ bảo hiểm     │                             │
     │                             │                             │
```

**Ví dụ cụ thể:**
- Phí cứu hộ từ Patient: **500,000 VNĐ**

| Bên nhận | Tỷ lệ | Số tiền | Mục đích |
|----------|-------|---------|----------|
| **Rescuer** | 75% | 375,000 VNĐ | Thu nhập chính từ cứu hộ (giảm từ 85% → 75%) |
| **Expert** | 10% | 50,000 VNĐ | Phí hỗ trợ khẩn cấp cho Rescuer |
| **Platform** | 10% | 50,000 VNĐ | Phí vận hành hệ thống |
| **Quỹ bảo hiểm** | 5% | 25,000 VNĐ | Bảo hiểm cho Rescuer |
| **TỔNG** | 100% | 500,000 VNĐ | |

**Lưu ý:**
- Phương án 1 được khuyến khích để Rescuer không lo lắng về chi phí khi cần hỗ trợ
- Phương án 2 áp dụng khi có thỏa thuận trước giữa Rescuer và Expert
- Admin có thể cấu hình chọn phương án nào áp dụng cho hệ thống

#### 3.2. Tính năng liên quan

| Mã tính năng | Mô tả | Vai trò |
|--------------|-------|---------|
| **FE-12** (Rescuer) | Trao đổi thông tin với chuyên gia rắn để nhận diện chính xác | Rescuer |
| **FE-13** (Rescuer) | Yêu cầu hỗ trợ từ xa khi gặp loài rắn khó xác định | Rescuer |
| **FE-14** (Rescuer) | Chia sẻ ảnh/video real-time với chuyên gia | Rescuer |
| **FE-11** (Expert) | Tư vấn cho đội cứu hộ về cách xử lý loài rắn phức tạp | Expert |

---

## 📊 TỔNG HỢP PHÂN CHIA DOANH THU

### Bảng tổng hợp tỷ lệ phân chia

| Loại dịch vụ | Patient trả | Rescuer nhận | Expert nhận | Platform nhận | Quỹ bảo hiểm | Ghi chú |
|--------------|-------------|--------------|-------------|---------------|--------------|---------|
| **Cứu hộ rắn** (không có Expert) | 100% | 85% | - | 10% | 5% | Trường hợp thông thường |
| **Cứu hộ rắn** (có hỗ trợ Expert - PA1) | 100% | 85% | Platform trả | 10% - phí Expert | 5% | Platform chịu chi phí Expert |
| **Cứu hộ rắn** (có hỗ trợ Expert - PA2) | 100% | 75% | 10% | 10% | 5% | Rescuer chia cho Expert |
| **Tư vấn trực tiếp** | 100% | - | 90% | 10% | - | Patient đặt lịch với Expert |

### Ví dụ minh họa tổng hợp

**Tình huống 1: Cứu hộ rắn đơn giản (không cần Expert)**
- Patient trả: **500,000 VNĐ**
- Rescuer nhận: **425,000 VNĐ** (85%)
- Platform nhận: **50,000 VNĐ** (10%)
- Quỹ bảo hiểm: **25,000 VNĐ** (5%)

**Tình huống 2: Cứu hộ rắn phức tạp (cần Expert hỗ trợ - Phương án 1)**
- Patient trả: **500,000 VNĐ**
- Rescuer nhận: **425,000 VNĐ** (85%)
- Expert nhận: **50,000 VNĐ** (Platform trả)
- Platform nhận: **0 VNĐ** (10% - 50,000 = 0, hoặc lỗ nếu Expert fee > 50,000)
- Quỹ bảo hiểm: **25,000 VNĐ** (5%)
- **Platform lỗ hoặc hòa vốn** để đảm bảo an toàn cho Rescuer

**Tình huống 3: Cứu hộ rắn phức tạp (cần Expert hỗ trợ - Phương án 2)**
- Patient trả: **500,000 VNĐ**
- Rescuer nhận: **375,000 VNĐ** (75%)
- Expert nhận: **50,000 VNĐ** (10%)
- Platform nhận: **50,000 VNĐ** (10%)
- Quỹ bảo hiểm: **25,000 VNĐ** (5%)

**Tình huống 4: Tư vấn chuyên gia trực tiếp**
- Patient trả: **300,000 VNĐ**
- Expert nhận: **270,000 VNĐ** (90%)
- Platform nhận: **30,000 VNĐ** (10%)

---

## 💳 PHƯƠNG THỨC THANH TOÁN

### Các cổng thanh toán được tích hợp

| Phương thức | Ví dụ | Phí giao dịch | Thời gian xử lý |
|-------------|-------|---------------|-----------------|
| **Ví điện tử** | Momo, VNPay, ZaloPay | 1-2% | Tức thì |
| **Thẻ tín dụng/ghi nợ** | Visa, Mastercard, JCB | 2.5-3% | 1-2 phút |
| **Internet Banking** | Vietcombank, BIDV, Techcombank | 0.5-1% | 5-10 phút |
| **Tiền mặt** | Trực tiếp cho Rescuer | 0% | Tức thì |

**Lưu ý:**
- Phí giao dịch do **Platform chịu**, không trừ vào phần của Rescuer/Expert
- Nếu phí giao dịch là 2% → Platform chịu 2% để đảm bảo Rescuer/Expert nhận đủ tỷ lệ đã cam kết
- Ví dụ: Rescuer nhận 85% của 500,000 = 425,000 VNĐ (không bị trừ phí giao dịch)

---

## 🔄 QUY TRÌNH THANH TOÁN CHI TIẾT

### Quy trình chi tiết từng bước

```
┌─────────────────────────────────────────────────────────────────┐
│                    QUY TRÌNH THANH TOÁN                         │
└─────────────────────────────────────────────────────────────────┘

[Bước 1] Hoàn thành dịch vụ
         ↓
[Bước 2] Rescuer/Expert đánh dấu "Hoàn thành"
         ↓
[Bước 3] Hệ thống gửi thông báo đến Patient
         "Vui lòng thanh toán và đánh giá dịch vụ"
         ↓
[Bước 4] Patient mở app → Xem hóa đơn → Chọn phương thức thanh toán
         ↓
[Bước 5] Patient xác nhận thanh toán
         ↓
[Bước 6] Cổng thanh toán xử lý (Momo/VNPay/Card...)
         ↓
[Bước 7] Thanh toán thành công → Tiền vào tài khoản Platform
         ↓
[Bước 8] Platform tự động phân chia:
         - X% → Tài khoản Rescuer/Expert (trong 5-10 phút)
         - Y% → Doanh thu Platform
         - Z% → Quỹ bảo hiểm (nếu có)
         ↓
[Bước 9] Rescuer/Expert nhận thông báo "Đã nhận thanh toán XXX VNĐ"
         ↓
[Bước 10] Patient đánh giá dịch vụ (1-5 sao + nhận xét)
         ↓
[Bước 11] Hệ thống cập nhật rating và lưu vào lịch sử
         ↓
[Bước 12] Xuất hóa đơn điện tử cho tất cả các bên
```

---

## ⚠️ CÁC TRƯỜNG HỢP ĐẶC BIỆT

### 1. Tranh chấp thanh toán

#### Tình huống 1: Patient khiếu nại "Rescuer không đến"

**Quy trình xử lý:**
```
[Bước 1] Patient gửi khiếu nại qua app
         ↓
[Bước 2] Admin nhận thông báo và kiểm tra:
         - Lịch sử GPS của Rescuer
         - Thời gian chấp nhận nhiệm vụ
         - Log cuộc gọi/tin nhắn
         - Ảnh chụp hiện trường (nếu có)
         ↓
[Bước 3A] Nếu Rescuer KHÔNG ĐẾN (GPS không đến gần địa điểm)
          → Hoàn tiền 100% cho Patient
          → Phạt Rescuer (giảm rating, cảnh cáo)
          ↓
[Bước 3B] Nếu Rescuer ĐÃ ĐẾN nhưng không hoàn thành
          → Tùy tình huống:
             * Patient cung cấp sai địa chỉ → Patient mất 50%
             * Rắn đã chạy mất trước khi Rescuer đến → Patient trả 30%
             * Rescuer từ chối bắt (quá nguy hiểm) → Không tính phí
          ↓
[Bước 4] Admin đưa ra quyết định cuối cùng và thực hiện hoàn tiền (nếu có)
         ↓
[Bước 5] Gửi thông báo kết quả cho cả 2 bên
```

#### Tình huống 2: Rescuer khiếu nại "Patient không thanh toán"

**Quy trình xử lý:**
```
[Bước 1] Rescuer gửi khiếu nại qua app
         ↓
[Bước 2] Admin kiểm tra trạng thái thanh toán:
         - Patient đã xác nhận hoàn thành chưa?
         - Có ảnh chụp hoàn thành không?
         - Thời gian đã bao lâu kể từ lúc hoàn thành?
         ↓
[Bước 3] Admin gửi nhắc nhở đến Patient:
         "Vui lòng thanh toán cho dịch vụ cứu hộ"
         ↓
[Bước 4A] Patient thanh toán trong 24h → Giải quyết xong
         ↓
[Bước 4B] Patient không phản hồi trong 48h
          → Admin tự động trừ tiền từ thẻ đã lưu (nếu có)
          → Hoặc khóa tài khoản Patient cho đến khi thanh toán
          ↓
[Bước 5] Rescuer nhận tiền + Thông báo kết quả
```

#### Tình huống 3: Expert khiếu nại "Tư vấn xong nhưng chưa nhận tiền"

**Quy trình xử lý:**
```
[Lưu ý] Với tư vấn, tiền đã được giữ trong escrow nên ít xảy ra vấn đề

[Bước 1] Expert kiểm tra tài khoản và thấy chưa nhận tiền
         ↓
[Bước 2] Expert gửi khiếu nại qua app
         ↓
[Bước 3] Admin kiểm tra:
         - Expert đã đánh dấu "Hoàn thành" chưa?
         - Tiền có trong escrow không?
         - Có lỗi kỹ thuật không?
         ↓
[Bước 4] Admin xử lý:
         - Nếu Expert quên đánh dấu hoàn thành → Hướng dẫn đánh dấu
         - Nếu lỗi kỹ thuật → Chuyển tiền thủ công trong 1h
         - Nếu Patient khiếu nại chất lượng → Admin xem xét lại
         ↓
[Bước 5] Giải quyết và thông báo cho Expert
```

### 2. Hoàn tiền (Refund)

#### Các trường hợp được hoàn tiền

| Tình huống | Hoàn tiền | Thời gian | Ghi chú |
|------------|-----------|-----------|---------|
| **Rescuer không đến** | 100% | 3-5 ngày | Patient được hoàn tiền đầy đủ |
| **Patient hủy trước 2h** | 80% | 3-5 ngày | Mất 20% phí hủy |
| **Patient hủy trong 2h** | 50% | 3-5 ngày | Mất 50% vì Rescuer đã chuẩn bị |
| **Expert không tham gia** | 100% | Tức thì | Tiền từ escrow trả lại ngay |
| **Expert đến muộn >15 phút** | 100% | Tức thì | Patient có quyền hủy và hoàn tiền |
| **Dịch vụ không đạt yêu cầu** | 30-50% | 5-7 ngày | Admin xem xét từng trường hợp |

#### Quy trình hoàn tiền

```
[Bước 1] Patient/Expert gửi yêu cầu hoàn tiền qua app
         (Mục: "Yêu cầu hoàn tiền" + Lý do)
         ↓
[Bước 2] Admin nhận yêu cầu và xem xét trong 24h
         ↓
[Bước 3] Admin kiểm tra:
         - Lý do hoàn tiền có chính đáng không?
         - Có bằng chứng không?
         - Quy định hoàn tiền áp dụng cho trường hợp này
         ↓
[Bước 4A] Chấp nhận hoàn tiền:
          → Tính toán số tiền hoàn lại (100%, 80%, 50%...)
          → Thực hiện hoàn tiền qua cổng thanh toán
          → Thời gian: 3-5 ngày làm việc (tùy phương thức)
          ↓
[Bước 4B] Từ chối hoàn tiền:
          → Gửi thông báo kèm lý do rõ ràng cho Patient
          ↓
[Bước 5] Gửi thông báo trạng thái hoàn tiền cho Patient
         ↓
[Bước 6] Lưu vào lịch sử giao dịch và báo cáo tài chính
```

### 3. Chính sách hoàn tiền của Platform

**Nguyên tắc chung:**
- Platform cam kết hoàn tiền nếu dịch vụ không được thực hiện
- Thời gian hoàn tiền: 3-5 ngày làm việc
- Phí hoàn tiền (refund fee): Platform chịu, không trừ vào số tiền hoàn lại
- Nếu hoàn tiền do lỗi của Rescuer/Expert → Platform sẽ xử lý kỷ luật (cảnh cáo, khóa tài khoản)

---

## 📈 BÁO CÁO TÀI CHÍNH (ADMIN)

### Dashboard tài chính Admin

Admin có thể theo dõi các chỉ số sau:

#### 1. Doanh thu tổng thể

| Chỉ số | Công thức | Ví dụ |
|--------|-----------|-------|
| **Tổng giao dịch trong tháng** | Số lượng giao dịch | 1,234 giao dịch |
| **Tổng giá trị giao dịch** | Tổng tiền Patient đã trả | 450,000,000 VNĐ |
| **Doanh thu Platform** | 10% tổng giá trị | 45,000,000 VNĐ |
| **Doanh thu Rescuer** | 85% từ cứu hộ | 280,000,000 VNĐ |
| **Doanh thu Expert** | 90% từ tư vấn | 108,000,000 VNĐ |
| **Quỹ bảo hiểm tích lũy** | 5% từ cứu hộ | 17,000,000 VNĐ |

#### 2. Phân tích theo loại dịch vụ

```
┌────────────────────────────────────────────────────────┐
│                   THÁNG 12/2025                        │
├────────────────────────────────────────────────────────┤
│                                                        │
│  Cứu hộ rắn:                                          │
│  - Số ca: 856 ca                                      │
│  - Tổng tiền: 320,000,000 VNĐ                        │
│  - Trung bình: 373,832 VNĐ/ca                        │
│  - Rescuer nhận: 272,000,000 VNĐ (85%)              │
│  - Platform: 32,000,000 VNĐ (10%)                    │
│  - Bảo hiểm: 16,000,000 VNĐ (5%)                    │
│                                                        │
│  Tư vấn chuyên gia:                                   │
│  - Số buổi: 378 buổi                                  │
│  - Tổng tiền: 130,000,000 VNĐ                        │
│  - Trung bình: 344,086 VNĐ/buổi                      │
│  - Expert nhận: 117,000,000 VNĐ (90%)               │
│  - Platform: 13,000,000 VNĐ (10%)                    │
│                                                        │
│  TỔNG DOANH THU PLATFORM: 45,000,000 VNĐ             │
│                                                        │
└────────────────────────────────────────────────────────┘
```

#### 3. Báo cáo thanh toán

| Trạng thái | Số lượng | Tỷ lệ | Giá trị |
|------------|----------|-------|---------|
| **Đã thanh toán** | 1,156 | 93.7% | 421,000,000 VNĐ |
| **Đang chờ thanh toán** | 56 | 4.5% | 21,000,000 VNĐ |
| **Tranh chấp** | 15 | 1.2% | 6,500,000 VNĐ |
| **Đã hoàn tiền** | 7 | 0.6% | 2,800,000 VNĐ |
| **TỔNG** | 1,234 | 100% | 451,300,000 VNĐ |

#### 4. Xuất báo cáo

Admin có thể xuất các báo cáo sau:
- **Báo cáo ngày:** Doanh thu hàng ngày
- **Báo cáo tuần:** Doanh thu theo tuần
- **Báo cáo tháng:** Tổng hợp chi tiết theo tháng (FE-33)
- **Báo cáo quý:** Phân tích xu hướng theo quý
- **Báo cáo năm:** Tổng kết doanh thu cả năm

**Định dạng xuất báo cáo:**
- PDF (in ấn, gửi email)
- Excel (phân tích chi tiết)
- CSV (import vào phần mềm kế toán)

---

## 🔐 BẢO MẬT & AN TOÀN THANH TOÁN

### Các biện pháp bảo mật

1. **Mã hóa dữ liệu:**
   - Tất cả thông tin thanh toán được mã hóa SSL/TLS
   - Thông tin thẻ không được lưu trên server (tokenization)
   - Tuân thủ chuẩn PCI DSS

2. **Xác thực giao dịch:**
   - OTP qua SMS cho giao dịch > 500,000 VNĐ
   - 3D Secure cho thanh toán thẻ quốc tế
   - Biometric (vân tay/Face ID) trên mobile

3. **Phòng chống gian lận:**
   - Giám sát giao dịch bất thường (quá nhiều giao dịch trong ngày)
   - Xác minh vị trí GPS (Patient và Rescuer phải gần nhau)
   - Hệ thống chống rửa tiền (AML)

4. **Bảo vệ dữ liệu cá nhân:**
   - Tuân thủ GDPR và luật bảo vệ dữ liệu Việt Nam
   - Chỉ hiển thị 4 số cuối thẻ
   - Không chia sẻ thông tin thanh toán cho bên thứ 3

---

## 📞 HỖ TRỢ & GIẢI ĐÁP

### Câu hỏi thường gặp (FAQ)

**Q1: Tôi bị trừ tiền nhưng Rescuer không đến, làm sao?**
- A: Hãy liên hệ ngay với Admin qua app → "Báo cáo vấn đề" → "Yêu cầu hoàn tiền". Admin sẽ kiểm tra và hoàn tiền trong 24h nếu xác nhận Rescuer không đến.

**Q2: Tôi là Rescuer, khi nào tôi nhận được tiền?**
- A: Sau khi Patient thanh toán, tiền sẽ được chuyển vào tài khoản của bạn trong vòng 5-10 phút. Bạn có thể rút tiền về ngân hàng bất kỳ lúc nào.

**Q3: Phí 10% của Platform bao gồm những gì?**
- A: Phí Platform bao gồm: chi phí vận hành server, cổng thanh toán, bảo trì hệ thống, hỗ trợ khách hàng 24/7, marketing, và các tính năng AI.

**Q4: Nếu tôi hủy lịch tư vấn với Expert, có được hoàn tiền không?**
- A: 
  - Hủy trước 2h: hoàn 80% (mất 20% phí hủy)
  - Hủy trong 2h: hoàn 50%
  - Expert không tham gia: hoàn 100%

**Q5: Tôi có thể thanh toán bằng tiền mặt không?**
- A: Có, bạn có thể thanh toán trực tiếp bằng tiền mặt cho Rescuer. Tuy nhiên, hệ thống khuyến khích thanh toán qua app để có bảo vệ và hóa đơn điện tử.

**Q6: Quỹ bảo hiểm 5% dùng để làm gì?**
- A: Quỹ bảo hiểm được sử dụng để hỗ trợ Rescuer khi gặp tai nạn trong quá trình cứu hộ (bị rắn cắn, chấn thương...). Đây là chương trình bảo hiểm do Platform tài trợ.

---

## 📋 TỔNG KẾT

### Sơ đồ luồng tiền tổng quan

```
                          ┌─────────────────────┐
                          │                     │
                          │   PATIENT (100%)    │
                          │                     │
                          └──────────┬──────────┘
                                     │
                    ┌────────────────┴────────────────┐
                    │                                  │
                    ▼                                  ▼
        ┌───────────────────┐              ┌───────────────────┐
        │  CỨHỘ RẮN      │              │  TƯ VẤN EXPERT    │
        │   (500K)          │              │   (300K)          │
        └─────────┬─────────┘              └─────────┬─────────┘
                  │                                    │
        ┌─────────┴──────────┐              ┌─────────┴─────────┐
        │                     │              │                    │
        ▼                     ▼              ▼                    ▼
   ┌─────────┐         ┌─────────┐    ┌─────────┐        ┌─────────┐
   │ RESCUER │         │PLATFORM │    │  EXPERT │        │PLATFORM │
   │  425K   │         │  50K    │    │  270K   │        │  30K    │
   │  (85%)  │         │  (10%)  │    │  (90%)  │        │  (10%)  │
   └─────────┘         └─────────┘    └─────────┘        └─────────┘
        │                    │
        ▼                    ▼
   ┌─────────┐         ┌─────────┐
   │ BẢO HIỂM│         │         │
   │  25K    │         │  (Chi   │
   │  (5%)   │         │  phí)   │
   └─────────┘         └─────────┘
```

### Điểm chính cần nhớ

1. **Cứu hộ rắn:** 85% Rescuer + 10% Platform + 5% Bảo hiểm
2. **Tư vấn Expert:** 90% Expert + 10% Platform
3. **Hỗ trợ khẩn cấp:** Platform trả hoặc Rescuer chia 10% cho Expert
4. **Thanh toán cứu hộ:** SAU khi hoàn thành
5. **Thanh toán tư vấn:** TRƯỚC khi bắt đầu (escrow)
6. **Hoàn tiền:** 3-5 ngày làm việc
7. **Phí giao dịch:** Platform chịu
8. **Bảo mật:** Tuân thủ PCI DSS và các chuẩn quốc tế

---

## 📎 PHỤ LỤC

### Danh sách tính năng liên quan đến thanh toán

**Patient:**
- FE-27: Thanh toán phí tư vấn chuyên gia rắn trực tuyến
- FE-28: Thanh toán phí cứu hộ rắn trực tiếp cho đội cứu hộ qua nền tảng
- FE-29: Theo dõi trạng thái thanh toán và hóa đơn điện tử
- FE-30: Xem lịch sử giao dịch và chi tiết dịch vụ đã sử dụng

**Rescuer:**
- FE-24: Chấp nhận yêu cầu cứu hộ có trả phí từ bệnh nhân
- FE-25: Theo dõi doanh thu, trạng thái thanh toán và lịch sử giao dịch
- FE-26: Nhận thanh toán qua nền tảng sau khi hoàn thành cứu hộ
- FE-27: Xem đánh giá và nhận phản hồi từ khách hàng để cải thiện ưu tiên xếp hạng

**Expert:**
- FE-13: Thiết lập mức phí tư vấn trực tuyến
- FE-14: Nhận thanh toán qua nền tảng và xuất hóa đơn điện tử
- FE-15: Xem báo cáo doanh thu theo tháng/quý
- FE-16: Theo dõi số lượt tư vấn và đánh giá từ khách hàng

**Admin:**
- FE-30: Thiết lập mức phí cho dịch vụ cứu hộ và tư vấn chuyên gia
- FE-31: Theo dõi tổng doanh thu và phân chia thu nhập cho rescuer/expert
- FE-32: Quản lý thanh toán giữa bệnh nhân – rescuer/expert – nền tảng
- FE-33: Tạo báo cáo tài chính định kỳ (tháng/quý/năm)
- FE-34: Quản lý hoa hồng nền tảng và chính sách hoàn tiền
- FE-35: Xử lý tranh chấp thanh toán và yêu cầu hoàn tiền

---

**HẾT TÀI LIỆU**

*Tài liệu này là phần của SnakeAid Platform Documentation*  
*Liên hệ Admin nếu có thắc mắc về luồng thanh toán*
