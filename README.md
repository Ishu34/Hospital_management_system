# 🏥 ZeeCare Medical Institute - Hospital Management System

A comprehensive Hospital Management System built with the MERN stack, providing separate interfaces for patients and administrators to manage appointments, doctors, and medical services efficiently.

[![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)](https://mongodb.com/)
[![Express.js](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)](https://expressjs.com/)

---

# 📋 Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Installation](#-installation)
- [Environment Variables](#-environment-variables)
- [Database Schema](#-database-schema)
- [API Endpoints](#-api-endpoints)
- [Authentication & Authorization](#-authentication--authorization)
- [Usage](#-usage)
- [Screenshots](#-screenshots)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

# ✨ Features

## 🔐 Authentication & Authorization

- **Multi-role Authentication**: Separate login systems for Patients, Doctors, and Admins
- **JWT Token-based Security**: Secure authentication with HTTP-only cookies
- **Role-based Access Control**: Different permissions for different user types

## 👨‍⚕️ Admin Dashboard Features

- **Doctor Management**: Add, view, and manage doctor profiles with avatar uploads
- **Admin Management**: Create new admin accounts
- **Appointment Management**: View, accept, reject, and track all appointments
- **Message Center**: View and manage patient inquiries
- **Real-time Statistics**: Dashboard with appointment and doctor counts

## 👤 Patient Portal Features

- **User Registration & Login**: Secure patient account creation
- **Appointment Booking**: Schedule appointments with preferred doctors
- **Department Selection**: Choose from 9 medical departments
- **Doctor Selection**: View available doctors by department
- **Medical History**: Track previous visits and appointments
- **Contact Form**: Send messages to hospital administration

## 🏥 Medical Departments

- Pediatrics
- Orthopedics
- Cardiology
- Neurology
- Oncology
- Radiology
- Physical Therapy
- Dermatology
- ENT (Ear, Nose, Throat)

---

# 🚀 Tech Stack

## Backend

- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT
- bcrypt
- Cloudinary
- CORS
- Cookie Parser

## Frontend

- React 19
- React Router DOM
- Axios
- React Toastify
- React Icons
- React Multi Carousel
- Vite

## Development Tools

- Nodemon
- ESLint
- dotenv

---

# 📁 Project Structure

```bash
hospital-management-system/
├── Backend/
│   ├── controllers/
│   │   ├── appointmentController.js
│   │   ├── messageController.js
│   │   └── userController.js
│   ├── database/
│   │   └── dbConnection.js
│   ├── middlewares/
│   │   ├── auth.js
│   │   ├── catchAsyncErrors.js
│   │   └── errorMiddleware.js
│   ├── models/
│   │   ├── appointmentSchema.js
│   │   ├── messageSchema.js
│   │   └── userSchema.js
│   ├── router/
│   │   ├── appointmentRouter.js
│   │   ├── messageRouter.js
│   │   └── userRouter.js
│   ├── utils/
│   │   └── jwtToken.js
│   ├── app.js
│   ├── server.js
│   └── package.json
├── dashboard/
│   ├── src/
│   │   ├── components/
│   │   ├── App.jsx
│   │   ├── App.css
│   │   └── main.jsx
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── Pages/
│   │   ├── App.jsx
│   │   ├── App.css
│   │   └── main.jsx
│   └── package.json
└── README.md
```

---

# 📋 Prerequisites

Before running this project, make sure you have the following installed:

- Node.js (v16 or higher)
- npm or yarn
- MongoDB
- Git

---

# 🛠 Installation

## 1. Clone the Repository

```bash
git clone https://github.com/yourusername/hospital-management-system.git
cd hospital-management-system
```

## 2. Backend Setup

```bash
cd Backend
npm install
```

## 3. Frontend Setup

```bash
cd ../frontend
npm install
```

## 4. Dashboard Setup

```bash
cd ../dashboard
npm install
```

---

# 🔧 Environment Variables

Create a `.env` file in the `Backend/config/` directory:

```env
# Database
MONGO_URI=mongodb://localhost:27017/hospital_management

# JWT Configuration
JWT_SECRET_KEY=your-super-secret-jwt-key-here
JWT_EXPIRES=7d
COOKIE_EXPIRE=7

# Server Configuration
PORT=4000

# Frontend URLs
FRONTEND_URL=http://localhost:5173
DASHBOARD_URL=http://localhost:5174

# Cloudinary Configuration
CLOUDINARY_CLOUD_NAME=your-cloudinary-cloud-name
CLOUDINARY_API_KEY=your-cloudinary-api-key
CLOUDINARY_API_SECRET=your-cloudinary-api-secret
```

---

# 🗄 Database Schema

## User Schema

```javascript
{
  firstName: String,
  lastName: String,
  email: String,
  phone: String,
  nic: String,
  dob: Date,
  gender: String,
  password: String,
  role: String,
  doctorDepartment: String
}
```

## Appointment Schema

```javascript
{
  firstName: String,
  lastName: String,
  email: String,
  phone: String,
  nic: String,
  dob: Date,
  gender: String,
  appointment_date: String,
  department: String,
  doctorId: ObjectId,
  patientId: ObjectId,
  status: String
}
```

## Message Schema

```javascript
{
  firstName: String,
  lastName: String,
  email: String,
  phone: String,
  message: String
}
```

---

# 🔗 API Endpoints

## User Routes (`/api/v1/user`)

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/patient/register` | Register Patient |
| POST | `/login` | User Login |
| POST | `/admin/addnew` | Add Admin |
| POST | `/doctor/addnew` | Add Doctor |
| GET | `/doctors` | Get All Doctors |

---

## Appointment Routes (`/api/v1/appointment`)

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/post` | Create Appointment |
| GET | `/getall` | Get All Appointments |
| PUT | `/update/:id` | Update Appointment |
| DELETE | `/delete/:id` | Delete Appointment |

---

## Message Routes (`/api/v1/message`)

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/send` | Send Message |
| GET | `/getall` | Get All Messages |

---

# 🔐 Authentication & Authorization

## JWT Token System

- Patient Token stored in `patientToken`
- Admin Token stored in `adminToken`
- Token Expiry: 7 Days
- HTTP-only Cookies

## Password Security

- bcrypt password hashing
- Protected routes with middleware

---

# 🚀 Usage

## Start Backend

```bash
cd Backend
npm run dev
```

## Start Frontend

```bash
cd frontend
npm run dev
```

## Start Dashboard

```bash
cd dashboard
npm run dev
```

---

# 🌐 Application URLs

- Patient Portal → `http://localhost:5173`
- Admin Dashboard → `http://localhost:5174`
- Backend API → `http://localhost:4000`

---

# 👥 User Roles & Access

## 🏥 Admin

- Manage Doctors
- Manage Appointments
- Manage Admins
- Read Patient Messages

## 👤 Patient

- Register/Login
- Book Appointments
- Browse Departments
- Send Messages

## 👨‍⚕️ Doctor

- Added and managed by Admin

---

# 🖼 Screenshots

```md
### Patient Portal
![Home Page](screenshots/patient-home.png)

### Admin Dashboard
![Dashboard](screenshots/admin-dashboard.png)
```

---

# 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Commit changes
4. Push changes
5. Create Pull Request

```bash
git checkout -b feature-name
git commit -m "Added new feature"
git push origin feature-name
```

---

# 🐛 Known Issues

- Validation inconsistencies
- Limited error handling
- Cloudinary duplicate config issue

---

# 🔄 Future Enhancements

- Real-time Notifications
- Email Integration
- Payment Gateway
- Video Consultation
- Mobile App
- Dark Mode

---

# 🔧 Troubleshooting

## MongoDB Connection Error

```bash
MongoNetworkError: failed to connect to server
```

### Solution

Ensure MongoDB is running properly.

---

## CORS Error

```bash
Access to XMLHttpRequest blocked by CORS policy
```

### Solution

Check backend CORS configuration.

---

## JWT Error

```bash
JsonWebTokenError: invalid token
```

### Solution

Clear browser cookies and login again.


