# AuthSystem

A Node.js/Express + React authentication system that provides secure user signup, login, and logout functionality with JWT-based authentication and MongoDB persistence. This full-stack project includes both backend and frontend, and is suitable as a boilerplate for building secure, modern authentication workflows.

---

## Features

- **User Signup**: Registration via email, password, and name. Passwords are hashed using bcrypt. Account verification handled via tokens.
- **Login & Logout**: Secure endpoints with JWT token-based authentication. Session managed via HTTP-only cookies.
- **MongoDB Integration**: All user data is stored in MongoDB via Mongoose.
- **JWT Token Management**: Tokens are issued and stored securely for each session.
- **Account Verification**: Handles verification tokens for account activation and password resets.
- **Password Reset**: Secure password reset flow, including email notifications.
- **Frontend**: Built with React, Zustand for state management, Vite, and TailwindCSS for UI.
- **API Security**: CORS, cookie parsing, and environment-based config.

---

## Tech Stack

- **Backend**: Node.js, Express.js
- **Frontend**: React, Zustand, Vite, TailwindCSS
- **Database**: MongoDB (Mongoose)
- **Authentication**: JWT, bcrypt
- **Email**: Nodemailer/Mailtrap for transactional emails
- **Env Management**: dotenv

---

## Getting Started

### Prerequisites

- Node.js (v18+ recommended)
- MongoDB instance (local or cloud)
- npm

### Setup & Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/gauravk-io/authSystem.git
   cd authSystem/backend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure Environment Variables**  
   Create a `.env` file in the `backend` directory with the following keys:
   ```
   MONGO_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret
   NODE_ENV=development
   PORT=5000
   ```

4. **Start the backend server**
   ```bash
   npm start
   ```
   The backend will run on `http://localhost:5000/` by default.

5. **Start the frontend**
   ```bash
   cd ../frontend
   npm install
   npm run dev
   ```
   The frontend will run on `http://localhost:5173/` by default.

---

## API Endpoints

All endpoints are prefixed with `/api/auth`.

| Method | Endpoint            | Description                |
|--------|---------------------|----------------------------|
| POST   | /signup             | Register a new user        |
| POST   | /login              | User login                 |
| POST   | /logout             | User logout                |
| POST   | /forgot-password    | Send reset password email  |
| POST   | /reset-password/:token | Reset user password      |
| POST   | /verify-email       | Verify email with code     |
| GET    | /check-auth         | Validate user session      |

---

## Project Structure

```
backend/
├── controllers/
│   └── auth.controller.js
├── db/
│   └── connectDB.js
├── models/
│   └── user.model.js
├── routes/
│   └── auth.route.js
├── utils/
│   └── generateTokenAndSetCookie.js
├── mailtrap/
│   └── emailTemplates.js
└── index.js

frontend/
├── src/
│   ├── App.jsx
│   ├── store/
│   │   └── authStore.js
│   ├── components/
│   │   └── PasswordStrengthMeter.jsx
│   └── index.css
├── index.html
├── vite.config.js
└── eslint.config.js
```

---

## Security & Best Practices

- Passwords are hashed with bcrypt before storage.
- JWT tokens are stored as HTTP-only cookies.
- Includes password reset and account verification via email.
- CORS is configured for secure cross-origin requests.
- Environment variables manage secrets and configuration.

---
---

**Maintainer:** [gauravk-io](https://github.com/gauravk-io)