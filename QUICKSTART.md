# 🚀 LiveBoard Quick Start Guide

## Prerequisites
- Node.js v16+ installed
- npm or yarn package manager

## 🎯 Fastest Way to Start (Recommended)

### Windows Users
```bash
# Double-click or run:
start-dev.bat
```

### Mac/Linux Users
```bash
# Make executable and run:
chmod +x start-dev.sh
./start-dev.sh
```

This will automatically:
1. Install all dependencies (if needed)
2. Start backend server on port 4000
3. Start frontend dev server on port 5174
4. Open two terminal windows for monitoring

## 📱 Access the Application

- **Frontend**: http://localhost:5174
- **Backend API**: http://localhost:4000
- **Health Check**: http://localhost:4000/api/health

## 🔐 Demo Credentials

```
Username: admin
Password: admin123
```

## 🛠️ Manual Setup (Alternative)

### Step 1: Install Dependencies

```bash
# Install root dependencies
npm install

# Install server dependencies
cd server
npm install
cd ..

# Install client dependencies
cd client
npm install
cd ..
```

### Step 2: Start Backend Server

```bash
cd server
npm run dev
```

Backend will start on **http://localhost:4000**

### Step 3: Start Frontend (in a new terminal)

```bash
cd client
npm run dev
```

Frontend will start on **http://localhost:5174**

## 🎨 Features Available

### ✅ Core Features (Working)
- ✅ User Authentication (Login/Register)
- ✅ JWT-based Security
- ✅ Dashboard with Statistics
- ✅ Schedule Management
- ✅ Announcements System
- ✅ Task Management
- ✅ Real-time Updates (Socket.io)
- ✅ Admin Panel
- ✅ Responsive UI with Tailwind CSS

### 🚧 Enterprise Features (Ready for Extension)
- Employee Management
- Visitor Management
- Room Booking System
- Asset Tracking
- Attendance Management
- Leave Management
- Notification Center
- Reports & Analytics

## 📂 Project Structure

```
LiveDisplay/
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/    # Reusable UI components
│   │   ├── contexts/      # React contexts (Auth, etc.)
│   │   ├── pages/         # Page components
│   │   ├── services/      # API service layer
│   │   ├── utils/         # Utility functions
│   │   └── config/        # Configuration
│   └── vite.config.js     # Vite configuration
│
├── server/                # Node.js backend
│   ├── src/
│   │   ├── bulletproof-server.js  # Main server (in-memory DB)
│   │   ├── controllers/   # Route controllers
│   │   ├── middleware/    # Express middleware
│   │   └── routes/        # API routes
│   └── .env.local         # Environment variables
│
├── start-dev.bat          # Windows startup script
├── start-dev.sh           # Mac/Linux startup script
└── QUICKSTART.md          # This file
```

## 🔧 Configuration

### Backend (.env.local in server/)
```env
PORT=4000
CLIENT_ORIGIN=http://localhost:5174
JWT_SECRET=afnanpathan_liveboard_secret_key_2024
DATABASE_URL=mock://localhost
ADMIN_USER=admin
ADMIN_PASSWORD=admin123
```

### Frontend (Environment Variables)
The frontend automatically connects to `http://localhost:4000` in development.

## 🐛 Troubleshooting

### Port Already in Use
If port 4000 or 5174 is already in use:

**Backend:**
```bash
# Edit server/.env.local and change PORT
PORT=4001
```

**Frontend:**
```bash
# Edit client/vite.config.js and change port
server: {
  port: 5174
}
```

### Dependencies Not Installing
```bash
# Clear npm cache
npm cache clean --force

# Delete node_modules and reinstall
rm -rf node_modules package-lock.json
npm install
```

### React Router Warnings
These are deprecation warnings for React Router v7. They're harmless and have been addressed with future flags in the code.

### CORS Errors
Make sure both servers are running and the backend is configured to allow requests from `http://localhost:5174`.

## 📦 Production Deployment

### Option 1: Using Build Script
```bash
node build.js
```

### Option 2: Using PM2
```bash
npm install -g pm2
pm2 start ecosystem.config.js
```

### Option 3: Using Docker
```bash
docker-compose up -d
```

See `DEPLOYMENT.md` for detailed production deployment instructions.

## 🎓 Development Tips

### Hot Reload
Both frontend and backend support hot reload:
- Frontend: Vite HMR (instant updates)
- Backend: Nodemon (auto-restart on file changes)

### API Testing
Use the health check endpoint to verify backend:
```bash
curl http://localhost:4000/api/health
```

### Browser DevTools
- React DevTools: Install browser extension for better debugging
- Network Tab: Monitor API calls
- Console: Check for errors and logs

## 📚 API Endpoints

### Authentication
- `POST /api/auth/login` - User login
- `POST /api/auth/register` - User registration
- `GET /api/auth/me` - Get current user
- `POST /api/auth/logout` - Logout
- `POST /api/auth/refresh` - Refresh token

### Schedule
- `GET /api/schedule` - Get all schedules
- `POST /api/schedule` - Create schedule
- `PUT /api/schedule/:id` - Update schedule
- `DELETE /api/schedule/:id` - Delete schedule

### Announcements
- `GET /api/announcements` - Get all announcements
- `POST /api/announcements` - Create announcement
- `PUT /api/announcements/:id` - Update announcement
- `DELETE /api/announcements/:id` - Delete announcement

### Tasks
- `GET /api/tasks` - Get all tasks
- `POST /api/tasks` - Create task
- `PUT /api/tasks/:id` - Update task
- `DELETE /api/tasks/:id` - Delete task

### Dashboard
- `GET /api/dashboard/stats` - Get dashboard statistics

## 🤝 Support

For issues or questions:
1. Check this guide first
2. Review `DEPLOYMENT.md` for production setup
3. Check browser console for errors
4. Check server logs in terminal

## 🎉 Success Checklist

- [ ] Both servers are running without errors
- [ ] Can access http://localhost:5174
- [ ] Can login with admin/admin123
- [ ] Dashboard loads with statistics
- [ ] Can create/edit schedules
- [ ] Can create/edit announcements
- [ ] Can create/edit tasks
- [ ] Real-time updates work (Socket.io connected)

---

**Ready to deploy?** See `DEPLOYMENT.md` for production deployment guide.
**Need help?** Check the troubleshooting section above.
