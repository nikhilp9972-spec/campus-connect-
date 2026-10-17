# CampusConnect Backend - Spring Boot API

Social media platform backend built with Java Spring Boot, featuring posts, followers, and real-time messaging.

## 🚀 Features

### Core Features

- **User Authentication** - Secure login and registration
- **Posts & Feed** - Create, edit, delete posts with media
- **Follow System** - One-way follow model (like Twitter)
- **Private Messaging** - Real-time chat with followers
- **User Profiles** - Customizable profiles with college info
- **Admin Panel** - User management and moderation

### Technical Features

- RESTful API architecture
- PostgreSQL database with Flyway migrations
- JPA/Hibernate ORM
- CORS configuration
- Input validation
- Error handling

## 🛠️ Tech Stack

- **Java** 17
- **Spring Boot** 2.7+
- **Spring Data JPA**
- **PostgreSQL** 12+
- **Flyway** (database migrations)
- **Maven** (build tool)

## 🚂 Quick Deploy to Railway (5 minutes)

See **[RAILWAY_DEPLOY.md](RAILWAY_DEPLOY.md)** for detailed Railway deployment instructions.

### Quick Steps:

1. Push code to GitHub
2. Connect to Railway
3. Add PostgreSQL database
4. Deploy automatically
5. Get your live URL!

**Free Tier:** 500 hours/month, 500MB database

## Installation and Setup

1. Clone the repository: git clone https://github.com/AkshunChauhan/CampusConnect.git
2. Navigate to the project directory: cd Front-end
3. Install dependencies: npm install
4. Navigate to the project backend: cd.., cd Back-end
5. Update application.properties: mysql username and password
6. To create database uncomment this line in application.properties: spring.jpa.hibernate.ddl-auto = create-drop
7. Start the Spring Boot application: spring-boot:run
8. Access the application at http://localhost:8081 in your web browser.

## Dont forget to give it a star.

## 📋 Prerequisites

- Java JDK 17 or higher
- Maven 3.6+
- PostgreSQL 12+
- Git

## 🔧 Local Development Setup

### 1. Clone Repository

```bash
git clone https://github.com/nikhilp9972-spec/campus-connect-.git
cd Campus-connect-backend-
```

### 2. Configure Database

Create PostgreSQL database:

```sql
CREATE DATABASE campusconnect;
```

Update `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/campusconnect
spring.datasource.username=your_username
spring.datasource.password=your_password
```

### 3. Build and Run

```bash
# Install dependencies and build
mvn clean install

# Run application
mvn spring-boot:run
```

Server starts at: `http://localhost:8081`

## 📁 Project Structure

```
src/
├── main/
│   ├── java/com/socialmediaweb/socialmediaweb/
│   │   ├── controller/      # REST API endpoints
│   │   ├── service/         # Business logic
│   │   ├── repository/      # Database access
│   │   ├── entities/        # JPA entities
│   │   └── dto/            # Data transfer objects
│   └── resources/
│       ├── application.properties
│       └── db/migration/    # Flyway migrations
└── test/
```

## 🔌 API Endpoints

### Authentication

- `POST /createuser` - Register new user
- `POST /login` - User login

### Posts

- `GET /feed` - Get all posts
- `POST /createpost` - Create post
- `PUT /updatepost` - Update post
- `DELETE /deletepost/{id}` - Delete post

### Follow System

- `POST /api/follow` - Follow user
- `DELETE /api/follow` - Unfollow user
- `GET /api/follow/followers/{userId}` - Get followers
- `GET /api/follow/following/{userId}` - Get following

### Messaging

- `GET /api/chats` - Get user's chats
- `POST /api/chats/{chatId}/messages` - Send message
- `GET /api/chats/{chatId}/messages` - Get messages

## 🗄️ Database Migrations

Flyway automatically runs migrations on startup:

- `V1__create_follows_table.sql` - Follow relationships
- `V2__create_chat_tables.sql` - Chat and messages

## ⚙️ Configuration

### Environment Variables

```properties
DATABASE_URL=postgresql://user:pass@host:5432/dbname
PORT=8080
CORS_ORIGINS=http://localhost:3000
```

## 🚀 Deployment

See **[RAILWAY_DEPLOY.md](RAILWAY_DEPLOY.md)** for Railway deployment guide.

## ⭐ Don't forget to give it a star!
