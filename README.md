# Project-3 Microservices

A microservices architecture with API Gateway and multiple services.

## Architecture

```
Frontend (Port 3000)
       ↓
API Gateway (Port 8080)
       ↓
┌─────────────────────────────────────┐
│  Auth Service (Port 3001)           │
│  User Service (Port 3002)           │
│  Notes Service (Port 3003)          │
│  Tags Service (Port 3004)           │
└─────────────────────────────────────┘
       ↓
PostgreSQL Database (Port 5432)
```

## Services

- **API Gateway** (8080): Routes requests to microservices, handles authentication
- **Auth Service** (3001): User authentication, JWT tokens, registration/login
- **User Service** (3002): User management and profiles
- **Notes Service** (3003): Notes management
- **Tags Service** (3004): Tags and categorization
- **PostgreSQL**: Database for all services

## Quick Start with Docker

### Prerequisites

- Docker and Docker Compose installed
- Node.js 18+ (for local development)

### Development Setup

1. **Clone and navigate to project:**

   ```bash
   git clone <repository-url>
   cd Project-3
   ```

2. **Create environment file:**

   ```bash
   cp .env.example .env
   ```

3. **Start all services:**

   ```bash
   docker-compose up -d
   ```

4. **Initialize database:**
   ```bash
   # Run Prisma migrations
   docker-compose exec auth-service npm run db:migrate
   ```

## Available Endpoints

- **API Gateway**: http://localhost:8080
- **Auth Service**: http://localhost:3001
- **Database**: localhost:5432

## Development Commands

```bash
# Start all services
docker-compose up -d

# View logs
docker-compose logs -f

# Stop services
docker-compose down
```
