# Smart Parking Management System
### Hệ thống quản lý bãi đỗ xe thông minh

**Smart Parking Management System** là đồ án thực tập chuyên ngành Công nghệ thông tin, hướng đến xây dựng một hệ thống hỗ trợ quản lý bãi đỗ xe, phương tiện, lượt gửi xe, vị trí đỗ và thanh toán. Dự án định hướng ứng dụng công nghệ nhận diện biển số xe tự động (ALPR) nhằm hỗ trợ nhân viên kiểm soát xe vào, xe ra và nâng cao hiệu quả quản lý.

> **Trạng thái dự án:** Đang trong giai đoạn phân tích, thiết kế và phát triển.

## 1. Mục tiêu dự án

- Xây dựng website quản lý hoạt động của bãi đỗ xe.
- Quản lý thông tin bãi xe, cổng, khu vực và vị trí đỗ.
- Theo dõi quá trình xe vào, xe ra và lịch sử gửi xe.
- Hỗ trợ nhận diện biển số bằng AI và cho phép nhân viên chỉnh sửa khi nhận diện sai.
- Tự động tính phí gửi xe theo bảng giá được cấu hình.
- Quản lý vé tháng và thông tin thanh toán.
- Hiển thị trạng thái vị trí đỗ xe để hỗ trợ điều phối phương tiện.
- Cung cấp dashboard và báo cáo phục vụ công tác quản lý.

## 2. Chức năng dự kiến

### 2.1. Quản lý tài khoản
- Đăng nhập và đăng xuất.
- Quản lý thông tin người dùng.
- Phân quyền theo vai trò.
- Giới hạn quyền truy cập theo bãi xe được phân công.

### 2.2. Quản lý bãi đỗ xe
- Quản lý thông tin bãi đỗ xe.
- Quản lý cổng vào và cổng ra.
- Quản lý khu vực và vị trí đỗ xe.
- Theo dõi trạng thái các vị trí đỗ.
- Quản lý thiết bị tại các cổng.

### 2.3. Quản lý phương tiện và lượt gửi xe
- Ghi nhận thông tin xe vào bãi.
- Lưu biển số và hình ảnh phương tiện.
- Ghi nhận thời gian xe vào, xe ra.
- Tra cứu lịch sử gửi xe.
- Hỗ trợ điều chỉnh biển số khi hệ thống nhận diện chưa chính xác.

### 2.4. Nhận diện biển số xe
- Tiếp nhận hình ảnh từ camera hoặc nguồn ảnh thử nghiệm.
- Nhận diện biển số bằng mô hình AI.
- Lưu kết quả nhận diện và độ tin cậy.
- Cho phép nhân viên kiểm tra, xác nhận hoặc chỉnh sửa kết quả.

### 2.5. Quản lý phí và thanh toán
- Cấu hình bảng giá gửi xe.
- Tính phí dựa trên quy tắc được thiết lập.
- Ghi nhận giao dịch thanh toán.
- Theo dõi trạng thái thanh toán.
- Quản lý vé tháng và biển số đăng ký.

### 2.6. Dashboard và báo cáo
- Tổng hợp số lượng xe đang gửi.
- Thống kê lượt xe vào và ra.
- Theo dõi tình trạng vị trí đỗ.
- Tổng hợp doanh thu theo khoảng thời gian.
- Tra cứu lịch sử hoạt động và sự cố.

*Các chức năng trên là phạm vi dự kiến; trạng thái triển khai thực tế sẽ được cập nhật trong quá trình phát triển.*

## 3. Công nghệ sử dụng

| Thành phần | Công nghệ dự kiến | Vai trò |
|---|---|---|
| Frontend | React + TypeScript | Xây dựng giao diện website |
| Backend | Node.js + Express + TypeScript | Xử lý nghiệp vụ và cung cấp API |
| Cơ sở dữ liệu | PostgreSQL | Lưu trữ dữ liệu hệ thống |
| Nhận diện biển số | Python + mô hình AI có sẵn | Thử nghiệm nhận diện biển số xe |
| Quản lý mã nguồn | Git + GitHub | Theo dõi thay đổi và quản lý công việc |
| Phần cứng mô phỏng | ESP32 + servo | Thử nghiệm điều khiển barie |

**Lưu ý:** Công nghệ được liệt kê là lựa chọn dự kiến cho dự án. Cấu hình cuối cùng sẽ được cập nhật theo quá trình triển khai.

## 4. Kiến trúc hệ thống dự kiến

```text
Người dùng
    |
    v
Frontend: React + TypeScript
    |
    v
Backend API: Node.js + Express + TypeScript
    |
    +--------------------+
    |                    |
    v                    v
PostgreSQL          Dịch vụ nhận diện
Cơ sở dữ liệu       biển số bằng Python
    |
    v
Quản lý bãi xe, phương tiện,
lượt gửi xe, vị trí và thanh toán
```

Trong giai đoạn thử nghiệm, hệ thống có thể sử dụng hình ảnh có sẵn hoặc webcam. Việc kết nối camera chuyên dụng và điều khiển barie thực tế sẽ được xem xét sau khi các chức năng phần mềm cơ bản hoạt động ổn định.

## 5. Cơ sở dữ liệu

Cơ sở dữ liệu được thiết kế để quản lý các nhóm thông tin chính:

