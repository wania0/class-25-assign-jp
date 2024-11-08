# Job Fair Application API Documentation

POST /auth/login
Description: This API Authenticates the users (Employer or Job Seeker) and returns a token for access.
Request:
{
  "username": "string",
  "password": "string"
}
Response:
{
  "message": "logged in successfully",
  "token": "string"
}

Signup
POST /auth/signup
Description: Registers new users(Employer or Job Seeker).
Request (Employer):
{
  "role": "employer",
  "company_name": "string",
  "email": "string",
  "password": "string",
  "company_description": "string"
}
Request (Job Seeker):
{
  "role": "job_seeker",
  "name": "string",
  "email": "string",
  "password": "string",
}
Response:
{
  "message": "Registration successful"
}


Employer 
POST /employer/jobs
Description: Employer can create job posting.
Request:
{
  "job_title": "string",
  "description": "string",
  "required_skills": ["string"],
  "salary_range": "string",
  "status": "enabled"
}
Response:
{
  "message": "Jobpost created successfully"
}

GET /employer/jobs
Description: Lists all job posts created by the employer.
Response:
{
  "jobs": [
    {
      "job_id": "integer",
      "job_title": "string",
      "description": "string",
      "status": "enabled",
      "required_skills": ["string"],
      "salary_range": "string",
      "created_at": "datetime"
    }
  ]
}

GET /employer/jobs/{job_id}/applications
Description: Retrieves applications for a specific job post.
Response:

{
  "applications": [
    {
      "id": "integer",
      "name": "string",
      "contact_info": "string",
      "cv": "file",
      "status": "pending"
    }
  ]
}

Job Seeker
GET /jobs
Description: Lists available job posts.
Response:
{
  "jobs": [
    {
      "job_id": "integer",
      "title": "string",
      "company_name": "string",
      "description": "string",
      "required_skills": ["string"],
      "salary_range": "string"
    }
  ]
}

PUT: employer/{post_id}/application/{id}/status
Request:{
    "stauts": (0,1,2)
}
Response: {
"application approved/rejected etc"
}
POST /jobseeker/application
Description: Creates a application.
Request:
{
      "job_seeker_name": "string",
      "contact_info": "string",
      "cv": "file",
      "status": "pending"
    }
Response:
{
  "status": "application created successfully"
}

GET : jobseeker/job_seeker_id/status
Description : Show the status of specific job seeker
Response :
{
"approved, rejected, or hired"
}
GET : admin/approved_job_seeker
Description : Show all approved job seekers to the admin
Response: {
"list of approved job seeker"
}

