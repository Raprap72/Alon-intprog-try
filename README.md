<div align="center">

<h1>🎩 User Management System 🎩</h1>

<img src="https://img.shields.io/badge/Author-Ralph%20Theodore%20D.%20Alon-blueviolet?style=for-the-badge" />
<img src="https://img.shields.io/badge/Backend-Node.js-green?style=for-the-badge" />
<img src="https://img.shields.io/badge/Frontend-Angular-red?style=for-the-badge" />
<img src="https://img.shields.io/badge/DB-MySQL-blue?style=for-the-badge" />

</div>

---

## ✨ Why You'll Love This Project
- 🦄 All-in-one user, workflow, and department management
- 🔒 Secure authentication (JWT)
- ⚡ Lightning-fast Angular frontend
- 📬 Email notifications
- 🧩 Modular, scalable, and fun to hack on!

---

## 🧑‍💻 About Me
> **Ralph Theodore D. Alon**  
> Building things that make life easier!

- 📫 [Email me!](mailto:ralph.alon@email.com)
- 🌐 [LinkedIn](https://linkedin.com/in/ralph-alon)

---

## 🚦 How to Get Started

```sh
# Clone & install
$ git clone <repo-url>
$ cd frontend && npm install

# Run the app
$ npm start

# Backend? Easy!
$ cd ../backend && npm install && npm run dev
```

---

## 🗂️ Folders At a Glance

| Folder      | What’s Inside                |
|-------------|-----------------------------|
| frontend/   | Angular client app          |
| backend/    | Node.js/Express API server  |
| database/   | SQL scripts, migrations     |

---

## 🛠️ Built With
- Angular
- Node.js (Express)
- MySQL
- Bootstrap

---

## 🦾 Notable Features
- Role-based access: Admin & User
- RESTful API
- Responsive UI
- Error handling & validation
- Email integration

---

## 💡 Pro Tips
- Want to add a new module? Just drop it in `frontend/src/features/` and wire up the routing!
- Need to seed your DB? Check `database/` for ready-to-run SQL.
- All configs are in each folder—no hunting around!

---

## 📜 License & Credits

> © 2025 Ralph Theodore D. Alon. All rights reserved.  
> Inspired by the need for better user management everywhere.  
> Made with ☕, 💻, and a bit of magic.

---

### ⚡ Happy coding! ⚡
json
Copy
Edit
{
  "database": {
    "host": "localhost",
    "port": 3306,
    "user": "root",
    "password": "your_db_password",
    "database": "ums_api_db"
  },
  # ETHERNAL EMAIL ACCOUNT
  "secret": "YourSecretKeyHere",
  "emailFrom": "info@yourdomain.com",
  "smtpOptions": {
    "host": "smtp.example.com",
    "port": 587,
    "auth": {
      "user": "erick.shanahan@ethereal.email",
        "pass": "EDUugw48M7FsmzfFjU",
    }
  }
}
🔒 Replace credentials before deployment!

Start Development Server
bash
Copy
Edit
cd frontend
npm run start:dev
MySQL Setup
sql
Copy
Edit
-- # Database Setup

cd database

# Connect to MySQL
\connect root@localhost

-- # Create the database
CREATE DATABASE `ums_api_db`;

-- Use the new database
USE ums_api_db;
API Endpoints
Authentication
Register (First user becomes Admin)
POST /accounts/register

json
Copy
Edit
{
  "title": "Mr",
  "firstName": "John",
  "lastName": "Doe",
  "email": "john.doe@example.com",
  "password": "Password123!",
  "confirmPassword": "Password123!",
  "acceptTerms": true
}
Verify Email
POST /accounts/verify-email

json
Copy
Edit
{
  "token": "email-verification-token"
}
Authenticate/Login
POST /accounts/authenticate

json
Copy
Edit
{
  "email": "john.doe@example.com",
  "password": "Password123!"
}
Response Example

json
Copy
Edit
{
  "id": 5,
  "firstName": "John",
  "lastName": "Doe",
  "email": "john.doe@example.com",
  "role": "User",
  "jwtToken": "...",
  "refreshToken": "..."
}
Refresh Token
POST /accounts/refresh-token
Requires: refreshToken cookie

Revoke Token
POST /accounts/revoke-token

json
Copy
Edit
{
  "token": "refresh-token"
}
Admin Endpoints
Get All Users
GET /accounts
Access: Admin Only

Get User by ID
GET /accounts/{id}
Access: Admin or Owner

Create User (Admin)
POST /accounts

json
Copy
Edit
{
  "title": "Mr",
  "firstName": "John",
  "lastName": "Doe",
  "email": "john.doe@example.com",
  "password": "Password123!",
  "confirmPassword": "Password123!",
  "role": "User"
}
Update User
PUT /accounts/{id}

json
Copy
Edit
{
  "firstName": "Updated",
  "lastName": "Name"
}
Delete User
DELETE /accounts/{id}

Password Management
Forgot Password
POST /accounts/forgot-password

json
Copy
Edit
{
  "email": "john.doe@example.com"
}
Validate Reset Token
POST /accounts/validate-reset-token

json
Copy
Edit
{
  "token": "reset-token"
}
Reset Password
POST /accounts/reset-password

json
Copy
Edit
{
  "token": "reset-token",
  "password": "NewPassword123!",
  "confirmPassword": "NewPassword123!"
}
Error Handling
200 OK

400 Bad Request

401 Unauthorized

403 Forbidden

404 Not Found

500 Internal Server Error

Error Response Format:

json
Copy
Edit
{
  "message": "Description of the error"
}