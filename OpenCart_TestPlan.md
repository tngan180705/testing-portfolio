# 📋 Test Plan & Test Scenarios: OPENCART E-COMMERCE

- **Dự án**: Kiểm thử hệ thống thương mại điện tử OpenCart
- **Website thực hiện**: https://demo.opencart.com/
- **Người thực hiện**: Nguyễn Thanh Thiên Ngân

---

## Phần 1: Kế hoạch kiểm thử (TEST PLAN)

### 1. Mục tiêu kiểm thử (Objective)

- **Giới thiệu**: OpenCart là nền tảng thương mại điện tử phục vụ người dùng tìm kiếm, lựa chọn sản phẩm và thanh toán trực tuyến.
- **Mục tiêu**: Đảm bảo luồng trải nghiệm mua sắm cốt lõi (từ lúc tạo tài khoản đến khi thanh toán thành công) hoạt động chính xác, ổn định, dữ liệu đồng nhất và không có lỗi nghiêm trọng (Blocker/Critical).

### 2. Phạm vi kiểm thử (Scope)

- **In-Scope (Phân hệ kiểm thử)**:
  - Phân hệ Tài khoản: Đăng ký & Đăng nhập (Register & Login).
  - Phân hệ Sản phẩm: Tìm kiếm sản phẩm (Search).
  - Phân hệ Mua hàng: Giỏ hàng (Shopping Cart) & Đặt hàng/Thanh toán (Checkout).
- **Out-of-Scope (Chưa kiểm thử đợt này)**:
  - Các trang liên quan đến quản trị viên (Admin Portal / Backend).
  - Tích hợp cổng thanh toán thẻ ngân hàng trực tiếp (Live Credit Card Gateway).

### 3. Chiến lược kiểm thử (Test Strategy)

- **Phương pháp tiếp cận**: Black-box Testing (Kiểm thử hộp đen).
- **Các loại kiểm thử áp dụng**:
  - Functional Testing: Kiểm thử chức năng (bao gồm Positive & Negative cases).
  - UI/Usability Testing: Kiểm thử độ thân thiện của giao diện trang web theo 10 nguyên lý Heuristics.
  - Cross-browser Testing: Kiểm thử độ tương thích trên Google Chrome và Microsoft Edge.

### 4. Tiêu chí Bắt đầu & Kết thúc (Entry & Exit Criteria)

- **Entry Criteria (Bắt đầu khi)**:
  - Môi trường kiểm thử của web OpenCart hoạt động ổn định.
  - Kế hoạch kiểm thử và danh sách Test Scenarios được hoàn thiện và phê duyệt.
- **Exit Criteria (Kết thúc khi)**:
  - Tất cả (100%) Test Case được thực thi.
  - Tỷ lệ Test Case đạt (Pass rate) từ 95% trở lên.
  - Không có lỗi ở mức độ Blocker hoặc Critical tồn đọng trong hệ thống.

### 5. Môi trường & Công cụ kiểm thử (Environment & Tools)

- **Thiết bị**: Laptop Windows 11.
- **Trình duyệt**: Google Chrome (v128+), Microsoft Edge.
- **Công cụ hỗ trợ**:
  - Chrome DevTools (bắt lỗi Network status code và Console).
  - Git / GitHub (quản lý tài liệu kiểm thử).

---

## Phần 2: Bảng 20 TEST SCENARIOS cho các phân hệ

### 🔹 Module 1: Đăng ký tài khoản (Registration)

| Scenario ID   | Module   | Mô tả kịch bản kiểm thử (Scenario Description)                                                              | Test Type |
| :------------ | :------- | :---------------------------------------------------------------------------------------------------------- | :-------- |
| **TS_REG_01** | Register | Đăng ký tài khoản thành công với các thông tin hợp lệ và tích chọn đồng ý điều khoản Privacy Policy         | Positive  |
| **TS_REG_02** | Register | Đăng ký tài khoản không thành công với các thông tin hợp lệ nhưng không tích chọn điều khoản Privacy Policy | Negative  |
| **TS_REG_03** | Register | Đăng ký không thành công khi nhập Email đã được đăng ký trước đó trong hệ thống                             | Negative  |
| **TS_REG_04** | Register | Đăng ký không thành công khi bỏ trống một trong các ô bắt buộc                                              | Negative  |

