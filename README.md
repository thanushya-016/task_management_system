# Task Management System

A simple web application for managing tasks, built with Python (Flask), SQLite, and a minimal HTML/CSS/JavaScript frontend. The app allows users to create, view, update, and delete tasks, focusing on core CRUD functionality.

---

## Features

- *Backend*: Flask-based RESTful API for CRUD operations.
- *Frontend*: Minimal UI for task management with forms and task filters.
- *Database*: SQLite for persistent task storage.

### Additional Features:
- Status change toggle between "Pending" and "Completed".
- Basic error handling (e.g., empty fields, invalid requests).
- Confirmation prompt before deleting tasks.

---

## Table of Contents

1. [Technologies Used](#technologies-used)
2. [Installation](#installation)
   - [Backend Setup](#steps-to-set-up-the-backend)
   - [Frontend Setup](#steps-to-set-up-the-frontend)
3. [Usage](#usage)
4. [API Endpoints](#api-endpoints)
5. [Folder Structure](#folder-structure)
6. [Known Issues](#known-issues)
7. [Contributing](#contributing)
8. [License](#license)

---

## Technologies Used

### Backend:
- Python
- Flask
- Flask-CORS
- Flask-SQLAlchemy

### Frontend:
- HTML
- CSS
- JavaScript

### Database:
- SQLite

---

## Installation

### Prerequisites
Make sure you have the following installed on your system:
- Python 3.7+
- A code editor (e.g., VS Code or PyCharm)
- A browser (for running the frontend)

---

### Steps to Set Up the Backend

1. *Navigate to the Backend Folder*
    bash
    cd backend
    

2. *Create a Virtual Environment*
    - *Linux/macOS*:
      bash
      python -m venv venv
      source venv/bin/activate
      
    - *Windows*:
      bash
      python -m venv venv
      venv\Scripts\activate
      

3. *Install Required Python Packages*
    bash
    pip install flask flask-cors flask-sqlalchemy
    

4. *Set Up the Database*
    - Initialize the SQLite database:
      bash
      python
      >>> from app import db
      >>> db.create_all()
      >>> exit()
      
    - This creates a database.db file for task storage.

5. *Run the Backend Server*
    bash
    python app.py
    
    The backend will run on http://127.0.0.1:5000/.

---

### Steps to Set Up the Frontend

1. *Navigate to the Frontend Folder*
    bash
    cd ../frontend
    

2. **Open index.html**
    - Use any browser to open the index.html file and access the application.

---

## Usage

### Creating a Task:
- Use the form on the frontend to enter task details such as title, description, due date, and status.
- Click "Add Task" to save the task.

### Viewing Tasks:
- All tasks are displayed in a list format on the main page.

### Updating Tasks:
- Click the "Edit" button next to a task to modify its details.
- Save the changes to update the task.

### Deleting Tasks:
- Use the "Delete" button next to a task to remove it.
- A confirmation prompt will appear before deletion.

### Filtering Tasks:
- Use the status filter dropdown to view tasks by "Pending" or "Completed".

---

## API Endpoints

| Method | Endpoint          | Description                 |
|--------|--------------------|-----------------------------|
| GET    | /tasks          | Retrieve all tasks.         |
| POST   | /tasks          | Create a new task.          |
| PUT    | /tasks/<task_id>| Update an existing task.    |
| DELETE | /tasks/<task_id>| Delete a specific task.     |

### Sample Payload for POST and PUT:
```json
{
  "title": "Complete Homework",
  "description": "Finish the math assignment.",
  "due_date": "2024-12-05",
  "status": "Pending"
}
