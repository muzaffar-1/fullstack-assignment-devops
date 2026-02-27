# 🚀 Full-Stack DevOps Deployment
This project is a fully containerized full-stack application deployed on AWS EC2 using a CI/CD pipeline via GitHub Actions.

## 🛠️ Tech Stack & Infrastructure
* **Cloud Provider:** AWS (EC2 T2.Micro)
* **Containerization:** Docker & Docker Compose
* **CI/CD:** GitHub Actions
* **Backend:** Django (Uvicorn ASGI)
* **Frontend:** React / Next.js

---

## 📡 Deployment Configuration
The application is configured to run in a production environment with the following networking setup:

| Service | Public URL | Internal Port |
| :--- | :--- | :--- |
| **Frontend** | http://54.165.243.216:3000 | 3000 |
| **Backend API** | http://54.165.243.216:8000 | 8000 |

### Key Environment Variables
* **ALLOWED_HOSTS**: Set to 54.165.243.216 to permit secure AWS traffic.
* **NEXT_PUBLIC_API_URL**: Points the frontend to the backend API on port 8000.
* **DJANGO_SECRET_KEY**: Secured for production runtime.

---

## 📊 Monitoring & Maintenance Strategy

### 1. Real-time Log Monitoring
Used to debug connectivity and application errors during deployment:
`docker compose logs -f`

### 2. Resource Observability
Manual health checks are performed to monitor CPU and Memory usage:
`docker stats`

### 3. Proposed Production Monitoring
* **Infrastructure:** AWS CloudWatch for instance-level hardware metrics.
* **Metrics:** Prometheus & Grafana for container performance visualization.
* **Error Tracking:** Sentry for real-time exception handling.

---

## 🔧 Troubleshooting Log
* **Issue:** DisallowedHost error on backend.
  * **Fix:** Updated ALLOWED_HOSTS in docker-compose.yml to include the AWS IP.
* **Issue:** Frontend 404 error on /login.
  * **Fix:** Corrected the NEXT_PUBLIC_API_URL to point to port 8000.