### 🔹 Module 2: Đăng nhập (Login)

| Scenario ID   | Module | Mô tả kịch bản kiểm thử (Scenario Description)                              | Test Type |
| :------------ | :----- | :-------------------------------------------------------------------------- | :-------- |
| **TS_LOG_01** | Login  | Đăng nhập thành công với Email và Password chính xác đã đăng ký             | Positive  |
| **TS_LOG_02** | Login  | Đăng nhập không thành công khi Email chưa từng được đăng ký trong hệ thống  | Negative  |
| **TS_LOG_03** | Login  | Đăng nhập không thành công khi nhập sai Password so với Password đã đăng ký | Negative  |
| **TS_LOG_04** | Login  | Đăng nhập không thành công khi để trống trường E-mail Address               | Negative  |

### 🔹 Module 3: Tìm kiếm sản phẩm (Search)

| Scenario ID   | Module | Mô tả kịch bản kiểm thử (Scenario Description)                                                | Test Type |
| :------------ | :----- | :-------------------------------------------------------------------------------------------- | :-------- |
| **TS_SRH_01** | Search | Tìm kiếm sản phẩm thành công với từ khóa chính xác có tồn tại trong hệ thống (VD: "MacBook")  | Positive  |
| **TS_SRH_02** | Search | Tìm kiếm sản phẩm không thành công khi nhập từ khóa không tồn tại (VD: "xyz123")              | Negative  |
| **TS_SRH_03** | Search | Kiểm tra phản hồi của hệ thống khi để trống ô tìm kiếm và bấm nút Search / Enter              | Negative  |
| **TS_SRH_04** | Search | Kiểm tra tìm kiếm nâng cao theo danh mục (Category filter) hoặc tìm trong phần mô tả sản phẩm | Positive  |

### 🔹 Module 4: Giỏ hàng (Shopping Cart)

| Scenario ID   | Module | Mô tả kịch bản kiểm thử (Scenario Description)                                                        | Test Type           |
| :------------ | :----- | :---------------------------------------------------------------------------------------------------- | :------------------ |
| **TS_CRT_01** | Cart   | Kiểm tra thêm sản phẩm vào giỏ hàng thành công từ trang chi tiết sản phẩm                             | Positive            |
| **TS_CRT_02** | Cart   | Kiểm tra tăng/giảm số lượng sản phẩm trong giỏ hàng và kiểm tra hệ thống tính lại tổng tiền chính xác | Positive            |
| **TS_CRT_03** | Cart   | Kiểm tra thao tác xóa sản phẩm thành công ở trang giỏ hàng                                            | Positive            |
| **TS_CRT_04** | Cart   | Kiểm tra áp dụng mã giảm giá (Coupon Code) hợp lệ và không hợp lệ                                     | Positive / Negative |

### 🔹 Module 5: Thanh toán & Đặt hàng (Checkout)

| Scenario ID   | Module   | Mô tả kịch bản kiểm thử (Scenario Description)                                                              | Test Type |
| :------------ | :------- | :---------------------------------------------------------------------------------------------------------- | :-------- |
| **TS_CHK_01** | Checkout | Kiểm tra hoàn tất quy trình thanh toán thành công với tài khoản đã đăng nhập (End-to-End flow)              | Positive  |
| **TS_CHK_02** | Checkout | Kiểm tra phản hồi của hệ thống khi người dùng không nhập các trường địa chỉ bắt buộc (như address, city,..) | Negative  |
| **TS_CHK_03** | Checkout | Kiểm tra chọn phương thức vận chuyển và phương thức thanh toán                                              | Positive  |
| **TS_CHK_04** | Checkout | Kiểm tra phản hồi hiển thị của hệ thống khi hoàn tất đặt hàng thành công                                    | Positive  |
