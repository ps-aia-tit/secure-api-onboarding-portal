# secure-api-onboarding-portal  -SecureOnboard – Angular + Spring Boot Login Module

A modular full-stack POC showcasing secure login, JWT authentication, and role-based access control using Angular and Spring Boot. This is the foundational module for a larger admin dashboard that will manage API onboarding, retry logic, and stale data views.

---

## 🔐 Features

- JWT-based login authentication
- Role-based routing (`ROLE_ADMIN`, `ROLE_USER`)
- Angular route guards and interceptors
- Spring Security configuration
- Modular folder structure for scalability

---

## 🧱 Tech Stack

- **Frontend:** Angular 17
- **Backend:** Spring Boot 3.x
- **Security:** JWT + Spring Security
- **Database:** H2 (in-memory) or PostgreSQL
- **DevOps (optional):** Docker + GitHub Actions

---

## 📁 Folder Structure

### Angular (Frontend)

- `angular-frontend/src/app/`
  - `auth/`
    - `login/`
    - `auth.service.ts`
    - `auth.guard.ts`
  - `shared/`
    - `jwt.interceptor.ts`
  - `app.module.ts`

### Spring Boot (Backend)

- `springboot-backend/src/main/java/com/aiatit/`
  - `controller/`
    - `AuthController.java`
  - `service/`
    - `AuthService.java`
  - `model/`
    - `User.java`
  - `repository/`
    - `UserRepository.java`
  - `config/`
    - `SecurityConfig.java`
    - `JwtUtil.java`

---

## 🚀 Setup Instructions

### Backend

```bash
cd springboot-backend
./mvnw spring-boot:run
