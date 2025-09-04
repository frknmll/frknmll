<h1 align="center">Hi 👋, I'm Furkan</h1>
<h3 align="center">"Junior Web Developer with hands-on experience in full-stack development (C#, .NET Core, Ruby on Rails, and front-end technologies like HTML, CSS, JavaScript, Bootstrap). Passionate about building responsive, user-friendly applications and continuously learning modern frameworks such as React."</h3>

- 🔭 I’m currently working on: [mimakademi](https://akademim.org/) & [TalQuick](https://furkanmolla.me)
- 💬 Want to learn more: .NET, Docker, REST APIs, Postgres, React
- ## 🔗 Connect
- LinkedIn: https://linkedin.com/in/frknmll

---

## 🚀 TalQuick Overview
TalQuick; kimlik doğrulama, gerçek zamanlı (SignalR planlı) grup mesajlaşması ve rol bazlı genişlemeye uygun bir full‑stack öğrenme / deneme projesi.

### 🧱 Stack
- Backend: ASP.NET Core 8 (RESTful Web API), Entity Framework Core (Code First Migrations)
- DB: PostgreSQL 17 (Docker)
- Frontend: React + TypeScript + Vite (Dev: 5173, Prod: static build / 3000)
- Auth: JWT (HMAC-SHA512), stateless
- Containerization: Docker Compose (base + dev override)
- Config: .env / .env.development + appsettings.* merge
- Future: SignalR hubs, role-based authorization

### 📦 Core Features (current)
- User registration / login (JWT)
- Profile endpoint
- Group & GroupMessages schema
- Auto DB migrations on startup (retry + healthcheck)
- Runtime frontend config injection (public/config.js)

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

### ⚙️ CI/CD & Deployment (Auto Deploy)
- Platform: GitHub Actions (main branch trigger + optional manual dispatch)
- Stages:
  1. Checkout & cache (Node + NuGet)
  2. Backend: dotnet restore, build, test
  3. Frontend: npm ci, build (Vite)
  4. Docker build (multi-stage): backend + frontend production images
  5. Push images to registry (e.g. ghcr.io or Docker Hub)
  6. Remote deploy: SSH (or GitHub Actions runner) → `docker compose pull && docker compose up -d`
  7. Post-deploy smoke check: `curl /api/user/profile` (unauthorized expected 401)
- Database migrations: applied automatically on backend container start (no manual `dotnet ef` in pipeline)
- Secrets: supplied via repository secrets (JWT key, DB password, registry credentials)
- Backups (optional job):
  - Uses `scripts/backup.Dockerfile` (pg_dump client only)
  - Cron (scheduled workflow) → run container → `pg_dump > timestamped.sql.gz` → upload artifact / push to object storage
- Rollback: redeploy previous image tag (pipeline keeps last N tags)

(If pipeline repo differs or registry not configured yet, this section acts as implementation spec.)

---

## 🛠 Languages & Tools
<p align="left">
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" width="40"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" width="40"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/rails/rails-original-wordmark.svg" width="40"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/csharp/csharp-original.svg" width="40"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/dot-net/dot-net-original-wordmark.svg" width="40"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original.svg" width="40"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original.svg" width="40"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" width="40"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" width="40"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original.svg" width="40"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg" width="40"/>
</p>
