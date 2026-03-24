# 🎓 SkillAcademy – Full Stack Learning Marketplace

A professional EdTech platform similar to Udemy, built with Node.js, Express, MongoDB, and vanilla JavaScript with Tailwind-inspired CSS.

---

## 🚀 Quick Start

### Prerequisites
- Node.js v16+
- MongoDB running locally on port 27017 (or update `.env` with your MongoDB URI)

### Installation

```bash
# 1. Install dependencies
npm install

# 2. (Optional) Seed sample data
npm run seed

# 3. Start development server
npm run dev
```

Open your browser at **http://localhost:5000**

---

## 🔑 Demo Credentials

After running `npm run seed`:

| Role  | Email                       | Password   |
|-------|-----------------------------|------------|
| Admin | admin@skillacademy.com      | admin123   |
| User  | alice@example.com           | password123|

The login page also has **"Demo User"** and **"Demo Admin"** quick-fill buttons.

---

## 📁 Project Structure

```
SkillAcademy/
│
├── server/
│   ├── config/
│   │   └── db.js              # MongoDB connection
│   ├── models/
│   │   ├── User.js            # User schema (bcrypt password)
│   │   ├── Course.js          # Course schema
│   │   └── Enrollment.js      # Enrollment schema
│   ├── controllers/
│   │   ├── authController.js  # Register, login, profile
│   │   └── courseController.js# CRUD + stats
│   ├── routes/
│   │   ├── authRoutes.js
│   │   ├── courseRoutes.js
│   │   └── enrollmentRoutes.js
│   ├── middleware/
│   │   └── authMiddleware.js  # JWT protect + admin guard
│   ├── seed.js                # Sample data seeder
│   └── server.js              # Express app entry point
│
├── client/
│   ├── index.html             # Landing page
│   ├── login.html             # Login page
│   ├── signup.html            # Registration page
│   ├── courses.html           # Course catalog
│   ├── dashboard/
│   │   ├── userDashboard.html # Student dashboard
│   │   └── adminDashboard.html# Admin panel
│   ├── css/
│   │   └── style.css          # All styles (glassmorphism, 3D, dark mode)
│   └── js/
│       └── app.js             # Shared JS utilities
│
├── .env                       # Environment variables
├── package.json
└── README.md
```

---

## 🌐 API Endpoints

### Authentication
| Method | Endpoint              | Access  | Description          |
|--------|-----------------------|---------|----------------------|
| POST   | /api/auth/register    | Public  | Register new user    |
| POST   | /api/auth/login       | Public  | Login                |
| GET    | /api/auth/me          | Private | Get current user     |
| PUT    | /api/auth/profile     | Private | Update profile       |
| GET    | /api/auth/users       | Admin   | List all users       |
| DELETE | /api/auth/users/:id   | Admin   | Delete user          |

### Courses
| Method | Endpoint              | Access  | Description          |
|--------|-----------------------|---------|----------------------|
| GET    | /api/courses          | Public  | Get all courses      |
| GET    | /api/courses/featured | Public  | Get featured courses |
| GET    | /api/courses/:id      | Public  | Get single course    |
| POST   | /api/courses          | Admin   | Create course        |
| PUT    | /api/courses/:id      | Admin   | Update course        |
| DELETE | /api/courses/:id      | Admin   | Delete course        |
| GET    | /api/courses/stats    | Admin   | Platform statistics  |

### Enrollments
| Method | Endpoint                        | Access  | Description       |
|--------|---------------------------------|---------|-------------------|
| POST   | /api/enroll                     | Private | Enroll in course  |
| GET    | /api/enrollments                | Private | My enrollments    |
| GET    | /api/enrollments/all            | Admin   | All enrollments   |
| PUT    | /api/enrollments/:courseId/progress | Private | Update progress |
| GET    | /api/enrollments/check/:courseId | Private | Check enrollment |

---

## ✨ Features

### 🎨 Frontend
- **Landing Page** – Hero with 3D floating cards, animated stats counters, featured courses
- **Authentication** – Beautiful login/signup with password strength indicator
- **Course Catalog** – Search, filter by category/level/price, pagination, sorting
- **User Dashboard** – Enrolled courses, progress tracking, Chart.js charts
- **Admin Dashboard** – Full CRUD for courses, user management, analytics
- **Dark Mode** – Toggle between light/dark themes
- **3D Card Hover Effects** – CSS perspective transforms
- **Glassmorphism** – Frosted glass UI components
- **Scroll Animations** – Intersection Observer based AOS
- **Responsive Design** – Works on mobile, tablet, desktop

### 🔧 Backend
- **JWT Authentication** – Secure stateless auth
- **bcrypt Password Hashing** – 12 salt rounds
- **Protected Routes** – Middleware guards for user and admin
- **RESTful API** – Standard HTTP methods and status codes
- **MongoDB Aggregations** – User growth stats, category analytics
- **Input Validation** – Mongoose schema validators

---

## 🛠️ Environment Variables

```env
PORT=5000
MONGO_URI=mongodb://localhost:27017/skillacademy
JWT_SECRET=your_super_secret_key_here
JWT_EXPIRE=7d
NODE_ENV=development
```

---

## 📦 Dependencies

```json
{
  "express": "^4.18.2",
  "mongoose": "^8.0.3",
  "bcryptjs": "^2.4.3",
  "jsonwebtoken": "^9.0.2",
  "cors": "^2.8.5",
  "dotenv": "^16.3.1",
  "nodemon": "^3.0.2" (dev)
}
```

---

## 🎯 Tech Stack

- **Frontend**: HTML5, CSS3, JavaScript (ES6+), Chart.js
- **Backend**: Node.js, Express.js
- **Database**: MongoDB with Mongoose ODM
- **Auth**: JWT + bcryptjs
- **Dev Tools**: nodemon

---

Made with ❤️ – SkillAcademy © 2024
