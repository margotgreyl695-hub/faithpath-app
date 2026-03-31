# API Endpoint Documentation

## Authentication
- **POST /api/auth/login**  
  - Description: Authenticates a user and returns a token.
  - Request Body: `{ "username": "string", "password": "string" }`
  - Response: `200 OK (JWT Token)`  

- **POST /api/auth/register**  
  - Description: Registers a new user account.
  - Request Body: `{ "username": "string", "password": "string", "email": "string" }`  
  - Response: `201 Created`

## Bible
- **GET /api/bible/verses**  
  - Description: Retrieves specific verses from the Bible.
  - Query Parameters: `book`, `chapter`, `verse`
  - Response: `200 OK (array of verses)`

- **GET /api/bible/books**  
  - Description: Lists all books in the Bible.
  - Response: `200 OK (array of books)`

## Emotions
- **GET /api/emotions**  
  - Description: Retrieves a list of emotions.
  - Response: `200 OK (array of emotions)`  

- **POST /api/emotions**  
  - Description: Creates a new emotion entry.
  - Request Body: `{ "name": "string", "description": "string" }`  
  - Response: `201 Created`

## Plans
- **GET /api/plans**  
  - Description: Retrieves all user plans.
  - Response: `200 OK (array of plans)`

- **POST /api/plans**  
  - Description: Creates a new plan.
  - Request Body: `{ "title": "string", "details": "string" }`  
  - Response: `201 Created`

## Memorization
- **GET /api/memorization**  
  - Description: Retrieves memorization tasks.
  - Response: `200 OK (array of tasks)`

- **POST /api/memorization**  
  - Description: Adds a new memorization task.
  - Request Body: `{ "text": "string" }`  
  - Response: `201 Created`

## Chat
- **GET /api/chat/messages**  
  - Description: Retrieves messages from a chat session.
  - Response: `200 OK (array of messages)`

- **POST /api/chat/send**  
  - Description: Sends a message in the chat.
  - Request Body: `{ "message": "string" }`
  - Response: `200 OK`

## Users
- **GET /api/users**  
  - Description: Retrieves user details.
  - Response: `200 OK (array of users)`

- **PUT /api/users/{id}**  
  - Description: Updates user details.
  - Request Body: `{ "username": "string", "email": "string" }`
  - Response: `200 OK`

## Admin
- **GET /api/admin/statistics**  
  - Description: Retrieves statistics for admin dashboard.
  - Response: `200 OK (statistics data)`

- **DELETE /api/admin/users/{id}**  
  - Description: Deletes a user account.
  - Response: `204 No Content`

## Notifications
- **GET /api/notifications**  
  - Description: Retrieves notifications for the user.
  - Response: `200 OK (array of notifications)`

- **POST /api/notifications**  
  - Description: Creates a new notification.
  - Request Body: `{ "message": "string", "userId": "string" }`
  - Response: `201 Created` 

## Conclusion
This document outlines the API endpoints for all core features in the FaithPath application. For further details, refer to the corresponding documentation or comments in the code.