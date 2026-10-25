# TEMPLATE SRS (BẢN HIỆU CHỈNH)

> Bản này giữ **khung 7 chương của `srs-bookstore-example`**, tích hợp các thành phần bắt buộc mà `srs-relevant` nêu ra, và giữ lại phần bổ sung hữu ích từ bản NotebookLM nhưng gắn nhãn **Mở rộng** để không làm nặng đồ án.

## Cách đọc nhãn

| Nhãn nguồn | Ý nghĩa |
|---|---|
| **[BS]** | Có trong `srs-bookstore-example` |
| **[RL]** | Có trong `srs-relevant` |
| **[+]** | Bổ sung ngoài hai file mẫu (theo hướng Karl Wiegers / ISO 29148, lấy từ bản NotebookLM) |

| Nhãn mức độ | Ý nghĩa |
|---|---|
| ★ **Cốt lõi** | Phải có, kể cả đồ án |
| ◐ **Nên có** | Có nếu dự án đủ lớn hoặc có đối tác bên ngoài |
| ○ **Mở rộng** | Làm sau, hoặc khi dự án thực sự cần |

**Quy tắc chung:** mục nào không áp dụng thì ghi *"Không áp dụng cho dự án này"* (hoặc *"Không có."* như trong `[BS]`), không để trống và không xóa mục.

---

# PHẦN MỞ ĐẦU

## Bản học thuật `[BS]` ★
1. Trang bìa: trường, khoa, đề tài, học phần, nhóm, GVHD, ngày
2. Danh sách thành viên: STT, họ tên, MSSV, tỉ lệ hoàn thành, trưởng nhóm
3. Nhận xét của giảng viên
4. Lời cảm ơn
5. Lời mở đầu: bối cảnh đề tài, mục tiêu, công nghệ và kiến thức áp dụng, hạn chế
6. Mục lục (kèm danh mục bảng, hình)

## Bản doanh nghiệp `[+]` ◐ (thay cho mục 2-5 ở trên)
1. Trang bìa: tên dự án, **mã tài liệu**, **số phiên bản** (v1.0 Baseline), tác giả, ngày
2. **Lịch sử sửa đổi**: phiên bản, ngày, người sửa, lý do
3. **Phê duyệt / ký nhận** `[RL]`: khách hàng/PO, PM, Tech Lead, QA
4. Mục lục

---

# CHƯƠNG 1. GIỚI THIỆU `[BS][RL]` ★

### 1.1. Mục tiêu ★
- Mục đích của tài liệu và sản phẩm: giải quyết vấn đề gì, cho ai, vì sao quan trọng `[RL]`
- Đối tượng đọc: Dev, Tester, Designer, khách hàng, PM, nhà đầu tư `[RL]`
- Vai trò của SRS: nền tảng chung cho phân tích, thiết kế, phát triển, kiểm thử, bảo trì `[BS]`

### 1.2. Phạm vi ★
- Hệ thống **sẽ làm gì** (mô hình hoạt động, nhóm chức năng chính, mục tiêu kinh doanh) `[BS][RL]`
- Hệ thống **không làm gì** (Out-of-scope) và các ràng buộc phạm vi đặc thù. Ví dụ `[BS]`: *"mô hình một chủ quản lý, người quản lý không thể là khách hàng"*

### 1.3. Các định nghĩa, từ viết tắt, chữ viết tắt ★
- **Bảng 1:** `Từ viết tắt | Nội dung`. Ghi cả tên đầy đủ tiếng Anh và giải thích tiếng Việt (SRS, API, UI, UX, SSL, HTTP, ISBN, và các vai trò như Customer, Staff, Owner) `[BS]`
- Dùng thống nhất một thuật ngữ cho một khái niệm trong cả tài liệu `[RL]`

### 1.4. Tổng quan ★
- Mỗi chương một đoạn tóm tắt để người đọc biết tìm gì ở đâu `[BS]`

### 1.5. Quy ước tài liệu `[+]` ○
- Cách đánh mã yêu cầu (ví dụ `FR-CUS-01`, `NFR-PERF-01`), ý nghĩa chữ đậm/nghiêng, quy ước "Hệ thống phải..." (bắt buộc) và "nên..." (khuyến nghị)

---

# CHƯƠNG 2. MÔ TẢ TỔNG QUAN `[BS][RL]` ★

### 2.1. Bối cảnh sản phẩm ★
- Sản phẩm mới hay thay thế hệ thống cũ; độc lập hay là phần bổ sung của hệ thống khác `[RL]`
- Các hệ thống bên ngoài dự kiến kết nối: kho, cổng thanh toán, vận chuyển, CRM `[BS]`
- Sơ đồ ngữ cảnh (Context Diagram) thể hiện luồng dữ liệu vào/ra `[+]` ○

