# RESCUE REQUEST FLOW - UI DESIGN SCREENS (PATIENT ROLE)

## Thông tin tài liệu
- **Tên dự án:** SnakeAid - AI-Powered Platform for Snakebite First Aid and Rescue Support
- **Module:** Patient Mobile Application
- **Role:** 🧑 **PATIENT** (Người dùng phát hiện rắn và yêu cầu cứu hộ)
- **Flow:** Rescue Request Flow (Yêu cầu cứu hộ rắn)
- **Công cụ thiết kế:** Stitch with Google (prompt-based design)
- **Số lượng màn hình:** 11 screens (8 main screens + 3 alternative/error screens)
- **Ngày tạo:** December 4, 2025
- **Location:** `/02-UI-Design/Patient-Rescue-Request-Flow-Screens.md`

> **⚠️ LƯU Ý:** Document này chỉ cover màn hình cho **PATIENT role**. 
> Màn hình cho **Rescuer** và **Expert** sẽ được thiết kế trong documents riêng.

---

## 🎨 Design System Overview

### Color Palette:
- **Primary Color:** Forest Green `#228B22`
- **Background:** White `#FFFFFF`
- **Text Primary:** Dark Gray `#333333`
- **Text Secondary:** Medium Gray `#666666`
- **Accent - Emergency:** Red `#DC3545`
- **Accent - Warning:** Amber `#FFC107`
- **Accent - Success:** Green `#28A745`
- **Accent - Info:** Blue `#007BFF`

### Typography:
- **Logo:** Bold, Large (32-36pt)
- **Headings:** Semi-bold (20-24pt)
- **Body Text:** Regular (16-18pt)
- **Button Text:** Medium (16pt)
- **Caption:** Regular (14pt)

### Component Style:
- **Cards:** Rounded corners (12px), subtle shadow
- **Buttons:** Rounded (8px), clear hierarchy (Primary/Secondary)
- **Input Fields:** Outlined style, rounded (8px)
- **Minimal icons:** Only essential ones (star rating, arrow navigation)

---

## 📱 SCREEN DESIGNS & PROMPTS

> **🧑 Tất cả screens dưới đây là cho PATIENT role** - người dùng phát hiện rắn và yêu cầu cứu hộ

---

### Screen 1: Report Snake Discovery Screen (Patient)

#### Thông tin màn hình:
- **Tên:** Màn hình báo cáo phát hiện rắn
- **Mục đích:** Cho phép người dùng báo cáo phát hiện rắn với ảnh chụp và thông tin chi tiết
- **Flow position:** Giai đoạn 2.1 - Phát hiện và báo cáo rắn
- **Priority:** ⭐⭐⭐ (Cao nhất)

#### Key Components:
1. **Header:**
   - Back button (top-left)
   - Title: "Report Snake Sighting"
   - Info icon (top-right)

2. **Camera Section:**
   - Large dashed border rectangle (camera capture area)
   - Camera icon in center
   - Text: "Take photo of the snake"
   - Subtitle: "Multiple angles recommended"
   - Primary button: "Open Camera"
   - Secondary text link: "Choose from Gallery"

3. **Location Section:**
   - Auto-detected GPS icon with green checkmark
   - Text: "Location automatically detected"
   - Address preview (gray text)
   - Small text link: "Edit location manually"

4. **Additional Information Card:**
   - Title: "Additional Details (Optional)"
   - 4 input fields with labels:
     - "Specific location" (text input: e.g., "in house/garden/street")
     - "Estimated size" (dropdown: small/medium/large)
     - "Snake behavior" (text input: e.g., "moving/stationary/aggressive")
     - "Urgency level" (3 chips: Low/Medium/High)

5. **Action Buttons:**
   - Large primary button (forest green): "Submit Report →"
   - Text below button: "AI will analyze the snake species"

#### Stitch Prompt (English):

```
Mobile app screen for reporting snake discovery in emergency assistance app "SnakeAid". Clean modern design with forest green (#228B22) primary color on white background.

Top navigation: Back arrow left, centered title "Báo Cáo Phát Hiện Rắn", info icon right.

Main content area starts with large camera capture section: dashed border rectangle (aspect ratio 4:3) with light gray background. Center contains camera icon and text "Chụp ảnh con rắn" in dark gray. Below that, smaller text "Nên chụp từ nhiều góc độ" in medium gray. Below rectangle, large forest green button "Mở Camera" and small gray text link "Chọn từ thư viện".

Below camera section, white card with subtle shadow labeled "Vị Trí". Inside card: green checkmark icon next to "Đã tự động xác định vị trí" text. Below that, gray text showing address preview "123 Tên đường, Quận...". Small blue text link "Chỉnh sửa vị trí thủ công" at bottom right of card.

Next section titled "Thông Tin Bổ Sung (Tùy chọn)" in dark gray. White card containing 4 form fields vertically stacked with spacing:
- Text input labeled "Vị trí cụ thể" with placeholder "trong nhà/vườn/đường phố"
- Dropdown labeled "Kích thước ước tính" showing "Chọn kích thước"
- Text input labeled "Hành vi của rắn" with placeholder "đang di chuyển/đứng yên/hung dữ"
- Three horizontal chips labeled "Thấp", "Trung bình", "Cao" under label "Mức độ khẩn cấp". Medium chip has forest green border (selected state).

Bottom of screen: Large solid forest green button "Gửi Báo Cáo →" spanning full width with padding. Below button, centered gray text "AI sẽ phân tích loài rắn".

Design: Clean medical/utility app style, clear form hierarchy, mobile-optimized touch targets, minimal decorative elements.
```

#### Notes for Stitch:
- Nếu camera icon không rõ → "Use simple outline camera icon, centered in dashed rectangle"
- Nếu chips không đều → "Ensure three chips are equal width with 8px spacing"
- Location card phải nổi bật với green checkmark để user biết GPS đã hoạt động

---

### Screen 2: AI Snake Recognition Result Screen

#### Thông tin màn hình:
- **Tên:** Màn hình kết quả nhận diện rắn bằng AI
- **Mục đích:** Hiển thị kết quả phân tích AI về loài rắn và đưa ra 2 lựa chọn hành động
- **Flow position:** Sau khi submit báo cáo, AI xử lý và trả về kết quả
- **Priority:** ⭐⭐⭐

#### Key Components:
1. **Header:**
   - Back button
   - Title: "Snake Identified"
   - Close button (X)

2. **Uploaded Image Display:**
   - Show the photo user uploaded (thumbnail preview)
   - Small edit icon to retake/change photo

