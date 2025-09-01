🦀 **Rust CRUD API with PostgreSQL**

A fast, minimalist CRUD (Create, Read, Update, Delete) API built in pure Rust no frameworks, just raw performance and control. This project demonstrates low-level HTTP handling, PostgreSQL integration and containerized deployment using Docker Compose.

Built to showcase deep Rust proficiency in networking, database interaction and system design.

✨ **Key Features**

⚡ High Performance
Written in Rust for speed, memory safety and concurrency.

🧱 No Framework
Uses std::net::TcpListener for direct HTTP handling.

🗃️ PostgreSQL Integration
Connects via the postgres crate for reliable data storage and retrieval.

🐳 Containerized Deployment
Fully Dockerized with docker-compose for isolated, reproducible environments.

🖼️ **Screenshots**

### Postman
![Postman Post Request](./assets/Rust%20Crud%20Api%20Post%20Request.png)
![Postman Put Request](./assets/Rust%20Crud%20Api%20Put%20Request.png)
![Postman Delete Request](./assets/Rust%20Crud%20Api%20Delete%20Request.png)
![Postman Get One Request](./assets/Rust%20Crud%20Api%20Get%20One%20Request.png)
![Postman Get All Request](./assets/Rust%20Crud%20Api%20Get%20All%20Request.png)

### Terminal
![Postgres Terminal Request](./assets/Rust%20Crud%20Api%20Postgres%20Request.png)

🚀 **Getting Started**
✅ *Prerequisites*
    - Docker and Docker Compose

🛠️ *Setup Instructions*
- Clone the Repository

    bash
    git clone <repository-url>
    cd <repository-name>

- Build & Run with Docker Compose

    bash
    docker compose up --build

    This will:

    Build the Rust API container

    Start the PostgreSQL database

    Expose the API at http://localhost:8080

📂 **API Endpoints**
This RESTful API manages users. You can interact using curl, Postman or any HTTP client.

🔸 Create a User
Method: POST

Endpoint: /users

    Body:

    json
    {
    "name": "John Doe",
    "email": "john.doe@example.com"
    }

    Example:

    bash
    curl -X POST -H "Content-Type: application/json" \
    -d '{"name":"Jane Smith","email":"jane.smith@example.com"}' \
    http://localhost:8080/users

🔹 Get All Users
Method: GET

Endpoint: /users

    Example:

    bash
    curl http://localhost:8080/users

🔹 Get a Single User
Method: GET

Endpoint: /users/{id}

    Example:

    bash
    curl http://localhost:8080/users/
    
🔸 Update a User
Method: PUT

Endpoint: /users/{id}

    Body:

    json
    {
    "name": "Jane Doe",
    "email": "jane.doe.updated@example.com"
    }
    Example:

    bash
    curl -X PUT -H "Content-Type: application/json" \
    -d '{"name":"Jane Doe","email":"jane.doe@example.com"}' \
    http://localhost:8080/users/1

🔸 Delete a User
Method: DELETE

Endpoint: /users/{id}

    Example:

    bash
    curl -X DELETE http://localhost:8080/users/1

🐳 **Docker & Project Structure**

📦 Dockerfile
Multi-stage build for a compact final image.

Compiles Rust app and packages it into a self-contained container.

📦 docker-compose.yml
Defines two services:

rustapp: The Rust API, exposed on port 8080/.

db: PostgreSQL container, networked with rustapp.
