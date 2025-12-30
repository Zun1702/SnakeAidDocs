# PATIENT APP - THƯ VIỆN LOÀI RẮN (SNAKE SPECIES LIBRARY)

## Thông tin tài liệu
- **Tên module:** Snake Species Library (Thư viện loài rắn)
- **Mục đích:** Cung cấp thông tin chi tiết về các loài rắn tại Việt Nam để người dùng học hỏi, nhận diện, và phòng tránh
- **Đối tượng:** Patient/User muốn tìm hiểu về rắn, nhận diện loài, học cách phòng tránh
- **Độ ưu tiên:** ★★★ (Medium-High - Educational & Reference)
- **Entry point:** Homepage → Grid Menu → "Thư viện loài rắn" (Badge: 250+)
- **Version:** 1.0
- **Date:** December 24, 2025

---

## MỤC ĐÍCH VÀ PHẠM VI

### Vai trò trong hệ thống SnakeAid:

**1. Educational (Giáo dục):**
- Giúp người dùng nhận biết rắn độc vs rắn không độc
- Hiểu hành vi, môi trường sống của từng loài
- Học cách phòng tránh và ứng xử khi gặp rắn

**2. Reference (Tra cứu):**
- Tìm kiếm loài rắn theo tên, khu vực, mức độ nguy hiểm
- Xem chi tiết đặc điểm, phân bố, độc tính
- So sánh các loài tương tự dễ nhầm lẫn

**3. Support AI Identification (Hỗ trợ AI):**
- Người dùng có thể đối chiếu kết quả AI với thư viện
- Xem thêm ảnh tham khảo của loài đã nhận diện
- Học cách phân biệt các loài giống nhau

**4. Emergency Preparation (Chuẩn bị khẩn cấp):**
- Biết trước loài rắn độc trong khu vực mình sống
- Chuẩn bị kiến thức sơ cứu phù hợp
- Nắm thông tin bệnh viện có huyết thanh tương ứng

---

## DANH SÁCH MÀN HÌNH

### Screen 1: Snake Library Home (Trang chủ thư viện)
- **Tên:** Màn hình tổng quan thư viện loài rắn
- **Entry:** Homepage → "Thư viện loài rắn"
- **Mục đích:** Browse, search, filter 250+ loài rắn
- **Priority:** ★★★ (High)

### Screen 2: Snake Species Detail (Chi tiết loài rắn)
- **Tên:** Màn hình thông tin chi tiết một loài
- **Entry:** Screen 1 → Tap vào card loài rắn
- **Mục đích:** Xem đầy đủ thông tin: đặc điểm, phân bố, nguy hiểm, sơ cứu
- **Priority:** ★★★ (High)

### Screen 3: Compare Snakes (So sánh loài rắn)
- **Tên:** Màn hình so sánh 2-3 loài rắn giống nhau
- **Entry:** Screen 2 → "So sánh với loài tương tự"
- **Mục đích:** Phân biệt rắn độc/không độc dễ nhầm lẫn
- **Priority:** ★★ (Medium)

### Screen 4: Regional Snakes (Rắn theo khu vực)
- **Tên:** Màn hình hiển thị rắn phổ biến ở khu vực người dùng
- **Entry:** Screen 1 → Filter "Khu vực của tôi"
- **Mục đích:** Cảnh báo loài rắn nguy hiểm gần nơi ở
- **Priority:** ★★★ (High)

---

## SCREEN 1: SNAKE LIBRARY HOME

### Thông tin màn hình:
- **Tên:** Trang chủ thư viện loài rắn
- **Mục đích:** Browse, search, filter 250+ loài rắn Việt Nam
- **Flow position:** Homepage → Grid "Thư viện loài rắn" → Screen 1
- **Priority:** ★★★ (High)

### Layout Structure:

```
┌─────────────────────────────────────┐
│ ← Thư viện loài rắn          ⋮     │ Header
├─────────────────────────────────────┤
│ [Tìm tên rắn, đặc điểm...]         │ Search Bar
├─────────────────────────────────────┤
│ Khu vực: Toàn quốc ▼               │ Location Filter
├─────────────────────────────────────┤
│ ╔═══════════════════════════════╗  │
│ ║ QUICK FILTERS (Chips)         ║  │
│ ║ [Tất cả] [Độc] [Không độc]   ║  │
│ ║ [Khu vực của tôi] [Nguy hiểm]║  │
│ ╚═══════════════════════════════╝  │
├─────────────────────────────────────┤
│ Hiển thị 250 loài rắn              │ Count
├─────────────────────────────────────┤
│ ┌───────────────────────────────┐  │
│ │ SNAKE CARD 1                   │  │
│ │ ┌─────┐ Rắn hổ mang chúa      │  │
│ │ │Photo│ Ophiophagus hannah     │  │
│ │ │120px│ [Độc mạnh]            │  │
│ │ └─────┘ Miền Bắc, Trung        │  │
│ └───────────────────────────────┘  │
│ ┌───────────────────────────────┐  │
│ │ SNAKE CARD 2                   │  │
│ │ ┌─────┐ Rắn lục đuôi đỏ       │  │
│ │ │Photo│ Trimeresurus albolabris│  │
│ │ │120px│ [Độc trung bình]      │  │
│ │ └─────┘ Toàn quốc              │  │
│ └───────────────────────────────┘  │
│ ... (scrollable list)              │
└─────────────────────────────────────┘
```

