# Node.js Authentication Backend Project

This project is a Node.js backend application with authentication and authorization functionality, using JSON Web Tokens (JWT) for authentication, bcrypt for password encryption, and MongoDB with Mongoose for the database.

## Project Structure

- **index.js**: The main file that creates the Express app, sets up middleware functions, connects to the database, and defines routes.
- **config/database.js**: Connects to the MongoDB database using the Mongoose library.
- **routes/users.js**: Defines the routes for login, signup, and protected routes with middleware functions to check the JWT and user's role.
- **models/User.js**: Defines the User schema for the MongoDB database using the Mongoose Schema constructor.
- **middleware/auth.js**: Middleware functions to check the JWT and user's role.
- **controllers/Auth.js**: Functions to handle user login and signup requests.

## Installation

1. Clone the repository: `git clone https://github.com/your-username/nodejs-authentication-backend.git`
2. Install dependencies: `npm install`
3. Set up your MongoDB database and update the database connection in `config/database.js`.
4. Start the server: `npm start`

## Usage

- Register a new user: `POST /api/signup`
  - Body: `{ "email": "user@example.com", "password": "password", "role": "student" }`
- Login with existing user: `POST /api/login`
  - Body: `{ "email": "user@example.com", "password": "password" }`
  - Response: `{ "token": "your_jwt_token" }`
- Access protected routes:
  - Add the JWT token to the Authorization header in your request: `Authorization: Bearer your_jwt_token`
  - Example: `GET /api/protected-route`

## Dependencies

- Express: Web application framework
- Mongoose: MongoDB object modeling tool
- JSON Web Token (JWT): Authentication mechanism
- Bcrypt: Password hashing function
