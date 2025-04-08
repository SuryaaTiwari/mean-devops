# MEAN DevOps Project 🚀

A full-stack MEAN (MongoDB, Express, Angular, Node.js) application integrated with Docker, Jenkins CI/CD, and GitHub.

---

## 🔧 Project Structure

mean-devops/ ├── backend/ # Node.js + Express REST API ├── frontend/ # Angular app served via Nginx │ └── frontend-app/ # Angular source code ├── mongo/ # MongoDB database (via Docker) ├── docker-compose.yml # Multi-container setup ├── Jenkinsfile # Jenkins pipeline definition └── README.md # This file

yaml
Copy
Edit

---

## 🐳 Dockerized Setup

Make sure Docker and Docker Compose are installed.

Some Plugin and Additional Credentials Needs to be added in Jenkins:
Credentials: global
:Dockerhub account and id:dockerhub
git:github username and token which is generated from github

Plugins:
JDK  : Give its path also  and same name as the you provide in jenkinsfile
MAVEN
NODEJS
BUILD TIMESTAMP
PIPELINE UTILITY STEPS
PIPELINE MAVEN INTEGRATION
CLOUD BEES DOCKER 
GIT 
GITHUB




### Run the full stack:

```bash
docker-compose up --build -d
Frontend: http://localhost:4200

Backend: http://localhost:3000

MongoDB: localhost:27017

⚙️ CI/CD Pipeline with Jenkins
Jenkinsfile Highlights:
Pulls code from GitHub

Builds Docker images

Starts services via Docker Compose

Optional test stages

Jenkins runs this pipeline automatically on each push to main/master.

📦 Backend API
Built with Express.js

Connects to MongoDB via Mongoose

Runs on port 3000

Sample Route:
http
Copy
Edit
GET /api/posts
🌐 Frontend
Built with Angular

Compiled app is served via Nginx (port 4200)

To develop Angular manually:

bash
Copy
Edit
cd frontend/frontend-app
npm install
ng serve

