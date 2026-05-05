# Docker Compose Healthcheck Demo

This project demonstrates how to use **Docker Compose v2** with a **healthcheck**
to monitor the readiness of a Python Flask application running on **Amazon Linux 2023**.

The healthcheck allows Docker to determine whether the application is actually
working, not just whether the container is running.

---

## 🔧 Tech Stack

- **Language**: Python
- **Framework**: Flask
- **Containerization**: Docker
- **Orchestration**: Docker Compose v2
- **Base OS**: Amazon Linux 2023

---

## 📂 Project Structure

```md

.
├── Dockerfile
├── docker-compose.yml
├── app.py
└── README.md
---*

🐳 Docker Compose Healthcheck
The docker-compose.yml includes a healthcheck that periodically checks an HTTP endpoint exposed by the Flask application.
Example 
### Healthcheck Logic

- Docker sends HTTP requests to `/health`
- If the endpoint responds successfully → container is **healthy**
- If the endpoint fails → container is **unhealthy**


This is useful for:

Dependency readiness
Startup sequencing
Container monitoring
Production-style checks

---

🚀 How It Works

Flask app starts and exposes a /health endpoint
Docker Compose runs a healthcheck using curl
Docker updates container status:

starting
healthy
unhealthy



You can verify container health using:
Shelldocker psShow more lines

▶️ How to Run
1️⃣ Clone the repository
Shellgit clone https://github.com/suprajagollapalli-lang/docker-compose-healthcheck.gitcd docker-compose-healthcheckShow more lines

2️⃣ Build and start the application
Shelldocker compose up --buildShow more lines

3️⃣ Check container health
Shelldocker ps``Show more lines
You should see:
Plain TextSTATUS:healthy)Show more lines

🔍 Healthcheck Endpoint
The Flask app exposes:
Plain TextGET /healthShow more lines
Expected response:
Plain Text{  "status": "ok"Show more lines
This endpoint is used by Docker Compose to determine container health.
---

✅ Why Healthchecks Matter
Without a healthcheck:

Docker only knows if the container process is running

With a healthcheck:

Docker knows if the application inside the container is actually ready

This is critical for:

Microservices
CI/CD pipelines
Real-world production deployments

---

🧠 Key Learnings

Difference between container running vs container healthy
Using Docker Compose healthchecks effectively
Running containerized Flask apps on Amazon Linux 2023
Writing production‑style Docker configurations

---

👤 Author
Supraja Gollapalli
Hands-on Docker & DevOps learning project.
---

📌 Notes

This project is designed for learning and demonstration purposes
Works well on low-resource environments like AWS free-tier instances