3. **AI Result Card:**
   - Badge: "AI Analysis" with icon
   - Snake name (Vietnamese + Scientific name)
   - Example: "Rắn hổ mang chúa (Ophiophagus hannah)"
   - Confidence level: "95% Match"

4. **Danger Level Indicator:**
   - Color-coded alert box:
     - High danger: Red background with "⚠️ HIGHLY VENOMOUS"
     - Medium: Amber with "⚠️ MILDLY VENOMOUS"
     - Low: Green with "✓ NON-VENOMOUS"
   - Risk description text below

5. **Snake Information Summary:**
   - Expandable section titled "Species Details"
   - Bullet points:
     - Habitat
     - Behavior
     - Distribution area

6. **Action Choice Section:**
   - Bold heading: "What would you like to do?"
   - Two large option cards (vertically stacked):
     
     **Option A Card (Primary):**
     - Icon: Rescue truck or person icon
     - Title: "Request Rescue Team"
     - Subtitle: "Professional snake catcher will arrive"
     - Badge: "Paid Service"
     - Right arrow
     
     **Option B Card (Secondary):**
     - Icon: Bell or alert icon
     - Title: "Alert Community Only"
     - Subtitle: "Notify nearby users about snake sighting"
     - Badge: "Free"
     - Right arrow

#### Stitch Prompt (English):

```
Mobile app screen showing AI snake identification results for emergency snake app "SnakeAid". Modern clean interface with forest green (#228B22) brand color.

Top navigation: Back arrow left, centered title "Snake Identified", X close button right.

Content begins with small uploaded image thumbnail (square, rounded corners, 80px) showing user's snake photo. Small pencil edit icon overlaid on bottom-right of thumbnail.

Below image, prominent white card with subtle shadow labeled with small badge "AI Analysis" in top-left (forest green background, white text). Inside card: Large bold heading "Rắn hổ mang chúa" in dark gray. Below that, italic gray text "(Ophiophagus hannah)". Small green badge showing "95% Match".

Next, full-width alert box with red background (#FFEBEE) and red left border. Contains warning emoji and bold text "⚠️ HIGHLY VENOMOUS" in red. Below that, smaller gray text "This snake species can cause serious harm. Keep distance and contact professionals."

Below alert, expandable section with heading "Species Details" and small down arrow. When expanded, shows 3 bullet points in gray text:
• Habitat: Forests and grasslands
• Behavior: Aggressive when threatened
• Distribution: Southeast Asia regions

Large heading "What would you like to do?" in dark gray below species info.

Two large vertically stacked cards with white background and subtle shadow:

CARD 1 (primary focus): Left side has rescue icon. Main text "Request Rescue Team" in bold dark gray. Subtitle below "Professional snake catcher will arrive" in medium gray. Small amber badge "Paid Service" in top-right. Right arrow on far right. Forest green left border (4px).

CARD 2 (secondary): Left side has bell icon. Main text "Alert Community Only" in bold. Subtitle "Notify nearby users about snake sighting" in gray. Small green badge "Free" in top-right. Right arrow on far right. Gray left border (2px).

Design: Card-based medical app interface, clear visual hierarchy, color-coded danger levels, tap-friendly card heights (minimum 80px).
```

#### Notes for Stitch:
- Danger level box phải rất nổi bật (full width, strong color)
- Nếu scientific name hiển thị khó đọc → "Use italic gray text for scientific name, smaller than Vietnamese name"
- 2 option cards phải có kích thước bằng nhau nhưng visual weight khác nhau (primary có border màu)

---

### Screen 3: Request Rescue Confirmation Screen

#### Thông tin màn hình:
- **Tên:** Màn hình xác nhận yêu cầu cứu hộ
- **Mục đích:** Hiển thị ước tính phí dịch vụ và cho phép người dùng xác nhận yêu cầu
- **Flow position:** Sau khi chọn "Request Rescue Team"
- **Priority:** ⭐⭐⭐

#### Key Components:
1. **Header:**
   - Back button
   - Title: "Confirm Rescue Request"

2. **Service Summary Card:**
   - Icon: Checkmark
   - Service type: "Snake Rescue Service"
   - Snake species detected
   - Your location preview

3. **Estimated Fee Section:**
   - Title: "Service Fee"
   - Base fee amount (e.g., "300,000 VNĐ")
   - Platform fee (10%): "30,000 VNĐ"
   - Divider line
   - Total amount (bold, large): "330,000 VNĐ"
   - Small note: "Final fee may vary based on actual service"

4. **What Happens Next:**
   - Numbered steps (1-2-3) with icons:
     1. "Finding nearby rescuer (2-5 min)"
     2. "Rescuer arrives and handles snake"
     3. "Payment after completion"

5. **Important Notes:**
   - Yellow info box with bullet points:
     - "Stay safe, keep distance from snake"
     - "Rescuer response time: 15-60 minutes"
     - "You can track rescuer location on map"

6. **Action Buttons:**
   - Large primary button (forest green): "Confirm & Request Rescue"
   - Secondary text link: "Cancel and go back"

#### Stitch Prompt (English):

```
Mobile app confirmation screen for snake rescue request in app "SnakeAid". Clean transactional interface with forest green (#228B22) primary color.

Top navigation: Back arrow left, centered title "Xác Nhận Yêu Cầu Cứu Hộ".

Main content starts with white card containing checkmark icon in forest green circle. Next to icon: bold text "Dịch Vụ Cứu Hộ Rắn". Below that, two lines of gray text: "Loài: Rắn hổ mang chúa" and "Vị trí: 123 Tên đường, Quận".

Below service card, section titled "Chi Phí Dịch Vụ" in dark gray bold text. White card with pricing breakdown:
- Line 1: "Phí cứu hộ cơ bản" aligned left, "300,000 VNĐ" aligned right, both in dark gray
- Line 2: "Phí nền tảng (10%)" aligned left, "30,000 VNĐ" aligned right, both in medium gray
- Thin gray divider line
- Line 3: "Tổng Cộng" bold dark gray left, "330,000 VNĐ" bold large dark gray right
Below card, small gray italic text "Chi phí cuối cùng có thể thay đổi tùy dịch vụ thực tế".

Next section titled "Điều Gì Sẽ Xảy Ra Tiếp Theo" with 3 numbered steps vertically arranged. Each step has circular number badge (1, 2, 3) in forest green, followed by text description:
1. Tìm đội cứu hộ gần nhất (2-5 phút)
2. Đội cứu hộ đến và xử lý rắn
3. Thanh toán sau khi hoàn tất

Yellow info box (#FFF3CD background, #FFC107 left border) titled "Lưu ý Quan Trọng" with 3 bullet points:
• Giữ an toàn, giữ khoảng cách với rắn
• Thời gian đội cứu hộ phản hồi: 15-60 phút
• Bạn có thể theo dõi vị trí đội cứu hộ trên bản đồ

Bottom section: Large solid forest green button "Xác Nhận & Yêu Cầu Cứu Hộ" spanning full width. Below button, centered gray text link "Hủy và quay lại".

Design: Transaction confirmation style, clear pricing breakdown, reassuring step-by-step explanation, mobile-optimized.
```

