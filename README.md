
# TSNO Docker-Compose

# Project focus
I created this project to quickly transfer snippets of text such as code segments from my phone to my university computer without any sign-ins. Unlike other services like Privnote, which require multiple confirmations and can feel laggy, this solution is faster, more modern, mobile-friendly, and completely ad-free.

## Overview
This repository contains a `docker-compose.yml` file that orchestrates the entire TSNO application:
- **Frontend (Next.js)**
- **Backend (.NET Core Web API + SQL Server)**
- **Database (SQL Server)**

![image](https://github.com/user-attachments/assets/f4ba380c-4f32-4b16-a52e-dfa8b7b06722)

By using Docker Compose, you can launch all services with a single command, simplifying development and deployment.

## Github repositories 
- **Frontend:** `(https://github.com/RazvanBordinc/TSNO-client)` 
- **Backend:** (`https://github.com/RazvanBordinc/TSNO-server`)

## What It Does
- **Single Command Startup:** A single `docker-compose up -d` command will start the frontend, backend, and database together.  
- **Shared Network:** All services run on a common Docker network, enabling the backend to communicate with the database and the frontend to access the backend.  
- **Pre-Configured Ports:** The frontend defaults to `http://localhost:3000` and the backend to `http://localhost:8080`.

## Running the Stack
**Prerequisites:**  
- Docker and Docker Compose installed.

**Start All Services:**
```bash
docker-compose up -d
```
**After the build, refresh the page at the given port, to make sure you get fresh data, not mockup data from the build**

- **Frontend**: http://localhost:3000
- **Backend**: http://localhost:8080

## Stop All Services:

```bash
docker-compose down
```
This stops and removes all the containers, but retains images and volumes unless otherwise specified.

## Customization
- Modify docker-compose.yml to change environment variables, ports, or image tags.
- Use a .env file to override default values if needed.

## Maintenance
- Update frontend and backend images by rebuilding and pushing them to Docker Hub.
- Re-run `docker-compose up -d` after `docker-compose pull` to fetch updated images.
