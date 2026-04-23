#  Inventory Service

A production-ready **Inventory Management Microservice** built with **Spring Boot**, **PostgreSQL**, and fully containerized using **Docker**. This project demonstrates modern backend development practices including RESTful APIs, containerization, and CI/CD readiness.

---

##  Overview

The **Inventory Service** provides a scalable and maintainable backend system for managing inventory items. It supports full CRUD operations and is designed to be easily deployable using Docker.

This project is ideal for:

* Learning microservice architecture fundamentals
* Demonstrating DevOps and containerization skills
* Serving as a backend foundation for full-stack applications

---

##  Tech Stack

| Layer      | Technology              |
| ---------- | ----------------------- |
| Backend    | Spring Boot (Java 17)   |
| Database   | PostgreSQL              |
| Build Tool | Maven                   |
| Container  | Docker & Docker Compose |
| API Style  | RESTful                 |

---

##  Project Structure

```
inventory-service/
├── src/
│   ├── main/
│   │   ├── java/... (controllers, services, repositories, entities)
│   │   └── resources/
│   │       └── application.properties
├── Dockerfile
├── docker-compose.yml
├── pom.xml
└── README.md
```

---

##  Getting Started

###  Prerequisites

* Docker installed and running
* Git installed

---

##  Run with Docker (Recommended)

### 1. Clone the repository

```bash
git clone https://github.com/cengiztansel/inventory-service.git
cd inventory-service
```

---

### 2. Start the application

```bash
docker compose up -d --build
```

---

### 3. Access the service

```
http://localhost:8080
```

---

##  Database Configuration

Default PostgreSQL settings:

| Property | Value        |
| -------- | ------------ |
| Database | inventory_db |
| User     | postgres     |
| Password | postgres     |
| Port     | 5432         |

These can be configured in:

* `docker-compose.yml`
* `application.properties`

---

## 📡 API Endpoints

| Method | Endpoint       | Description          |
| ------ | -------------- | -------------------- |
| GET    | /products      | Retrieve all items   |
| GET    | /products/{id} | Get item by ID       |
| POST   | /products      | Create new item      |
| PUT    | /products/{id} | Update existing item |
| DELETE | /products/{id} | Delete item          |

---

##  Run Without Docker

### Build the project

```bash
mvn clean package
```

### Run the application

```bash
java -jar target/inventory-service.jar
```

---

##  Docker Details

### Build image manually

```bash
docker build -t inventory-service:1.0 .
```

### Run container

```bash
docker run -p 8080:8080 inventory-service:1.0
```

---

##  Using Prebuilt Image (GHCR)

If published, you can run directly:

```bash
docker pull ghcr.io/cengiztansel/inventory-service:latest
docker run -p 8080:8080 ghcr.io/cengiztansel/inventory-service:latest
```

---

##  Development Workflow

```bash
git add .
git commit -m "feature/update"
git push
```

If CI/CD is configured:

* Image is built automatically
* Pushed to container registry
* Ready for deployment

---

##  Common Issues

### Port already in use

```bash
sudo lsof -i :8080
```

Or change port in `docker-compose.yml`.

---

### Container fails to start

```bash
docker logs <container_id>
```

---

### Reset environment

```bash
docker compose down -v
docker system prune -a
```

---

##  Future Improvements

* JWT Authentication & Authorization
* Pagination & Filtering
* Swagger / OpenAPI Documentation
* CI/CD with GitHub Actions
* Kubernetes Deployment
* Monitoring (Prometheus & Grafana)
* Logging (ELK Stack)

---

##  Author

**Tansel**
Backend Development • DevOps • Microservices

---

##  License

This project is licensed under the MIT License.

---

##  Final Note

This project is not just a CRUD application—it represents a **real-world backend service setup** 
with containerization and deployment readiness. It can be extended into a full production system 
or integrated into larger architectures.
