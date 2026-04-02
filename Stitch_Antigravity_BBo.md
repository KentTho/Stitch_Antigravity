# HƯỚNG DẪN SỬ DỤNG

## Bộ đôi AI miễn phí từ Google: STITCH + ANTIGRAVITY

> **Thiết kế và xây dựng website không cần code — Từ ý tưởng đến sản phẩm chỉ trong 5–10 phút**

_Tài liệu lưu hành nội bộ — BBo Tech_  
Ngày cập nhật: 31/03/2026

---

## 1. TỔNG QUAN VÀ MỤC TIÊU

Trong năm 2026, công nghệ AI đã giúp việc tạo website trở nên đơn giản như viết email. Bạn không cần biết lập trình — chỉ cần mô tả điều mình muốn bằng tiếng Việt, AI sẽ tự tạo ra trang web hoàn chỉnh. Bộ đôi công cụ miễn phí từ Google dưới đây giúp rút ngắn quy trình từ 3–8 tuần xuống chỉ còn 5–10 phút.

### 1.1 Tài liệu này dành cho ai?

- Ban Giám đốc muốn xem demo ý tưởng ngay trong buổi họp.
- Nhân viên Marketing, Sales muốn tự tạo trang quảng cáo mà không cần chờ team kỹ thuật.
- Bất kỳ ai trong công ty — dù chưa từng viết một dòng code nào.

### 1.2 Hai công cụ chính

**🎨 Google Stitch — "Người thiết kế"**

