# 🏥 ZeeCare Medical Institute - Hospital Management System

A comprehensive Hospital Management System built with the MERN stack, providing separate interfaces for patients and administrators to manage appointments, doctors, and medical services efficiently.

[![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)](https://mongodb.com/)
[![Express.js](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)](https://expressjs.com/)

---

## 📋 Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [Environment Variables](#-environment-variables)
- [API Endpoints](#-api-endpoints)
- [Authentication & Authorization](#-authentication--authorization)
- [Usage](#-usage)
- [Contributing](#-contributing)
- [License](#-license)

---

# ✨ Features

## 🔐 Authentication & Authorization
- Multi-role Authentication
- JWT Token-based Security
- Role-based Access Control

## 👨‍⚕️ Admin Dashboard Features
- Doctor Management
- Admin Management
- Appointment Management
- Message Center
- Real-time Statistics

## 👤 Patient Portal Features
- User Registration & Login
- Appointment Booking
- Department Selection
- Doctor Selection
- Medical History
- Contact Form

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

## Frontend
- React 19
- React Router DOM
- Axios
- React Toastify
- Vite

---

# 📁 Project Structure

```bash
hospital-management-system/
├── Backend/
├── dashboard/
├── frontend/
└── README.md
git clone https://github.com/yourusername/hospital-management-system.git
cd hospital-management-system
cd Backend
npm install
cd ../frontend
npm install
cd ../dashboard
npm install
MONGO_URI=your_mongodb_uri

JWT_SECRET_KEY=your_secret_key
JWT_EXPIRES=7d
COOKIE_EXPIRE=7

PORT=4000

FRONTEND_URL=http://localhost:5173
DASHBOARD_URL=http://localhost:5174

CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

| Method | Endpoint            | Description      |
| ------ | ------------------- | ---------------- |
| POST   | `/patient/register` | Register Patient |
| POST   | `/login`            | User Login       |
| POST   | `/admin/addnew`     | Add Admin        |
| POST   | `/doctor/addnew`    | Add Doctor       |
| GET    | `/doctors`          | Get Doctors      |

| Method | Endpoint      | Description          |
| ------ | ------------- | -------------------- |
| POST   | `/post`       | Book Appointment     |
| GET    | `/getall`     | Get All Appointments |
| PUT    | `/update/:id` | Update Appointment   |
| DELETE | `/delete/:id` | Delete Appointment   |

| Method | Endpoint  | Description  |
| ------ | --------- | ------------ |
| POST   | `/send`   | Send Message |
| GET    | `/getall` | Get Messages |

Authentication & Authorization
JWT Authentication
HTTP-only Cookies
bcrypt Password Hashing
Role-based Access

cd Backend
npm run dev
cd frontend
npm run dev
cd dashboard
npm run dev

Admin
Manage Doctors
Manage Appointments
Manage Admins
Read Messages
👤 Patient
Register/Login
Book Appointments
Browse Departments
Send Messages
👨‍⚕️ Doctor
Managed by Admin

### Patient Portal
![Home](screenshots/home.png)

### Admin Dashboard
![Dashboard](screenshots/dashboard.png)

git checkout -b feature-name
git commit -m "Add feature"
git push origin feature-name

Known Issues
Validation inconsistencies
Limited error handling
Cloudinary duplicate config issue

Future Enhancements
Real-time Notifications
Payment Gateway
Video Consultation
Mobile App
Analytics Dashboard
Dark Mode

MongoNetworkError