#### Notes for Stitch:
- Pricing section phải rất rõ ràng với alignment left-right cho label và amount
- Yellow info box không được quá sáng làm khó đọc
- Nếu numbered steps không tròn đều → "Use circular badges for numbers 1-2-3, each 32px diameter"

---

### Screen 4: Searching for Rescuer Screen

#### Thông tin màn hình:
- **Tên:** Màn hình tìm kiếm đội cứu hộ
- **Mục đích:** Hiển thị trạng thái đang tìm kiếm rescuer phù hợp trong bán kính
- **Flow position:** Giai đoạn 2.2 - Matching với rescuer
- **Priority:** ⭐⭐

#### Key Components:
1. **Header:**
   - Title: "Finding Rescue Team..."
   - Close button (X)

2. **Loading Animation Section:**
   - Animated spinner or pulsing circles
   - Main message: "Searching for available rescuers"
   - Subtitle: "This may take 2-5 minutes"

3. **Search Status Card:**
   - Icon: Radar or search icon
   - Text: "Searching within 10km radius"
   - Secondary text: "3 rescuers found, waiting for response..."

4. **Your Request Summary:**
   - Small card showing:
     - Snake type
     - Your location
     - Time requested

5. **What's Happening (Timeline):**
   - Step 1: ✓ "Request submitted" (green checkmark)
   - Step 2: ⏳ "Notifying nearby rescuers" (in progress, animated)
   - Step 3: ○ "Waiting for acceptance" (pending)

6. **Cancel Option:**
   - Text link at bottom: "Cancel rescue request"

#### Stitch Prompt (English):

```
Mobile app loading screen for finding snake rescuer in app "SnakeAid". Modern waiting interface with forest green (#228B22) accents.

Top navigation: Centered title "Đang Tìm Đội Cứu Hộ..." with X close button on right.

Center of screen features animated loading spinner (circular, forest green color, rotating animation). Below spinner, large bold text "Đang tìm kiếm đội cứu hộ" in dark gray. Below that, smaller gray text "Quá trình này có thể mất 2-5 phút".

White card with subtle shadow below loading section. Contains radar/search icon on left in forest green. Main text "Tìm kiếm trong bán kính 10km" in dark gray bold. Below that, medium gray text "Đã tìm thấy 3 đội cứu hộ, đang chờ phản hồi...".

Below search card, smaller white card titled "Yêu Cầu Của Bạn" in small gray text. Inside card, 3 lines of information with icons:
- Snake icon: "Loài: Rắn hổ mang chúa"
- Location pin icon: "123 Tên đường"
- Clock icon: "2:45 PM"

Section titled "Đang Diễn Ra" with 3 steps displayed vertically:
- Step 1: Green checkmark icon, "Đã gửi yêu cầu" in dark gray (completed state)
- Step 2: Animated hourglass/loading icon in amber, "Đang thông báo cho đội cứu hộ gần đó" in dark gray (active state with pulsing animation)
- Step 3: Empty circle outline in gray, "Chờ chấp nhận" in light gray (pending state)

Bottom of screen: Centered text link in medium gray "Hủy yêu cầu cứu hộ".

Design: Loading/waiting state interface, clear progress indication, calming animation, informative status updates.
```

#### Notes for Stitch:
- Animation phải smooth và calming, không gây căng thẳng
- Nếu Stitch không render animation → "Show static spinner with note 'animated in implementation'"
- Timeline steps phải rõ ràng về trạng thái (completed/in-progress/pending)

---

### Screen 5: Rescuer Matched Screen

#### Thông tin màn hình:
- **Tên:** Màn hình đã tìm thấy đội cứu hộ
- **Mục đích:** Hiển thị thông tin rescuer đã chấp nhận và chuẩn bị di chuyển
- **Flow position:** Sau khi rescuer chấp nhận yêu cầu
- **Priority:** ⭐⭐⭐

#### Key Components:
1. **Header:**
   - Back button
   - Title: "Rescuer Found!"
   - Timer showing elapsed time

2. **Success Banner:**
   - Green success background
   - Checkmark icon
   - Text: "Rescue team is on the way!"

3. **Rescuer Profile Card:**
   - Avatar image (circular)
   - Name of rescuer
   - Star rating (e.g., "4.8 ⭐")
   - Badge: "Verified Rescuer"
   - Total rescues completed: "127 rescues"
   - Phone call button
   - Message button

4. **Status Timeline:**
   - Current status badge: "Preparing equipment" (amber background)
   - Estimated arrival time: "20-30 minutes"
   - Progress bar (optional)

5. **Rescuer Location Preview:**
   - Small map thumbnail showing route
   - Distance: "3.5 km away"
   - Button: "View Live Tracking →" (leads to Screen 6)

6. **Action Buttons:**
   - Primary: "View on Map" (forest green)
   - Secondary: "Call Rescuer" (outlined)
   - Text link: "Cancel rescue" (small, gray)

#### Stitch Prompt (English):

```
Mobile app screen showing matched rescuer in snake rescue app "SnakeAid". Success confirmation interface with forest green (#228B22) primary color.

Top navigation: Back arrow left, centered title "Đã Tìm Thấy Đội Cứu Hộ!", right side shows timer "02:15" in gray.

Full-width success banner with light green background (#D4EDDA) and green checkmark icon. Large bold text "Đội cứu hộ đang trên đường đến!" in dark green (#28A745).

Main content white card with subtle shadow. Top of card shows circular avatar image (60px diameter) centered. Below avatar, bold dark gray text showing rescuer name "Nguyễn Văn A". Below name, yellow star rating "4.8 ⭐" with "(45 đánh giá)" in gray. Small forest green badge below rating displaying "Đã Xác Minh". Bottom line shows gray text "Đã hoàn thành 127 ca cứu hộ".

Two equal-width buttons below profile section in horizontal row:
- Left button: Phone icon with "Gọi" label (forest green outline)
- Right button: Message icon with "Nhắn Tin" label (forest green outline)

Below profile card, white card titled "Trạng Thái Hiện Tại". Inside card, amber badge "Đang chuẩn bị thiết bị" with clock icon. Below badge, text "Thời gian ước tính đến" in gray. Large bold text "20-30 phút" in dark gray.

Next section shows small map thumbnail (rectangular, 16:9 ratio, placeholder with "Xem Trước Bản Đồ"). Overlaid on bottom-left of map: white badge showing "Cách 3.5 km". Right side of map area: forest green button "Xem Theo Dõi Trực Tiếp →".

Bottom section has 2 buttons vertically stacked:
- Large solid forest green button "Xem Trên Bản Đồ"
- Large outlined forest green button "Gọi Đội Cứu Hộ"
Small centered gray text link below buttons "Hủy cứu hộ".

Design: Success state interface, trust-building profile display, clear call-to-action hierarchy, mobile-optimized.
```

