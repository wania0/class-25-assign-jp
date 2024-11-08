# Job Fair Application API Documentation

## Authentication 

### Login

**POST /auth/login**  
Description: Authenticates the users (Employer or Job Seeker) and returns a token for access.  

**Request:**

```json
{
  "username": "string",
  "password": "string"
}

**Response:**

```json
{
  "message": "logged in successfully",
  "token": "string"
}

