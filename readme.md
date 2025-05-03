# Task Manager API

A simple **Task Management API** built using **Express.js**. This API allows you to perform basic CRUD operations on a list of tasks, along with filtering, sorting, and searching functionality.

---

## 🧾 Overview

This project serves as a basic in-memory task management system. It demonstrates the implementation of RESTful routes using Express. Tasks are stored in memory (no database), making it suitable for learning or prototyping.

Each task contains:
- `id`: Unique identifier
- `title`: Task title
- `description`: Task details
- `completed`: Boolean status of task completion
- `priority`: Priority level (e.g., low, medium, high)
- `cd`: Created date

---

## 🚀 Setup Instructions

1. **Clone the Repository**

git clone https://github.com/your-username/task-manager-api.git
cd task-manager-api
Install Dependencies

npm install
node app.js

📮 API Endpoints

🔹 GET /tasks
Description: Retrieve all tasks

Query Params:

completed=true: Get only completed tasks

sort=true: Sort tasks by creation date

Optional Path Param:

/tasks/:level: Filter tasks by priority level (e.g., /tasks/high)

📘 Example:

GET /tasks?completed=true
GET /tasks?sort=true
GET /tasks/high

🔹 GET /tasks/:id
Description: Get a specific task by ID

Response: Task object or 404 if not found

📘 Example:

GET /tasks/1
🔹 POST /tasks
Description: Create a new task

Body Params (JSON):

{
  "title": "My Task",
  "description": "Some details here",
  "completed": false,
  "priority": "low"
}
Response: Created task object or 400 if title/description missing

📘 Example:


POST /tasks
🔹 PUT /tasks/:id
Description: Update a task by ID

Body Params (JSON): Same as POST

Response: Updated task or 404/400 if task not found or input is invalid

📘 Example:

PUT /tasks/1
🔹 DELETE /tasks/:id
Description: Delete a task by ID

Response: Remaining tasks list or 404 if not found

📘 Example:


DELETE /tasks/1
🧪 Testing the API
You can use Postman, cURL, or Supertest (automated tests) to test each endpoint.

Sample cURL:

curl -X POST http://localhost:3000/tasks \
-H "Content-Type: application/json" \
-d '{"title":"Learn Node","description":"Practice Express routing","completed":false,"priority":"medium"}'

📁 Folder Structure

/models
  └── taskModal.js     # In-memory task array
/routes
  └── taskRoutes.js    # Express route handlers
index.js               # App entry point
README.md

📌 Notes
This API does not use a database — all data is stored in memory.

Useful for small demos or practicing RESTful APIs.

🛠️ Tech Stack
Node.js
Express.js

