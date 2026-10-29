# TaskFlow API

A simple task management REST API built with Spring Boot. This is the sample project for the **Module 4 - End of Module Assignment**. Refer to the assignment instructions in **NTULearn** for the full list of tasks.

## Assignment submission

> [!IMPORTANT]
> **Submit your GitHub repository link to NTULearn.** This is the only thing you submit there - your live URL, screenshots and notes all go in this `README.md`.

## Christopher Teoh Repo Link
 - **Github:** https://github.com/xxopher/ntu-aie-m4-assignment

## Live Application
- **Live URL:** https://ntu-aie-m4-assignment.onrender.com/api/tasks
- **Platform:** Render (Web Service deployed via Docker)

## Deployment Screenshots
### Render Dashboard
![Render Dashboard](screenshots/Task%204%20-%20Render%20Dashboard%20Live.png)

### Live API Working
![Live Endpoint](screenshots/Task%204%20-%20Render%20Live%20Application%20Working.png)

## Overview & Implementation Notes
- Containerized the Spring Boot TaskFlow API using a multi-stage Docker build (`maven:3.9-eclipse-temurin-21` for build stage, `eclipse-temurin:21-jre-alpine` for production runtime).
- Deployed as a Docker web service on Render, exposed on port 8080.
- Verified live endpoint returning JSON task collection.



### Errors and failures

If you didn't complete every task, list what you completed, what went wrong, and the error messages you saw. If everything worked, write "None".

```
Completed: Task 1, Task 2

Error at Task 3:
<paste the error message here>
```

### Stretch goal (optional)

Which stretch goal you chose (if any), what you built, and any links (for example, your frontend URL, CI pipeline run or Docker Hub tags).

```
Stretch goal: <option number and name, or "None">
Links: <https://...>
Notes: <what you built and anything that didn't work>
```

## Getting started

### Prerequisites

- Java 21
- Maven (or use the included Maven Wrapper)

### Running the Application

From the project root:

```bash
./mvnw spring-boot:run
```

On Windows:

```bash
mvnw.cmd spring-boot:run
```

The application starts on `http://localhost:8080`.

### API Routes

| Method | Path              | Description             | Request Body | Success Response |
|--------|-------------------|--------------------------|---------------|-------------------|
| GET    | `/api/tasks`      | Get all tasks            | —             | `200 OK`          |
| GET    | `/api/tasks/{id}` | Get a single task by ID  | —             | `200 OK`          |
| POST   | `/api/tasks`      | Create a new task        | Task JSON     | `201 Created`     |

### Testing the API

Create a task:

```bash
curl -X POST http://localhost:8080/api/tasks \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Complete Module 3",
    "description": "Finish assignment",
    "priority": "HIGH",
    "dueDate": "2026-05-20",
    "completed": false
  }'
```

Get all tasks:

```bash
curl http://localhost:8080/api/tasks
```

Get a task by ID:

```bash
curl http://localhost:8080/api/tasks/1
```

### H2 Database Console

While the app is running, the H2 console is available at `http://localhost:8080/h2-console`.

Use the following connection settings:

- JDBC URL: `jdbc:h2:mem:taskflowdb`
- Username: `sa`
- Password: *(leave blank)*
# ntu-aie-m4-assignment