### 2.2. Đặc điểm người dùng ★
Mỗi nhóm người dùng (Customer, Staff, Owner...) gồm 4 mục `[BS]`:
- **Nhu cầu**
- **Hành vi**
- **Kinh nghiệm kỹ thuật**
- **Mục tiêu sử dụng**

### 2.3. Chức năng sản phẩm ★
- Tóm tắt các chức năng chính **theo từng nhóm người dùng**, mỗi chức năng một dòng ngắn `[BS]`
- Chưa đi vào chi tiết, chi tiết nằm ở Chương 3 và Chương 4
- Cây tính năng (Feature Tree) `[+]` ○

### 2.4. Các ràng buộc ★
- **2.4.1. Ràng buộc về hiệu suất** (ví dụ xử lý ≥ 1000 yêu cầu đồng thời, tải trang ≤ 2 giây trong điều kiện bình thường) `[BS]`
- **2.4.2. Ràng buộc về công nghệ** (công nghệ bắt buộc, trình duyệt hỗ trợ, yêu cầu CSDL) `[BS]`
- **2.4.3. Ràng buộc về pháp lý** (thương mại điện tử, bảo vệ người tiêu dùng, dữ liệu cá nhân, phải có chính sách rõ ràng) `[BS]`
- **2.4.4. Môi trường vận hành** (thiết bị, hệ điều hành, trình duyệt, phiên bản CSDL và máy chủ) `[RL][+]` ◐

### 2.5. Kiến trúc hệ thống ◐ `[BS]`
- Mô hình 3 lớp (Presentation, Business Logic, Data Access) và/hoặc MVC, kèm sơ đồ
- **Lưu ý:** chỉ đưa vào SRS khi kiến trúc là **ràng buộc đã chốt** hoặc yêu cầu của môn học. Trong dự án thực tế, quyết định kiến trúc thường nằm ở tài liệu thiết kế và ADR, vì SRS nên nói "làm gì" hơn "làm thế nào" `[RL]`

### 2.6. Giả định và phụ thuộc ★
- **2.6.1. Giả định:** các điều được xem là đúng khi viết SRS (CSDL đủ lớn, dịch vụ bên thứ ba ổn định, quy định pháp lý không đổi lớn) `[BS]`
- **2.6.2. Phụ thuộc:** nhà cung cấp thanh toán và vận chuyển, nhân lực, thay đổi công nghệ hoặc bảo mật `[BS][RL]`

