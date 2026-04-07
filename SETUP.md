# Todo App with User Login - Complete Setup

## ✅ What's Been Created

I've built a complete full-stack Todo List application with user authentication using the MERN stack. Here's what you have:

### Frontend (React + Vite)
- **Login Page** (`src/pages/Login.jsx`) - User login form
- **Register Page** (`src/pages/Register.jsx`) - New user registration
- **Todo List Page** (`src/pages/TodosList.jsx`) - Main dashboard with:
  - Add/Edit/Delete todos
  - Mark todos as complete/incomplete
  - Filter todos (All, Active, Completed)
  - View statistics (total, active, completed)
  
- **Components**:
  - `NavBar.jsx` - Navigation with logout button
  - `TodoItem.jsx` - Individual todo item display
  - `PrivateRoute.jsx` - Protected routes (redirects to login)
  - `AuthContext.jsx` - Global auth state management
  - `api.js` - Axios client with JWT interceptor

### Backend (Express.js + MongoDB)
- **Authentication Routes**:
  - `POST /api/auth/register` - User registration
  - `POST /api/auth/login` - User login (returns JWT token)

- **Todo Routes** (all protected with JWT):
  - `GET /api/todos` - Get all user's todos
  - `POST /api/todos` - Create new todo
  - `PUT /api/todos/:id` - Update a todo
  - `DELETE /api/todos/:id` - Delete todo

- **Models**:
  - `User.js` - User schema (name, email, password)
  - `Todo.js` - Todo schema (title, description, completed status, user reference)

### Styling
- Tailwind CSS for responsive, modern UI
- Clean, professional design

## 📋 Next Steps - Getting Started

### 1. Install Backend Dependencies
```bash
cd mern-lab/server
npm install
```

### 2. Setup Database & Environment
Create a `.env` file in the `server` folder with:
```
MONGO_URI=mongodb://localhost:27017/mern_lab
JWT_SECRET=my_secret_key_123
PORT=5000
```

**Note:** 
- For local MongoDB: Make sure MongoDB is running
- For cloud MongoDB: Get your connection string from MongoDB Atlas and update MONGO_URI

### 3. Start Backend Server
```bash
# From mern-lab/server directory
npm run dev
```
Server will run on `http://localhost:5000`

### 4. Install Frontend Dependencies
```bash
cd ../client  # or open new terminal and cd to mern-lab/client
npm install
```

### 5. Start Frontend Development Server
```bash
npm run dev
```
Frontend will run on `http://localhost:5173`

### 6. Open in Browser
Go to `http://localhost:5173`

## 🎯 How to Use

1. **Register** - Click "Register" to create a new account
2. **Login** - Log in with your credentials
3. **Add Todo** - Fill in the title and description, click "Add Todo"
4. **Manage** - Check off completed items, edit, or delete todos
5. **Filter** - Use filter buttons to see All/Active/Completed todos
6. **Logout** - Click the red "Logout" button when done

## 📁 Project File Structure

```
mern-lab/
├── client/
│   ├── src/
│   │   ├── pages/
│   │   │   ├── Login.jsx
│   │   │   ├── Register.jsx
│   │   │   └── TodosList.jsx
│   │   ├── components/
│   │   │   ├── NavBar.jsx
│   │   │   ├── TodoItem.jsx
│   │   │   └── PrivateRoute.jsx
│   │   ├── AuthContext.jsx
│   │   ├── api.js
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── index.html
│   ├── package.json
│   └── vite.config.js
│
├── server/
│   ├── models/
│   │   ├── User.js
│   │   └── Todo.js
│   ├── index.js
│   ├── package.json
│   └── .env
│
├── QUICKSTART.md (detailed guide)
└── README.md
```

## 🔧 Key Technologies Used

- **Frontend**: React 18, React Router, Axios, Tailwind CSS, Vite
- **Backend**: Node.js, Express, MongoDB, Mongoose, JWT, bcryptjs
- **Authentication**: JWT tokens stored in localStorage

## ✨ Features Included

- ✅ User registration and login
- ✅ Secure password hashing with bcryptjs
- ✅ JWT token-based authentication
- ✅ Protected routes (only logged-in users can see todos)
- ✅ Complete CRUD operations for todos
- ✅ Mark todos as complete/incomplete
- ✅ Edit existing todos
- ✅ Delete todos
- ✅ Filter todos by status
- ✅ Todo statistics dashboard
- ✅ Responsive mobile-friendly design
- ✅ Error handling and validation
- ✅ Loading states

## 🐛 Troubleshooting

**Can't see frontend?**
- Make sure frontend is running on port 5173
- Clear browser cache (Ctrl+Shift+Delete)

**Can't connect to backend?**
- Ensure backend is running on port 5000
- Check if CORS is enabled (it is by default)
- Try opening http://localhost:5000/api/todos to see if backend responds

**MongoDB not connecting?**
- Make sure MongoDB is running (`mongod` command)
- Or update MONGO_URI to use MongoDB Atlas
- Check .env file for correct connection string

**Port already in use?**
- Kill the process on that port
- Or change PORT in .env file and vite.config.js

## 📝 Notes

- Tokens are stored in localStorage and persist across browser sessions
- Each user can only see and manage their own todos
- All passwords are securely hashed with bcryptjs
- JWT tokens expire after 1 day of creation

## 🚀 Ready to Code!

Everything is set up and ready to run. Just follow the steps above and you'll have a working todo app with user authentication!

If you need to add features like:
- Due dates
- Categories
- Sharing todos
- Search functionality

Feel free to extend the code. The structure is modular and easy to expand.

Enjoy your todo app! 📝
