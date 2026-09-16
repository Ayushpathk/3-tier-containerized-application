# 3-Tier Containerized Application

A 3-tier web application deployed using Docker Compose on AWS EC2 Ubuntu.

## Architecture

Frontend (Nginx) -> Backend (Flask/Gunicorn) -> MySQL Database

## Technologies

- Docker
- Docker Compose
- Python Flask
- Gunicorn
- MySQL 8.0
- Nginx
- Linux / Ubuntu
- AWS EC2
- Git & GitHub

## Features

- 3-tier containerized architecture
- Custom Docker bridge network
- Persistent MySQL storage using Docker volume
- Environment-based database configuration
- MySQL healthcheck
- Backend health endpoint
- REST API for retrieving users
- Gunicorn production WSGI server

## API Endpoints

- GET /health - Backend health check
- GET /users - Retrieve users from MySQL

## Run

Create a .env file with the required database variables, then run: docker compose up -d --build

## Security

Database credentials are stored in .env, which is excluded from Git. MySQL port 3306 is not exposed publicly.
