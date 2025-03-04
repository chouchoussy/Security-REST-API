## Các API cần kiểm tra
- ``` /api/auth/register ``` (POST): Đăng ký người dùng.
- ``` /api/auth/login``` (POST): Đăng nhập để lấy token JWT.
- ``` /api/products``` (POST): Tạo sản phẩm (yêu cầu token, chỉ ADMIN).
- ``` /api/products``` (GET): Lấy danh sách sản phẩm (yêu cầu token, USER hoặc ADMIN).
- ``` /api/products/{id} ``` (PUT): Cập nhật sản phẩm (yêu cầu token, chỉ ADMIN).
- ``` /api/products/{id} ``` (DELETE): Xóa sản phẩm (yêu cầu token, chỉ ADMIN).

## Đăng ký người dùng (POST)
#### User
![image](https://github.com/user-attachments/assets/99f888c3-2594-4611-b4f5-be24632c5e6c)
#### Admin
![image](https://github.com/user-attachments/assets/899a986d-b536-462a-b4d8-1d62b1db37b4)

## Đăng nhập & Lấy token JWT (POST)
#### User 
![image](https://github.com/user-attachments/assets/df7b4001-3cb5-44bc-ba13-0edd89b6a829)
#### Admin
![image](https://github.com/user-attachments/assets/8f9d255c-716a-4c45-98be-c8879e15ea7b)

## Tạo sản phẩm (POST)
- Tạo sản phẩm yêu cầu token, chỉ admin có quyền.
#### User
###### Nhập với token của user đã lấy ở bước trước, không thành công (status 403) do user không có quyền. 
![image](https://github.com/user-attachments/assets/9fcc629b-667d-4d96-8efd-1f91f27c8e8a)

#### Admin
###### Nhập với token của admin đã lấy ở bước trước
  ![image](https://github.com/user-attachments/assets/eef9347d-6cc3-4b1c-a122-6d4177af43fe)
###### Tạo sản phẩm thành công, status 200 
![image](https://github.com/user-attachments/assets/ef6099bb-2679-4c49-8392-69134dbf2589)






