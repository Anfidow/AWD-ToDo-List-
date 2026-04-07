# Todo App - Quick Start Guide

## What's Been Created

A full-stack todo list application with user authentication using the MERN stack:
- **Frontend**: React with Vite, React Router, and Tailwind CSS
- **Backend**: Express.js server with MongoDB
- **Authentication**: JWT-based user login/registration

## Project Structure

```
mern-lab/
├── client/                    # React frontend
│   ├── src/
│   │   ├── pages/
│   │   │   ├── Login.jsx      # Login page
│   │   │   ├── Register.jsx   # Registration page
│   │   │   └── TodosList.jsx  # Main todos dashboard
│   │   ├── components/
│   │   │   ├── NavBar.jsx     # Navigation & logout
│   │   │   ├── TodoItem.jsx   # Todo item component
│   │   │   └── PrivateRoute.jsx # Protected routes
│   │   ├── AuthContext.jsx    # Auth state management
│   │   ├── api.js             # API client with interceptors
│   │   └── App.jsx            # Main app component
│   ├── package.json
│   └── vite.config.js
│
└── server/                    # Express backend
    ├── models/
    │   ├── User.js            # User schema
    │   └── Todo.js            # Todo schema
    ├── index.js               # Express server & routes
    ├── package.json
    └── .env                   # Environment variables
```

## Features

✅ **User Authentication**
  - User registration with email and password
  - Secure login with JWT tokens  
  - Auto-login after registration
  - Persistent login (tokens saved in localStorage)

✅ **Todo Management**
  - Create new todos with title and description
  - Mark todos as complete/incomplete
  - Edit existing todos
  - Delete todos
  - Filter todos (All, Active, Completed)
  - View statistics (total, active, completed count)
  - Todos sorted by creation date (newest first)

✅ **UI/UX**
  - Clean, responsive design with Tailwind CSS
  - Protected routes (redirect to login if not authenticated)
  - Error messages and validation
  - Loading states
  - Automatic logout button

## Prerequisites

- **Node.js** (v14 or higher)
- **npm** or **yarn**
- **MongoDB** (local installation or MongoDB Atlas cloud service)

## Installation & Setup

### 1. Setup Backend

```bash
# Navigate to server directory
cd mern-lab/server

# Install dependencies
npm install

# Create .env file (if not already created)
# Add these variables:
# MONGO_URI=mongodb://localhost:27017/mern_lab
# JWT_SECRET=your_secret_key_here
# PORT=5000

# Start the server
npm run dev  # with nodemon (development)
# OR
npm start    # regular start (production)
```

The server will run on `http://localhost:5000`

### 2. Setup Frontend

```bash
# In a new terminal, navigate to client directory
cd mern-lab/client

# Install dependencies
npm install

# Start the development server
npm run dev
```

The client will run on `http://localhost:5173`

### 3. Open in Browser

Navigate to `http://localhost:5173` in your web browser.

## Usage

1. **Register**: Click "Register" to create a new account
2. **Login**: Log in with your email and password
3. **Create Todo**: Use the form to add a new todo
4. **Manage Todos**: 
   - Check the checkbox to mark as complete
   - Click "Edit" to modify a todo
   - Click "Delete" to remove a todo
5. **Filter**: Use filter buttons to view by status
6. **Logout**: Click the red "Logout" button in the navbar

## API Endpoints

### Authentication
- `POST /api/auth/register` - Create new user account
- `POST /api/auth/login` - User login (returns JWT token)

### Todos (All require authentication)
- `GET /api/todos` - Get all user's todos
- `POST /api/todos` - Create new todo
- `PUT /api/todos/:id` - Update a todo
- `DELETE /api/todos/:id` - Delete a todo

## Environment Variables

### Server (.env file)
```
MONGO_URI=mongodb://localhost:27017/mern_lab
JWT_SECRET=your_secret_key_here
PORT=5000
```

### Frontend
No .env file needed. The API URL is configured in `src/api.js` to use `http://localhost:5000/api`

## Troubleshooting

**Frontend can't connect to backend:**
- Ensure backend is running on port 5000
- Check that CORS is enabled (it should be by default)
- Check browser console for errors

**MongoDB connection issues:**
- Ensure MongoDB is running locally or use MongoDB Atlas
- Update MONGO_URI in .env file if using cloud

**Port already in use:**
- Change PORT in .env file (server)
- Use `npm run dev -- --port 3000` for frontend

## Future Enhancements

- Add due dates for todos
- Priority levels
- Todo categories/labels  
- Reminders/notifications
- Share todos with other users
- Dark mode toggle
- Todo search functionality
