# 🚀 Project 7 – Dockerized Nginx Reverse Proxy for Flask App on EC2

This project demonstrates how to containerize a Flask web application and serve it through an Nginx reverse proxy using Docker Compose.
It works both locally (Docker Desktop / WSL2) and on AWS EC2 with public IP access (e.g., http://16.16.123.122/).

---

## 📂 Project Structure
```
project7-nginx-flask-docker-ec2/
│
├── app/
│   ├── app.py # Flask app returning a greeting message
│   └── requirements.txt # Flask dependency
│
├── nginx/
│   └── default.conf # Nginx reverse proxy configuration
│
├── .gitignore
├── Dockerfile # Flask app container definition
├── docker-compose.yml # Multi-container setup (Flask + Nginx)
└── README.md # Project documentation
```
---

## 🛠 Prerequisites

Make sure you have:

- **Docker** installed  
- **Docker Compose** installed  
  - For v1: `docker-compose` (with dash)  
  - For v2: `docker compose` (no dash)  
- **Git** installed

---
### 🧠 What This Demonstrates

- 🚀 Flask app containerization  
- 🌐 Nginx reverse proxy setup in Docker  
- 🐳 Multi-container orchestration with Docker Compose  
- 🔀 Port mapping from Nginx (80) → Flask (5000)  
- ☁️ Works locally and on AWS EC2
---
```text
    ┌───────────┐
    │ Browser   │
    └─────┬─────┘
          │ HTTP:80
          ▼
┌─────────────────────┐
│ Nginx Reverse Proxy │
│ Container           │
│ Ports: 80 → 5000    │
│ (docker-compose)    │
└─────────┬───────────┘
          │ Forward to Flask
          ▼
┌─────────────────────┐
│ Flask App Container │
│ Port: 5000          │
│ Runs app.py         │
└─────────────────────┘
```
---
## 📦 Setup & Run

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/YOUR_GITHUB_USERNAME/project7-nginx-flask-docker-ec2.git
cd project7-nginx-flask-docker-ec2
```
### 2️⃣ Build & Start Containers
For Docker Compose v2 (most modern installs, including EC2):
```bash
docker compose up -d --build
```
For Docker Compose v1:
```
docker-compose up -d --build
```
### 3️⃣ Verify the Setup
Visit in browser:
```
http://localhost       # for local setup
http://<EC2-PUBLIC-IP> # for EC2
```
### 📸 Example Output
```
✅ Hello from Flask Docker App via Nginx!
```
### 📜 License
This project is licensed under the MIT License.

## 👤 Author
TaimoorDevOps
## 🔗 GitHub
https://github.com/taimoordevops/project7-nginx-flask-docker-ec2
