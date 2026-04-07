# Project Structure

## Frontend (React + Vite)
- `client/src/pages/` - Page components
  - `Login.jsx` - Login page
  - `Register.jsx` - Registration page  
  - `TodosList.jsx` - Main todos list with add/edit/delete functionality
- `client/src/components/` - Reusable components
  - `NavBar.jsx` - Navigation bar with logout button
  - `TodoItem.jsx` - Individual todo item component
  - `PrivateRoute.jsx` - Protected route component
- `client/src/AuthContext.jsx` - Authentication context and hooks
- `client/src/api.js` - Axios API instance with auth interceptors

## Backend (Node.js + Express)
- `server/models/`
  - `User.js` - User schema
  - `Todo.js` - Todo schema (new)
- `server/index.js` - Express server with:
  - Auth routes (register, login)
  - Todo CRUD routes (get, post, put, delete)
  - JWT middleware for protected routes
  - MongoDB connection

## Features
✅ User registration and login with JWT authentication
✅ Create, read, update, delete todos
✅ Mark todos as completed/incomplete
✅ Filter todos (all, active, completed)
✅ View todo statistics
✅ Edit existing todos
✅ Responsive UI with Tailwind CSS

## Setup Instructions

### Backend Setup
1. Navigate to the server folder
2. Install dependencies: `npm install`
3. Create a `.env` file with MongoDB connection string and JWT secret
4. Start the server: `npm run dev` (development) or `npm start` (production)

### Frontend Setup
1. Navigate to the client folder
2. Install dependencies: `npm install`
3. Start the dev server: `npm run dev`
4. Open http://localhost:5173 in your browser

### Requirements
- Node.js 14+
- MongoDB (local or cloud like MongoDB Atlas)
- npm or yarn

## API Endpoints

### Auth
- POST `/api/auth/register` - Register new user
- POST `/api/auth/login` - Login user

### Todos (requires authentication)
- GET `/api/todos` - Get all user's todos
- GET `/api/todos/:id` - Get single todo
- POST `/api/todos` - Create new todo
- PUT `/api/todos/:id` - Update todo
- DELETE `/api/todos/:id` - Delete todo
