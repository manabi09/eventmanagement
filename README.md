![Image](frontend/src/assets/Banner.png)

# EasyEvent - Modern Event Management System

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](README.md) [![React](https://img.shields.io/badge/React-18.0.0-blue)](https://reactjs.org/) [![Node.js](https://img.shields.io/badge/Node.js-14.0.0-green)](https://nodejs.org/) [![MySQL](https://img.shields.io/badge/MySQL-8.0-orange)](https://www.mysql.com/) [![Express](https://img.shields.io/badge/Express-4.18.2-green)](https://expressjs.com/)

EasyEvent is a comprehensive event management platform built with React and Node.js, designed to streamline the process of creating, managing, and attending events.

![Image](frontend/src/assets/screenshot.png)

## 📋 Table of Contents


- [System Overview](#-system-overview)
- [Technology Stack](#%EF%B8%8F-technology-stack)
- [Architecture](#%EF%B8%8F-architecture)
- [Installation and Setup](#-installation-and-setup)
- [Key Features](#-key-features)
- [API Documentation](#-api-documentation)
- [Security Features](#-security-features)
- [Error Handling](#%EF%B8%8F-error-handling)
- [Performance Optimization](#-performance-optimization)
- [Testing](#-testing-not-updated-yet)
- [Deployment](#-deployment-not-updated-yet)
- [Contributing](#-contributing)
- [Support](#-support)
- [License](#-license)

## 🎯 System Overview

EasyEvent supports three user roles:

- **Admin**: Full system control and user management
- **Organizer**: Event creation and management
- **Attendee**: Event participation and enrollment

## 🛠️ Technology Stack

### Frontend

- React.js 18+ with Vite
- React Router v6
- Axios for API calls
- CSS Modules
- Context API for state management
- JWT for authentication

### Backend

- Node.js
- Express.js
- MySQL Database
- JWT Authentication
- Bcrypt for password hashing
- Multer for file uploads

## 🏗️ Architecture

### Frontend Structure
```
├── src/
│   ├── components/     Reusable UI components
│   ├── contexts/       React context providers
│   ├── pages/          Page components
│   ├── services/       API service layers
│   ├── styles/         CSS and style modules
│   ├── utils/          Utility functions
│   └── assets/         Static files and images
```

### Backend Structure
```
├── src/
│   ├── config/        Configuration files
│   ├── controllers/   Request handlers
│   ├── middleware/    Custom middleware
│   ├── routes/        API routes
│   ├── services/      Business logic
│   └── utils/         Utility functions
```
## 🚀 Installation and Setup

### Prerequisites

- Node.js (v14+)
- MySQL (v8.0+)
- npm or yarn
- git

### Step 1: Clone the Repository

```bash
git clone https://github.com/devops-dtc/eventmanagement.git
cd eventmanagement
```

### Step 2: Frontend Setup

```bash
cd frontend
npm install
```

Create a `.env` file in the frontend directory:

```env
VITE_API_URL=http://localhost:3000/api
```

### Step 3: Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file in the backend directory:

```env
# Server Configuration
PORT=3000
NODE_ENV=development
FRONTEND_URL=http://localhost:5173

# Database Configuration
DB_HOST=localhost
DB_USER=your_username
DB_PASSWORD=your_password // set a valid password if your password is by default('')
DB_NAME=easyevent_db
DB_PORT=3306

# JWT Configuration
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRES_IN=24h


```

### Step 4: Database Setup


```sql
CREATE DATABASE easyevent_db;
```

Run the sql queries to create a the Database Schema from `backend/src/database/DatabaseSetup.sql`

> [!Note]
> To Populate the Database with Mock Data run the Query file in `backend/src/database/MockData.sql`



### Step 5: Start the Application

Frontend:

```bash
cd frontend
npm run dev
```

Backend:

```bash
cd backend
npm run dev
```

## 🎮 Key Features

### 1. Authentication System

- Secure JWT-based authentication
- Role-based access control
- Password hashing with bcrypt
- Session management

### 2. Event Management

- Create, read, update, and delete events
- Event categorization
- Image upload functionality
- Event status tracking
- Search and filtering

### 3. User Management

- User registration and login
- Profile management
- Role assignment
- Account suspension system

### 4. Enrollment System

- Event registration
- Attendance tracking
- Capacity management
- Waitlist functionality

## 📡 API Documentation
### Authentication Endpoints

```javascript
POST /api/auth/register     # Register new user
POST /api/auth/login        # User login
POST /api/auth/logout       # User logout
GET  /api/auth/profile     # Get user profile
PUT  /api/auth/profile     # Update user profile
```

### Event Endpoints

```javascript
GET    /api/events              # Get all events
POST   /api/events              # Create new event
GET    /api/events/:id          # Get specific event
PUT    /api/events/:id          # Update event
DELETE /api/events/:id          # Delete event
GET    /api/events/featured     # Get featured events
GET    /api/events/categories   # Get event categories
```

### Enrollment Endpoints

```javascript
POST   /api/enrollments/:eventId    # Enroll in event
GET    /api/enrollments/my          # Get user enrollments
DELETE /api/enrollments/:id         # Cancel enrollment
PUT    /api/enrollments/:id/status  # Update enrollment status
```

### Admin Endpoints

```javascript
GET    /api/admin/users        # Get all users
PUT    /api/admin/users/:id    # Update user
DELETE /api/admin/users/:id    # Delete user
```

## 🔒 Security Features

### 1. Authentication & Authorization

- JWT-based authentication
- Role-based access control (RBAC)
- Password hashing using bcrypt
- Token refresh mechanism

### 2. Data Protection

- Input validation and sanitization
- XSS protection
- CSRF protection
- SQL injection prevention

### 3. API Security

- Rate limiting
- CORS configuration
- Secure headers
- Request validation

## 🚦 Error Handling

### Frontend

- Toast notifications for user feedback
- Error boundary implementation
- Form validation feedback
- Loading states

### Backend

- Standardized error responses
- Error logging
- Custom error classes
- Validation middleware

## 📊 Performance Optimization

### Frontend

- Code splitting
- Lazy loading
- Image optimization
- Caching strategies
- Memoization

### Backend

- Database indexing
- Query optimization
- Connection pooling
- Response caching
- Compression

## 🧪 Testing (Not Updated Yet)

### Frontend Testing

```bash
cd frontend
npm run test        # Run unit tests
npm run test:e2e    # Run E2E tests
```

### Backend Testing

```bash
cd backend
npm run test        # Run unit tests
npm run test:integration  # Run integration tests
```

## 📦 Deployment (Not Updated Yet)

### Frontend Deployment

- Build the production version:

```bash
cd frontend
npm run build
```

### Backend Deployment

- Prepare for production:

```bash
cd backend
npm run build
```

### Environment Considerations

- Set up proper environment variables
- Configure database connections
- Set up SSL certificates
- Configure server security

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📞 Support

- GitHub Issues: [Create an issue](https://github.com/devops-dtc/eventmanagement/issues)
## 📄 License

This project is licensed under the MIT License - see the [LICENSE](README.md) file for details.

---

Made with ❤️ by the EasyEvent Team

[Live Demo](https://easyevent.com/) | [Report Bug](https://github.com/devops-dtc/eventmanagement/issues)
