Name: Gatwech Ruach Karkuon
Date: 28. 08. 2026
Course: Technical Writing for Software Development and Reports

Exercise A: User Manual Procedure
Creating and Activating a Python Virtual Environment
Prerequisites
Before starting, you need:
A computer with Python installed.
Visual Studio Code or another code editor.
Basic knowledge of using the terminal.
Internet connection for installing packages.
Procedure
Open Visual Studio Code.
 Expected result: Visual Studio Code opens successfully.
Open the project folder.
 Expected result: The project files appear in the Explorer.
Open the terminal.
 Expected result: A terminal window appears at the bottom of Visual Studio Code.
Create a virtual environment by running python -m venv venv.
 Expected result: A folder named venv is created.
Activate the virtual environment by running venv\Scripts\activate on Windows.
 Expected result: (venv) appears before the terminal prompt.
Install a package by running pip install requests.
 Expected result: The Requests package is installed successfully.
Check the installed package by running pip show requests.
 Expected result: Information about the Requests package is displayed.

Screenshot: The screenshot shows the VS Code terminal with the Python virtual environment activated as (venv) and the Requests package successfully installed. 
Troubleshooting
Problem: The command python is not recognized.
 Solution: Make sure Python is installed and added to the system PATH, then restart Visual Studio Code.
Exercise B: API Reference Entry
Create a New Task
HTTP Method: POST
 Endpoint: /api/v1/projects/{projectId}/tasks
Description
This endpoint creates a new task inside a project for an authenticated user.
Path Parameter
Parameter
Type
Required
Description
projectId
String
Yes
ID of the project where the task will be created.

Request Body
Parameter
Type
Required
Description
title
String
Yes
Name of the task.
description
String
No
Additional information about the task.
assigneeId
String
Yes
ID of the user assigned to the task.
dueDate
String
Yes
Task deadline in YYYY-MM-DD format.
priority
String
Yes
Priority: low, medium, or high.

Required Headers
Header
Required
Description
Authorization
Yes
Bearer token used to authenticate the user.
Content-Type
Yes
Must be application/json.

Possible Responses
Code
Meaning
201 Created
Task was created successfully.
400 Bad Request
Request contains invalid or missing information.
401 Unauthorized
Authentication token is missing or invalid.
403 Forbidden
User does not have permission to create a task.
404 Not Found
The project or assigned user does not exist.
409 Conflict
Task cannot be created because of a conflicting request.
500 Internal Server Error
An unexpected server error occurred.

Example Request
{
  "title": "Complete database design",
  "description": "Create the database tables for the project.",
  "assigneeId": "USR-1025",
  "dueDate": "2026-09-15",
  "priority": "high"
}
Example Successful Response
{
  "id": "TASK-4582",
  "projectId": "PROJ-1001",
  "title": "Complete database design",
  "description": "Create the database tables for the project.",
  "assigneeId": "USR-1025",
  "dueDate": "2026-09-15",
  "priority": "high",
  "status": "open",
  "createdAt": "2026-08-28T10:30:00Z"
}

