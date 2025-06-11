# AuthSystem

A Node.js and Express-based authentication system that provides user signup, login, and logout functionality with secure password handling and JWT token authentication. The backend is connected to a MongoDB database, ensuring user data is securely managed.

## Features

- **User Signup**: Users can sign up with email, password, and name. Passwords are hashed using bcrypt, and verification tokens are generated for account verification.
- **Login & Logout**: Secure login and logout endpoints with token-based authentication using JWT.
- **MongoDB Integration**: All user data is stored in a MongoDB database via Mongoose.
- **Token Management**: JWT tokens are set as HTTP-only cookies for secure session management.
- **Account Verification**: Handles verification tokens and expiration logic for account activation and password resets.

## Tech Stack

- **Backend**: Node.js, Express.js
- **Database**: MongoDB (Mongoose)
- **Authentication**: JWT (JSON Web Tokens), bcrypt
- **Environment Management**: dotenv

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

4. **Start the server**
   ```bash
   npm start
   ```

   The backend will run on `http://localhost:5000/` by default.

## API Endpoints

All endpoints are prefixed with `/app/auth`.

| Method | Endpoint        | Description            |
|--------|----------------|------------------------|
| POST   | /signup        | Register a new user    |
| POST   | /login         | User login             |
| POST   | /logout        | User logout            |

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
├── index.js
```

## License

This project is licensed under the MIT License.

---
**Maintainer:** [gauravk-io](https://github.com/gauravk-io)