# 3-Tier Containerized Application

A 3-tier web application deployed on AWS EC2 using Docker Compose, with Nginx frontend, Flask/Gunicorn backend, and MySQL database.

## Architecture

Browser
   |
   v
Nginx (Frontend :8080)
   |
   v
Flask + Gunicorn (Backend :5000)
   |
   v
MySQL (Database)

## Technology Stack

- Docker
- Docker Compose
- Linux / Ubuntu
- Python / Flask
- Gunicorn
- MySQL

## Services

- Frontend: Nginx serving the web interface
- Backend: Flask application running with Gunicorn
- Database: MySQL 8.0
- Networking: Docker bridge network

## Features
- Containerized frontend, backend, and database
- Nginx reverse proxy for backend API requests
- MySQL persistent storage using Docker volumes
- Docker healthcheck for MySQL


## Application Flow

1. User accesses the application through the EC2 public IP.
2. Nginx serves the frontend application.
3. Nginx forwards /api/ requests to the Flask backend.
4. Flask connects to MySQL through the Docker network.
5. MySQL returns data to the backend.
6. The backend response is displayed in the browser.

## API Endpoints

- GET /api/ → Backend status
- GET /api/users → Retrieve users from MySQL

## Environment Configuration

The application uses environment variables for database configuration.
Create a `.env` file in the project root directory.
Store database credentials in `.env` and keep the file excluded from Git using `.gitignore`.

## Run the Application

Clone the repository and move into the project directory.
Create the `.env` file with the required database environment variables.
Build and start all services using Docker Compose.

docker compose up --build -d

Check running containers with `docker compose ps`.

## Project Structure

- `frontend/` - Nginx frontend application
- `backend/` - Flask/Gunicorn backend application
- `database/` - MySQL initialization files
- `docker-compose.yml` - Multi-container orchestration
- `README.md` - Project documentation

## Git Workflow

Development was managed using feature branches, pull requests, and merges into the main branch.
The project includes separate feature branches for MySQL integration and Nginx reverse proxy implementation.
Current release: `v1.0.0`