- Đơn vị vận hành và người dùng.
- Bãi đỗ xe, cổng và thiết bị.
- Sơ đồ bãi, khu vực và vị trí đỗ.
- Bảng giá và vé tháng.
- Lượt gửi xe và kết quả nhận diện biển số.
- Giao dịch thanh toán.
- Danh sách kiểm soát biển số.
- Sự cố và nhật ký hệ thống.

Thiết kế cơ sở dữ liệu sẽ tiếp tục được rà soát để bảo đảm khóa chính, khóa ngoại, ràng buộc dữ liệu và quy tắc nghiệp vụ phù hợp.

## 6. Cấu trúc repository

Cấu trúc thư mục dự kiến:

```text
smart-parking-management/
├── docs/                   # Tài liệu phân tích và thiết kế
│   ├── requirements/       # Yêu cầu chức năng và phi chức năng
│   ├── diagrams/           # Use Case, ERD và sơ đồ hệ thống
│   └── reports/            # Tài liệu và báo cáo đồ án
├── frontend/               # Mã nguồn React + TypeScript
├── backend/                # Mã nguồn Node.js + Express
├── alpr-service/           # Dịch vụ nhận diện biển số bằng Python
├── database/               # Thiết kế cơ sở dữ liệu và SQL
├── hardware/               # Tài liệu thử nghiệm ESP32 và barie
├── .gitignore
└── README.md
```

Đây là cấu trúc định hướng. Các thư mục sẽ được tạo khi bắt đầu triển khai từng phần.

## 7. Yêu cầu môi trường

Để phát triển hệ thống theo công nghệ dự kiến, môi trường làm việc cần có:

- Node.js và npm.
- PostgreSQL.
- Visual Studio Code hoặc trình soạn thảo tương đương.
- Git.
- Python cho dịch vụ nhận diện biển số.
- Trình duyệt web hiện đại.

Phiên bản cụ thể của các công cụ và thư viện sẽ được xác định khi khởi tạo dự án.

## 8. Hướng dẫn cài đặt

**Hiện tại dự án đang trong giai đoạn thiết lập.** Các bước dưới đây là quy trình dự kiến sau khi mã nguồn được tạo.

### Bước 1: Sao chép repository

```bash
git clone https://github.com/hodong440-droid/smart-parking-management.git
cd smart-parking-management
```

### Bước 2: Cài đặt frontend

Sau khi thư mục `frontend/` được khởi tạo:

```bash
cd frontend
npm install
```

### Bước 3: Cài đặt backend

Sau khi thư mục `backend/` được khởi tạo:

```bash
cd ../backend
npm install
```

### Bước 4: Cấu hình cơ sở dữ liệu

1. Cài đặt PostgreSQL.
2. Tạo cơ sở dữ liệu cho dự án.
3. Cấu hình thông tin kết nối trong file môi trường `.env`.
4. Chạy các tập lệnh tạo bảng và dữ liệu thử nghiệm khi chúng được hoàn thiện.

Không đưa mật khẩu, khóa bí mật hoặc thông tin kết nối nhạy cảm lên GitHub.

### Bước 5: Khởi chạy hệ thống

Lệnh chạy chính thức sẽ được bổ sung sau khi cấu hình frontend và backend hoàn tất.

## 9. Kế hoạch phát triển

| Giai đoạn | Nội dung | Trạng thái |
|---|---|---|
| 1 | Phân tích yêu cầu và xác định phạm vi | Đang hoàn thiện |
| 2 | Thiết kế cơ sở dữ liệu và ERD | Đang hoàn thiện |
| 3 | Khởi tạo frontend, backend và cơ sở dữ liệu | Chưa xác nhận hoàn thành |
| 4 | Xây dựng đăng nhập và phân quyền | Dự kiến |
| 5 | Xây dựng quản lý bãi xe và vị trí đỗ | Dự kiến |
| 6 | Xây dựng nghiệp vụ xe vào, xe ra và tính phí | Dự kiến |
| 7 | Tích hợp nhận diện biển số | Dự kiến |
| 8 | Hoàn thiện thanh toán, dashboard và báo cáo | Dự kiến |
| 9 | Kiểm thử, sửa lỗi và hoàn thiện báo cáo | Dự kiến |

Tiến độ sẽ được cập nhật theo các công việc thực tế trên GitHub Issues và Projects.

## 10. Quản lý công việc

Dự án sử dụng GitHub để:

- Quản lý mã nguồn bằng Git.
- Theo dõi công việc thông qua Issues.
- Quản lý tiến độ qua Projects.
- Ghi lại lịch sử thay đổi bằng commit.
- Lưu trữ tài liệu phân tích và thiết kế.
- Theo dõi lỗi và các chức năng cần bổ sung.

## 11. Thông tin dự án

- **Tên dự án:** Smart Parking Management System.
- **Tên tiếng Việt:** Hệ thống quản lý bãi đỗ xe thông minh.
- **Loại dự án:** Đồ án thực tập chuyên ngành Công nghệ thông tin.
- **Người thực hiện:** Hồ Sỹ Đông.
- **GitHub Repository:** [smart-parking-management](https://github.com/hodong440-droid/smart-parking-management).

## 12. Định hướng phát triển

Dự án hướng đến một hệ thống có thể hỗ trợ quản lý bãi đỗ xe một cách có tổ chức, giảm thao tác thủ công và tăng khả năng theo dõi phương tiện. Các tính năng AI và phần cứng sẽ được tích hợp từng bước, phù hợp với phạm vi và điều kiện triển khai của đồ án.