#### Notes for Stitch:
- Rescuer profile phải tạo cảm giác tin cậy với verified badge và rating
- Map thumbnail chỉ cần placeholder với text "Map Preview"
- Nếu buttons bị chồng chéo → "Ensure 16px vertical spacing between buttons"

---

### Screen 6: Live Tracking Map Screen

#### Thông tin màn hình:
- **Tên:** Màn hình theo dõi vị trí rescuer real-time
- **Mục đích:** Hiển thị vị trí rescuer đang di chuyển trên bản đồ với ETA
- **Flow position:** Giai đoạn 2.3 - Rescuer đang di chuyển
- **Priority:** ⭐⭐⭐ (Cao nhất - key feature)

#### Key Components:
1. **Header (overlay on map):**
   - Back button (white with shadow)
   - Status text: "Rescue in Progress"
   - Minimize button

2. **Full-Screen Map:**
   - User's location marker (blue pin)
   - Rescuer's location marker (green pin with avatar)
   - Route line connecting both (dashed or solid blue line)
   - Optional: Rescuer's path history (faded trail)

3. **Floating Status Card (bottom sheet):**
   - Draggable handle at top
   - Rescuer avatar + name
   - Current status badge: "On the way" (amber/green)
   - ETA (large, prominent): "Arriving in 12 minutes"
   - Distance remaining: "2.1 km away"
   - Last updated: "Updated 30 seconds ago"

4. **Quick Action Bar (inside status card):**
   - Call button
   - Message button
   - Share location button

5. **Collapse/Expand:**
   - Card can be collapsed to show minimal info (just ETA)
   - Can be expanded to show full details

#### Stitch Prompt (English):

```
Mobile app full-screen map tracking interface for snake rescue app "SnakeAid". Map-first design with overlay UI elements.

Full screen displays map view (use placeholder: light gray background with minimal street lines pattern). 

Map markers:
- Blue location pin marker labeled "You" at bottom-center of map
- Green location pin marker with small circular avatar overlay labeled "Rescuer" at top-left of map
- Dashed blue route line connecting the two pins

Top overlay (translucent white bar with shadow): Back arrow button on left (white background, circular), centered text "Đang Cứu Hộ" in white/dark gray, minimize button on right.

Bottom of screen: Draggable white card with rounded top corners (20px radius) and shadow. Small horizontal handle bar at top-center of card (gray, 40px wide, 4px tall, rounded).

Inside card:
- Left side: Small circular avatar (40px) of rescuer
- Right of avatar: Bold name "Nguyễn Văn A"
- Below name: Small amber badge "Đang trên đường" with arrow icon

Main ETA section (prominent):
- Large bold text "12 phút" in forest green (#228B22), 32pt font
- Above it, small gray text "Sẽ đến trong"
- Below it, medium gray text "Cách 2.1 km"

Below ETA, small gray text "Cập nhật 30 giây trước" with refresh icon.

Bottom section of card: Three equal-width outlined buttons in horizontal row with forest green borders:
- Phone icon button "Gọi"
- Message icon button "Nhắn Tin"  
- Share icon button "Chia Sẻ"

Design: Map-based navigation interface, floating overlay controls, real-time tracking visualization, minimal UI to maximize map visibility.
```

#### Notes for Stitch:
- Map phải chiếm phần lớn màn hình
- Bottom sheet card phải rõ ràng là draggable (có handle)
- ETA text phải rất nổi bật (largest text on screen)
- Nếu Stitch không render map đẹp → "Use simple gray background with minimal street grid lines, focus on markers and route line"

---

### Screen 7: Rescuer Arrived Screen

#### Thông tin màn hình:
- **Tên:** Màn hình rescuer đã đến nơi
- **Mục đích:** Thông báo rescuer đã đến và đang xử lý
- **Flow position:** Sau khi rescuer cập nhật "Đã đến"
- **Priority:** ⭐⭐

#### Key Components:
1. **Header:**
   - Back button
   - Title: "Rescuer Arrived"
   - Timer (total elapsed time)

2. **Status Banner:**
   - Green background
   - Checkmark icon
   - Text: "The rescuer is now at your location"

3. **Current Status Card:**
   - Large icon (person with tool)
   - Status badge: "Handling snake" (amber or blue)
   - Description: "The rescuer is safely capturing the snake"

4. **Rescuer Info Summary:**
   - Avatar
   - Name
   - Quick action buttons: Call / Message

5. **What to Do:**
   - Instructions for patient:
     - "Stay at a safe distance"
     - "Do not approach the snake"
     - "The rescuer will update you when complete"

6. **Estimated Completion:**
   - Text: "Typical rescue takes 10-20 minutes"

7. **Action Button:**
   - Text link: "Cancel rescue (if needed)"

#### Stitch Prompt (English):

```
Mobile app status screen showing rescuer has arrived for snake rescue in app "SnakeAid". Confirmation interface with forest green (#228B22) theme.

Top navigation: Back arrow left, centered title "Đội Cứu Hộ Đã Đến", right side timer "15:30".

Full-width success banner with light green background (#D4EDDA) and green checkmark icon on left. Bold text "Đội cứu hộ đã có mặt tại vị trí của bạn" in dark green.

Main white card with subtle shadow. Center contains large icon illustration of person with rescue tool (simple line art, forest green color). Below icon, blue badge "Đang Xử Lý" with wrench/tool icon. Below badge, medium gray text "Đội cứu hộ đang an toàn bắt rắn".

Below status card, smaller white card showing horizontal layout: Left side has small circular avatar (50px) of rescuer. Right side shows bold name "Nguyễn Văn A" with two small outlined buttons below: "Gọi" and "Nhắn Tin" in forest green borders.

Next section titled "Điều Cần Làm" in dark gray bold. White card with yellow-amber background (#FFF3CD) containing 3 bullet points:
• Giữ khoảng cách an toàn
• Không tiếp cận con rắn
• Đội cứu hộ sẽ thông báo khi hoàn tất

Below instructions, gray text "Thường mất khoảng 10-20 phút để cứu hộ" with clock icon.

Bottom: Centered small gray text link "Hủy cứu hộ (nếu cần)".

Design: In-progress status interface, reassuring messaging, clear safety instructions, minimal interaction needed.
```

