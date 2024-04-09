# FastAPI Authentication Application

This application is a simple authentication system built with FastAPI. It uses JSON Web Tokens (JWT) for authentication and bcrypt for password hashing.

## Features

- User authentication with JWT
- Password hashing with bcrypt
- Endpoints for user login and fetching user data

## How to Run

1. Install the required Python packages:

```
pip install fastapi uvicorn python-jose[cryptography] passlib[bcrypt] pydantic
```

2. Run the application:

```
uvicorn main:app --reload
```

Replace main with the name of your Python file.

## Endpoints

- `POST /token`: Authenticate a user and return an access token. The request body should be a form with username and password fields.
- `GET /users/me/`: Return the authenticated user's data.
- `GET /users/me/items`: Return a list of items owned by the authenticated user.

## Security

The application uses the HS256 algorithm for JWT. The secret key for JWT is stored in the `SECRET_KEY` variable. The access token expires after 30 minutes.

Passwords are hashed using bcrypt. The hashed password for the user "tim" is stored in the `db` dictionary.

## Note

This is a simple application for demonstration purposes. In a real-world application, you should store user data in a database and manage secret keys securely.
