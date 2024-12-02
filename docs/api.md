# API Documentation

Document your API endpoints, request formats, and responses.
Use tools like Swagger or Postman, or continue to write them in Markdown.

## Base URL

`https://api.example.com/v1`

## Authentication

- All requests must include a valid `Authorization: Bearer <token>` header.

### Endpoints

#### 1. User Authentication

| Method | Endpoint       | Description        | Request Body                   | Response                       |
|--------|----------------|--------------------|--------------------------------|--------------------------------|
| POST   | `/auth/login`  | User login         | `{ "email", "password" }`     | `{ "token": "JWT_TOKEN" }`    |
| POST   | `/auth/signup` | Register a user    | `{ "email", "password" }`     | `{ "message": "Success" }`    |

#### 2. Notes Management

| Method | Endpoint        | Description          | Request Body                  | Response                       |
|--------|-----------------|----------------------|--------------------------------|--------------------------------|
| GET    | `/notes`        | Fetch all notes      | None                          | `[ { "id": 1, "title": "" } ]`|
| POST   | `/notes`        | Create a new note    | `{ "title": "string" }`       | `{ "id": 1, "title": "" }`    |
