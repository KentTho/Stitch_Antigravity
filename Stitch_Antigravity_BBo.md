# HƯỚNG DẪN SỬ DỤNG

## Bộ đôi AI miễn phí từ Google: STITCH + ANTIGRAVITY

> **Thiết kế và xây dựng website không cần code — Từ ý tưởng đến sản phẩm chỉ trong 5–10 phút**

_Tài liệu lưu hành nội bộ — BBo Tech_  
Ngày cập nhật: 31/03/2026

---

## 1. TỔNG QUAN VÀ MỤC TIÊU

Trong kỷ nguyên AI năm 2026, việc tạo ra một website không còn là đặc quyền của riêng lập trình viên. Bộ đôi công cụ miễn phí từ Google giúp rút ngắn quy trình từ 3–8 tuần xuống chỉ còn 5–10 phút, không yêu cầu bất kỳ kiến thức lập trình nào.

### 1.1 Mục tiêu tài liệu

- Giúp bất kỳ thành viên (kể cả non-IT) tự tạo landing page hoặc website hoàn chỉnh.
- Tận dụng AI để rút ngắn thời gian thiết kế từ vài tuần xuống vài phút.

### 1.2 Hai công cụ chính

**Google Stitch — Vai trò "Kiến trúc sư"**

Địa chỉ truy cập: [stitch.withgoogle.com](http://stitch.withgoogle.com)

- Nhận ảnh chụp màn hình hoặc mô tả bằng ngôn ngữ tự nhiên.
- Tạo ra 2–3 biến thể giao diện đẹp, hiện đại, chuyên nghiệp.
- Hỗ trợ thiết kế luồng công việc đa trang cùng lúc.
- Cho phép chỉnh sửa trực tiếp bằng công cụ Annotate (chú thích).
- Chuyên xử lý phần giao diện trực quan (front-end); **KHÔNG** bao gồm cơ sở dữ liệu hay chức năng hoạt động.

**Google Antigravity — Vai trò "Người thợ xây"**

- Tiếp nhận bản thiết kế từ Stitch, tự động chuyển thành mã code hoạt động được.
- Thêm cơ sở dữ liệu, tính năng động.
- Chạy thử ngay trên máy tính (local) và triển khai (deploy) ứng dụng thực tế.
- Tích hợp sẵn Nano Banana 2 và Gemini Flash để tạo hình ảnh chất lượng cao.

### 1.3 Sơ đồ quy trình tổng thể

> **Ý tưởng → Stitch (tạo 2–3 biến thể UI) → Xuất file ZIP / Dùng Skill → Antigravity (viết code + chạy) → Website thật | Chỉ mất 5–10 phút**

---

## 2. LỢI ÍCH SO VỚI CÁCH LÀM TRUYỀN THỐNG

| Tiêu chí               | Cách làm cũ                   | Stitch + Antigravity      |
| ---------------------- | ----------------------------- | ------------------------- |
| Thời gian hoàn thành   | 3–8 tuần                      | 5–10 phút                 |
| Nhân sự cần thiết      | Designer + Developer          | 1 người (không cần code)  |
| Chi phí                | Cao (thuê ngoài hoặc nhân sự) | 0 đồng (công cụ miễn phí) |
| Tính linh hoạt khi sửa | Khó sửa, tốn nhiều thời gian  | Sửa ngay bằng lệnh chat   |
| Thử nghiệm ý tưởng     | Phải chờ bản prototype        | Demo ngay trong buổi họp  |

---

## 3. HƯỚNG DẪN THỰC HÀNH TỪNG BƯỚC

### Bước 1: Cài đặt Stitch Skill vào Antigravity (Kết nối MCP Server)

Đây là bước thiết lập một lần duy nhất, giúp hai công cụ "nói chuyện" được với nhau qua đường dây MCP Server.

1. Mở phần mềm Antigravity trên máy tính, tạo một thư mục dự án mới.
2. Lấy link mã nguồn kỹ năng (GitHub: [google-labs-code/stitch-skills · GitHub](https://github.com/google-labs-code/stitch-skills)) của Stitch Skill do Google cung cấp (xem tài liệu nội bộ hoặc liên hệ team Dev).
3. Dán link vào khung chat của Antigravity, sau đó dùng một trong hai lệnh:
   - `Install this skill - https://github.com/google-labs-code/stitch-skills` → **Cài cục bộ, chỉ áp dụng cho dự án đang mở hiện tại.**
   - `Install the skill globally - https://github.com/google-labs-code/stitch-skills` → **Cài toàn cục, áp dụng cho tất cả dự án hiện tại và tương lai.**
4. Đợi hệ thống tự động sao chép (clone) kho lưu trữ và cài đặt kỹ năng vào thư mục làm việc.

---

**💡 Cách thay thế: Kết nối trực tiếp MCP Server (không cần lệnh install)**

Thay vì gõ lệnh `Install this skill`, bạn có thể kết nối Stitch trực tiếp vào MCP Server của Antigravity theo các bước sau. Đây là phương pháp nâng cao giúp Antigravity luôn sẵn sàng gọi Stitch mà không cần cài thủ công từng dự án:

- Mở Antigravity → Chọn vào **(3 chấm)** ở góc trên bên phải → chọn tab **MCP Servers** → gõ "Stitch" → Chọn tải về.
- Nhấp vào **Stitch** → chọn **Configure** → Nhập API Key.
- Lấy API Key ở Stitch: Click vào Trang cá nhân góc trên bên phải → chọn **Cài đặt Stitch** → Cuộn xuống sẽ thấy tạo khóa → Nhấn **Tạo khóa** → Copy API và Paste lại Antigravity.
- Kiểm tra kết nối: gõ vào Antigravity `List available Stitch tools` — nếu Antigravity liệt kê được các công cụ của Stitch là kết nối thành công.

> ⚠️ **Bảo mật:** Luôn kiểm tra kỹ file `.md` (skill MD file) trước khi cài đặt bất kỳ kỹ năng nào từ mạng vào Antigravity để đảm bảo tính an toàn.

---

### Bước 2: Thiết kế giao diện với Google Stitch

Truy cập [stitch.withgoogle.com](http://stitch.withgoogle.com) để bắt đầu. Có 2 cách tạo thiết kế:

**Cách 1: Từ ảnh chụp màn hình (phổ biến nhất)**

1. Chụp ảnh màn hình trang web bạn muốn lấy cảm hứng.
2. Dán ảnh vào giao diện Stitch.
3. Nhập câu lệnh mô tả mong muốn. Ví dụ prompt mẫu:
   - _"Hãy làm cho thiết kế này đẹp hơn, hiện đại hơn, cảm giác công nghệ sạch, màu xanh tre làm điểm nhấn."_
   - _"Make this more beautiful, interesting, and dopamine-inducing."_
4. Stitch trả về 2–3 biến thể giao diện. Chọn biến thể ưng ý để tiếp tục.

**Cách 2: Từ mô tả bằng chữ (không cần ảnh)**

Nhập trực tiếp mô tả vào Stitch. Ví dụ:

- _"Tạo landing page cho dịch vụ AI Assistant, phong cách hiện đại, có form đăng ký dùng thử, màu xanh trắng."_
- [Prompt mẫu — Landing Page](https://docs.google.com/document/d/1q22CyIQR_9IfZjV4skQRSjNAWgb0GEQ_R9osFNhgOiQ/edit?tab=t.jfiyq9e0q71z)
- [Prompt mẫu — Full Website](https://docs.google.com/document/d/1q22CyIQR_9IfZjV4skQRSjNAWgb0GEQ_R9osFNhgOiQ/edit?tab=t.wbmwv7njrlvg)

**Tính năng Annotate — Chỉnh sửa chi tiết trực tiếp**

- Nhấp vào biểu tượng bút chì (Annotate) trên giao diện Stitch.
- Khoanh vùng muốn sửa (nút, màu nền, khoảng cách...), nhập yêu cầu. Ví dụ:
  - _"Đổi màu nút này thành xanh lá, thêm hiệu ứng hover."_
  - _"Modify this section better"_ / _"Change the colors."_
- Nhấn **Apply** — AI chỉnh riêng vùng đó mà không ảnh hưởng đến phần còn lại.

**Kiểm tra giao diện di động (Mobile Preview)**

- Nhấp vào trình đơn thả xuống trên phần xem trước của Stitch.
- Chọn **Show QR code**.
- Dùng điện thoại quét mã để trải nghiệm giao diện mobile ngay lập tức.

---

### Bước 3: Chuyển thiết kế thành code web (2 phương pháp)

**Phương pháp 1: Thủ công qua file ZIP**

1. Trên Stitch, chọn biến thể ưng ý → **Export** → **Download as ZIP**.
2. Mở Antigravity, tạo thư mục mới (ví dụ: "test site"), kéo file ZIP vào.
3. Gõ lệnh trong Antigravity: _"Hãy biến cái này thành một trang web đẹp, chạy được."_
4. Antigravity tự động giải nén, viết code và hiển thị kết quả.

**Phương pháp 2: Tự động hóa (Dùng Skill đã cài)**

1. Copy nội dung mã lệnh HTML/CSS (Xem Mã).
2. Tạo file HTML tại Antigravity (Cách tạo: `[Tên_file.html]`).
3. Dán đoạn mã lệnh vào file vừa tạo.
4. Ra lệnh tại khung chat Agent: _"Hãy thiết kế landing page từ nội dung này, dùng Stitch skill để tạo UI."_
5. Antigravity chạy song song: một bên tự gọi Stitch tạo file CSS, bên còn lại viết code toàn bộ trang.

---

**📌 Prompt khi sử dụng Antigravity lấy thiết kế từ Stitch**

Khi muốn Antigravity tự động lấy tất cả các project trong Stitch:

```
List my Stitch projects
```

**📌 Prompt nên bổ sung khi sử dụng Antigravity lấy thiết kế từ một màn hình cụ thể:**

Khi muốn Antigravity tự động lấy thiết kế từ một màn hình cụ thể trong Stitch, hãy dùng cấu trúc prompt sau:

```
Sử dụng Stitch, hãy tìm trong project [Tên dự án hoặc ID dự án].
Lấy mã nguồn (HTML/Thiết kế) của màn hình có tên là [Tên biến thể/Tên Screen].
Trích xuất đầy đủ màu sắc, font chữ, bố cục và tạo trong thư mục dự án.
```

Ví dụ cụ thể: _Sử dụng Stitch, hãy tìm trong project BBo-LandingPage-2026. Lấy mã nguồn của màn hình có tên là Hero_Variant_2. Sau đó lưu vào file /src/components/Hero.html._

> 💡 **Lưu ý về hình ảnh:** Antigravity tích hợp sẵn Nano Banana 2 + Gemini Flash giúp tự động tạo ảnh chất lượng cao chèn trực tiếp vào trang. Gõ lệnh: _"Tạo ảnh sản phẩm với phong cách tối giản, màu xanh trắng."_

---

### Bước 4: Tinh chỉnh và kiểm tra

Sau khi có bản web hoàn thiện, kiểm tra và tinh chỉnh theo hai hướng:

**Chỉnh sửa qua Stitch (Annotate)**

- Khoanh vùng cần sửa → nhập yêu cầu → **Apply**.
- Ví dụ: _"Đổi màu nút sang neon"_, _"Thay chữ thành Brand Strategy"_, _"Thêm hiệu ứng hover"_ → Chọn **Change with AI**, lúc này AI sẽ thiết kế lại phần đã khoanh vùng.

**Chỉnh sửa qua Antigravity (lệnh chat)**

- Dùng chat để ra lệnh trực tiếp. Ví dụ:
  - _"Đổi tiêu đề thành: AI cho mọi doanh nghiệp"_
  - _"Thêm icon vào mỗi mục tính năng"_
- Antigravity cập nhật code và hiển thị kết quả ngay lập tức.
- **Điểm lưu ý:** Khi muốn chỉnh phần nào ở giao diện, cần mô tả chi tiết đoạn nào trong trang và kêu Antigravity thiết kế đoạn đó. Càng chi tiết phần prompt thì AI sẽ thiết kế chính xác hơn.

---

## 4. ỨNG DỤNG THỰC TẾ

### Các loại trang web có thể tạo nhanh

- Landing page thu thập thông tin khách hàng (Lead Magnet Page)
- Cổng thông tin hướng dẫn khách hàng mới (Client Onboarding Portal)
- Trang tổng quan cho thành viên (Member Dashboard)
- Công cụ trực quan hóa luồng công việc
- Trang demo sản phẩm nội bộ, thử nghiệm ý tưởng trước khi đầu tư

---

## 5. CÔNG THỨC GHI NHỚ NHANH

> **Ý tưởng → Stitch (3 biến thể) → Chọn 1 → Xuất ZIP → Antigravity (code + chạy) = 5–10 phút**

Với tư duy _"Ngôn ngữ là công cụ — quan trọng là làm chủ luồng kiến trúc"_, bộ đôi Stitch + Antigravity chính là đòn bẩy để tăng tốc mọi dự án thiết kế web tại BBo Tech.

---

## 6. CHECKLIST HOÀN THÀNH

- [ ] Đã cài đặt Stitch Skill vào Antigravity (**MCP Server**).
- [ ] Đã chọn được mẫu website hoặc mô tả ý tưởng rõ ràng.
- [ ] Đã có thiết kế ưng ý từ Stitch (chọn 1 trong 2–3 biến thể).
- [ ] Antigravity đã nhận diện được kỹ năng Stitch qua MCP.
- [ ] Website đã chạy ổn định trên máy tính (local).
- [ ] Giao diện hiển thị tốt trên thiết bị di động (kiểm tra QR code).

---

## 7. TÀI NGUYÊN VÀ LIÊN KẾT THAM KHẢO

| Tài nguyên               | Mô tả                            | Link / Ghi chú                                                                                                                                                                                                                                    |
| ------------------------ | -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Google Stitch            | Công cụ thiết kế giao diện AI    | [stitch.withgoogle.com](http://stitch.withgoogle.com)                                                                                                                                                                                             |
| Video hướng dẫn chi tiết | Ghi hình thực hành step-by-step  | [Link video nội bộ]                                                                                                                                                                                                                               |
| Slide giới thiệu         | Slide trình bày tổng quan        | [Stitch + Antigravity Overview](https://canva.link/1i8eungsswz9ywy)                                                                                                                                                                               |
| Prompt mẫu               | Tập hợp câu lệnh hay dùng nhất   | [Landing Page](https://docs.google.com/document/d/1q22CyIQR_9IfZjV4skQRSjNAWgb0GEQ_R9osFNhgOiQ/edit?tab=t.jfiyq9e0q71z) · [Full Website](https://docs.google.com/document/d/1q22CyIQR_9IfZjV4skQRSjNAWgb0GEQ_R9osFNhgOiQ/edit?tab=t.wbmwv7njrlvg) |
| Stitch Skill (GitHub)    | File kỹ năng cài vào Antigravity | [google-labs-code/stitch-skills](https://github.com/google-labs-code/stitch-skills)                                                                                                                                                               |

---

_Tài liệu này được biên soạn để lưu hành nội bộ tại BBo Tech_