#### Notes for Stitch:
- Screen này tập trung vào reassurance - patient cần biết mọi việc đang được xử lý
- Icon minh họa rescuer phải đơn giản và professional
- Yellow instruction box phải dễ đọc với contrast tốt

---

### Screen 8: Payment & Rating Screen

#### Thông tin màn hình:
- **Tên:** Màn hình thanh toán và đánh giá
- **Mục đích:** Xử lý thanh toán và cho phép đánh giá rescuer sau khi hoàn thành
- **Flow position:** Giai đoạn 2.4 - Sau khi rescue hoàn tất
- **Priority:** ⭐⭐⭐

#### Key Components:
1. **Header:**
   - Back button
   - Title: "Service Complete"

2. **Completion Banner:**
   - Green success background
   - Checkmark icon
   - Text: "Snake successfully removed!"
   - Subtitle: "Thank you for using SnakeAid"

3. **Service Summary Card:**
   - Rescuer info (avatar + name)
   - Service details:
     - Snake species handled
     - Time taken: "25 minutes"
     - Date & time completed
   - Photos (if uploaded by rescuer): thumbnails of captured snake

4. **Invoice Section:**
   - Title: "Payment Details"
   - Breakdown:
     - Base rescue fee: "300,000 VNĐ"
     - Platform fee (10%): "30,000 VNĐ"
     - Divider
     - Total: "330,000 VNĐ" (bold, large)

5. **Payment Method Selection:**
   - Title: "Select Payment Method"
   - Radio buttons or cards for:
     - Momo (with logo)
     - VNPay (with logo)
     - ZaloPay (with logo)
     - Credit Card

6. **Rating Section:**
   - Title: "Rate Your Experience"
   - 5 star rating (tap to select)
   - Text input: "Write a review (optional)"
   - Character count: "0/200"

7. **Action Buttons:**
   - Large primary button: "Pay & Submit Rating"
   - Secondary text link: "Pay later / Dispute"

#### Stitch Prompt (English):

```
Mobile app payment and rating screen for completed snake rescue in app "SnakeAid". Transaction completion interface with forest green (#228B22) primary color.

Top navigation: Back arrow left, centered title "Hoàn Thành Dịch Vụ".

Full-width success banner with light green background (#D4EDDA). Large green checkmark icon centered above text. Bold dark green text "Đã loại bỏ rắn thành công!" Below that, smaller gray text "Cảm ơn bạn đã sử dụng SnakeAid".

Main white card showing service summary. Top shows small circular avatar (50px) and bold name "Nguyễn Văn A" next to it. Below, 3 lines of gray text with icons:
- Snake icon: "Loài: Rắn hổ mang chúa"
- Clock icon: "Thời gian: 25 phút"
- Calendar icon: "04/12/2025 - 3:15 PM"

Horizontal row of 2 small thumbnail images (square, rounded corners) labeled "Ảnh từ ca cứu hộ".

Below photos, section titled "Chi Tiết Thanh Toán" in dark gray bold. White card with pricing breakdown:
- "Phí cứu hộ cơ bản" left aligned, "300,000 VNĐ" right aligned (dark gray)
- "Phí nền tảng (10%)" left aligned, "30,000 VNĐ" right aligned (medium gray)
- Thin gray divider line
- "Tổng Cộng" bold left, "330,000 VNĐ" bold large right (forest green color)

Next section titled "Chọn Phương Thức Thanh Toán". Four horizontally arranged payment option cards (equal width, white background, forest green border when selected):
- Card 1: "Momo" with Momo logo placeholder
- Card 2: "VNPay" with VNPay logo placeholder
- Card 3: "ZaloPay" with ZaloPay logo placeholder
- Card 4: "Thẻ" with credit card icon
First card (Momo) has forest green border indicating selection.

Below payment, section titled "Đánh Giá Trải Nghiệm". Row of 5 large star outlines (yellow/amber color). First 4 stars filled, 5th empty (indicating 4-star rating). 

Below stars, multiline text input field with placeholder "Viết nhận xét (tùy chọn)" and character counter "0/200" in bottom-right.

Bottom section: Large solid forest green button "Thanh Toán & Gửi Đánh Giá" spanning full width. Below button, centered gray text link "Thanh toán sau / Khiếu nại".

Design: Transaction completion flow, clear pricing breakdown, integrated rating system, mobile payment optimization.
```

#### Notes for Stitch:
- Payment method cards phải rõ ràng về selection state (border color change)
- Star rating phải large và easy to tap (minimum 44px touch target)
- Pricing breakdown phải align rõ ràng left-right như invoice thực tế
- Nếu logo payment không có → "Use simple text labels with colored backgrounds: Momo (pink), VNPay (blue), ZaloPay (blue), Card (gray)"

---

## 📋 SUMMARY - SCREEN FLOW

### Luồng các màn hình theo thứ tự:

```
1. Trang Chủ
   → (Người dùng chọn "Báo Cáo Rắn" từ Quick Actions)
   ↓
2. Màn Hình Báo Cáo Phát Hiện Rắn
   → (Chụp ảnh, điền thông tin, gửi báo cáo)
   ↓
3. Màn Hình Kết Quả Nhận Diện AI
   → (Người dùng chọn "Yêu Cầu Đội Cứu Hộ")
   ↓
4. Màn Hình Xác Nhận Yêu Cầu Cứu Hộ
   → (Xác nhận và thanh toán phí dịch vụ)
   ↓
5. Màn Hình Đang Tìm Đội Cứu Hộ
   → (Hệ thống tìm và ghép nối với rescuer)
   ↓
6. Màn Hình Đã Tìm Thấy Đội Cứu Hộ
   → (Người dùng chọn "Xem Theo Dõi Trực Tiếp")
   ↓
7. Màn Hình Bản Đồ Theo Dõi Trực Tiếp
   → (Đội cứu hộ đến nơi và bắt đầu xử lý)
   ↓
8. Màn Hình Đội Cứu Hộ Đã Đến
   → (Đội cứu hộ hoàn thành nhiệm vụ)
   ↓
9. Màn Hình Thanh Toán & Đánh Giá
   → (Người dùng thanh toán và đánh giá, kết thúc)
```

