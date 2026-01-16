# JWT-Secured Microservices with Auth0

This project demonstrates a microservices architecture using .NET Core, JWT authentication via Auth0, and MS SQL Server database with Entity Framework migrations.

## Services

- **UserService**: Manages user data with CRUD operations.
- **ProductService**: Manages product data with CRUD operations.

## Technologies

- .NET 9
- ASP.NET Core Web API
- Entity Framework Core
- MS SQL Server
- Auth0 for JWT authentication
- Docker & Docker Compose

## Prerequisites

- .NET 9 SDK
- Docker & Docker Compose
- MS SQL Server (or use Docker container)
- Auth0 account and API configuration

## Setup

1. Clone the repository.
2. Configure Auth0:
   - Create an Auth0 application and API.
   - Update `appsettings.json` in each service with your Auth0 domain and audience.
3. Run with Docker:
   ```bash
   docker-compose up --build
   ```
   Services will be available at:
   - UserService: http://localhost:5002
   - ProductService: http://localhost:5003

## Database

The services use MS SQL Server. Migrations are included for code-first approach.

To run migrations manually:
```bash
cd src/Services/UserService/UserService
dotnet ef database update

cd ../../../ProductService/ProductService
dotnet ef database update
```

## Authentication

All services validate JWT tokens issued by Auth0. Endpoints require authorization.

### API Endpoints (Require JWT Authentication)

- **Users API**: http://localhost:5002/api/users
- **Products API**: http://localhost:5003/api/products

## Git Repository

This project is initialized as a Git repository. Push to your remote repository as needed.