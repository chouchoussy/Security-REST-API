## Các API cần kiểm tra
- ``` /api/auth/register ``` (POST): Đăng ký người dùng.
- ``` /api/auth/login``` (POST): Đăng nhập để lấy token JWT.
- ``` /api/products``` (GET): Lấy danh sách sản phẩm (yêu cầu token, USER hoặc ADMIN).
- ``` /api/products``` (POST): Tạo sản phẩm (yêu cầu token, chỉ ADMIN).
- ``` /api/products/{id} ``` (PUT): Cập nhật sản phẩm (yêu cầu token, chỉ ADMIN).
- ``` /api/products/{id} ``` (DELETE): Xóa sản phẩm (yêu cầu token, chỉ ADMIN).
