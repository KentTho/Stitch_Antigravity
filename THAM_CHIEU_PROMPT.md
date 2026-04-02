# 💬 Tham Chiếu Prompt & Trường Hợp Sử Dụng: Stitch + Antigravity

> **BBo Tech** · Tài liệu kỹ thuật nội bộ · Cập nhật: 31/03/2026

---

## Mục lục

- [Nguyên tắc viết prompt hiệu quả](#nguyên-tắc-viết-prompt-hiệu-quả)
- [Thư viện prompt — Stitch](#thư-viện-prompt--stitch)
- [Thư viện prompt — Antigravity](#thư-viện-prompt--antigravity)
- [Trường hợp sử dụng thực tế](#trường-hợp-sử-dụng-thực-tế)
- [Checklist trước khi chạy](#checklist-trước-khi-chạy)

---

## Nguyên tắc viết prompt hiệu quả

Prompt càng cụ thể → AI càng làm đúng ý. Ba yếu tố cần có:

```
[Hành động] + [Đối tượng cụ thể] + [Kết quả mong muốn]
```

| ❌ Không rõ | ✅ Nên dùng |
|---|---|
| `"Sửa nút"` | `"Đổi nút CTA màu xanh ở cuối trang thành màu cam, giữ nguyên kích thước"` |
| `"Làm đẹp hơn"` | `"Tăng contrast tiêu đề, thêm shadow nhẹ cho card, dùng font Inter"` |
| `"Tạo website"` | `"Tạo landing page 1 trang, có hero + 3 feature card + form email + footer"` |
| `"Lấy design Stitch"` | `"Dùng Stitch MCP, lấy project BBo-2026, màn hình Hero_v2, lưu vào /src/Hero.jsx"` |

---

## Thư viện prompt — Stitch

### Nhóm 1: Thiết kế mới từ mô tả

**Landing page đơn giản:**
```
Tạo landing page cho dịch vụ [TÊN_DỊCH_VỤ].
Phong cách: hiện đại, tối giản, chuyên nghiệp.
Màu chủ đạo: [MÀU_THƯƠNG_HIỆU].
Bắt buộc có: hero section có headline + subtext + nút CTA,
             phần giới thiệu 3 tính năng chính,
             form đăng ký email,
             footer đơn giản.
```

**Trang tổng quan nội bộ (Dashboard):**
```
Tạo trang dashboard nội bộ cho [TÊN_NHÓM/DỰ_ÁN].
Giao diện: sidebar bên trái + vùng nội dung bên phải.
Sidebar gồm: logo, menu điều hướng 5 mục, avatar người dùng.
Vùng chính: 4 ô thống kê (số liệu tóm tắt) + bảng dữ liệu + biểu đồ.
Tông màu: [MÀU], nền tối hoặc nền sáng: [CHỌN].
```

**Trang onboarding khách hàng:**
```
Tạo trang chào đón và hướng dẫn khách hàng mới cho [TÊN_CÔNG_TY].
Gồm: tiêu đề chào mừng, 4 bước bắt đầu dạng timeline dọc,
     video hướng dẫn embed placeholder, nút liên hệ hỗ trợ.
Phong cách: thân thiện, rõ ràng, dễ đọc.
```

---

### Nhóm 2: Redesign từ ảnh có sẵn

**Nâng cấp toàn bộ trang:**
```
Làm cho thiết kế này hiện đại hơn, chuyên nghiệp hơn.
Giữ nguyên toàn bộ bố cục và nội dung, chỉ nâng cấp phần hình ảnh.
Màu chủ đạo mới: [MÀU].
Tăng white space, cải thiện typography, thêm micro-shadow cho các card.
```

**Thay đổi phong cách:**
```
Chuyển thiết kế hiện tại sang phong cách [tối giản / bold / glassmorphism / neumorphism].
Giữ nguyên cấu trúc layout.
Điều chỉnh: màu sắc, font chữ, border-radius, shadow.
```

**Tối ưu cho mobile:**
```
Redesign trang này để hiển thị tốt hơn trên điện thoại.
Điều chỉnh: font size lớn hơn, padding rộng hơn, các cột dồn về 1 cột,
            nút CTA to hơn và dễ nhấn trên màn hình cảm ứng.
```

---

### Nhóm 3: Chỉnh sửa vùng cụ thể (Annotate)

**Chỉnh phần tử đơn lẻ:**
```
Đổi [tên phần tử] thành [yêu cầu mới].
Giữ nguyên tất cả phần còn lại trong trang.
```

**Ví dụ cụ thể:**
```
Đổi nút CTA "Bắt đầu ngay" thành màu cam #FF6B35,
thêm hiệu ứng hover làm sáng 10%, thêm icon mũi tên bên phải.
Giữ nguyên font và kích thước.
```

```
Section testimonial hiện tại đang dạng list dọc.
Chuyển thành dạng 3 card nằm ngang, mỗi card có avatar tròn,
tên người dùng, chức vụ, và đoạn trích dẫn trong ngoặc kép.
```

---

### Nhóm 4: Tạo nhiều biến thể để so sánh

```
Tạo 3 phiên bản khác nhau cho hero section này:
- Phiên bản A: nền gradient, chữ trắng, hình ảnh bên phải
- Phiên bản B: nền trắng, chữ đen, hình ảnh bên trái
- Phiên bản C: nền ảnh full-width với overlay tối, chữ trắng, căn giữa
Giữ nguyên nội dung văn bản, chỉ thay đổi bố cục và màu sắc.
```

---

## Thư viện prompt — Antigravity

### Nhóm 1: Build từ file ZIP

**Build cơ bản:**
```
Biến bản thiết kế trong file ZIP này thành trang web hoàn chỉnh, chạy được.
```

**Chỉ định stack cụ thể:**
```
Biến bản thiết kế này thành ứng dụng React + Tailwind CSS.
Tách thành các component riêng biệt, đặt trong thư mục /src/components/.
Dùng Tailwind utility classes, không dùng CSS file riêng.
```

**Với yêu cầu đặc biệt:**
```
Biến bản thiết kế này thành trang web HTML thuần (không dùng framework).
Đảm bảo: responsive trên mọi thiết bị, tốc độ tải nhanh,
          không dùng thư viện ngoài trừ Google Fonts.
```

---

### Nhóm 2: Fetch từ Stitch MCP

**Lấy toàn bộ project:**
```
Dùng Stitch, liệt kê tất cả project của tôi.
```

**Lấy một màn hình cụ thể:**
```
Dùng Stitch, tìm trong project [TÊN_PROJECT].
Lấy toàn bộ mã nguồn của màn hình [TÊN_MÀN_HÌNH].
Trích xuất: color tokens, font stack, spacing scale, breakpoints.
Tạo file component tại [ĐƯỜNG_DẪN].
```

**Lấy và build thành ứng dụng hoàn chỉnh:**
```
Dùng Stitch MCP:
1. Lấy danh sách tất cả màn hình trong project [TÊN_PROJECT]
2. Lần lượt lấy mã nguồn từng màn hình
3. Build thành ứng dụng React hoàn chỉnh với routing giữa các trang
4. Lưu vào thư mục [ĐƯỜNG_DẪN]
```

---

### Nhóm 3: Chỉnh sửa sau khi build

**Thay đổi nội dung:**
```
Trong phần hero section (nằm đầu trang, có nền xanh):
Đổi tiêu đề thành: "[TIÊU_ĐỀ_MỚI]"
Đổi subtext thành: "[NỘI_DUNG_MỚI]"
Đổi text nút CTA thành: "[TÊN_NÚT_MỚI]"
Giữ nguyên màu sắc và font.
```

**Thêm tính năng:**
```
Thêm vào trang hiện tại:
- Nút "Cuộn lên đầu trang" xuất hiện khi người dùng cuộn xuống quá 300px
- Hiệu ứng fade-in cho các section khi cuộn đến
- Tooltip khi hover vào các icon trong phần tính năng
```

**Tối ưu hiệu năng:**
```
Tối ưu trang hiện tại:
- Lazy load tất cả ảnh
- Minify CSS và JS
- Thêm meta tags SEO cơ bản (title, description, og:image)
- Đảm bảo điểm Lighthouse Performance > 90
```

---

### Nhóm 4: Tạo ảnh với Nano Banana 2 / Gemini Flash

**Ảnh hero:**
```
Tạo ảnh hero cho trang landing page:
Nội dung: [mô tả khung cảnh hoặc sản phẩm]
Phong cách: hiện đại, tối giản, chuyên nghiệp
Bảng màu: [màu chủ đạo] làm nền, tông sáng
Tỉ lệ: 16:9
Chèn vào: hero section, thay thế placeholder hiện tại
```

**Ảnh minh họa tính năng:**
```
Tạo 3 ảnh icon minh hoạ cho phần tính năng:
- Ảnh 1: đại diện cho [TÍNH_NĂNG_1]
- Ảnh 2: đại diện cho [TÍNH_NĂNG_2]
- Ảnh 3: đại diện cho [TÍNH_NĂNG_3]
Phong cách: flat illustration, màu [MÀU_THƯƠNG_HIỆU], nền trong suốt
Kích thước: 200x200px mỗi ảnh
```

---

## Trường hợp sử dụng thực tế

### Tình huống 1: Tạo landing page thu thập lead trong 10 phút

```
# Bước 1 — Thiết kế trên Stitch
Tạo landing page thu thập email cho chiến dịch [TÊN_CHIẾN_DỊCH].
Gồm: headline mạnh + subtext + form email 1 trường + nút submit + trust badges.
Màu: [MÀU_THƯƠNG_HIỆU BBo Tech]. Phong cách: tối giản, chuyển đổi cao.

# Bước 2 — Build trên Antigravity
Biến bản thiết kế này thành trang HTML thuần.
Form email khi submit sẽ gọi API endpoint: [ENDPOINT_URL]
Thêm validation: email hợp lệ, không để trống.
Thêm thông báo "Đăng ký thành công!" sau khi submit.
```

### Tình huống 2: Tái sử dụng design system từ trang có sẵn

```
# Bước 1 — Trích xuất design tokens
Dùng Stitch, lấy project [TÊN_PROJECT_CŨ], màn hình [MAIN_SCREEN].
Trích xuất và xuất ra file design-tokens.json gồm:
- Bảng màu đầy đủ (primary, secondary, neutral, semantic)
- Font stack và scale
- Spacing scale
- Border-radius values
- Shadow values

# Bước 2 — Áp dụng cho project mới
Dùng file design-tokens.json vừa tạo, build trang [TÊN_TRANG_MỚI]
với cùng design system, nhưng bố cục khác hoàn toàn.
```

### Tình huống 3: Tạo bộ component dùng chung

```
# Bước 1 — Lấy thiết kế nhiều màn hình
Dùng Stitch MCP, lấy tất cả màn hình trong project [TÊN_PROJECT].

# Bước 2 — Phân tích và tách component
Phân tích toàn bộ màn hình đã lấy.
Xác định các phần tử lặp lại (Header, Footer, Card, Button, Modal...).
Tách thành các React component riêng biệt, đặt trong /src/components/.
Mỗi component nhận props linh hoạt, có PropTypes đầy đủ.
Tạo file index.js export tất cả component.
```

---

## Checklist trước khi chạy

### Trước khi thiết kế trên Stitch
- [ ] Đã xác định rõ mục đích trang (landing / dashboard / onboarding...)
- [ ] Đã có màu thương hiệu BBo Tech để nhập vào prompt
- [ ] Đã chuẩn bị ảnh mẫu tham khảo nếu dùng Workflow Redesign
- [ ] Đã viết sẵn nội dung văn bản (headline, subtext, CTA...)

### Trước khi build trên Antigravity
- [ ] Kết nối MCP đã hoạt động (`List available Stitch tools` → có kết quả)
- [ ] Đã chọn được variant thiết kế ưng ý từ Stitch
- [ ] Đã xác định stack công nghệ (React+Tailwind / HTML thuần / Vue)
- [ ] Đã biết API endpoint cần tích hợp (nếu có form)

### Sau khi build xong
- [ ] Trang chạy ổn định ở localhost
- [ ] Giao diện hiển thị đúng trên mobile (kiểm tra bằng QR code trong Stitch)
- [ ] Form hoạt động và validation chạy đúng
- [ ] Không có lỗi console nghiêm trọng

---

*BBo Tech · Team Developer · Cập nhật 31/03/2026*