### 2.7. Phân bổ yêu cầu ★
- **2.7.1. Giai đoạn 1: chức năng quan trọng**, liệt kê theo nhóm người dùng `[BS]`
- **2.7.2. Giai đoạn 2: các chức năng còn lại** `[BS]`
- **2.7.3. Yêu cầu có thể dời sang phiên bản sau:** tính năng mở rộng, cải thiện hiệu suất, tăng cường bảo mật, tùy chỉnh giao diện `[BS]`
- **Nêu rõ yêu cầu phi chức năng nào cố ý chưa làm ở phiên bản này.** Ví dụ `[BS]`: *"bảo mật không phải mối quan tâm lớn của dự án này nên chưa mã hóa thông tin thẻ"*. Viết ra tường minh để tránh bị hiểu là sót
- Độ ưu tiên từng chức năng (Must / Should / Could / Won't) `[RL][+]` ◐

---

# CHƯƠNG 3. YÊU CẦU CỤ THỂ `[BS][RL]` ★

### 3.1. Yêu cầu chức năng ★ `[BS]`
- Chia theo nhóm người dùng (3.1.1 Customer, 3.1.2 Unregistered Customer, 3.1.3 Registered Customer, 3.1.4 Staff, 3.1.5 Owner)
- Mỗi yêu cầu: **ID duy nhất** `[+]` + tên chức năng + câu bắt đầu bằng **"Hệ thống phải..."** + điều kiện cụ thể
- Dữ liệu dài (danh mục, trường tìm kiếm, báo cáo) **không nhét vào câu yêu cầu**, mà tham chiếu bảng ở phụ lục (ví dụ *"xem Bảng 4. Các trường tìm kiếm sách"*)
- Mỗi yêu cầu chỉ nói **một việc**, tách nhỏ nếu gộp nhiều việc

### 3.2. Yêu cầu giao diện bên ngoài ◐ `[RL]`
- **3.2.1. Giao diện người dùng:** nguyên tắc UI/UX, thiết bị và độ phân giải hỗ trợ, **liên kết đến wireframe / mockup / prototype (Figma)**
- **3.2.2. Giao diện phần mềm:** các hệ thống/API bên ngoài (cổng thanh toán, email/SMS, xác thực), định dạng dữ liệu trao đổi
- **3.2.3. Giao diện phần cứng:** thiết bị ngoại vi nếu có (máy quét mã vạch, máy in...). Không có thì ghi *"Không áp dụng"*
- **3.2.4. Giao diện truyền thông:** giao thức bắt buộc (HTTPS...)

### 3.3. Yêu cầu phi chức năng ★ `[BS][RL]`
Mỗi mục viết **đo được và nêu điều kiện đo**:
1. **Hiệu suất** (Performance) `[BS][RL]`: ví dụ *tải trang ≤ 2 giây trong điều kiện tải bình thường, hỗ trợ ≥ 1000 người dùng đồng thời*
2. **Khả năng mở rộng** (Scalability) `[BS]`
3. **Khả năng bảo trì** (Maintainability) `[BS][RL]`
4. **Khả năng sử dụng** (Usability) `[BS][RL]`: ví dụ *người dùng mới hoàn thành đặt hàng trong ≤ 3 bước*
5. **Bảo mật** (Security) `[RL]`: nêu **yêu cầu**, không nêu thuật toán. Ví dụ *"mật khẩu không được lưu dạng văn bản thuần"*, không viết sẵn tên thư viện băm. Nếu quyết định chưa làm thì ghi ở mục 2.7
6. **Độ sẵn sàng và độ tin cậy** (Availability, Reliability) `[RL]` ◐: ví dụ uptime mục tiêu
7. **Tương thích** (trình duyệt, thiết bị) `[RL]`
8. **An toàn** (Safety) `[RL]` ○: chỉ khi hệ thống có nguy cơ gây hại cho con người hoặc môi trường. Đừng gộp với Security

### 3.4. Yêu cầu dữ liệu `[+]` ○
- Mô hình dữ liệu logic (trỏ sang Class Diagram / ERD ở Chương 4)
- Từ điển dữ liệu: tên trường, kiểu, độ dài, ràng buộc, bắt buộc hay tùy chọn
- Yêu cầu báo cáo (trỏ sang bảng ở phụ lục), thời gian lưu trữ, sao lưu, xóa dữ liệu

### 3.5. Tiêu chí nghiệm thu ★ `[RL]`
Danh sách điều kiện để hệ thống được xem là **hoàn thành, sẵn sàng đưa vào sử dụng**:
- Tất cả use case của giai đoạn 1 chạy đúng luồng chính và các luồng ngoại lệ
- Yêu cầu phi chức năng đạt ngưỡng đã nêu ở 3.3
- Các kiểm thử cần vượt qua (ví dụ kiểm thử chức năng, kiểm thử tải theo con số ở 3.3)
- Khách hàng / GVHD đã duyệt

> Đây là tiêu chí cấp **hệ thống**. Acceptance Criteria của từng User Story vẫn nằm ở từng story.

---

# CHƯƠNG 4. YÊU CẦU MÔ HÌNH HÓA `[BS]` ★

### 4.1. Use Case Diagram ★
- Sơ đồ tổng thể các actor và use case (hình + link xem bản lớn)
- **Đặc tả từng use case** theo mẫu bảng:

| [n] | Tên Use Case (Anh - Việt) |
|:---:|---|
| **Actor** | Tác nhân thực hiện |
| **Trigger** | Sự kiện kích hoạt (người dùng nhấn/chọn gì) |
| **Description** | Tóm tắt use case làm gì |
| **Pre-Conditions** | Trạng thái cần có trước (đã đăng nhập...) hoặc "Không có." |
| **Post-Conditions** | Trạng thái sau khi thành công |
| **Main Flow** | Các bước đánh số, xen kẽ Actor và Hệ thống. Nếu gọi use case khác thì ghi rõ tên (ví dụ *Hệ thống thực hiện use case Verify Email*) |
| **Alternate Flow** | Nhánh hợp lệ khác, hoặc "Không có." |
| **Exception Flow** | Mỗi lỗi **đánh số theo bước trong Main Flow**, ví dụ `+ 5.1 Nếu nhập thiếu trường, hệ thống hiển thị "Vui lòng nhập trường này"` |

- **Phụ lục mô tả use case:** gom các bảng dài tham chiếu từ Chương 3 và Chương 4 (danh mục thể loại, trường tìm kiếm, danh mục báo cáo, công thức chỉ số, thông tin đính kèm use case), đánh số Bảng 2, 3, 4... `[BS]`

### 4.2. Class Diagram ★
- Sơ đồ lớp mức miền nghiệp vụ (Domain), kèm link xem bản lớn. ERD có thể thêm ở đây `[+]` ○

### 4.3. Sequence Diagrams ◐
- Cho các luồng chính hoặc phức tạp (đăng ký, thanh toán, hoàn trả...)

### 4.4. Collaboration Diagrams `[BS]` ○
- Có thể thay hoặc bổ sung cho Sequence Diagram tùy yêu cầu môn học

### 4.5. State / Activity Diagrams `[+]` ○
- Cho đối tượng có vòng đời phức tạp. Ví dụ trạng thái đơn hàng: *Chờ xác nhận → Đã xác nhận → Đang giao → Hoàn thành / Hủy / Hoàn trả*

---

# CHƯƠNG 5. ĐÍNH KÈM `[BS]` ★

### 5.1. Liên kết dự án
- Tài liệu dự án, board công việc (Jira / ClickUp / GitHub Projects), repository, sơ đồ, prototype Figma, biên bản họp khảo sát

### 5.2. Ma trận truy vết yêu cầu (RTM) `[+]` ○
- Bảng nối: User Requirement (Use Case ID) ↔ Functional Requirement ID ↔ module/class ↔ Test Case ID

---

# CHƯƠNG 6. TÀI LIỆU THAM KHẢO `[BS]` ★

- Luận văn, báo cáo, SRS của hệ thống tương tự
- Website thương mại điện tử tham khảo (Amazon, Barnes & Noble, ...)
- Tiêu chuẩn áp dụng nếu có (ví dụ ISO/IEC/IEEE 29148) `[+]`

---

# CHƯƠNG 7. ĐIỀU KHOẢN VÀ CHÍNH SÁCH `[BS]` ◐

Đây là nội dung **đặc thù theo lĩnh vực**. Giữ mục nào đúng với hệ thống của bạn:

| Mục | Nội dung |
|---|---|
| 7.1 Giới thiệu cửa hàng / tổ chức | Thông tin, liên hệ, sứ mệnh |
| 7.2 Điều khoản khách hàng | Quyền, nghĩa vụ, điều kiện sử dụng |
| 7.3 Chính sách bảo mật | Thu thập, sử dụng, bảo vệ dữ liệu cá nhân |
| 7.4 Chính sách vận chuyển | Phạm vi, biểu phí, thời gian giao |
| 7.5 Chính sách đổi trả | Điều kiện, thời hạn, quy trình |
| 7.6 Chính sách khuyến mãi | Mã giảm giá, voucher, thẻ quà tặng, điều kiện áp dụng |
| 7.7 Chính sách thành viên | Hạng, quyền lợi, điều kiện nâng hạng |
| 7.8 Danh mục quy tắc nghiệp vụ `[+]` ○ | Công thức tính (phí vận chuyển, giảm giá) và quy tắc điều kiện (chỉ hủy đơn trước khi xác nhận) |

> Các chính sách ở đây là nguồn để các yêu cầu ở Chương 3 và các luồng ở Chương 4 tham chiếu.

---

# NGUYÊN TẮC VIẾT (từ `srs-relevant`)

| Đặc tính | Áp dụng vào template |
|---|---|
| **Explicit** (rõ ràng) | Một thuật ngữ một nghĩa (Bảng 1), có sơ đồ minh họa |
| **Measurable** (đo được) | Mọi NFR có con số và điều kiện đo |
| **Complete** (đầy đủ) | Không bỏ mục, mục không áp dụng thì ghi rõ |
| **Viable** (khả thi) | Phù hợp ngân sách, thời gian, công nghệ thực tế |
| **Flexible** (linh hoạt) | SRS là tài liệu sống, có phiên bản, thay đổi qua quy trình kiểm soát |
| **Verifiable** (kiểm chứng được) | Test được. Team đọc xong không cần hỏi lại |
| **Consistent** (nhất quán) | Yêu cầu không mâu thuẫn, định dạng và thuật ngữ đồng nhất |
| **No implementation constraints** | Không áp đặt giải pháp kỹ thuật, trừ khi là ràng buộc đã chốt |
| **Accurate** (chính xác) | Mỗi yêu cầu chỉ có một cách hiểu |

**Lỗi cần tránh:** ngôn ngữ mơ hồ; viết quá phức tạp, nhiều thuật ngữ chưa định nghĩa; **quá chi tiết** đến mức thành mô tả hệ thống cho lập trình viên và kiến trúc sư.

---

# ƯU TIÊN KHI LÀM ĐỒ ÁN

**Làm trước (★):** Phần mở đầu học thuật · Chương 1 · Chương 2 (2.1 đến 2.4, 2.6, 2.7) · 3.1 · 3.3 (các mục 1-5) · 3.5 · 4.1 (use case) · 4.2 · Chương 5.1 · Chương 6

**Làm khi có thời gian (◐):** 2.4.4 · 2.5 · 3.2 · 4.3 · Chương 7 · độ ưu tiên MoSCoW · lịch sử sửa đổi và phê duyệt

**Để sau (○):** 1.5 · Context Diagram, Feature Tree · 3.4 dữ liệu · 4.4, 4.5 · RTM · 7.8 · An toàn (Safety)

> Một SRS ngắn, nhất quán, đo được, được cả team đọc và dùng có giá trị hơn một SRS điền đủ mọi mục mà không ai mở lại.