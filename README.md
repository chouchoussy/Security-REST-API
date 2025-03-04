# GIỚI THIỆU
## Giới thiệu chung
Dự án **Security REST API** là một ứng dụng Spring Boot cung cấp các REST API cơ bản (GET, POST, PUT, DELETE) để quản lý sản phẩm (`Product`). Ứng dụng sử dụng **JWT (JSON Web Token)** để quản lý phân quyền người dùng với hai vai trò: `USER` (chỉ có quyền GET) và `ADMIN` (quyền truy cập đầy đủ).

## Công nghệ sử dụng
- **Spring Boot**: 3.2.3
- **Spring Security**: Bảo mật và xác thực JWT
- **Spring Data JPA**: Quản lý cơ sở dữ liệu
- **H2 Database**: Cơ sở dữ liệu in-memory
- **JWT**: io.jsonwebtoken (jjwt-api 0.11.5)
- **Java**: 17
- **Maven**: Quản lý dependency
- **Phần mềm POSTMAN**: Có thể sử dụng extension tại VSCODE

## Chạy ứng dụng 
1. Cách 1: Sử dụng Maven:
   ```
   ./mvnw spring-boot:run
   ```
2. Cách 2: Sử dụng file jar
  ```
    java -jar target/securing-web-initial-0.0.1-SNAPSHOT.jar
  ```
- Ứng dụng sẽ khởi động tại ``` http://localhost:8080 ```
- Sau đó, sử dụng ``` POSTMAN ``` để chạy demo các API như demo bên dưới. 


# DEMO 
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

## Xem sản phẩm (GET)
- Cả user và admin đều có quyền xem sản phẩm
#### User 
![image](https://github.com/user-attachments/assets/1045dda6-cc8a-4d47-9997-0859d387b4df)

#### Admin 
![image](https://github.com/user-attachments/assets/94d0645a-a37e-49d8-8d18-3c820b4c6fc3)

## Cập nhật sản phẩm (PUT)
#### User 
###### Nhập với token của user đã lấy ở bước trước, không thành công (status 403) do user không có quyền. 
![image](https://github.com/user-attachments/assets/d3ff596f-f42d-40b6-b6b0-075ae5b9fe28)

#### Admin 
###### Nhập với token của admin đã lấy ở bước trước
![image](https://github.com/user-attachments/assets/14b7f956-03f6-4ae7-b692-34d2ede9d321)

###### Cập nhật sản phẩm thành công, Body trả về thông tin sản phẩm đó sau khi cập nhật, Status 200 ok. 
![image](https://github.com/user-attachments/assets/210a1b85-6da3-4e99-a933-9a8a8389b86c)

## Xóa sản phẩm (DELETE)
#### User 
###### Nhập với token đã lấy ở trước, xóa sản phẩm không thành công do user không có quyền, status trả về 403. 
![image](https://github.com/user-attachments/assets/c7cb2688-a96f-42d3-a1c3-7bcc002b71fe)

#### Admin
###### Nhập với token admin đã lấy ở trước, xóa sản phẩm thành công, status trả về 204 No Content. 
![image](https://github.com/user-attachments/assets/8f51c4c1-9124-4a11-a4a0-e3a9fada22fa)









