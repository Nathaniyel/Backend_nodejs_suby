# 🍽️ MERN Stack Multi-Vendor Restaurant Application Documentation

**Date:** March 23, 2024

---

## 📘 Project Overview

This repository contains the **backend** of a **MERN Stack Multi-Vendor Restaurant Application**.
It manages vendor registration, firm creation, and product management with JWT authentication and MongoDB integration.

---

## ⚙️ Dependencies

The backend uses the following key dependencies:

* **express** – Web framework for Node.js
* **mongoose** – MongoDB object modeling tool
* **dotenv** – Loads environment variables
* **body-parser** – Parses incoming request bodies
* **nodemon** – Auto restarts server during development
* **jsonwebtoken (JWT)** – For secure authentication
* **bcryptjs** – For password hashing
* **multer** – For image/file uploads
* **cors** – Enables cross-origin requests

---

## 🗄️ Connection to Database

The server connects to **MongoDB** using **Mongoose** and environment variables from `.env`.
Ensure your `.env` file includes:

```
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
PORT=5000
```

---

## 🧱 API Structure

### **Models**

#### 🧑 Vendor

**Properties:**

* username
* email
* password

#### 🏢 Firm

**Properties:**

* firmName
* area
* category
* region
* offer
* image

#### 🍔 Product

**Properties:**

* productName
* price
* category
* image
* bestseller
* description

---

### **Controllers**

* `vendorController` – Handles vendor authentication and registration
* `firmController` – Manages firm creation and deletion
* `productController` – Handles product management

---

### **Routes**

* `vendorRoutes`
* `firmRoutes`
* `productRoutes`

---

## 🔐 JWT Tokens

Different JWT tokens are generated for each login session.
Examples:

```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ2ZW5kb3JJZCI6IjY1ZjA5Njk0YWZlYzMwNWE1YTI5MDVkYSIsImlhdCI6MTcxMDMzMDkwOSwiZXhwIjoxNzEwMzM0NTA5fQ.b_FvfjFXA7fE-rzicZI41htrPZHFM2YyfmoGnA7Cj9o

eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ2ZW5kb3JJZCI6IjY1ZjA5Njk0YWZlYzMwNWE1YTI5MDVkYSIsImlhdCI6MTcxMDMzMDk0OCwiZXhwIjoxNzEwMzM0NTQ4fQ.gVMwMO8kz8d-LwaM8CrzKWgd2UvgCC9J83VGUrCSHw8

eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ2ZW5kb3JJZCI6IjY1ZjA5Njk0YWZlYzMwNWE1YTI5MDVkYSIsImlhdCI6MTcxMDMzMDk3MSwiZXhwIjoxNzEwMzM0NTcxfQ.WjflFZK47SkO3-sOr9MjrfwBQKJj7uAYvI6j4IvJcLY
```

---

## 🌐 API Endpoints

### **Vendor APIs**

* **Register Vendor:**
  `POST https://backend-nodejs-suby.onrender.com/vendor/register`

* **Login Vendor:**
  `POST https://backend-nodejs-suby.onrender.com/vendor/login`

* **Get All Vendors (with relations):**
  `GET https://backend-nodejs-suby.onrender.com/vendor/all-vendors`

* **Get Single Vendor by ID:**
  `GET https://backend-nodejs-suby.onrender.com/vendor/single-vendor/:vendorId`

* **Image Uploads:**
  `GET https://backend-nodejs-suby.onrender.com/uploads/:imageName`

---

### **Firm APIs**

* **Add Firm (Authenticated via JWT):**
  `POST https://backend-nodejs-suby.onrender.com/firm/add-firm`

* **Delete Firm by ID:**
  `DELETE https://backend-nodejs-suby.onrender.com/firm/:firmId`

---

### **Product APIs**

* **Add Product to Firm:**
  `POST https://backend-nodejs-suby.onrender.com/product/add-product/:firmId`

* **Get Products by Firm ID:**
  `GET https://backend-nodejs-suby.onrender.com/product/:firmId/products`

* **Delete Product by ID:**
  `DELETE https://backend-nodejs-suby.onrender.com/product/:productId`

---

## 🚀 Run the Backend Locally

### **1. Install dependencies**

```bash
npm install
```

### **2. Start the development server**

```bash
npm run dev
```

### **3. Access API**

Backend runs by default at:

```
http://localhost:5000
```

---

## 📄 Note

This repository contains **only the backend code**.
Frontend (React client) is not included or pushed to GitHub.
