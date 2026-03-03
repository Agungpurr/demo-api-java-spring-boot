# Demo API - Spring Boot REST API

REST API sederhana menggunakan **Spring Boot**, **Spring Security**, dan **Spring Data JPA** dengan autentikasi **HTTP Basic** dan enkripsi password menggunakan **BCrypt**.

## 🚀 Tech Stack

- Java 17+
- Spring Boot
- Spring Security
- Spring Data JPA
- Hibernate
- MySQL / H2 (sesuaikan dengan config)
- Maven

---

## 📁 Project Structure
src/main/java/com/domain
│
├── controllers # REST Controller
├── services # Business Logic
├── models # Entity / Model
├── dto # Data Transfer Object
├── security # Security Configuration
├── helpers / utils # Utility class


---

## 🔐 Authentication

Project ini menggunakan:

- **HTTP Basic Authentication**
- Password di-hash menggunakan **BCryptPasswordEncoder**
- Endpoint register bisa diakses tanpa login

Contoh konfigurasi security:

```java
.requestMatchers("/api/users/register").permitAll()
.anyRequest().authenticated()

⚙️ Setup & Installation
1️⃣ Clone Repository
git clone https://github.com/username/demo-api.git
cd demo-api
2️⃣ Konfigurasi Database

Edit file:

src/main/resources/application.properties

Contoh konfigurasi MySQL:

spring.datasource.url=jdbc:mysql://localhost:3306/demo_db
spring.datasource.username=root
spring.datasource.password=yourpassword

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect

Jika menggunakan H2:

spring.datasource.url=jdbc:h2:mem:testdb
spring.h2.console.enabled=true

3️⃣ Run Application

Menggunakan Maven:

mvn spring-boot:run

Atau:

./mvnw spring-boot:run

Aplikasi akan berjalan di:

http://localhost:8080

📌 API Endpoints
✅ Register User (Public)
POST /api/users/register

Request Body:

{
  "username": "agung",
  "password": "123456"
}
🔒 Endpoint Lain (Protected)

Semua endpoint selain /register membutuhkan Basic Auth.

Gunakan Authorization:

Authorization: Basic base64(username:password)

Atau langsung via Postman:

Type: Basic Auth

Username: agung

Password: 123456

🧠 Fitur

CRUD API

Spring Security Configuration terbaru (SecurityFilterChain)

DaoAuthenticationProvider

BCrypt Password Encoding

Layered Architecture (Controller → Service → Repository)

🛠 Future Improvement

Implement JWT Authentication

Role-based Authorization (ADMIN / USER)

Swagger Documentation

Unit Testing

Docker Support

👨‍💻 Author

Agung Purnomo
Backend Developer (Spring Boot)
