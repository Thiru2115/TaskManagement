# Task Management API

## 📌 Overview
This is a **CRUD API** built with **Node.js, Express, and MongoDB** for managing tasks. It allows users to:
- ✅ Create a new task
- ✅ Retrieve all tasks
- ✅ Get a single task by ID
- ✅ Update a task
- ✅ Delete a task

## 🛠 Technologies Used
- Node.js
- Express.js
- MongoDB & Mongoose
- dotenv (for environment variables)
- CORS & Body Parser

## 📂 Project Structure
```
task-manager-api/
│── node_modules/
│── config/
│   └── db.js
│── models/
│   └── Task.js
│── routes/
│   └── taskRoutes.js
│── controllers/
│   └── taskController.js
│── .env
│── server.js
│── package.json
│── README.md
```

## 🚀 Installation & Setup

1️⃣ **Clone the repository**
```sh
git clone https://github.com/your-repo/task-manager-api.git
cd task-manager-api
```

2️⃣ **Install dependencies**
```sh
npm install
```

3️⃣ **Set up environment variables**
Create a `.env` file and add:
```
MONGO_URI=mongodb://localhost:27017/taskmanager
PORT=5000
```

4️⃣ **Start the server**
```sh
npm run dev
```

## 🚀 API Endpoints

### ✅ Create a Task
- **URL:** `POST /api/tasks`
- **Request Body:**
  ```json
  {
    "title": "Learn Node.js",
    "description": "Complete the Node.js course"
  }
  ```
- **Response:**
  ```json
  {
    "_id": "60d21b4867d0d8992e610c85",
    "title": "Learn Node.js",
    "description": "Complete the Node.js course",
    "completed": false,
    "createdAt": "2024-02-05T12:00:00.000Z"
  }
  ```

### ✅ Get All Tasks
- **URL:** `GET /api/tasks`
- **Response:**
  ```json
  [
    {
      "_id": "60d21b4867d0d8992e610c85",
      "title": "Learn Node.js",
      "description": "Complete the Node.js course",
      "completed": false,
      "createdAt": "2024-02-05T12:00:00.000Z"
    }
  ]
  ```

### ✅ Get a Task by ID
- **URL:** `GET /api/tasks/:id`
- **Response:**
  ```json
  {
    "_id": "60d21b4867d0d8992e610c85",
    "title": "Learn Node.js",
    "description": "Complete the Node.js course",
    "completed": false,
    "createdAt": "2024-02-05T12:00:00.000Z"
  }
  ```

### ✅ Update a Task
- **URL:** `PUT /api/tasks/:id`
- **Request Body:**
  ```json
  {
    "completed": true
  }
  ```
- **Response:**
  ```json
  {
    "_id": "60d21b4867d0d8992e610c85",
    "title": "Learn Node.js",
    "description": "Complete the Node.js course",
    "completed": true,
    "createdAt": "2024-02-05T12:00:00.000Z"
  }
  ```

### ✅ Delete a Task
- **URL:** `DELETE /api/tasks/:id`
- **Response:**
  ```json
  {
    "message": "Task deleted successfully"
  }
  ```

## 🔥 Testing with Postman
1. **Download and install Postman** from [here](https://www.postman.com/).
2. Import the provided **Postman Collection JSON** (see below).
3. Test the API endpoints easily!

```json
{
  "info": {
    "_postman_id": "12345-abcde",
    "name": "Task Management API",
    "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json"
  },
  "item": [
    {
      "name": "Create Task",
      "request": {
        "method": "POST",
        "header": [{"key": "Content-Type", "value": "application/json"}],
        "body": { "mode": "raw", "raw": "{\"title\":\"Learn Node.js\",\"description\":\"Complete the Node.js course\"}" },
        "url": { "raw": "http://localhost:5000/api/tasks", "protocol": "http", "host": ["localhost"], "port": "5000", "path": ["api", "tasks"] }
      }
    },
    {
      "name": "Get All Tasks",
      "request": { "method": "GET", "url": { "raw": "http://localhost:5000/api/tasks", "host": ["localhost"], "port": "5000", "path": ["api", "tasks"] } }
    }
  ]
}
```

## 📜 License
This project is open-source and available for use under the MIT License.

## 🎯 Next Steps
- Add **user authentication (JWT)**.
- Implement **sorting, filtering, and pagination**.
- Deploy the API to **Cloud (Render, Heroku, or AWS)**.

🚀 Happy Coding! 🎉
