# 🔧 Hướng Dẫn Cài Đặt & Tích Hợp: Stitch + Antigravity

> **BBo Tech** · Tài liệu kỹ thuật nội bộ · Cập nhật: 31/03/2026

---

## Mục lục

- [Tổng quan kiến trúc](#tổng-quan-kiến-trúc)
- [Yêu cầu hệ thống](#yêu-cầu-hệ-thống)
- [Cài đặt & Kết nối MCP Server](#cài-đặt--kết-nối-mcp-server)
- [Workflow chi tiết](#workflow-chi-tiết)
- [Prompt Engineering](#prompt-engineering)
- [Cấu trúc file output](#cấu-trúc-file-output)
- [Tích hợp nâng cao](#tích-hợp-nâng-cao)
- [Troubleshooting](#troubleshooting)

---

## Tổng quan kiến trúc

```
┌──────────────────────────────────────────────────────────┐
│                       STITCH                             │
│         (Lớp thiết kế UI — Front-end only)               │
│                                                          │
│  Input:   Text prompt  /  Screenshot                     │
│  Output:  HTML/CSS variants  /  ZIP export  /  MCP API   │
└─────────────────────┬────────────────────────────────────┘
                      │
              MCP Server  /  ZIP Export
                      │
                      ▼
┌──────────────────────────────────────────────────────────┐
│                    ANTIGRAVITY                           │
│         (Lớp build & runtime — Full stack)               │
│                                                          │
│  Input:   ZIP file  /  MCP tool calls  /  Text prompt    │
│  Output:  Web app chạy được (local / deploy)             │
│  Tích hợp: Nano Banana 2 · Gemini Flash (image gen)      │
└──────────────────────────────────────────────────────────┘
```

**Phân tách trách nhiệm:**
- **Stitch** → Xử lý toàn bộ phần thiết kế giao diện (front-end design). Không có runtime logic, không có database.
- **Antigravity** → Nhận design từ Stitch, build thành ứng dụng web hoàn chỉnh, xử lý back-end và deploy.

---

## Yêu cầu hệ thống

| Thành phần | Yêu cầu |
|---|---|
| Antigravity | Phiên bản mới nhất, cài trên máy tính (desktop app) |
| Tài khoản Google | Đăng nhập để dùng Stitch và lấy API Key |
| Kết nối internet | Bắt buộc khi gọi MCP / Stitch API |
| Trình duyệt | Chrome hoặc Edge (để dùng Stitch Web) |

---

## Cài đặt & Kết nối MCP Server

### Phương pháp 1 — Kết nối qua giao diện Antigravity (Khuyến nghị)

Phương pháp này dùng giao diện đồ hoạ, không cần lệnh:

**Bước 1 — Cài Stitch trong MCP Servers:**
```
Antigravity → nhấp ⋯ (3 chấm) góc trên phải
           → tab MCP Servers
           → gõ "Stitch" vào ô tìm kiếm
           → nhấn Tải về
```

**Bước 2 — Cấu hình API Key:**
```
Antigravity → nhấp vào Stitch → Configure → Nhập API Key
```

**Cách lấy API Key từ Stitch:**
```
stitch.withgoogle.com → Ảnh đại diện (góc trên phải)
                      → Cài đặt Stitch
                      → Cuộn xuống mục "API Keys"
                      → Nhấn Tạo khóa → Copy
                      → Dán vào ô API Key trong Antigravity
```

**Bước 3 — Xác nhận kết nối:**

Gõ lệnh sau vào khung chat Antigravity:
```
List available Stitch tools
```

Kết quả mong đợi: Antigravity liệt kê danh sách tool của Stitch (list_projects, get_screen, export_design...).
Nếu có danh sách → kết nối thành công.

---

### Phương pháp 2 — Cài Skill qua GitHub

Dán vào khung chat Antigravity, chọn một trong hai:

```bash
# Chỉ áp dụng cho project hiện tại
install this skill - https://github.com/google-labs-code/stitch-skills

# Áp dụng cho tất cả project (khuyến nghị)
install the skill globally - https://github.com/google-labs-code/stitch-skills
```

Antigravity sẽ tự clone repo và mount skill vào working directory.

> ⚠️ **Bảo mật:** Luôn review file `.md` trong skill repo trước khi install. Không install từ nguồn ngoài danh sách được duyệt của BBo Tech.

---

## Workflow chi tiết

### Workflow A — ZIP Export (Thủ công)

Phù hợp khi muốn kiểm soát hoàn toàn từng bước:

```
1. Thiết kế trên Stitch
   → Chọn variant ưng ý
   → Export → Download as ZIP

2. Mở Antigravity
   → Tạo thư mục project mới
   → Kéo file ZIP vào

3. Gõ lệnh build:
   "Biến bản thiết kế này thành một trang web hoàn chỉnh, chạy được."

4. Antigravity tự:
   → Giải nén ZIP
   → Phân tích HTML/CSS
   → Sinh toàn bộ code ứng dụng
   → Chạy local để xem trước
```

---

### Workflow B — MCP Auto-fetch (Tự động hoàn toàn)

Phù hợp khi muốn tích hợp Stitch vào pipeline tự động:

**Bước 1 — Liệt kê project:**
```
List my Stitch projects
```

**Bước 2 — Fetch design và build:**
```
Sử dụng Stitch, hãy tìm trong project [TÊN_PROJECT].
Lấy mã nguồn của màn hình có tên [TÊN_MÀNN_HÌNH].
Trích xuất đầy đủ: color tokens, font, layout grid.
Tạo output trong thư mục [ĐƯỜNG_DẪN].
```

**Ví dụ cụ thể:**
```
Sử dụng Stitch, hãy tìm trong project BBo-LandingPage-2026.
Lấy mã nguồn của màn hình Hero_Variant_2.
Trích xuất đầy đủ màu sắc, font chữ, bố cục.
Lưu vào thư mục /src/components/Hero.html.
```

Antigravity sẽ chạy song song: một luồng gọi Stitch MCP lấy CSS/design tokens, luồng còn lại build toàn bộ ứng dụng.

---

## Prompt Engineering

### Prompts thiết kế trên Stitch

**Redesign từ screenshot:**
```
Làm cho thiết kế này đẹp hơn, hiện đại hơn.
Tông màu chủ đạo: [MÀU].
Giữ nguyên bố cục tổng thể, nâng cao chất lượng hình ảnh.
```

**Tạo mới từ mô tả:**
```
Tạo landing page cho [TÊN_DỊCH_VỤ].
Phong cách: [hiện đại / tối giản / chuyên nghiệp]
Màu chủ đạo: [MÀU]
Bắt buộc có: [hero section / form đăng ký / feature grid / testimonials]
```

**Chỉnh vùng cụ thể với Annotate:**
```
Chỉnh [tên phần tử] thành [yêu cầu].
Giữ nguyên tất cả phần còn lại.
```

---

### Prompts build trên Antigravity

**Build từ ZIP:**
```
Biến bản thiết kế này thành trang web hoàn chỉnh, chạy được.
Stack: [React + Tailwind / HTML + CSS thuần / Vue]
```

**Fetch từ Stitch rồi build:**
```
Dùng Stitch skill lấy project [TÊN], màn hình [TÊN_MÀN_HÌNH].
Build thành ứng dụng [React/HTML] hoàn chỉnh.
Lưu vào [ĐƯỜNG_DẪN].
```

**Chỉnh sửa sau khi build:**
```
Ở phần [tên section/component], thay [phần tử] thành [giá trị mới].
Mô tả vị trí cụ thể: [mô tả nơi xuất hiện trên trang].
```

**Tạo ảnh với Nano Banana 2 / Gemini Flash:**
```
Tạo ảnh sản phẩm: [mô tả chi tiết].
Phong cách: [tối giản / chụp thực / minh hoạ].
Bảng màu: [màu sắc].
Tỉ lệ: [16:9 / 1:1 / 4:3].
Chèn vào: [tên section hoặc đường dẫn file].
```

---

## Cấu trúc file output

### Vanilla HTML + CSS

```
project/
├── index.html
├── styles/
│   ├── main.css          # Global styles (từ Stitch color tokens)
│   └── components.css    # Component-level styles
├── scripts/
│   └── main.js
└── assets/
    ├── images/           # Ảnh AI-generated (Nano Banana 2)
    └── icons/
```

### React + Tailwind

```
project/
├── src/
│   ├── App.jsx
│   ├── components/
│   │   ├── Hero.jsx
│   │   ├── Features.jsx
│   │   └── [TênComponent].jsx
│   └── styles/
│       └── globals.css
├── public/
├── package.json
└── tailwind.config.js
```

---

## Tích hợp nâng cao

### Danh sách MCP tools của Stitch

Sau khi kết nối MCP, các tool sau có thể gọi trực tiếp trong Antigravity:

| Tool | Mô tả |
|---|---|
| `list_projects` | Lấy danh sách tất cả Stitch project |
| `list_screens` | Liệt kê tất cả màn hình trong một project |
| `get_screen` | Lấy design của một màn hình cụ thể |
| `export_design` | Export HTML/CSS của một variant |

**Ví dụ gọi trực tiếp:**
```
Dùng Stitch MCP: list_projects
Dùng Stitch MCP: get_screen từ project "BBo-Landing", màn hình "Hero_v2"
```

### Kiểm tra giao diện mobile

Trong Stitch:
```
Dropdown menu trong phần Preview → Show QR code → Quét bằng điện thoại
```

---

## Troubleshooting

| Vấn đề | Nguyên nhân thường gặp | Cách xử lý |
|---|---|---|
| Antigravity không nhận Stitch tools | Chưa kết nối MCP hoặc API Key sai | Reconnect MCP, kiểm tra lại API Key |
| `List available Stitch tools` trả về rỗng | Skill chưa install hoặc kết nối lỗi | Reinstall skill, kiểm tra kết nối mạng |
| Design export bị lệch layout | Stitch variant chưa render xong | Đợi render hoàn tất rồi mới export |
| Antigravity build sai màu sắc | Color tokens chưa được extract đầy đủ | Thêm vào prompt: `"trích xuất toàn bộ color tokens từ design"` |
| Ảnh AI không chèn đúng vị trí | Mô tả vị trí trong prompt chưa rõ | Ghi rõ hơn: `"chèn vào hero section, bên dưới tiêu đề chính"` |
| Website không responsive trên mobile | Thiếu Tailwind breakpoints | Thêm vào prompt: `"đảm bảo responsive đầy đủ trên mobile"` |
| Antigravity không nhận file ZIP | File bị lỗi khi export từ Stitch | Export lại, hoặc dùng Workflow B (MCP auto-fetch) thay thế |

---

*BBo Tech · Team Developer · Mọi vấn đề kỹ thuật liên hệ nội bộ*
