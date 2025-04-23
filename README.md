# MoJ Task Manager – Backend API

This is a Spring Boot backend. It provides a REST API for managing tasks assigned to caseworkers.

## Features

- Create, retrieve, update, and delete tasks
- Update task status individually
- In-memory H2 database for easy setup
- Input validation and error handling
- Unit test for controller

## Technologies Used

- Java 17
- Spring Boot
- Spring Data JPA
- H2 Database
- Jakarta Validation
- Maven

## Getting Started

### Prerequisites

- Java 17+
- Maven (or use the included `mvnw` wrapper)

### Running the App

```bash
./mvnw spring-boot:run
```

The server will start on [http://localhost:8080](http://localhost:8080)

## API Endpoints

| Method | Endpoint                   | Description                  |
|--------|----------------------------|------------------------------|
| POST   | `/api/tasks`               | Create a new task            |
| GET    | `/api/tasks`               | Retrieve all tasks           |
| GET    | `/api/tasks/{id}`          | Retrieve a task by ID        |
| PATCH  | `/api/tasks/{id}/status`   | Update status of a task      |
| DELETE | `/api/tasks/{id}`          | Delete a task                |

### Example Request (Create Task)

```http
POST /api/tasks
Content-Type: application/json

{
  "title": "Submit report",
  "description": "Submit Q2 caseworker report",
  "status": "TODO",
  "dueDateTime": "2025-04-30T12:00:00"
}
```

## H2 Console

- URL: [http://localhost:8080/h2-console](http://localhost:8080/h2-console)
- JDBC URL: `jdbc:h2:mem:tasksdb`
- User: `sa`
- Password: *(leave blank)*

## Running Tests

```bash
./mvnw test
```
There is currently 1 unit test to cover the creation of a new task. More would be added in a full implementation.
## Notes

- The database is in-memory and resets on restart
- See frontend repo for a UI to interact with this API
