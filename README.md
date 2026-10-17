# Campus Connect

A full-stack social media platform built for campus communities. Students can create posts, follow each other, chat privately, build rich profiles with skills and interests, and discover people through search and smart recommendations.

This repository brings together the three Campus Connect projects in one place.

## Repository Structure

| Folder | What it contains |
|---|---|
| [`campus-connect-frontend/`](campus-connect-frontend/) | React web client (Create React App) |
| [`campus-connect-backend/`](campus-connect-backend/) | Spring Boot REST API with PostgreSQL |
| [`campus-connect/`](campus-connect/) | Full-stack project with Docker Compose, database scripts and deployment guides |

Each folder has its own README with detailed setup and deployment instructions.

## Features

- **Authentication** – secure registration and login
- **Posts & Feed** – create, edit and delete posts with images and videos
- **Follow System** – one-way follow model, similar to Twitter
- **Private Messaging** – real-time one-on-one chat with people you follow
- **Rich Profiles** – skills, interests, experience, education, projects, goals and social links
- **Search & Discovery** – search by name, skills, interests, college, semester or batch
- **Smart Recommendations** – match scoring based on profile similarity
- **Admin Panel** – user management and moderation tools
- **Responsive UI** – mobile-friendly, accessible design

## Tech Stack

**Frontend**

- React 18, React Router 6, Redux
- Axios for API calls
- Firebase for media storage

**Backend**

- Java 17, Spring Boot 3.1
- Spring Data JPA / Hibernate
- PostgreSQL with Flyway migrations
- Maven

**Infrastructure**

- Docker and Docker Compose
- Deployment configs for Render, Netlify, Vercel and Railway

## Getting Started

### Option 1: Docker (recommended)

Runs the database, backend and frontend together.

```bash
cd campus-connect
cp .env.docker .env        # edit values if needed
docker compose up --build
```

| Service | URL |
|---|---|
| Frontend | http://localhost:3000 |
| Backend API | http://localhost:8081 |
| PostgreSQL | localhost:5432 |

### Option 2: Run services manually

**Prerequisites:** Node.js 14+, Java JDK 17, Maven 3.6+ (or the included wrapper), PostgreSQL 12+

**1. Database**

```bash
psql -U postgres -c "CREATE DATABASE socialmedia_db;"
psql -U postgres -d socialmedia_db -f campus-connect/complete_setup.sql
```

**2. Backend**

```bash
cd campus-connect-backend
cp .env.example .env       # set DATA_SOURCE_URL, DATA_SOURCE_USER, DATA_SOURCE_PASSWORD
./mvnw spring-boot:run
```

The API starts on http://localhost:8081.

**3. Frontend**

```bash
cd campus-connect-frontend
cp .env.example .env       # set REACT_APP_API_URL and Firebase keys
npm install
npm start
```

The app opens at http://localhost:3000.

## Configuration

**Backend** (`campus-connect-backend/.env`)

| Variable | Purpose |
|---|---|
| `PORT` | Server port (default 8081) |
| `DATA_SOURCE_URL` | JDBC URL of the PostgreSQL database |
| `DATA_SOURCE_USER` / `DATA_SOURCE_PASSWORD` | Database credentials |
| `FRONTEND_URL` | Frontend origin used for links and CORS |
| `CORS_ALLOWED_ORIGINS` | Comma-separated list of allowed origins |

**Frontend** (`campus-connect-frontend/.env`)

| Variable | Purpose |
|---|---|
| `REACT_APP_API_URL` | Base URL of the backend API |
| `REACT_APP_FIREBASE_*` | Firebase project keys for media uploads |

## Deployment

Deployment guides live inside each project:

- [`campus-connect/PRODUCTION_DEPLOYMENT_GUIDE.md`](campus-connect/PRODUCTION_DEPLOYMENT_GUIDE.md) – full production walkthrough
- [`campus-connect/DOCKER_README.md`](campus-connect/DOCKER_README.md) – Docker details
- [`campus-connect-backend/DOCKER_DEPLOY_GUIDE.md`](campus-connect-backend/DOCKER_DEPLOY_GUIDE.md) – backend container deployment
- [`campus-connect-frontend/QUICK_DEPLOY.md`](campus-connect-frontend/QUICK_DEPLOY.md) – frontend hosting on Netlify or Vercel

## Credits

Original projects by [nikhilp9972](https://github.com/nikhilp9972):
[Campus-connect-frontend-](https://github.com/nikhilp9972-spec/campus-connect-) ·
[Campus-connect-backend-](https://github.com/nikhilp9972-spec/campus-connect-) ·
[Campus-Connect](https://github.com/nikhilp9972-spec/campus-connect-)
