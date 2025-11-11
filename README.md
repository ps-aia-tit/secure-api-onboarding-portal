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

## 🔐 SecureOnboard Vulnerability Guide — 

---


| #  | Vulnerability                  | Interview Question                                      | SecureOnboard Answer                                                                                                                                                       |
|----|-------------------------------|----------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | SQL Injection                 | How did you prevent SQL injection in SecureOnboard?      | We used Spring Data JPA with parameterized queries for onboarding workflows and validated inputs using Hibernate Validator. Legacy JDBC calls were refactored to use `PreparedStatement`. |
| 2  | Broken Authentication         | How did you secure authentication in SecureOnboard?      | Spring Security was integrated with BCrypt password encoding and JWT-based stateless authentication. Role-based access was enforced for onboarding stages using `@PreAuthorize`. |
| 3  | Sensitive Data Exposure       | How did you protect onboarding data in transit and at rest? | HTTPS and TLS 1.2+ were enforced. Personally identifiable information (PII) was encrypted using JCE, and onboarding logs were sanitized to mask sensitive fields. |
| 4  | Security Misconfiguration     | What misconfigurations did you fix in SecureOnboard?     | Actuator endpoints were restricted using Spring Security, `/env` was disabled, and headers like `X-Frame-Options` and `Content-Security-Policy` were added to harden onboarding APIs. |
| 5  | Outdated Dependencies         | How did you manage vulnerable dependencies in SecureOnboard? | Snyk and OWASP Dependency-Check were integrated into CI/CD. We migrated from Spring Boot 2.3 to 3.x and used BOM to lock safe versions across onboarding modules. |
| 6  | Cross-Site Scripting (XSS)    | How did you prevent XSS in SecureOnboard’s UI?           | Thymeleaf’s auto-escaping was used for onboarding forms, and inputs were sanitized using OWASP HTML Sanitizer. CSP headers restricted script sources. |
| 7  | Cross-Site Request Forgery    | How did you handle CSRF protection in SecureOnboard?     | CSRF tokens were enabled for onboarding web flows. For REST APIs, CSRF was disabled and JWT was used. Exceptions were documented for frontend integration. |
| 8  | Insecure Deserialization      | How did you mitigate deserialization risks in onboarding? | Java serialization was replaced with JSON and payloads were validated using Jackson. Deserialization was disabled for untrusted sources to prevent remote code execution. |
| 9  | Improper Logging & Error Handling | How did you improve logging in SecureOnboard?             | Logback was configured with custom converters to mask sensitive onboarding data. Stack traces were suppressed in production and logs were centralized with RBAC. |
| 10 | Unvalidated Redirects         | How did you prevent open redirects in SecureOnboard?     | Dynamic redirects were replaced with `RedirectView` and URLs were validated against a whitelist to prevent abuse during onboarding transitions. |


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