### Key Components:

#### 1. Header:
- **Back button:** ← (left)
- **Title:** "Thư viện loài rắn" (Bold, 20pt, #333)
- **Search icon:** (right, tap to focus search bar)
- **Menu icon:** ⋮ (right)
  - Options: "Yêu thích của tôi", "Lịch sử xem", "Cài đặt hiển thị"

#### 2. Search Bar:
- **Placeholder:** "Tìm tên rắn, đặc điểm, khu vực..."
- **Background:** Light Gray #F5F5F5
- **Height:** 48px
- **Border Radius:** 24px
- **Icon:** Search icon (left, 20px padding)
- **Clear button:** ✕ (right, when typing)
- **Auto-complete:** Hiện gợi ý khi gõ 2+ ký tự

#### 3. Location Filter:
- **Icon:** Globe icon (Forest Green #228B22)
- **Text:** "Khu vực: [Toàn quốc]" (Semi-bold, 16pt)
- **Dropdown:** ▼ (tap to show options)
- **Options:**
  - Toàn quốc (default)
  - Miền Bắc
  - Miền Trung
  - Miền Nam
  - Khu vực của tôi (GPS-based) KHUYẾN NGHỊ

#### 4. Quick Filters (Horizontal Chips):
- **Layout:** Horizontal scrollable chips with 8px gap
- **Chip Design:**
  - Height: 36px
  - Border Radius: 18px
  - Padding: 12px horizontal
  - Active: Forest Green background #228B22, White text
  - Inactive: Light Gray #E0E0E0, Dark Gray text #666

**Filters:**
- **[Tất cả]** (default active) - 250 loài
- **[Độc]** - 50 loài độc
- **[Không độc]** - 200 loài không độc
- **[Khu vực của tôi]** - GPS-based, 15-30 loài
- **[Cực kỳ nguy hiểm]** - Top 10 loài độc mạnh nhất
- **[Dễ nhầm lẫn]** - Các cặp rắn độc/không độc giống nhau

#### 5. Result Count:
- **Text:** "Hiển thị [X] loài rắn" (Semi-bold, 14pt, Gray #666)
- **Update:** Real-time khi filter thay đổi

#### 6. Snake Card (List Item):

**Design:**
- **Height:** 140px
- **Background:** White #FFFFFF
- **Border:** 1px solid #E0E0E0
- **Border Radius:** 12px
- **Shadow:** 0px 2px 6px rgba(0,0,0,0.06)
- **Padding:** 12px
- **Gap:** 12px between cards

**Layout (Horizontal):**

**Left Section (Photo):**
- **Size:** 120px x 120px
- **Border Radius:** 8px
- **Image:** High-quality snake photo
- **Badge (Top-left overlay):** 
  - Red badge for "Độc mạnh"
  - Orange badge for "Độc trung bình"
  - Green badge for "Không độc"

**Right Section (Info):**
- **Vietnamese Name:** 
  - "Rắn hổ mang chúa" (Bold, 18pt, #333)
  - 2 lines max, ellipsis if longer
- **Scientific Name:**
  - "Ophiophagus hannah" (Italic, 14pt, Gray #666)
- **Danger Badge:**
  - "Độc mạnh" (Red background #FFEBEE, Red text #DC3545)
  - OR "Độc trung bình" (Amber background #FFF3CD, Amber text #FFC107)
  - OR "Không độc" (Green background #E8F5E9, Green text #228B22)
  - Size: 12pt, padding 4px 8px, rounded 4px
- **Region:**
  - Icon: Location pin (12px)
  - Text: "Miền Bắc, Trung" (Regular, 13pt, Gray #999)
- **Favorite Icon:**
  - Star icon (24px, top-right corner)
  - Tap to add/remove from favorites
  - Yellow if favorited, Gray outline if not

**Tap Action:**
- Entire card clickable → Navigate to Screen 2 (Detail)

#### 7. Sort & View Options (Menu ⋮):
- **Grid View / List View** toggle
- **Sắp xếp theo:**
  - Tên (A-Z)
  - Độ nguy hiểm (Cao → Thấp)
  - Phổ biến nhất
  - Mới cập nhật

---

### Stitch Prompt (Screen 1):

```
Mobile app screen showing snake species library in "SnakeAid". Educational interface, forest green (#228B22) primary color.

Top navigation: Back arrow left, title "Thư viện loài rắn" (20pt bold), search icon and menu icon (⋮) right.

Search bar below header:
Light gray background (#F5F5F5), rounded 24px, height 48px
Placeholder "Tìm tên rắn, đặc điểm, khu vực..." in gray
Search icon left side, 20px padding

Location filter row:
Globe icon green, text "Khu vực: Toàn quốc" (16pt semi-bold), dropdown arrow (▼)

Horizontal scrollable chips (8px gap):
- Active chip: Green background (#228B22), white text "Tất cả"
- Inactive chips: Light gray (#E0E0E0), dark gray text
- Chips: "Độc", "Không độc", "Khu vực của tôi", "Cực kỳ nguy hiểm", "Dễ nhầm lẫn"
- Height 36px, rounded 18px, 12px horizontal padding

Result count: "Hiển thị 250 loài rắn" (14pt semi-bold gray)

Vertical scrollable list of snake cards (12px gap):

CARD 1:
White background, 1px border (#E0E0E0), rounded 12px, soft shadow
Height 140px, 12px padding
Left: Snake photo 120x120px, rounded 8px
Top-left overlay: Red badge for venomous
Right section (vertical layout):
- "Rắn hổ mang chúa" (18pt bold black)
- "Ophiophagus hannah" (14pt italic gray #666)
- Red danger badge "Độc mạnh" (red background #FFEBEE, red text #DC3545, 12pt, rounded 4px, 4px 8px padding)
- "Miền Bắc, Trung" (13pt regular gray #999)
Top-right corner: Star icon 24px for favorite

CARD 2:
Same layout, different data:
- Photo showing green pit viper
- Orange badge
- "Rắn lục đuôi đỏ" (18pt bold)
- "Trimeresurus albolabris" (14pt italic gray)
- Orange badge "Độc trung bình" (amber background #FFF3CD, amber text #FFC107)
- "Toàn quốc" (13pt gray)

CARD 3:
- Photo showing non-venomous snake
- Green badge
- "Rắn ráo trâu" (18pt bold)
- "Ptyas korros" (14pt italic gray)
- Green badge "Không độc" (green background #E8F5E9, green text #228B22)
- "Miền Nam" (13pt gray)

Continue scrollable list with similar cards.

Design: Clean educational interface, color-coded danger levels, easy scanning, scientific + common names, regional information visible at glance.
```

---

## SCREEN 2: SNAKE SPECIES DETAIL

### Thông tin màn hình:
- **Tên:** Chi tiết loài rắn
- **Mục đích:** Hiển thị đầy đủ thông tin về một loài rắn cụ thể
- **Flow position:** Screen 1 → Tap vào snake card → Screen 2
- **Priority:** ★★★ (High)

### Layout Structure:

```
┌─────────────────────────────────────┐
│ ← Rắn hổ mang chúa           ⋮     │ Header
├─────────────────────────────────────┤
│ ╔═══════════════════════════════╗  │
│ ║ PHOTO GALLERY (Swipeable)     ║  │
│ ║ [Photo 1 of 8]                ║  │
│ ║ Full-width 280px height       ║  │
│ ╚═══════════════════════════════╝  │
├─────────────────────────────────────┤
│ CỰC KỲ NGUY HIỂM - ĐỘC MẠNH     │ Alert Banner
├─────────────────────────────────────┤
│ Rắn hổ mang chúa                   │ Vietnamese Name
│ Ophiophagus hannah                 │ Scientific Name
├─────────────────────────────────────┤
│ ╔═══════════════════════════════╗  │
│ ║ QUICK STATS (3 cards)         ║  │
│ ║ [Kích thước] [Phân bố] [Độc] ║  │
│ ╚═══════════════════════════════╝  │
├─────────────────────────────────────┤
│ MÔ TẢ ĐẶC ĐIỂM                   │ Section 1
│ • Màu sắc: Nâu vàng, vảy to...    │
│ • Kích thước: 3-4 mét...          │
│ • Đầu: Hình oval rộng...          │
├─────────────────────────────────────┤
│ MÔI TRƯỜNG SỐNG                   │ Section 2
│ • Rừng núi, vùng đồi...           │
│ • Hay ẩn náu trong hang...        │
├─────────────────────────────────────┤
│ MỨC ĐỘ NGUY HIỂM                 │ Section 3
│ Nọc cực mạnh, liều chết người...  │
│ [Xem hướng dẫn sơ cứu →]         │
├─────────────────────────────────────┤
│ HUYẾT THANH                       │ Section 4
│ Cần: Monovalent Anti-Cobra...     │
│ [Tìm bệnh viện gần →]            │
├─────────────────────────────────────┤
│ DỄ NHẦM LẪN VỚI                   │ Section 5
│ [Snake Card] Rắn ráo đất          │
│ [So sánh chi tiết →]             │
├─────────────────────────────────────┤
│ PHÂN BỐ Ở VIỆT NAM                │ Section 6
│ [Map showing regions]             │
├─────────────────────────────────────┤
│ ╔═══════════════════════════════╗  │
│ ║ BOTTOM ACTIONS                ║  │
│ ║ [Báo cáo gặp] [Gọi cứu hộ]   ║  │
│ ╚═══════════════════════════════╝  │
└─────────────────────────────────────┘
```

### Key Components:

#### 1. Header:
- **Back button:** ← (left)
- **Title:** Vietnamese name (truncated if long)
- **Favorite:** Star icon (right, toggle)
- **Menu:** ⋮ (right)
  - Share
  - Report error
  - Download offline

#### 2. Photo Gallery (Swipeable):
- **Height:** 280px
- **Layout:** Horizontal swipe gallery
- **Indicator:** "1 of 8" (bottom-right, white text on dark overlay)
- **Photos:**
  - 8+ high-quality images from different angles
  - Full body, head close-up, pattern detail, color variation
- **Zoom:** Pinch to zoom
- **Fullscreen:** Tap to view fullscreen

#### 3. Danger Alert Banner (if venomous):
- **Background:** Red #FFEBEE (for highly venomous) OR Amber #FFF3CD (medium)
- **Icon:** Danger icon (red or orange)
- **Text:** 
  - "CỰC KỲ NGUY HIỂM - ĐỘC MẠNH" (Red, Bold, 16pt)
  - OR "NGUY HIỂM - ĐỘC TRUNG BÌNH" (Amber, Bold, 16pt)
- **Height:** 48px

#### 4. Title Section:
- **Vietnamese Name:** 
  - "Rắn hổ mang chúa" (Bold, 24pt, #333)
- **Scientific Name:**
  - "Ophiophagus hannah" (Italic, 18pt, Gray #666)
- **Family/Genus:**
  - "Họ: Elapidae" (Regular, 14pt, Gray #999)

#### 5. Quick Stats (3 Cards Horizontal):

**Card Design:**
- Width: 30% each, 8px gap
- Height: 80px
- Background: Light Gray #F8F9FA
- Border Radius: 12px
- Center aligned

**Card 1: Kích thước**
- Icon: Ruler icon (24px)
- Label: "Kích thước" (12pt, Gray)
- Value: "3-4 mét" (16pt, Bold, #333)

**Card 2: Phân bố**
- Icon: Globe icon (24px)
- Label: "Phân bố" (12pt, Gray)
- Value: "Miền Bắc, Trung" (16pt, Bold, #333)

**Card 3: Độc tính**
- Icon: Danger icon (24px)
- Label: "Độc tính" (12pt, Gray)
- Value: "Cực mạnh" (16pt, Bold, Red #DC3545)

#### 6. Mô tả đặc điểm (Collapsible Section):
- **Header:** "MÔ TẢ ĐẶC ĐIỂM" (Bold, 18pt, Forest Green)
- **Expand/Collapse:** ▼ (default expanded)
- **Content:**
  - **Màu sắc:** "Nâu vàng đến đen, vảy to, bóng loáng. Có vân ngang màu vàng nhạt ở thân."
  - **Kích thước:** "Trung bình 3-4 mét, có thể đạt 5.5 mét. Nặng 6-12 kg."
  - **Đầu:** "Hình oval rộng, phân biệt rõ với cổ. Mắt to, đồng tử tròn."
  - **Thân:** "To, dài, cơ bắp phát triển. Vảy trơn, bóng."
  - **Đặc điểm nhận dạng:** "Có thể phình cổ khi bị đe dọa (hood), tiếng rít đặc trưng."

#### 7. Môi trường sống:
- **Header:** "MÔI TRƯỜNG SỐNG" (Bold, 18pt, Forest Green)
- **Content:**
  - "Rừng núi, vùng đồi cao 500-2000m"
  - "Hay ẩn náu trong hang đá, hốc cây, gốc cây"
  - "Sống gần nguồn nước: suối, sông nhỏ"
  - "Hoạt động ban ngày và ban đêm"
  - "Ăn chủ yếu là rắn khác (ophiophagous)"

#### 8. Mức độ nguy hiểm (Red Box):
- **Background:** #FFEBEE (Light Red)
- **Border:** 3px solid #DC3545 (Red)
- **Icon:** Warning icon (32px)
- **Title:** "MỨC ĐỘ NGUY HIỂM" (Bold, 18pt, Red)
- **Content:**
  - "Nọc độc cực mạnh, neurotoxin"
  - "Một vết cắn chứa lượng nọc đủ giết 20 người"
  - "Triệu chứng: liệt cơ, suy hô hấp, tử vong trong 6-12h nếu không điều trị"
  - "Rất hung dữ khi bảo vệ tổ, có thể tấn công chủ động"
- **Button:** 
  - "Xem hướng dẫn sơ cứu →" (Red outlined, 48px height, full width)
  - → Navigate to First Aid Guide (Screen 3 Emergency)

#### 9. Huyết thanh (Blue Box):
- **Background:** #E7F3FF (Light Blue)
- **Border:** 2px solid #007BFF (Blue)
- **Icon:** Hospital icon (32px)
- **Title:** "HUYẾT THANH CẦN THIẾT" (Bold, 16pt, Blue)
- **Content:**
  - "Loại: Monovalent Anti-Cobra Serum"
  - "Tên thương mại: King Cobra Antivenin"
  - "Liều khuyến nghị: 10-20 lọ (tùy mức độ)"
- **Button:**
  - "Tìm bệnh viện có huyết thanh gần nhất →" (Blue outlined)
  - → Navigate to Hospital Finder (với filter sẵn loại huyết thanh)

#### 10. Dễ nhầm lẫn với:
- **Header:** "DỄ NHẦM LẪN VỚI" (Bold, 18pt, Amber)
- **Content:** Small snake card (horizontal)
  - Photo (80px x 80px)
  - Name: "Rắn ráo đất" (Bold, 14pt)
  - Badge: "Không độc" (Green)
  - Difference: "Đầu nhỏ hơn, không phình cổ"
- **Button:** "So sánh chi tiết →" (Amber outlined)
  - → Navigate to Screen 3 (Compare)

#### 11. Phân bố ở Việt Nam (Map):
- **Map:** Vietnam map showing highlighted regions
  - Red areas: Common habitat
  - Orange areas: Rare sightings
  - Gray: Not found
- **Legend:**
  - [Red] Phổ biến
  - [Orange] Hiếm gặp
  - [Gray] Không có
- **List below map:**
  - Miền Bắc: Hà Giang, Cao Bằng, Lạng Sơn...
  - Miền Trung: Thanh Hóa, Nghệ An, Quảng Bình...

#### 12. Bottom Action Buttons (Fixed):
- **Background:** White with top shadow
- **Height:** 80px
- **Padding:** 16px

**Button 1: Báo cáo gặp loài này**
- Width: 48%
- Background: White
- Border: 2px solid Forest Green
- Text: "Báo cáo gặp" (Forest Green, Bold, 16pt)
- Icon: Camera icon
- → Open camera to report sighting

**Button 2: Gọi đội cứu hộ**
- Width: 48%
- Background: Forest Green #228B22
- Text: "Gọi cứu hộ" (White, Bold, 16pt)
- Icon: Emergency icon
- → Navigate to Rescue Request Flow

---

### Stitch Prompt (Screen 2):

```
Mobile app detail page for King Cobra in "SnakeAid" snake species library. Educational emergency reference design.

Top navigation: Back arrow left, title "Rắn hổ mang chúa" (20pt bold), star icon (favorite) and menu (⋮) right.

Photo gallery section:
Full-width image 280px height showing king cobra photo
Bottom-right overlay: "1 of 8" (white text on dark semi-transparent background)
Swipeable horizontal gallery

Red alert banner below photo:
Red background (#FFEBEE), danger icon, red bold text "CỰC KỲ NGUY HIỂM - ĐỘC MẠNH" (16pt)
Height 48px, centered text

Title section (20px padding):
"Rắn hổ mang chúa" (24pt bold black)
"Ophiophagus hannah" (18pt italic gray #666)
"Họ: Elapidae" (14pt regular gray #999)

Three quick stat cards (horizontal, 8px gap):
Each card: light gray background (#F8F9FA), rounded 12px, 80px height
CARD 1: Ruler icon, "Kích thước" label (12pt gray), "3-4 mét" value (16pt bold)
CARD 2: Globe icon, "Phân bố" label, "Miền Bắc, Trung" value
CARD 3: Danger icon, "Độc tính" label, "Cực mạnh" value (red #DC3545)

Expandable section "MÔ TẢ ĐẶC ĐIỂM" (18pt bold forest green #228B22):
Bullet points:
• Màu sắc: Nâu vàng đến đen, vảy to, bóng loáng...
• Kích thước: Trung bình 3-4 mét, có thể đạt 5.5 mét...
• Đầu: Hình oval rộng, phân biệt rõ với cổ...
• Thân: To, dài, cơ bắp phát triển...
• Đặc điểm: Có thể phình cổ khi đe dọa...

Section "MÔI TRƯỜNG SỐNG" (18pt bold green):
• Rừng núi, vùng đồi cao 500-2000m
• Hay ẩn náu trong hang đá, hốc cây
• Sống gần nguồn nước
• Hoạt động ban ngày và đêm
• Ăn chủ yếu rắn khác

Red danger box (#FFEBEE background, 3px red border #DC3545):
Warning icon 32px
"MỨC ĐỘ NGUY HIỂM" (18pt bold red)
Text content about neurotoxin, lethality, symptoms
Red outlined button "Xem hướng dẫn sơ cứu →" full width 48px height

Blue antivenom box (#E7F3FF background, 2px blue border #007BFF):
Hospital icon 32px
"HUYẾT THANH CẦN THIẾT" (16pt bold blue)
Details: Monovalent Anti-Cobra Serum, dosage info
Blue outlined button "Tìm bệnh viện có huyết thanh →"

Section "DỄ NHẦM LẪN VỚI" (18pt bold amber):
Horizontal snake card:
- Left: Photo 80x80px
- Right: "Rắn ráo đất" (14pt bold), green badge "Không độc", difference note
Amber outlined button "So sánh chi tiết →"

Map section "PHÂN BỐ Ở VIỆT NAM":
Vietnam map with color-coded regions
Legend: [Red] Phổ biến | [Orange] Hiếm | [Gray] Không có
List of provinces below

Fixed bottom action bar (white background, top shadow, 80px height):
Two equal buttons (48% width each, 8px gap):
LEFT: White background, 2px green border, "Báo cáo gặp" (green text 16pt bold)
RIGHT: Green background (#228B22), "Gọi cứu hộ" (white text 16pt bold)

Design: Comprehensive reference, color-coded danger levels, actionable emergency buttons, educational but emergency-ready.
```

---

## SCREEN 3: COMPARE SNAKES

### Thông tin màn hình:
- **Tên:** So sánh loài rắn
- **Mục đích:** So sánh 2-3 loài rắn dễ nhầm lẫn side-by-side
- **Flow position:** Screen 2 → "So sánh với loài tương tự" → Screen 3
- **Priority:** ★★

### Layout Structure:

```
┌─────────────────────────────────────┐
│ ← So sánh loài rắn           ⋮     │
├─────────────────────────────────────┤
│ ╔═══════════════════════════════╗  │
│ ║ Chọn loài để so sánh:         ║  │
│ ║ [Rắn 1 ▼] vs [Rắn 2 ▼]      ║  │
│ ╚═══════════════════════════════╝  │
├─────────────────────────────────────┤
│ ┌──────────────┬──────────────────┐ │
│ │ Rắn hổ mang  │ Rắn ráo đất      │ │
│ │ chúa         │                  │ │
│ │ [Photo]      │ [Photo]          │ │
│ │ Độc mạnh    │ Không độc       │ │
│ └──────────────┴──────────────────┘ │
├─────────────────────────────────────┤
│ BẢNG SO SÁNH                    │
│ ┌──────────────────────────────┐   │
│ │ Kích thước:                   │   │
│ │ 3-4m        │ 1.5-2m          │   │
│ ├──────────────────────────────┤   │
│ │ Màu sắc:                      │   │
│ │ Nâu vàng    │ Nâu đen         │   │
│ ├──────────────────────────────┤   │
│ │ Đầu:                          │   │
│ │ Oval rộng   │ Nhỏ, không      │   │
│ │ phình cổ    │ phình cổ        │   │
│ └──────────────────────────────┘   │
├─────────────────────────────────────┤
│ ĐIỂM KHÁC BIỆT QUAN TRỌNG        │
│ ╔═══════════════════════════════╗  │
│ ║ 1. Hổ mang CÓ THỂ phình cổ   ║  │
│ ║ 2. Ráo đất ĐẦU NHỎ hơn nhiều ║  │
│ ║ 3. Hổ mang có TIẾNG RÍT       ║  │
│ ╚═══════════════════════════════╝  │
└─────────────────────────────────────┘
```

### Key Components:

#### 1. Selector (Top):
- Dropdown for Snake 1 and Snake 2
- "vs" text between
- Suggest common pairs (venomous vs non-venomous lookalikes)

#### 2. Side-by-side Photos:
- 2 columns, equal width
- Photos 150px height each
- Danger badges below

#### 3. Comparison Table:
- Row headers: Kích thước, Màu sắc, Đầu, Thân, Môi trường sống, Độc tính
- Left column: Snake 1 data
- Right column: Snake 2 data
- Highlight differences in Amber

#### 4. Key Differences Box (Bottom):
- Amber background #FFF3CD
- Bold numbered list (1-5 max)
- Focus on life-saving differences
- Examples: Hood, head shape, sound, behavior

---

## SCREEN 4: REGIONAL SNAKES (GPS-Based)

### Thông tin màn hình:
- **Tên:** Rắn phổ biến ở khu vực của tôi
- **Mục đích:** Hiển thị 15-30 loài rắn thường gặp ở khu vực GPS người dùng
- **Flow position:** Screen 1 → Filter "Khu vực của tôi" → Screen 4
- **Priority:** ★★★

### Layout:

```
┌─────────────────────────────────────┐
│ ← Rắn ở khu vực của bạn      [Refresh] │
├─────────────────────────────────────┤
│ Đang hiển thị rắn ở:            │
│ Hà Nội, Việt Nam                   │
│ (Dựa trên GPS của bạn)             │
├─────────────────────────────────────┤
│ CẢNH BÁO: 5 LOÀI ĐỘC           │
│    phổ biến trong khu vực này      │
├─────────────────────────────────────┤
│ ┌───────────────────────────────┐  │
│ │ SECTION: LOÀI ĐỘC (5)         │  │
│ │ Rắn hổ mang chúa           │  │
│ │ Rắn lục đuôi đỏ            │  │
│ │ ... (snake cards)              │  │
│ └───────────────────────────────┘  │
│ ┌───────────────────────────────┐  │
│ │ SECTION: KHÔNG ĐỘC (12)       │  │
│ │ Rắn ráo trâu               │  │
│ │ ... (snake cards)              │  │
│ └───────────────────────────────┘  │
├─────────────────────────────────────┤
│ MẸO PHÒNG TRÁNH                 │
│ Khu vực bạn gần công viên/rừng... │
└─────────────────────────────────────┘
```

### Key Components:

#### 1. Location Header:
- GPS icon + detected location
- Refresh button to update
- Accuracy indicator

#### 2. Warning Banner (if venomous snakes present):
- Count of venomous species
- Amber/Red based on danger level

#### 3. Grouped List:
- **LOÀI ĐỘC** section (collapsed by default, can expand)
- **KHÔNG ĐỘC** section (expanded)
- Each uses same snake card from Screen 1

#### 4. Prevention Tips (Bottom):
- Context-aware based on location
- E.g., "Khu vực bạn gần sông" → Tips về rắn nước
- Link to full prevention guide

---

## NAVIGATION & FLOWS

### From Homepage:
```
Homepage → Grid Menu "Thư viện loài rắn" 
  → Screen 1 (Library Home)
    → Screen 2 (Detail)
      → Screen 3 (Compare)
      → First Aid Guide
      → Hospital Finder
      → Rescue Request
```

### From AI Identification Result:
```
AI Result Screen → "Xem chi tiết loài này"
  → Screen 2 (Detail - pre-filled with identified species)
```

### From Emergency SOS:
```
Emergency Screen → "Tôi không biết loài rắn"
  → Screen 1 (Library) with filter "Loài độc nguy hiểm"
```

---

## DATA STRUCTURE

### Snake Species Object:

```json
{
  "id": "cobra-king-001",
  "vietnameseName": "Rắn hổ mang chúa",
  "scientificName": "Ophiophagus hannah",
  "family": "Elapidae",
  "genus": "Ophiophagus",
  "dangerLevel": "extreme", // extreme | high | medium | low | none
  "isVenomous": true,
  "venomType": "neurotoxin",
  "photos": [
    "url1.jpg", "url2.jpg", ...
  ],
  "size": {
    "min": 3.0,
    "max": 5.5,
    "unit": "meters"
  },
  "weight": {
    "min": 6,
    "max": 12,
    "unit": "kg"
  },
  "description": {
    "color": "Nâu vàng đến đen...",
    "head": "Hình oval rộng...",
    "body": "To, dài, cơ bắp...",
    "scales": "Vảy trơn, bóng",
    "features": "Có thể phình cổ..."
  },
  "habitat": {
    "environment": ["Rừng núi", "Đồi cao"],
    "altitude": "500-2000m",
    "shelter": ["Hang đá", "Hốc cây"],
    "nearWater": true,
    "activity": "Cả ngày và đêm"
  },
  "diet": "Rắn khác (ophiophagous)",
  "behavior": {
    "aggressive": true,
    "defensive": "Phình cổ, rít lớn",
    "canAttackFirst": true
  },
  "distribution": {
    "regions": ["Miền Bắc", "Miền Trung"],
    "provinces": ["Hà Giang", "Cao Bằng", "Thanh Hóa"],
    "mapCoordinates": [...]
  },
  "danger": {
    "severity": "Cực kỳ nguy hiểm",
    "venomPotency": "Một vết cắn chứa lượng nọc đủ giết 20 người",
    "symptoms": "Liệt cơ, suy hô hấp...",
    "timeToFatal": "6-12 giờ nếu không điều trị"
  },
  "antivenom": {
    "type": "Monovalent Anti-Cobra Serum",
    "brandNames": ["King Cobra Antivenin"],
    "dosage": "10-20 vials"
  },
  "lookalikes": [
    {
      "speciesId": "rat-snake-001",
      "name": "Rắn ráo đất",
      "differences": "Đầu nhỏ hơn, không phình cổ"
    }
  ],
  "firstAidGuideId": "first-aid-cobra",
  "tags": ["độc mạnh", "phình cổ", "rít to", "ăn rắn"]
}
```

---

## DESIGN SYSTEM REFERENCE

### Colors:
- **Primary:** Forest Green #228B22
- **Danger High:** Red #DC3545
- **Danger Medium:** Amber #FFC107
- **Safe:** Green #28A745
- **Background:** White #FFFFFF
- **Gray Scale:** #F8F9FA, #E0E0E0, #999999, #666666, #333333

### Typography:
- **Title:** 24pt Bold
- **Heading:** 18-20pt Bold
- **Body:** 14-16pt Regular
- **Caption:** 12-13pt Regular
- **Scientific Name:** Italic

### Components:
- **Cards:** Rounded 12px, shadow 0px 2px 6px
- **Buttons:** 48px height, rounded 24px
- **Badges:** Rounded 4px, 4px 8px padding
- **Chips:** Rounded 18px, 36px height

---

## FUNCTIONAL REQUIREMENTS

### FE-Snake-Library-01: Browse & Search
- Display 250+ snake species
- Search by Vietnamese name, scientific name, characteristics
- Auto-complete suggestions
- Filter by danger level, region, venom type

### FE-Snake-Library-02: Detail View
- Show 8+ photos per species
- Display comprehensive info: size, color, habitat, danger
- Show antivenom requirements
- Link to first aid guide
- Link to hospital finder (pre-filtered)

### FE-Snake-Library-03: Comparison
- Compare 2-3 species side-by-side
- Highlight key differences
- Suggest common lookalike pairs

### FE-Snake-Library-04: Regional Display
- Use GPS to detect user location
- Filter snakes by region
- Show venomous species warning
- Provide location-specific prevention tips

### FE-Snake-Library-05: Favorites & History
- Save favorite species
- Track viewed species history
- Offline download for emergency reference

### FE-Snake-Library-06: Integration with Other Modules
- Link to Rescue Request with species pre-selected
- Link to Report Sighting with camera
- Link to Hospital Finder with antivenom filter
- Link to First Aid Guide for specific species

---

## NOTES FOR DEVELOPERS

### Data Source:
- Admin updates snake database via Admin Portal
- Sync with AI Model for image recognition
- Photos from Vietnam Herpetological Society + field researchers
- Scientific data verified by Snake Experts

### Offline Support:
- Cache 250+ species data locally
- Pre-download photos for top 50 dangerous species
- Sync updates when online

### Performance:
- Lazy load images (thumbnails first)
- Virtual scrolling for long lists
- Cache search results

### Localization:
- Vietnamese primary
- English secondary (scientific names always present)
- Future: Add regional dialects for common names

---

## FUTURE ENHANCEMENTS

### Version 2.0:
- AR identification: Point camera at snake → Overlay species info
- Community contributions: Users upload photos to database
- Seasonal alerts: "Rắn lục đuôi đỏ đang mùa sinh sản - cẩn thận"
- Quiz mode: "Có phải rắn độc không?" educational game

### Version 3.0:
- AI-powered lookalike detector: Upload photo → "85% match Rắn hổ mang, BUT check if can hood"
- Expert Q&A in detail page: Ask questions about specific species
- Incident heatmap: "5 vụ rắn cắn gần bạn trong tháng này - cẩn thận"

---

**END OF DOCUMENT**
