# SecureOnboard – Angular + Spring Boot Login Module

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

### 🧪 Test Credentials

• Admin• Username: admin
• Password: admin123
• Role: ROLE_ADMIN

• User• Username: user
• Password: user123
• Role: ROLE_USER

---

### 📌 Next Modules

This repository is designed to evolve into a full-featured admin portal for secure API onboarding and operational control. Upcoming modules include:

• 🔐 Admin Dashboard• Role-based landing page
• Summary cards for retry logs, stale data, and onboarded APIs
• Sidebar navigation and modular routing

• 🔁 Retry & Stale Table Views• Paginated table of failed API calls
• Manual retry trigger with status feedback
• Stale record detection and cleanup logic

• 🚀 API Onboarding & Access Management• Form-based onboarding of new APIs (name, endpoint, auth type)
• Toggle access control (enable/disable)
• Audit logging and role-based visibility

• 📊 Metrics & Monitoring (Optional)• API usage charts
• Success/failure trends
• Integration with Prometheus/Grafana or custom dashboards



Each module will follow the same principles of modularity, security, and recruiter-facing clarity.

---

### 🧠 Author

Purnendu Shankar
Java Integration Lead | FinTech Modernization Expert
Architecting secure, modular solutions for scalable enterprise platforms

---


## 🚀 Setup Instructions


```bash
# Backend (Spring Boot)
cd springboot-backend
./mvnw spring-boot:run

# Frontend (Angular)
cd angular-frontend
npm install
ng serve```

---
