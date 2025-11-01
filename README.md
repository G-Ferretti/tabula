# Tabula Project

This repository wraps the **Tabula Front-End** (Angular) and **Tabula Back-End** (API) projects as Git submodules, providing an easy one-command build and run workflow using **Docker Compose**.

---

## 🧩 Project Structure
```
tabula/
├── tabula-back-end/      # Back-end API 
├── tabula-front-end/     # Angular front-end (served via Nginx)
├── docker-compose.yml    # Defines and runs both services
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the repository (with submodules)
Make sure you clone recursively so both submodules are included:

```bash
  git clone --recurse-submodules https://github.com/G-Ferretti/tabula.git
  cd tabula
```

### 2. Build and run with Docker Compose
The `docker-compose.yml` file will build both the front-end and back-end images.

```bash
  docker compose build
  docker compose up
```

Once running:
- Front-end (Angular) → [http://localhost:4200](http://localhost:4200)
- Back-end (Swagger UI) → [http://localhost:8080/swagger-ui/index.html](http://localhost:8080/swagger-ui/index.html)

---

### 3. Stopping the app
To stop all containers:
```bash
  docker compose down
```

---

## 🧱 Troubleshooting
| Issue | Fix                                                                                    |
|-------|----------------------------------------------------------------------------------------|
| Submodules missing | `git submodule update --init --recursive`                                              |
| 405 errors from API | Check Nginx proxy in `tabula-front-end/nginx.conf`                                     |
| Backend unreachable | Ensure `proxy_pass` in Nginx points to the correct service name (e.g., `backend:8080`) |
| Build fails | Make sure Docker Desktop or the Docker daemon is running                               |

---

## 🧰 Requirements
- [Git](https://git-scm.com/)
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

---
