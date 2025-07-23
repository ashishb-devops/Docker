# A MERN stack application 

This directory contains a Docker Compose configuration for a full‑stack MERN (MongoDB, Express, React, Node.js) application.

## 📁 Folder Structure

```text
mern/
├── backend/        # Express + Node API server
├── frontend/       # React frontend app
└── docker-compose.yml
```

## 🚀 Getting Started

## Prerequisites

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

&nbsp;



## 🔧 Run the application

From the `mern/` folder, run:

`docker-compose up --build`

- ⭐ Builds and starts 3 containers: frontend, backend, MongoDB.
- 🌐 Frontend: http://localhost:3000 (or port configured)
- 🛠 Backend API: http://localhost:5050 (or configured port)
- 🗄 MongoDB: accessible at mongodb://mongo:27017

  
&nbsp;


## 🧱 Docker Compose Overview

The docker-compose.yml defines:
- frontend: builds the React client container
- backend: builds the Express.js API server
- mongo: runs a MongoDB container using the official image

All services are networked together for seamless communication.



&nbsp;


## Instructions

### Create a network for the docker containers

`docker network create mern`

### Build the client 

```sh
cd mern/frontend
docker build -t mern-frontend .
```

### Run the client

`docker run --name=frontend --network=demo -d -p 5173:5173 mern-frontend`

### Verify the client is running

Open your browser and type `http://localhost:5173`

### Run the mongodb container

`docker run --network=demo --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongodb:latest`

### Build the server

```sh
cd mern/backend
docker build -t mern-backend .
```

### Run the server

`docker run --name=backend --network=demo -d -p 5050:5050 mern-backend`

### Using Docker Compose

`docker compose up -d`

