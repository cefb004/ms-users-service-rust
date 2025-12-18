# Microstack Users Service (Rust)

A **Users microservice** for the **Microstack** platform, implemented in **Rust** as a RESTful CRUD API backed by **PostgreSQL**.

This service is responsible for managing user data and is designed to integrate seamlessly with the Microstack API Gateway.

---

## Ì∫Ä Features

* RESTful CRUD API for Users
* Built with **Rust** and **Axum** (async, high‚Äëperformance)
* PostgreSQL integration using **SQLx**
* Clean layered architecture (routes, handlers, models)
* Ready for API Gateway integration
* Designed for scalability and low latency

---

## Ì∑± Tech Stack

* **Language:** Rust (Edition 2021)
* **Web Framework:** Axum
* **Async Runtime:** Tokio
* **Database:** PostgreSQL
* **ORM / Driver:** SQLx (async)
* **Serialization:** Serde

---

## Ì≥Ç Project Structure

```text
ms-users-service-rust/
‚îú‚îÄ src/
‚îÇ  ‚îú‚îÄ main.rs        # Application entry point
‚îÇ  ‚îú‚îÄ routes.rs      # API route definitions
‚îÇ  ‚îú‚îÄ handlers.rs    # Request handlers (business logic)
‚îÇ  ‚îú‚îÄ models.rs      # Domain models and DTOs
‚îÇ  ‚îú‚îÄ db.rs          # Database connection pool
‚îÇ  ‚îî‚îÄ errors.rs      # Custom error handling
‚îú‚îÄ Cargo.toml        # Project dependencies and metadata
‚îú‚îÄ .env              # Environment variables (not committed)
‚îî‚îÄ README.md
```

---

## ‚öôÔ∏è Configuration

Create a `.env` file in the project root:

```env
DATABASE_URL=postgres://user:password@localhost/microstack_users
```

Make sure PostgreSQL is running and the database exists.

---

## Ì∑ÑÔ∏è Database Schema

Example `users` table:

```sql
CREATE TABLE users (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    name TEXT NOT NULL,
    email TEXT NOT NULL UNIQUE
);
```

---

## ‚ñ∂Ô∏è Running the Service Locally

```bash
cargo run
```

The service will start on:

```
http://localhost:8081
```

---

## Ì≥° API Endpoints

| Method | Endpoint    | Description       |
| ------ | ----------- | ----------------- |
| GET    | /users      | List all users    |
| POST   | /users      | Create a new user |
| GET    | /users/{id} | Get user by ID    |
| PUT    | /users/{id} | Update user       |
| DELETE | /users/{id} | Delete user       |

All endpoints use JSON for request and response bodies.

---

## Ì¥å Integration with Microstack Gateway

When integrated with the Microstack API Gateway, this service is typically exposed as:

```
/api/users ‚Üí ms-users-service-rust
```

The gateway handles routing, cross‚Äëcutting concerns, and frontend simplification.

---

## Ì∑™ Testing

You can test the endpoints using **Postman**, **curl**, or any HTTP client.

Example:

```bash
curl http://localhost:8081/users
```

---

## Ì≥à Future Improvements

* Request validation
* Structured logging
* Global error handling
* OpenAPI / Swagger documentation
* Authentication & authorization
* Dockerization
* Observability (metrics & tracing)

---

## Ì≥Ñ License

This project is part of the **Microstack** learning and experimentation ecosystem.

---

## ‚ú® Author

Developed as part of the Microstack architecture to explore **modern backend engineering with Rust**.

