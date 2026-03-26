# 🏍️ Hệ thống quản lý nhập, bán xe máy cho đại lý xe

## 📌 Giới thiệu dự án

**Hệ thống quản lý nhập, bán xe máy** là giải pháp phần mềm được xây dựng nhằm số hóa toàn bộ quy trình nghiệp vụ tại các đại lý xe máy quy mô vừa và nhỏ. Dự án hướng tới thay thế phương pháp quản lý thủ công (sổ sách, Excel) bằng một hệ thống tập trung, tự động hóa, giúp nâng cao hiệu quả vận hành, giảm thiểu sai sót và cung cấp thông tin kịp thời cho việc ra quyết định kinh doanh.

Đây là sản phẩm của nhóm sinh viên CNTT 17-02, Trường Đại học Đại Nam, thực hiện trong khuôn khổ học phần **Phân tích nghiệp vụ phần mềm**.

---

## 🎯 Mục tiêu của hệ thống

- **Tự động hóa quy trình nghiệp vụ**: nhập kho, bán hàng, cập nhật tồn kho theo thời gian thực.
- **Quản lý tập trung**: thông tin xe, khách hàng, nhà cung cấp, nhân viên, hóa đơn.
- **Hỗ trợ báo cáo quản trị**: doanh thu, lợi nhuận, tồn kho, xe bán chạy, công nợ nhà cung cấp.
- **Giao diện thân thiện**: dễ sử dụng cho nhân viên không chuyên về công nghệ.
- **Bảo mật và phân quyền**: phân quyền chi tiết theo vai trò (quản lý, nhân viên bán hàng, nhân viên kho).

---

## 📦 Phạm vi dự án (In-Scope)

- Quản lý danh mục xe (CRUD, hình ảnh, giá nhập/bán)
- Quản lý nhập hàng (phiếu nhập, nhà cung cấp, cập nhật tồn kho)
- Quản lý bán hàng (hóa đơn POS, tính tiền, in hóa đơn, trừ kho)
- Quản lý khách hàng (thông tin, lịch sử mua hàng)
- Quản lý nhà cung cấp (thông tin, công nợ, lịch sử nhập)
- Quản lý nhân viên và phân quyền truy cập
- Báo cáo thống kê (doanh thu, tồn kho, xe bán chạy, công nợ NCC)
- Cảnh báo tồn kho dưới mức tối thiểu

**Ngoài phạm vi (Out-of-Scope)**:
- Website bán hàng online, ứng dụng di động cho khách hàng
- Quản lý lương, chấm công nhân viên
- Tích hợp thanh toán trực tuyến
- Quản lý bảo hành, dịch vụ sửa chữa

---

## 🛠️ Công nghệ đề xuất

| Thành phần | Công nghệ lựa chọn |
|------------|-------------------|
| Kiến trúc | 3-Tier Web Application |
| Frontend | React.js / Vue.js |
| Backend | ASP.NET Core Web API / Node.js |
| Database | Microsoft SQL Server / MySQL |
| Giao diện | Figma (thiết kế), HTML/CSS/JS |

> Công nghệ có thể điều chỉnh phù hợp với năng lực nhóm phát triển và yêu cầu thực tế.

---

## 🧩 Chức năng chi tiết

### 1. Quản lý danh mục xe
- Thêm, sửa, xóa, tìm kiếm xe theo nhiều tiêu chí.
- Upload hình ảnh xe.

### 2. Quản lý kho hàng
- Tạo phiếu nhập kho, cập nhật tồn tự động.
- Kiểm kê kho, điều chỉnh tồn.
- Cảnh báo tồn kho thấp.

### 3. Quản lý bán hàng (POS)
- Tạo hóa đơn bán hàng nhanh.
- Tự động tính tổng tiền, thuế.
- In hóa đơn, hủy hóa đơn (có kiểm soát).

