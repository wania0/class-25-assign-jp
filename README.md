# Job Fair Application API

## Authentication and User Management

### Login

**POST /auth/login**  
Description: Authenticates the users (Employer or Job Seeker) and returns a token for access.  

**Request:**

```json
{
  "username": "string",
  "password": "string"
}
