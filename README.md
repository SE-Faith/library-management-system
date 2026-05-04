# Library Management System

A backend system built with Node.js, Express, and MongoDB for managing books, users (students & librarians) and borrowing activities in a library.

---

# Features

- User authentication (JWT)
- Role-based access control (Student & Librarian)
- Book management (Create, Read, Update, Delete)
- Borrow & return system
- Pagination and search functionality
- Password hashing using bcrypt
- Secure API design using MVC architecture

---

# 🏗️ Tech Stack

- Node.js
- Express.js
- MongoDB (Mongoose)
- JWT (Authentication)
- bcryptjs (Password hashing)

---

# Project Structure

models/
controllers/
routes/
middleware/
config/
service/
server.js

---

# ⚙️ Setup Instructions

## 1. Clone the repository

git clone https://github.com/SE-Faith/library-management-system.git

---

## 2. Install dependencies

npm install

---

## 3. Create `.env` file

PORT=port 
MONGO_URI=your_mongodb_connection_string  
JWT_SECRET=your_secret_key  

---

## 4. Run the server

npm run dev

Server runs on:
http://localhost:5000

---

#  User Roles

## 📖 Student
- View books
- Borrow books
- Return books

## 📚 Librarian
- Add books
- Update books
- Delete books
- Issue books

---

# Authentication Flow

1. User logs in
2. JWT token is generated
3. Token is sent in request headers:

Authorization: Bearer <token>

4. Middleware verifies token
5. Access is granted based on role

---

#  API Endpoints

## 📚 Books

POST /books (Librarian only)  
GET /books  
GET /books/:id  
PATCH /books/:id (Librarian only)  
DELETE /books/:id (Librarian only)  

GET /books?page=1&limit=10&search=keyword  

---

#  Borrowing System

POST /books/:id/borrow (Student only)  
POST /books/:id/return (Student only)  

---

#  Business Logic

- Only librarians can manage books
- Only students can borrow/return books
- A book cannot be borrowed if already borrowed
- Return date is automatically set when borrowing

---

#  Pagination & Search

Example:

GET /books?page=1&limit=10&search=math  

Response includes:
- page
- totalPages
- totalBooks
- data

---

#  Security Features

- Password hashing (bcrypt)
- JWT authentication
- Role-based authorization
- Protected routes middleware

---

#  Author

Omolafe Faith