### 4. Quản lý khách hàng
- Lưu trữ thông tin khách hàng, lịch sử mua hàng.
- Tích điểm cơ bản.

### 5. Quản lý nhà cung cấp
- Danh sách NCC, lịch sử nhập hàng.
- Theo dõi công nợ.

### 6. Quản lý nhân viên & phân quyền
- Phân quyền chi tiết (Admin, Quản lý, NV bán hàng, NV kho).
- Mã hóa mật khẩu.

### 7. Hệ thống báo cáo
- Doanh thu theo ngày/tuần/tháng/năm.
- Tồn kho hiện tại và biến động.
- Top xe bán chạy.
- Công nợ nhà cung cấp.

---

## 📊 Mô hình nghiệp vụ

Hệ thống được mô hình hóa bằng các biểu đồ UML và BPMN:

- **Use Case Diagram** – xác định tác nhân và chức năng.
- **Activity Diagram** – mô tả luồng xử lý nghiệp vụ (nhập kho, bán hàng, báo cáo...).
- **Context Diagram** – thể hiện tương tác với các thực thể bên ngoài.
- **BPMN** – mô tả quy trình phân tích nghiệp vụ tổng thể.

---

## 🗃️ Cấu trúc cơ sở dữ liệu (sơ bộ)

Các bảng chính:
- `Xe`, `NhaCungCap`, `PhieuNhap`, `ChiTietNhap`
- `KhachHang`, `HoaDonBan`, `ChiTietBan`
- `NhanVien`

> Sơ đồ quan hệ chi tiết có trong tài liệu thiết kế.

---

## 🧪 Kiểm thử

Hệ thống được kiểm thử theo các cấp độ:

- **Kịch bản kiểm thử chức năng** (đăng nhập, thêm xe, nhập hàng, bán hàng, báo cáo).
- **UAT (User Acceptance Test)** – mời người dùng thực tế thao tác và đánh giá.
- **Checklist test** – đảm bảo tất cả chức năng quan trọng đều được kiểm tra.

---

## 📁 Cấu trúc tài liệu dự án
docs/
├── BRD.md # Tài liệu yêu cầu nghiệp vụ
├── FRS.md # Tài liệu yêu cầu chức năng
├── SRS.md # Tài liệu đặc tả phần mềm
├── diagrams/ # Biểu đồ UML, BPMN
├── wireframes/ # Thiết kế giao diện (Wireframe, Mockup)
└── test/ # Kịch bản kiểm thử, UAT plan


---

## 🧑‍💻 Thành viên nhóm

| STT | Mã sinh viên | Họ và tên |
|-----|--------------|-----------|
| 1   | 1771020523   | Nguyễn Vũ Yến Nhi |
| 2   | 1771020777   | Nguyễn Thị Yến |

Giảng viên hướng dẫn: **Thầy Trần Quý Nam**

---

## 📅 Lộ trình phát triển (dự kiến)

| Giai đoạn | Thời gian | Nội dung |
|-----------|-----------|----------|
| Phân tích nghiệp vụ | 2 tuần | Khảo sát, xác định yêu cầu, mô hình hóa |
| Thiết kế hệ thống | 2 tuần | Thiết kế DB, giao diện, kiến trúc |
| Phát triển core | 2-3 tháng | Xây dựng các module chính (kho, bán hàng) |
| Báo cáo & kiểm thử | 1 tháng | Báo cáo, kiểm thử, UAT, hoàn thiện |

---

## 📝 Ghi chú

Dự án là bài tập lớn môn **Phân tích nghiệp vụ phần mềm**, tập trung vào giai đoạn phân tích và thiết kế. Các phần code và triển khai thực tế có thể được phát triển trong các giai đoạn tiếp theo.

Mọi góp ý, thắc mắc xin liên hệ nhóm sinh viên hoặc giảng viên hướng dẫn.

---

**© 2025 – Nhóm 5, CNTT 17-02, Trường Đại học Đại Nam**
