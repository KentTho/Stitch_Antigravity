<div align="center">

# Stitch + Antigravity
### Tài liệu tích hợp AI tạo website · BBo Tech

[![Google Stitch](https://img.shields.io/badge/Google-Stitch-2E9448?style=flat-square&logo=google&logoColor=white)](https://stitch.withgoogle.com)
[![Antigravity](https://img.shields.io/badge/Google-Antigravity-1B6B2F?style=flat-square&logo=google&logoColor=white)](https://labs.google)
[![Tài liệu](https://img.shields.io/badge/Tài_liệu-Tiếng_Việt-4CAF50?style=flat-square)]()
[![Cập nhật](https://img.shields.io/badge/Cập_nhật-31%2F03%2F2026-brightgreen?style=flat-square)]()

**Bộ tài liệu kỹ thuật nội bộ cho việc tích hợp và triển khai Stitch + Antigravity tại BBo Tech.**

</div>

---

## Tổng quan

Repo này chứa toàn bộ tài liệu kỹ thuật để team BBo Tech tích hợp **Google Stitch** (thiết kế UI bằng AI) với **Google Antigravity** (build và deploy ứng dụng web) vào quy trình phát triển sản phẩm.

### Kiến trúc hệ thống

```
Input (Prompt / Screenshot)
         │
         ▼
   ┌───────────┐
   │  STITCH   │  →  Thiết kế UI (front-end only)
   └─────┬─────┘     Output: HTML/CSS variants · ZIP · MCP API
         │
         │  MCP Server  hoặc  ZIP Export
         ▼
   ┌─────────────┐
   │ ANTIGRAVITY │  →  Build & Runtime (full stack)
   └─────────────┘     Output: Web app (local / deployed)
                        Tích hợp: Nano Banana 2 · Gemini Flash
```

---

## Cấu trúc repo

```
📦 stitch-antigravity-bbotech/
│
├── 📄 README.md                ← File này
│
├── 📄 CAI_DAT_TICH_HOP.md      ← Cài đặt, kết nối MCP, workflow A/B,
│                                  cấu trúc file output, troubleshooting
│
├── 📄 THAM_CHIEU_PROMPT.md     ← Thư viện prompt đầy đủ cho Stitch & Antigravity,
│                                  trường hợp sử dụng thực tế, checklist
│
├── 📄 Stitch_Antigravity_BBo.docx  ← Tài liệu đầy đủ kèm ảnh chụp màn hình
│
└── 📁 assets/
    └── logo_bbo_team.jpg
```

---

## Bắt đầu nhanh

### 1. Kết nối Stitch với Antigravity

**Cách A — Qua giao diện (khuyến nghị):**
```
Antigravity → ⋯ → MCP Servers → Tìm "Stitch" → Cài → Configure → Nhập API Key
```

Lấy API Key:
```
Stitch → Ảnh đại diện → Cài đặt → API Keys → Tạo khóa → Copy
```

Kiểm tra kết nối:
```
List available Stitch tools
```

**Cách B — Cài Skill từ GitHub:**
```bash
# Cài cho tất cả project (khuyến nghị)
install the skill globally - https://github.com/google-labs-code/stitch-skills
```

---

### 2. Hai workflow chính

**Workflow A — ZIP Export (Thủ công):**
```
Stitch → Export → Tải ZIP → Kéo vào Antigravity
→ "Biến bản thiết kế này thành trang web hoàn chỉnh, chạy được."
```

**Workflow B — MCP Auto-fetch (Tự động):**
```
# Liệt kê project
List my Stitch projects

# Fetch và build
Dùng Stitch, tìm project [TÊN]. Lấy màn hình [TÊN_MÀN_HÌNH].
Trích xuất color tokens, font, layout. Tạo app tại [ĐƯỜNG_DẪN].
```

---

### 3. Ví dụ prompt thực tế

Thiết kế trên Stitch:
```
Tạo landing page cho dịch vụ AI Assistant BBo Tech.
Phong cách: hiện đại, tối giản. Màu chủ đạo: xanh lá #2E9448.
Gồm: hero + 3 feature card + form đăng ký email + footer.
```

Build trên Antigravity:
```
Biến bản thiết kế này thành ứng dụng React + Tailwind CSS.
Tách thành component riêng trong /src/components/.
Đảm bảo responsive đầy đủ trên mobile.
```

---

## Tài liệu chi tiết

| File | Nội dung |
|---|---|
| [📄 CAI_DAT_TICH_HOP.md](./CAI_DAT_TICH_HOP.md) | Yêu cầu hệ thống · Cài đặt MCP · Workflow A & B chi tiết · Danh sách MCP tools · Cấu trúc file output · Bảng troubleshooting |
| [📄 THAM_CHIEU_PROMPT.md](./THAM_CHIEU_PROMPT.md) | Nguyên tắc viết prompt · Thư viện prompt Stitch · Thư viện prompt Antigravity · Tình huống sử dụng thực tế · Checklist |
| [📄 Stitch_Antigravity_BBo.docx](./Stitch_Antigravity_BBo.docx) | Tài liệu đầy đủ kèm ảnh chụp màn hình (dùng để trình bày) |

---

## Ứng dụng trong dự án BBo Tech

| Use case | Workflow | Stack gợi ý |
|---|---|---|
| Landing page / Lead magnet | Workflow A hoặc B | HTML thuần hoặc React |
| Client onboarding portal | Workflow B | React + Tailwind |
| Member dashboard | Workflow B | React + Tailwind |
| Prototype ý tưởng nhanh | Workflow A | HTML thuần |
| Component library | Workflow B (nhiều màn hình) | React + TypeScript |

---

## Liên kết

| Tài nguyên | Đường dẫn |
|---|---|
| Google Stitch | [stitch.withgoogle.com](https://stitch.withgoogle.com) |
| Stitch Skills GitHub | [github.com/google-labs-code/stitch-skills](https://github.com/google-labs-code/stitch-skills) |
| Slide tổng quan | [canva.link/1i8eungsswz9ywy](https://canva.link/1i8eungsswz9ywy) |
| Prompt mẫu Landing Page | [Google Docs nội bộ](https://docs.google.com/document/d/1q22CyIQR_9IfZjV4skQRSjNAWgb0GEQ_R9osFNhgOiQ/edit?tab=t.jfiyq9e0q71z) |
| Prompt mẫu Full Website | [Google Docs nội bộ](https://docs.google.com/document/d/1q22CyIQR_9IfZjV4skQRSjNAWgb0GEQ_R9osFNhgOiQ/edit?tab=t.wbmwv7njrlvg) |

---

<div align="center">

**BBo Tech** · Tài liệu nội bộ · Cập nhật 31/03/2026  
*Câu hỏi và đóng góp: mở Issue hoặc liên hệ trực tiếp team Developer*

</div>