Địa chỉ: [stitch.withgoogle.com](http://stitch.withgoogle.com)

Bạn nói hoặc dán ảnh mẫu vào → Stitch tự tạo ra giao diện website đẹp. Giống như thuê một nhà thiết kế, nhưng miễn phí và làm việc trong vài giây.

- Nhận ảnh chụp màn hình hoặc mô tả bằng ngôn ngữ tự nhiên.
- Tạo ra 2–3 phiên bản giao diện đẹp, hiện đại để bạn chọn.
- Cho phép sửa từng vùng cụ thể bằng cách khoanh vùng và nhập yêu cầu.
- **Lưu ý:** Stitch chỉ làm phần "hình ảnh" của website, chưa tạo ra trang web chạy thật sự.

**🔧 Google Antigravity — "Người xây dựng"**

Antigravity là phần mềm cài trên máy tính. Nó nhận bản thiết kế từ Stitch và tự động tạo ra website hoạt động thật sự — bao gồm cả cơ sở dữ liệu, nút bấm, form điền thông tin, v.v.

- Tự động chuyển bản thiết kế thành website chạy được.
- Có thể xem kết quả ngay trên máy tính trước khi đưa lên mạng.
- Tích hợp sẵn AI tạo hình ảnh chất lượng cao (Nano Banana 2 + Gemini Flash).

### 1.3 Quy trình tổng thể (5–10 phút)

> **Ý tưởng → Stitch tạo 2–3 giao diện → Chọn 1 giao diện ưng ý → Antigravity tự tạo website → Xong!**

---

## 2. LỢI ÍCH SO VỚI CÁCH LÀM TRUYỀN THỐNG

| Tiêu chí             | Cách làm cũ                              | Stitch + Antigravity              |
| -------------------- | ---------------------------------------- | --------------------------------- |
| Thời gian hoàn thành | 3–8 tuần                                 | 5–10 phút                         |
| Nhân sự cần thiết    | Cần cả nhà thiết kế + lập trình viên     | 1 người, không cần biết code      |
| Chi phí              | Cao (thuê ngoài hoặc nhân sự chuyên môn) | 0 đồng — hoàn toàn miễn phí       |
| Chỉnh sửa khi cần    | Phải gửi yêu cầu, chờ nhiều ngày         | Sửa ngay bằng câu lệnh tiếng Việt |
| Thử nghiệm ý tưởng   | Phải chờ bản thiết kế mẫu                | Demo ngay trong buổi họp          |

---

## 3. HƯỚNG DẪN THỰC HÀNH TỪNG BƯỚC

### Bước 1: Kết nối Stitch và Antigravity (Làm 1 lần duy nhất)

Trước khi bắt đầu, bạn cần "giới thiệu" để Stitch và Antigravity nhận ra nhau. Có 2 cách, bạn chọn 1 cách phù hợp nhất:

---

**Cách A: Kết nối qua cài đặt trong Antigravity (Khuyến nghị — đơn giản hơn)**

Đây là cách trực quan nhất, chỉ cần vài cú nhấp chuột:

1. Mở Antigravity → Nhấp vào biểu tượng **3 chấm (⋯)** ở góc trên bên phải màn hình.

2. Chọn tab **MCP Servers** (đây là nơi quản lý các công cụ kết nối) → Gõ "Stitch" vào ô tìm kiếm → Nhấn tải về.

3. Nhấp vào **Stitch** → Chọn **Configure** → Nhập **API Key** (mã xác nhận kết nối).

**👉 API Key là gì?** Đây là mã xác minh giúp Antigravity biết bạn có quyền dùng Stitch. Lấy mã này như sau:

- Mở Stitch → Nhấp vào ảnh đại diện của bạn ở góc trên bên phải → Chọn **Cài đặt Stitch**.
- Cuộn xuống phần **Tạo khóa** → Nhấn **Tạo khóa** → Copy mã vừa tạo → Dán lại vào Antigravity.

4. Kiểm tra kết nối: Gõ câu sau vào Antigravity và nhấn Enter:

> 💬 **Lệnh kiểm tra kết nối**
>
> ```
> List available Stitch tools
> ```

Nếu Antigravity liệt kê ra danh sách công cụ của Stitch → **Kết nối thành công!**

---

**Cách B: Kết nối bằng lệnh cài đặt nhanh**

Thay vì vào cài đặt, bạn có thể gõ lệnh trực tiếp vào khung chat của Antigravity:

- Dán đường dẫn sau vào khung chat: `https://github.com/google-labs-code/stitch-skills`
- Thêm dòng lệnh phía sau, chọn 1 trong 2:
  - `install this skill` → Chỉ dùng cho dự án đang mở.
  - `install the skill globally` → Dùng được cho tất cả dự án sau này _(khuyến nghị)_.

> ⚠️ **Lưu ý bảo mật:** Chỉ cài đặt từ các đường dẫn do Google hoặc BBo Tech cung cấp. Không cài từ nguồn lạ.

---

### Bước 2: Tạo giao diện website trên Stitch

Truy cập [stitch.withgoogle.com](http://stitch.withgoogle.com). Bạn có 2 cách để bắt đầu:

**Cách 1: Dùng ảnh mẫu (Dễ nhất — khuyến nghị)**

1. Tìm một trang web bạn thấy đẹp → Nhấn phím **Print Screen** (hoặc **Windows + Shift + S**) để chụp màn hình.
2. Dán ảnh vào Stitch (**Ctrl + V**).
3. Nhập yêu cầu của bạn bằng tiếng Việt. Ví dụ:

> 💬 **Mẫu câu lệnh tiếng Việt**
>
> ```
> Hãy làm cho thiết kế này đẹp hơn, hiện đại hơn, cảm giác công nghệ sạch, dùng màu xanh lá làm điểm nhấn.
> ```

> 💬 **Mẫu câu lệnh tiếng Anh**
>
> ```
> Make this more beautiful, interesting, and dopamine-inducing.
> ```

4. Stitch tự tạo 2–3 phiên bản giao diện khác nhau để bạn chọn. Chọn phiên bản ưng ý nhất.

**Cách 2: Mô tả bằng chữ (Không cần ảnh)**

Nếu bạn chưa có ảnh mẫu, cứ mô tả thẳng điều bạn muốn:

> 💬 **Ví dụ câu lệnh mô tả**
>
> ```
> Tạo landing page cho dịch vụ AI Assistant, phong cách hiện đại, có ô điền thông tin đăng ký dùng thử, dùng tông màu xanh trắng.
> ```

Xem thêm mẫu câu lệnh tại: [Landing Page mẫu](https://docs.google.com/document/d/1DgAwx36R2IvdfDNmfNCCPgm8dMZUo6Vcy5pffm1HrDA/edit?usp=sharing) | [Full Website mẫu](https://docs.google.com/document/d/1DgAwx36R2IvdfDNmfNCCPgm8dMZUo6Vcy5pffm1HrDA/edit?usp=sharing)

**Tính năng Chỉnh sửa trực tiếp (Annotate)**

Nếu muốn thay đổi một vùng cụ thể trên giao diện mà không muốn làm lại từ đầu:

- Nhấp vào biểu tượng bút chì **(Annotate)** → Khoanh vùng muốn sửa.
- Nhập yêu cầu. Ví dụ: _"Đổi màu nút này thành xanh lá, thêm hiệu ứng khi di chuột qua."_
- Nhấn **Apply (Áp dụng)** → AI chỉ sửa vùng đó, không đụng đến phần còn lại.

**Xem giao diện trên điện thoại**

- Nhấp vào nút menu thả xuống trong phần xem trước → Chọn **Show QR code**.
- Dùng điện thoại quét mã → Thấy ngay giao diện mobile trông như thế nào.

---

### Bước 3: Chuyển giao diện thành website thật (2 cách)

**Cách 1: Tải file về và dùng Antigravity xây dựng (Đơn giản nhất)**

1. Trên Stitch, chọn giao diện ưng ý → Nhấn **Export (Xuất)** → **Download as ZIP** (Tải về dạng file nén).
2. Mở Antigravity → Tạo thư mục mới (đặt tên tùy thích) → Kéo file ZIP vừa tải vào.
3. Gõ yêu cầu vào Antigravity:

> 💬 **Câu lệnh để Antigravity tạo website**
>
> ```
> Hãy biến bản thiết kế này thành một trang web đẹp, hoạt động được.
> ```

4. Antigravity tự giải nén, tự viết code và hiển thị kết quả. Bạn không cần làm gì thêm.

**Cách 2: Để Antigravity tự lấy thiết kế từ Stitch (Tự động hóa hoàn toàn)**

Với cách này, Antigravity sẽ tự vào Stitch lấy thiết kế mà không cần bạn tải file về tay.

1. Mở Antigravity → Gõ câu lệnh để xem danh sách dự án Stitch của bạn:

> 💬 **Xem danh sách dự án**
>
> ```
> List my Stitch projects
> ```

2. Ghi lại tên dự án và tên màn hình bạn muốn lấy, rồi dùng câu lệnh sau:

> 💬 **Câu lệnh lấy thiết kế từ Stitch**
>
> ```
> Sử dụng Stitch, hãy tìm trong project [Tên dự án]. Lấy thiết kế của màn hình có tên [Tên màn hình]. Trích xuất đầy đủ màu sắc, font chữ, bố cục và tạo website trong thư mục dự án.
> ```

**Ví dụ cụ thể:** _Sử dụng Stitch, hãy tìm trong project BBo-LandingPage-2026. Lấy thiết kế của màn hình có tên Hero_Variant_2. Sau đó lưu vào file /src/components/Hero.html._

> 💡 **Mẹo:** Câu lệnh càng mô tả chi tiết thì AI càng tạo ra kết quả chính xác hơn. Hãy nêu rõ tên dự án, tên màn hình và bạn muốn lưu ở đâu.

> 🖼️ **Tạo hình ảnh tự động:** Antigravity có thể tự tạo ảnh minh họa chèn vào trang web. Chỉ cần gõ: _"Tạo ảnh sản phẩm với phong cách tối giản, màu xanh trắng."_

---

### Bước 4: Chỉnh sửa và kiểm tra lần cuối

Khi đã có website hoàn chỉnh, bạn có thể tinh chỉnh theo 2 cách:

**Chỉnh sửa trực quan trên Stitch**

- Khoanh vùng muốn sửa → Nhập yêu cầu → Chọn **Change with AI**.
- **Ví dụ:** _"Đổi màu nút sang neon"_, _"Thay chữ thành Brand Strategy"_, _"Thêm hiệu ứng khi di chuột qua"_.

**Chỉnh sửa bằng câu lệnh trong Antigravity**

- Gõ yêu cầu trực tiếp vào Antigravity, Antigravity cập nhật ngay:
  - _"Đổi tiêu đề thành: AI cho mọi doanh nghiệp"_
  - _"Thêm biểu tượng vào mỗi mục tính năng"_

> 💡 **Mẹo chỉnh sửa hiệu quả:** Mô tả thật cụ thể vị trí muốn sửa. Ví dụ thay vì nói _"Sửa nút"_ thì nói _"Sửa nút màu xanh ở cuối trang, đổi thành màu cam"_. Càng chi tiết, AI càng làm đúng ý bạn hơn.

---

## 4. ỨNG DỤNG THỰC TẾ & LỢI ÍCH TỪNG BỘ PHẬN

| Bộ phận           | Có thể làm gì ngay?                                         | Lợi ích                             |
| ----------------- | ----------------------------------------------------------- | ----------------------------------- |
| Ban Giám đốc      | Demo ý tưởng trực quan ngay trong buổi họp                  | Không cần chờ, quyết định nhanh hơn |
| Marketing / Sales | Tự tạo trang quảng cáo, trang thu thập thông tin khách hàng | Không phụ thuộc team kỹ thuật       |
| Team Developer    | Nhận ngay bộ khung website sẵn để phát triển thêm           | Tiết kiệm ~70% thời gian ban đầu    |
| Nhân viên bất kỳ  | Tạo website thử nghiệm ý tưởng, dự án cá nhân               | Không cần học lập trình             |

**Các loại trang web có thể tạo nhanh**

- Trang quảng cáo, thu thập thông tin khách hàng tiềm năng
- Trang hướng dẫn và chào đón khách hàng mới
- Trang tổng quan nội bộ cho thành viên nhóm
- Trang sơ đồ quy trình công việc trực quan
- Bản demo ý tưởng để trình bày trong cuộc họp

---

## 5. CÔNG THỨC GHI NHỚ NHANH

> **Ý tưởng → Stitch (2–3 giao diện) → Chọn 1 → Antigravity tự tạo website = 5–10 phút**

Với tư duy _"Ngôn ngữ chính là công cụ"_, bộ đôi Stitch + Antigravity giúp bất kỳ ai tại BBo Tech cũng có thể tạo ra sản phẩm web chuyên nghiệp mà không cần chờ đợi.

---

## 6. CHECKLIST HOÀN THÀNH

- [ ] Đã kết nối Stitch và Antigravity (qua MCP Server hoặc lệnh cài đặt).
- [ ] Đã có ý tưởng hoặc ảnh mẫu để bắt đầu thiết kế.
- [ ] Đã chọn được 1 giao diện ưng ý từ Stitch (trong 2–3 phiên bản).
- [ ] Antigravity đã nhận ra kết nối với Stitch (kiểm tra bằng lệnh `List available Stitch tools`).
- [ ] Website đã hiển thị và chạy được trên máy tính.
- [ ] Giao diện trông ổn trên điện thoại (kiểm tra bằng QR code trong Stitch).

---

## 7. TÀI NGUYÊN VÀ LIÊN KẾT THAM KHẢO

| Tài nguyên                | Mô tả                            | Truy cập                                                                                                                                                            |
| ------------------------- | -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Google Stitch             | Công cụ thiết kế giao diện AI    | [stitch.withgoogle.com](http://stitch.withgoogle.com)                                                                                                               |
| Video hướng dẫn chi tiết  | Ghi hình thực hành từng bước     | [Link video nội bộ]                                                                                                                                                 |
| Slide giới thiệu          | Slide tổng quan để trình bày     | [canva.link/1i8eungsswz9ywy](https://canva.link/1i8eungsswz9ywy)                                                                                                    |
| Prompt mẫu — Landing Page | Câu lệnh mẫu tạo trang quảng cáo | [Xem tài liệu prompt](https://docs.google.com/document/d/1DgAwx36R2IvdfDNmfNCCPgm8dMZUo6Vcy5pffm1HrDA/edit?usp=sharing)                                             |
| Prompt mẫu — Full Website | Câu lệnh mẫu tạo website đầy đủ  | [Xem tài liệu prompt](https://docs.google.com/document/d/1DgAwx36R2IvdfDNmfNCCPgm8dMZUo6Vcy5pffm1HrDA/edit?usp=sharing)                                             |
| Stitch Skill (GitHub)     | Gói kết nối cài vào Antigravity  | [github.com/google-labs-code/stitch-skills](https://github.com/google-labs-code/stitch-skills)                                                                      |
| Google Drive              | Tổng hợp tài liệu + Video        | [google-drive-bbo-tech](https://docs.google.com/document/d/1DgAwx36R2IvdfDNmfNCCPgm8dMZUo6Vcy5pffm1HrDA/edit?usp=sharing)                                           |
| Documents                 | Tài liệu đọc                     | [documents-Stitch-Antigravity](https://docs.google.com/document/d/1h0s_9ip79DWxWq8VgCq2zRJTmr0tOQR4/edit?usp=sharing&ouid=101529481334145985368&rtpof=true&sd=true) |

---

_Tài liệu lưu hành nội bộ tại BBo Tech — Mọi thắc mắc liên hệ team Developer._
