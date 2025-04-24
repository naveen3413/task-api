# Task API

A simple RESTful API for creating and retrieving tasks with status filtering, built using **Node.js**, **Express**, and **MySQL**.

##  Features

-  Create a new task
-  Get all tasks or filter by status (`pending` or `done`)
-  Input validation (status, required fields)
-  Stores task creation time (auto `createdAt` field)


##  Setup Instructions

npm install express mysql2 dotenv

##  Run the API

node server.js

## API Endpoints
**Create Task**
Method:POST
URL:localhost:3001/api/tasks
Request:
{
  "title": "test task 1121",
  "status": "pending",
  "dueDate": "2025-04-25"
}
Response:
{
    "id": 1,
    "title": "Test task title",
    "status": "pending",
    "dueDate": "2025-05-01 12:00:00"
}

**Get All Tasks**
Method:GET
URL:localhost:3001/api/tasks
Response:
[
    {
        "id": 1,
        "title": "test task",
        "status": "pending",
        "dueDate": "2025-04-24T18:30:00.000Z",
        "createdAt": "2025-04-24T13:28:50.000Z"
    },
    {
        "id": 2,
        "title": "test task",
        "status": "done",
        "dueDate": "2025-04-24T18:30:00.000Z",
        "createdAt": "2025-04-24T13:29:54.000Z"
    }
]

**Get Tasks by status**
Method:GET
URL:localhost:3001/api/tasks?status=pending
Response:
[
    {
        "id": 1,
        "title": "test task",
        "status": "pending",
        "dueDate": "2025-04-24T18:30:00.000Z",
        "createdAt": "2025-04-24T13:28:50.000Z"
    },
    {
        "id": 3,
        "title": "test task 1111",
        "status": "pending",
        "dueDate": "2025-04-24T18:30:00.000Z",
        "createdAt": "2025-04-24T13:34:28.000Z"
    }
]