---

## 🎯 DESIGN PRINCIPLES FOR RESCUE FLOW

### 1. **Trust & Safety:**
- Hiển thị verified badges và ratings để tạo niềm tin
- Luôn hiển thị thông tin rescuer rõ ràng (avatar, name, contact)
- Cung cấp options để liên lạc (call/message) mọi lúc

### 2. **Real-time Updates:**
- ETA và distance phải update liên tục
- Status badges thay đổi theo real-time (On the way → Arrived → Handling)
- "Last updated X seconds ago" để user biết data mới nhất

### 3. **Transparency:**
- Pricing breakdown rõ ràng trước khi confirm
- Hiển thị "what happens next" để user biết quy trình
- Photos và details sau rescue để user xác nhận công việc

### 4. **Progressive Disclosure:**
- Không overwhelming user với quá nhiều info cùng lúc
- Map screen: focus vào map, details ở bottom sheet
- Expandable sections cho optional info (Species Details)

### 5. **Error Handling:**
- "Cancel rescue" option available ở mọi stage
- "Pay later / Dispute" cho payment issues
- Fallback: "No rescuer found" → suggest alternatives

---

### Screen 9: Community Alert Confirmation Screen

#### Thông tin màn hình:
- **Tên:** Màn hình xác nhận cảnh báo cộng đồng
- **Mục đích:** Hiển thị xác nhận khi user chọn "Alert Community Only" thay vì request rescue
- **Flow position:** Alternative path từ Screen 2 (AI Recognition Result)
- **Priority:** ⭐⭐

#### Key Components:
1. **Header:**
   - Back button
   - Title: "Alert Sent"
   - Close button (X)

2. **Success Icon:**
   - Large checkmark or bell icon
   - Green success color

3. **Confirmation Message:**
   - Main heading: "Community Alert Sent!"
   - Subtitle: "Nearby users have been notified about this snake sighting"

4. **Alert Details Card:**
   - Snake species detected
   - Location
   - Number of users notified (e.g., "27 users within 2km")
   - Time sent

5. **Map Preview:**
   - Small map showing alert radius
   - User's location at center
   - Circular radius indicator

6. **What Happens Next:**
   - Info section explaining:
     - "Nearby users will receive notification"
     - "They can see photo and location"
     - "Alert expires in 24 hours"

7. **Action Buttons:**
   - Primary button: "Back to Home"
   - Secondary text link: "View Alert History"

#### Stitch Prompt (English):

```
Mobile app confirmation screen for community snake alert in app "SnakeAid". Success notification interface with forest green (#228B22) primary color.

Top navigation: Back arrow left, centered title "Đã Gửi Cảnh Báo", X close button right.

Center of screen features large green bell icon (or checkmark with bell) in success green (#28A745), 80px size. Below icon, large bold heading "Đã Gửi Cảnh Báo Cộng Đồng!" in dark gray. Below that, medium gray text "Người dùng lân cận đã được thông báo về rắn này".

White card with subtle shadow showing alert details. Inside card, 4 lines with icons:
- Snake icon: "Loài: Rắn hổ mang chúa"
- Location pin icon: "123 Tên đường, Quận"
- Users icon: "Đã thông báo 27 người trong bán kính 2km"
- Clock icon: "04/12/2025 - 3:15 PM"

Below details card, small map preview (rectangular, 16:9 ratio, placeholder background). Map shows blue pin marker at center with circular radius overlay in light blue transparent color. Text overlay on map bottom: "Bán Kính Cảnh Báo: 2km".

Next section titled "Điều Gì Sẽ Xảy Ra Tiếp Theo" in dark gray bold. White card with light blue background (#E7F3FF) containing 3 bullet points:
• Người dùng lân cận sẽ nhận thông báo
• Họ có thể xem ảnh và vị trí
• Cảnh báo hết hạn sau 24 giờ

Bottom section has 2 elements:
- Large solid forest green button "Về Trang Chủ" spanning full width
- Below button, centered blue text link "Xem Lịch Sử Cảnh Báo"

Design: Success confirmation interface, informative and reassuring, community-focused messaging, clean hierarchy.
```

#### Notes for Stitch:
- Success icon phải lớn và prominent để convey success state
- Map preview với radius circle để visualize alert area
- Light blue info card để distinguish từ yellow warning boxes

---

### Screen 10: No Rescuer Found Screen

#### Thông tin màn hình:
- **Tên:** Màn hình không tìm thấy đội cứu hộ
- **Mục đích:** Hiển thị khi không có rescuer available sau thời gian timeout
- **Flow position:** Alternative path từ Screen 4 (Searching for Rescuer)
- **Priority:** ⭐⭐⭐

#### Key Components:
1. **Header:**
   - Back button
   - Title: "No Rescuer Available"

2. **Status Icon:**
   - Sad face or empty search icon
   - Amber/orange color

3. **Main Message:**
   - Heading: "We couldn't find a rescuer nearby"
   - Explanation: "No rescue teams are available in your area at this time"

4. **Search Details Card:**
   - Show what was searched:
     - "Searched within: 20km radius"
     - "Search duration: 5 minutes"
     - "Rescuers contacted: 8"

5. **Alternative Options Section:**
   - Title: "What You Can Do"
   - 3 option cards:
     
     **Option 1:**
     - Icon: Expand icon
     - "Expand Search Area"
     - "Search up to 50km with +20% service fee"
     - Button: "Try Again"
     
     **Option 2:**
     - Icon: Phone icon
     - "Call Animal Control"
     - "Contact local authorities directly"
     - Button: "Call 115"
     
     **Option 3:**
     - Icon: Bell icon
     - "Alert Community"
     - "Let nearby users know about the snake"
     - Button: "Send Alert"

6. **Bottom Actions:**
   - Text link: "Cancel and go back"

#### Stitch Prompt (English):

