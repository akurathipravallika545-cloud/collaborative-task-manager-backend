# 🧑‍💻 Collaborative Task Manager – Backend

This repository contains the **backend API** for the Collaborative Task Manager application.  
It is built using **Node.js, Express, TypeScript, PostgreSQL, Prisma**, and **Socket.io**, following a clean **service–repository architecture**.

---

## 🌐 Live API

- **Backend API URL:** https://<your-backend-url>.onrender.com  
- **Frontend URL:** https://<your-frontend-url>.vercel.app  

---

## 🛠 Tech Stack

- Node.js
- Express.js
- TypeScript
- PostgreSQL
- Prisma ORM
- JWT Authentication (HttpOnly Cookies)
- bcrypt (Password hashing)
- Socket.io (Real-time communication)
- Zod (DTO validation)
- Jest (Unit testing)

---

## 🗄 Database Choice

**PostgreSQL** was selected due to:
- Strong relational data integrity
- Support for enums (task status & priority)
- Excellent compatibility with Prisma
- Reliability for production-grade applications

---

## 🏗 Architecture Overview

The backend follows a **layered architecture**:
Routes → Controllers → Services → Repositories → Database

### Layer Responsibilities
- **Controllers:** Handle HTTP requests and responses
- **Services:** Business logic and validations
- **Repositories:** Database access using Prisma
- **DTOs:** Input validation using Zod schemas

This structure improves maintainability, scalability, and testability.

---

## 🔐 Authentication & Authorization

- User registration and login
- Passwords hashed using **bcrypt**
- JWT-based authentication
- Tokens stored securely in **HttpOnly cookies**
- Protected routes via authentication middleware

---

## ✅ Core Features

### Task Management (CRUD)
Each task includes:
- Title (max 100 characters)
- Description
- Due date
- Priority (Low, Medium, High, Urgent)
- Status (To Do, In Progress, Review, Completed)
- Creator ID
- Assigned User ID

### Dashboard Support
- Tasks created by the user
- Tasks assigned to the user
- Overdue tasks based on due date

### Filtering & Sorting
- Filter tasks by status and priority
- Sort tasks by due date

---

## ⚡ Real-Time Collaboration (Socket.io)

- Live task updates when status, priority, or assignee changes
- Instant in-app notifications on task assignment
- Socket events emitted from service layer to ensure consistency

---

## 📡 API Endpoints

### Authentication
- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/auth/me`

### Tasks
- `POST /api/tasks`
- `GET /api/tasks`
- `GET /api/tasks/:id`
- `PUT /api/tasks/:id`
- `DELETE /api/tasks/:id`

---

## 🧪 Testing

- Jest used for backend unit testing
- Tests cover critical business logic:
  - Task creation validation
  - Assignment handling
  - Error scenarios

✔ Meets the requirement of **minimum 3 unit tests**

---

## ▶️ Running Locally

```bash
git clone <backend-repo-url>
cd collaborative-task-manager-backend
npm install
npx prisma migrate dev
npm run dev
Environment Variables
Create a .env file in the root directory:
DATABASE_URL=postgresql://...
JWT_SECRET=your_jwt_secret
CLIENT_URL=https://<your-frontend-url>.vercel.app
📈 Trade-offs & Assumptions
JWT authentication used instead of server-side sessions
Role-based access control not implemented (not required)
Email notifications excluded; in-app notifications used instead
🏁 Conclusion
This backend service fulfills all functional, architectural, and real-time requirements of the assessment and is production-ready.

