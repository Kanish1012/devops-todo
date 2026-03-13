# DevOps Todo App (MERN + Docker + CI/CD)

A full-stack **MERN Todo application** with a **complete DevOps pipeline** using **Docker, GitHub Actions CI/CD, and AWS EC2 deployment**.

This project demonstrates how to build, containerize, test, and automatically deploy a MERN application using modern DevOps practices.

---

## Project Architecture

```
User
  │
  ▼
Frontend (React)
  │
  ▼
Backend (Node.js + Express)
  │
  ▼
MongoDB
```

All services are containerized using **Docker Compose**.

---

## Tech Stack

### Frontend

* React
* Axios

### Backend

* Node.js
* Express
* MongoDB

### Database

* MongoDB

### DevOps

* Docker
* Docker Compose
* GitHub Actions (CI/CD)
* AWS EC2
* SSH Deployment

---

## Repository Structure

```
devops-todo
│
├── backend
│   ├── controllers
│   ├── models
│   ├── routes
│   ├── seedTasksData.js
│   └── server.js
│
├── frontend
│   ├── src
│   └── public
│
├── docker-compose.yml
├── Dockerfile
│
└── .github
    └── workflows
        ├── ci.yaml
        └── cd.yaml
```

---

## Features

* Full MERN stack Todo application
* Dockerized services
* MongoDB database container
* Automated CI pipeline
* Automated CD pipeline
* EC2 deployment via SSH
* Container orchestration using Docker Compose

---

## CI Pipeline

The CI workflow runs automatically on push to `main`.

Steps:

1. Checkout repository
2. Setup Node.js
3. Start MongoDB service
4. Install backend dependencies
5. Seed database
6. Run backend tests

Workflow location:

```
.github/workflows/ci.yaml
```

---

## CD Pipeline

The CD workflow deploys the application to **AWS EC2**.

Steps:

1. SSH into EC2
2. Pull latest code
3. Stop existing containers
4. Rebuild Docker images
5. Restart services

Workflow location:

```
.github/workflows/cd.yaml
```

Deployment commands executed on server:

```
docker compose down
docker compose up -d --build
```

---

## Running Locally

Clone the repository

```
git clone https://github.com/Kanish1012/devops-todo.git
cd devops-todo
```

Run with Docker

```
docker compose up --build
```

Application will run at:

```
http://localhost:3000
```

---

## Environment Variables

Backend requires the following environment variables:

```
PORT=
MONGO_URI=
JWT_SECRET=
```

For CI/CD deployment, these are stored securely in **GitHub Secrets**.

---

## Deployment

The application is deployed on **AWS EC2** using GitHub Actions.

Deployment flow:

```
Developer pushes code
        │
        ▼
GitHub Actions CI runs tests
        │
        ▼
CD workflow triggers
        │
        ▼
SSH into EC2
        │
        ▼
Docker containers rebuilt
        │
        ▼
Application updated
```

---

## Future Improvements

* Add frontend tests
* Add Kubernetes deployment
* Add monitoring (Prometheus + Grafana)
* Add Nginx reverse proxy
* Add HTTPS with Let's Encrypt

---

## Author

Kanish

GitHub:
https://github.com/Kanish1012