```
Mobile app error state screen for no rescuer found in snake rescue app "SnakeAid". Problem-solving interface with forest green (#228B22) theme.

Top navigation: Back arrow left, centered title "Không Có Đội Cứu Hộ".

Center top section shows amber/orange colored icon (empty search or sad face emoji), 64px size. Below icon, large bold heading "Không tìm thấy đội cứu hộ gần đây" in dark gray. Below that, medium gray text "Hiện không có đội cứu hộ nào trong khu vực của bạn".

White card with subtle shadow titled "Tóm Tắt Tìm Kiếm" showing 3 lines:
- "Đã tìm kiếm trong: Bán kính 20km"
- "Thời gian tìm: 5 phút"  
- "Số đội cứu hộ đã liên hệ: 8"
All text in medium gray with small icons on left.

Below summary, bold heading "Bạn Có Thể Làm Gì" in dark gray.

Three vertically stacked option cards with white background and subtle shadow. Each card has left icon, title, subtitle, and right action button:

CARD 1: Left has expand/arrows icon in forest green. Title "Mở Rộng Vùng Tìm Kiếm" bold dark gray. Subtitle "Tìm kiếm trong 50km với phí thêm +20%" in medium gray. Right side: Forest green outlined button "Thử Lại".

CARD 2: Left has phone icon in blue. Title "Gọi Kiểm Soát Động Vật" bold. Subtitle "Liên hệ cơ quan chức năng trực tiếp" in gray. Right side: Blue outlined button "Gọi 115".

CARD 3: Left has bell icon in amber. Title "Cảnh Báo Cộng Đồng" bold. Subtitle "Thông báo cho người dùng lân cận về con rắn" in gray. Right side: Amber outlined button "Gửi Cảnh Báo".

Bottom: Centered gray text link "Cancel and go back".

Design: Error recovery interface, solution-focused, multiple clear alternatives, non-alarming tone.
```

#### Notes for Stitch:
- Không dùng red color để tránh panic - dùng amber/orange cho neutral tone
- 3 option cards phải equal height và rõ ràng về CTA
- "Try Again" option phải nổi bật nhất (forest green color)

---

### Screen 11: Rescue Cancellation Confirmation Screen

#### Thông tin màn hình:
- **Tên:** Màn hình xác nhận hủy cứu hộ
- **Mục đích:** Xác nhận và xử lý khi user hoặc rescuer cancel request
- **Flow position:** Có thể trigger từ nhiều screens (Screen 4, 5, 6, 7)
- **Priority:** ⭐⭐

#### Key Components:
1. **Header:**
   - Back button
   - Title: "Cancel Rescue?"

2. **Warning Icon:**
   - Alert/warning icon (amber color)

3. **Confirmation Message:**
   - Heading: "Are you sure you want to cancel?"
   - Explanation based on stage:
     - If before rescuer arrives: "The rescuer is on the way"
     - If rescuer arrived: "The rescuer has already arrived at location"

4. **Cancellation Fee Info (if applicable):**
   - Yellow info box explaining:
     - "Cancellation after rescuer departs: 50% fee"
     - "Cancellation after arrival: 100% fee"
     - "Free cancellation before rescuer departs"

5. **Reason Selection (optional):**
   - Title: "Why are you cancelling? (Optional)"
   - Radio buttons or dropdown:
     - "Snake already gone"
     - "Took too long"
     - "Found another solution"
     - "Changed my mind"
     - "Other"

6. **Rescuer Info Reminder:**
   - Small card showing rescuer who will be affected
   - Avatar, name, current status

7. **Action Buttons:**
   - Primary button (amber): "Yes, Cancel Rescue"
   - Secondary button (forest green): "No, Continue Rescue"

#### Stitch Prompt (English):

```
Mobile app cancellation confirmation dialog for snake rescue in app "SnakeAid". Decision confirmation interface with forest green (#228B22) theme.

Top navigation: Back arrow left, centered title "Hủy Cứu Hộ?".

Center shows amber warning triangle icon, 64px. Below icon, large bold heading "Bạn có chắc muốn hủy?" in dark gray. Below that, medium gray text "Đội cứu hộ đang trên đường đến vị trí của bạn".

Yellow warning box (#FFF3CD background, #FFC107 left border) titled "Phí Hủy" in bold. Inside box, 3 lines in dark gray:
• Hủy miễn phí trước khi đội cứu hộ khởi hành
• Hủy sau khi khởi hành: Phí 50% (150,000 VNĐ)
• Hủy sau khi đã đến: Phí 100% (300,000 VNĐ)

Below warning box, section titled "Lý do hủy? (Tùy chọn)" in dark gray. White card containing 5 radio button options vertically stacked:
○ Rắn đã biến mất
○ Mất quá nhiều thời gian
○ Đã tìm được giải pháp khác
○ Đổi ý
○ Lý do khác

Bottom section shows small white card with gray border labeled "Thông Tin Đội Cứu Hộ". Horizontal layout: Left has small avatar (40px), right shows name "Nguyễn Văn A" bold and status "Đang di chuyển - còn 8 phút" in gray with amber badge.

Bottom buttons vertically stacked with 12px spacing:
- Large amber button (#FFC107) "Có, Hủy Cứu Hộ"
- Large forest green outlined button "Không, Tiếp Tục Cứu Hộ"

Design: Cautious confirmation interface, clear consequence communication, respectful of rescuer, provides exit option.
```

#### Notes for Stitch:
- Warning box với cancellation fees phải rất rõ ràng
- Green "Continue" button phải nổi bật hơn amber "Cancel" để encourage keeping rescue
- Rescuer info reminder để humanize decision

---

## 📋 SUMMARY - SCREEN FLOW (UPDATED)

### Luồng các màn hình theo thứ tự:

```
1. Trang Chủ
   → (Người dùng chọn "Báo Cáo Rắn" từ Quick Actions)
   ↓
2. Màn Hình Báo Cáo Phát Hiện Rắn
   → (Chụp ảnh, điền thông tin, gửi báo cáo)
   ↓
3. Màn Hình Kết Quả Nhận Diện AI
   ├─→ (Lựa chọn A: Chọn "Yêu Cầu Đội Cứu Hộ")
   │   ↓
   │   4. Màn Hình Xác Nhận Yêu Cầu Cứu Hộ
   │      → (Xác nhận và thanh toán phí dịch vụ)
   │      ↓
   │      5. Màn Hình Đang Tìm Đội Cứu Hộ
   │      ├─→ (Thành công: Tìm thấy đội cứu hộ)
   │      │   ↓
   │      │   6. Màn Hình Đã Tìm Thấy Đội Cứu Hộ
   │      │      → (Chọn "Xem Theo Dõi Trực Tiếp")
   │      │      ↓
   │      │      7. Màn Hình Bản Đồ Theo Dõi Trực Tiếp
   │      │         → (Đội cứu hộ đến nơi và bắt đầu xử lý)
   │      │         ↓
   │      │         8. Màn Hình Đội Cứu Hộ Đã Đến
   │      │            → (Đội cứu hộ hoàn thành nhiệm vụ)
   │      │            ↓
   │      │            9. Màn Hình Thanh Toán & Đánh Giá
   │      │               → (Kết thúc luồng)
   │      │
   │      └─→ (Hết thời gian: Không tìm thấy đội cứu hộ)
   │          ↓
   │          10. Màn Hình Không Có Đội Cứu Hộ
   │              ├─→ Thử lại với bán kính mở rộng → Quay lại Screen 5
   │              ├─→ Gọi dịch vụ khẩn cấp → Thoát app
   │              └─→ Cảnh báo cộng đồng → Screen 9
   │
   └─→ (Lựa chọn B: Chọn "Chỉ Cảnh Báo Cộng Đồng")
       ↓
       9. Màn Hình Xác Nhận Cảnh Báo Cộng Đồng
          → (Kết thúc luồng)

LUỒNG HỦY (có thể truy cập từ Screens 4, 5, 6, 7, 8):
   → Người dùng chọn "Hủy cứu hộ"
   ↓
   11. Màn Hình Xác Nhận Hủy Cứu Hộ
       ├─→ Xác nhận hủy → Quay về Trang Chủ
       └─→ Tiếp tục cứu hộ → Quay lại màn hình trước
```

