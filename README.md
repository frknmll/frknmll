<h1 align="center">Hi 👋, I'm Furkan</h1>
<h3 align="center">"Junior Web Developer with hands-on experience in full-stack development (C#, .NET Core, Ruby on Rails, and front-end technologies like HTML, CSS, JavaScript, Bootstrap). Passionate about building responsive, user-friendly applications and continuously learning modern frameworks such as React."</h3>

- 🔭 I’m currently working on: [mimakademi](https://akademim.org/) & [TalQuick](https://furkanmolla.me)
- 🌐 Portfolio / Demo: https://furkanmolla.me
- 💬 Want to learn more: .NET, Docker, REST APIs, Postgres, React

---

## 🚀 TalQuick Overview

TalQuick; kimlik doğrulama, gerçek zamanlı (SignalR planlı) grup mesajlaşması ve rol bazlı genişlemeye uygun bir tam‑stack öğrenme / deneme projesi.

### 🧱 Stack
- Backend: ASP.NET Core 8 (RESTful Web API), Entity Framework Core (Code First Migrations)
- DB: PostgreSQL 17 (Docker)
- Frontend: React + TypeScript + Vite (Dev: 5173, Prod: static build / 3000)
- Auth: JWT (HMAC-SHA512), stateless
- Containerization: Docker Compose (ayrı dev & base dosyaları)
- Config: .env + environment overrides + appsettings.* merge
- Future: SignalR hubs (chat), role-based authorization

### 📦 Core Features (şu an)
- User Registration / Login (JWT üretimi)
- Profile endpoint (kullanıcı kimliği + ileride role)
- Group & GroupMessages tabloları (migration’larla hazır)
- Dynamic runtime frontend config (public/config.js build anında üretiliyor)
- Otomatik DB migrasyon uygulama (startup retry + healthcheck ile)

### 🌐 Example API Calls
```bash
# Register
curl -X POST http://localhost:5063/api/user/register \
  -H "Content-Type: application/json" \
  -d '{"username":"demo","email":"demo@example.com","password":"Test123!"}'

# Login
curl -X POST http://localhost:5063/api/user/login \
  -H "Content-Type: application/json" \
  -d '{"email":"demo@example.com","password":"Test123!"}'

# Profile
curl -H "Authorization: Bearer <JWT>" http://localhost:5063/api/user/profile
```


### 🧩 Architecture (simplified)
```
[ React (Vite Dev Server) ] --> HTTP (JWT) --> [ ASP.NET Core API ]
                                          │
                                          └--> [ PostgreSQL ]
```

### ✅ Roadmap (short)
- Add role claim into JWT
- Real-time SignalR group chat
- Refresh tokens / revoke
- Audit logging & metrics
- Admin management endpoints

---

## 🛠 Languages & Tools
<p align="left">
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/csharp/csharp-original.svg" width="40"/>
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/dot-net/dot-net-original-wordmark.svg" width="40"/>
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original.svg" width="40"/>
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original.svg" width="40"/>
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" width="40"/>
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" width="40"/>
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original.svg" width="40"/>
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg" width="40"/>
</p>

## 🔗 Connect
- LinkedIn: https://linkedin.com/in/frknmll
