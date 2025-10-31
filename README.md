# 🍽️ Backend_Nodejs_Suby – MERN Stack Multi-Vendor Restaurant Application

**Date:** March 23, 2024

---

## 📘 Project Overview

**Backend_Nodejs_Suby** is the **backend** service of a **MERN Stack Multi-Vendor Restaurant Application**.
It provides APIs for vendor registration, firm and product management, authentication using JWT, and secure data storage with MongoDB.

---

## ⚙️ Dependencies

The backend uses the following dependencies:

* **express** – Web framework for Node.js
* **mongoose** – MongoDB object modeling tool
* **dotenv** – Environment variable configuration
* **body-parser** – Parses incoming JSON requests
* **nodemon** – Development server auto-reloader
* **jsonwebtoken (JWT)** – Secure authentication
* **bcryptjs** – Password hashing
* **multer** – Image and file uploads
* **cors** – Enable cross-origin requests

---

## 🗄️ Database Connection

The server connects to **MongoDB** using **Mongoose**.
Ensure your `.env` file includes the following variables:

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

* `vendorController` – Manages vendor authentication and registration
* `firmController` – Handles firm creation and deletion
* `productController` – Handles product CRUD operations

---

### **Routes**

* `vendorRoutes`
* `firmRoutes`
* `productRoutes`

---

## 🔐 JWT Tokens

Each login generates a unique JWT for secure session management.

Example Tokens:

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

* **Get All Vendors (with related records):**
  `GET https://backend-nodejs-suby.onrender.com/vendor/all-vendors`

* **Get Single Vendor by ID:**
  `GET https://backend-nodejs-suby.onrender.com/vendor/single-vendor/:vendorId`

* **Image Uploads:**
  `GET https://backend-nodejs-suby.onrender.com/uploads/:imageName`

---

### **Firm APIs**

* **Add Firm (JWT Required):**
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

### **1. Install Dependencies**

```bash
npm install
```

### **2. Start Development Server**

```bash
npm run dev
```

### **3. Access API**

```
http://localhost:5000
```

---

## 📝 Note

This repository (**Backend_Nodejs_Suby**) contains **only the backend code** of the Multi-Vendor Restaurant Application.
The **frontend (React client)** is not included in this GitHub repository.
