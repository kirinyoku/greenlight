# Greenlight

Greenlight is a JSON API for searching and managing movie information, inspired by the Open Movie Database API. This project was developed while following along with Alex Edwards' book [Advanced Patterns for Building APIs and Web Applications in Go](https://lets-go-further.alexedwards.net). The goal of this project is to provide a hands-on learning experience for building robust and scalable web applications in Go.

## Project Overview

The Greenlight API allows users to perform CRUD operations on movie records, manage user accounts, and handle authentication and authorization. The API is built with best practices in mind, including input validation, secure authentication, and structured logging.

### Endpoints

The following is a list of supported endpoints and their actions:

| Method | URL Pattern                      | Action                                               |
|--------|----------------------------------|------------------------------------------------------|
| GET    | `/v1/healthcheck`                | Show application health and version information      |
| GET    | `/v1/movies`                     | Show the details of all movies                       |
| POST   | `/v1/movies`                     | Create a new movie                                   |
| GET    | `/v1/movies/:id`                 | Show the details of a specific movie                 |
| PATCH  | `/v1/movies/:id`                 | Update the details of a specific movie               |
| DELETE | `/v1/movies/:id`                 | Delete a specific movie                              |
| POST   | `/v1/users`                      | Register a new user                                  |
| PUT    | `/v1/users/activated`            | Activate a specific user                             |
| PUT    | `/v1/users/password`             | Update the password for a specific user              |
| POST   | `/v1/tokens/authentication`      | Generate a new authentication token                  |
| POST   | `/v1/tokens/password-reset`      | Generate a new password-reset token                  |
| GET    | `/debug/vars`                    | Display application metrics                          |

## How to Use

To get started with the Greenlight API:

1. **Clone the Repository**

```bash
git clone https://github.com/kirinyoku/greenlight.git
```
2. **Set Up Environment Variables**

You'll need to configure environment variables for the database connection. Example variables are stored in the .envrc-example file. Copy this file to .envrc and fill in the required values.

```bash
cd greenlight
cp .envrc-example .envrc
```
3. **Install Dependencies, Build, and Run**

Use the Makefile to manage the project. The Makefile includes commands for installing dependencies, building the application, and running it.

```bash
make vendor
make build/api
make run/api
```
4. **Access the API**

Once the server is running, the API will be available at http://localhost:4000. You can interact with it using tools like curl, Postman, or any HTTP client. Refer to the list of available endpoints for actions such as viewing, creating, updating, and deleting movie records.

```bash
curl http://localhost:4000/v1/healthcheck
```
