# URL Shortener in Go with Fiber, Redis & Docker

A simple, high-performance URL shortening service built with **Go**, **Fiber** web framework, **Redis** as a fast key-value store, and **Docker** for easy deployment.

---

## 📦 Features

- Shorten long URLs into compact, shareable links.
- Retrieve original URLs via shortened codes.
- Redis for ultra-fast in-memory data storage.
- Dockerized for easy deployment and scalability.
- Fiber framework for lightweight, blazing-fast API.

---

## 🔧 Tech Stack

- **Go (Golang)** — main programming language.
- **Fiber** — web framework inspired by Express.js.
- **Redis** — key-value store to persist URLs.
- **Docker** — containerization of the app.
- **Docker Compose** — orchestrates the Go API and Redis.

---

## 📁 Project Structure

URL_Shortner/ 
├── api/ # Go API service 
    ├── routes/ # Route handlers (ShortenURL, ResolveURL) 
    ├── helpers/ # Utility functions (random strings, validations) 
    ├── database/ # Creating Client Connection 
    ├── main.go # Entry point 
    ├── go.mod 
    / go.sum # Go modules 
    ├── db/ # Dockerfile for Redis 
    ├── .env # Environment variables 
    ├── docker-compose.yml # Compose file for services

*******yaml**********

    ### 1️⃣ Clone the repository

```bash
git clone https://github.com/Raghavendra-S-I/URL_Shortner.git
cd URL_Shortner

******* Set up .env file*********

APP_PORT=:3000
REDIS_ADDR=redis:6379
API_DOMAIN=http://localhost:3000

Note: Ensure APP_PORT matches the port exposed in Docker.

******Run the app with Docker**********

docker-compose up --build



📮 API Endpoints
🔹 Shorten URL
POST  /api/v1

Body (JSON):

json:
{
  "url": "https://www.google.com"
}
Response:

json
{
  "shortened_url": "http://localhost:3000/abc123"
}
🔹 Redirect URL
GET /:shortURL

Visit in browser:

bash
http://localhost:3000/abc123
You’ll be redirected to the original long URL.

🛠️ Dev Commands
Run locally without Docker
bash

go run main.go
Make sure Redis is running at localhost:6379.

🧼 Cleanup
Stop and remove all Docker containers:

bash

docker-compose down