---

## 🔄 ADDITIONAL ENHANCEMENTS TO CONSIDER

### Screens đã thiết kế đầy đủ trong document này:

✅ **Main Flow (8 screens):**
1. Màn Hình Báo Cáo Phát Hiện Rắn
2. Màn Hình Kết Quả Nhận Diện AI
3. Màn Hình Xác Nhận Yêu Cầu Cứu Hộ
4. Màn Hình Đang Tìm Đội Cứu Hộ
5. Màn Hình Đã Tìm Thấy Đội Cứu Hộ
6. Màn Hình Bản Đồ Theo Dõi Trực Tiếp
7. Màn Hình Đội Cứu Hộ Đã Đến
8. Màn Hình Thanh Toán & Đánh Giá

✅ **Alternative/Error Flows (3 screens):**
9. Màn Hình Xác Nhận Cảnh Báo Cộng Đồng
10. Màn Hình Không Có Đội Cứu Hộ
11. Màn Hình Xác Nhận Hủy Cứu Hộ

### Màn hình bổ sung có thể cần trong future iterations:

1. **Rescuer Rejected Screen:**
   - Khi rescuer từ chối request
   - Tự động tìm rescuer khác
   
2. **Payment Failed Screen:**
   - Khi thanh toán bị lỗi
   - Options to retry hoặc change payment method

3. **Expert Consultation Screen:**
   - Khi rescuer cần tư vấn expert (Flow 3.2 trong swimlane)
   - Video call hoặc chat interface

### Screens có thể thiết kế sau (lower priority):

1. **Rescuer Rejected Screen:**
   - Khi rescuer từ chối trong thời gian chờ
   - Tự động search rescuer khác

2. **Payment Failed Retry Screen:**
   - Khi thanh toán bị lỗi technical
   - Options to retry with same/different method

3. **Expert Consultation Screen:**
   - Khi rescuer request tư vấn từ expert (mentioned in swimlane Flow 3.2)
   - Video call hoặc chat interface để expert support rescuer

---

## 📝 IMPLEMENTATION NOTES

### For Developers:

1. **API Integration Points:**
   - `POST /api/rescue/request` - Submit rescue request (Screen 3)
   - `GET /api/rescue/find-rescuers` - Find available rescuers (Screen 4)
   - `POST /api/rescue/accept` - Rescuer accepts request (Screen 5)
   - `GET /api/rescue/track/:id` - Real-time location tracking (Screen 6)
   - `PUT /api/rescue/status` - Update rescue status (Screens 6, 7)
   - `POST /api/rescue/complete` - Mark rescue complete (Screen 8)
   - `POST /api/rescue/cancel` - Cancel rescue request (Screen 11)
   - `POST /api/payment/process` - Process payment (Screen 8)
   - `POST /api/rating/submit` - Submit rating (Screen 8)
   - `POST /api/alert/community` - Send community alert (Screen 9)

2. **Real-time Features:**
   - WebSocket connection for live location updates
   - Push notifications for status changes
   - Auto-refresh ETA every 30 seconds

3. **Image Handling:**
   - Compress images before upload (max 2MB)
   - Support multiple image upload (max 5 photos)
   - Thumbnail generation for gallery view

4. **Payment Integration:**
   - Integrate Momo, VNPay, ZaloPay SDKs
   - Implement escrow system (hold payment until completion)
   - Handle payment failures gracefully

5. **Map Integration:**
   - Use Google Maps SDK / Mapbox
   - Custom markers for user and rescuer
   - Route calculation with real-time traffic

---

## ✅ CHECKLIST FOR STITCH IMPLEMENTATION

### Before generating with Stitch:

- [ ] Review all 11 screen prompts (8 main + 3 alternative)
- [ ] Confirm color codes match design system
- [ ] Verify all text content is clear and accurate
- [ ] Check that component sizes are specified (when critical)
- [ ] Ensure button hierarchy is clear (primary/secondary)
- [ ] Confirm mobile-first responsive approach
- [ ] Validate error/alternative flows are covered

### After Stitch generates designs:

- [ ] Verify color consistency across all screens
- [ ] Check text readability (contrast ratios)
- [ ] Validate touch target sizes (minimum 44x44px)
- [ ] Test visual hierarchy on each screen
- [ ] Ensure consistent spacing and padding
- [ ] Verify icon consistency and clarity
- [ ] Check that cards have proper shadows and borders
- [ ] Validate that maps and images have proper placeholders

---

## 🔗 RELATED DOCUMENTATION

- Main Flow Document: `/01-Requirements/Main-Flow/Main-Flow.md` (Section 2)
- Swimlane Diagram: `/01-Requirements/Swimlane-Diagram/02-Swimlane-Rescue-Request-Flow.md`
- Feature List: `/01-Requirements/Major-Features/Major-Features-Summary.md`
- Emergency Flow Screens: `/02-UI-Design/Patient-Emergency-Flow-Screens.md` (for reference)

---

**Document Status:** ✅ Complete & Comprehensive - Ready for Stitch implementation  
**Role Coverage:** 🧑 **PATIENT ONLY** (Rescuer & Expert screens in separate documents)
**Screens Covered:** 11 screens (8 main flow + 3 alternative/error flows)
**Coverage:** 100% of swimlane diagram flows including error cases
**Last Updated:** December 4, 2025  

**Next Steps:** 
1. ✅ Generate designs with Stitch for Patient screens
2. ⏳ Create separate document: **Rescuer-Rescue-Request-Flow-Screens.md** (FE-01 to FE-27)
3. ⏳ Create separate document: **Expert-Consultation-Flow-Screens.md** (FE-01 to FE-16)
