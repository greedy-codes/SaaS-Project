# Auth Assignment - Simple Authentication System

A simple authentication system built with Node.js, Express, and MySQL for college assignment.

## Tech Stack

- Node.js
- Express.js
- MySQL
- bcrypt (password hashing)
- express-session (session management)

---

## How to Setup

### Step 1: Create the Database

Open MySQL terminal or MySQL Workbench and run:

```sql
CREATE DATABASE pg_auth;
```

That's it! The table will be created automatically when you run the server.

### Step 2: Update Database Password

Open `server.js` and find this line:

```js
password: '',  // change this to your mysql password
```

Replace `''` with your MySQL root password. For example:

```js
password: 'your_password_here',
```

### Step 3: Install Dependencies

Open terminal in the project folder and run:

```bash
npm install
```

### Step 4: Run the Server

```bash
npm start
```

You should see:

```
Connected to MySQL database!
Users table is ready!
Server running on http://localhost:3000
```

---

## How to Test Using Postman

### 1. Register a New User

- **Method:** POST
- **URL:** `http://localhost:3000/register`
- **Body (JSON):**

```json
{
  "name": "John",
  "email": "john@example.com",
  "password": "123456"
}
```

- **Expected Response:**

```json
{
  "message": "User registered successfully!"
}
```

### 2. Login

- **Method:** POST
- **URL:** `http://localhost:3000/login`
- **Body (JSON):**

```json
{
  "email": "john@example.com",
  "password": "123456"
}
```

- **Expected Response:**

```json
{
  "message": "Login successful!",
  "user": "John"
}
```

### 3. Access Dashboard (Protected Route)

- **Method:** GET
- **URL:** `http://localhost:3000/dashboard`

If logged in:

```json
{
  "message": "Welcome to your dashboard, John!"
}
```

If not logged in:

```json
{
  "message": "Please login first"
}
```

### 4. Logout

- **Method:** GET
- **URL:** `http://localhost:3000/logout`

- **Expected Response:**

```json
{
  "message": "Logged out successfully!"
}
```

---

## Project Structure

```
auth-assignment/
│
├── server.js        # Main server file (all code here)
├── package.json     # Project config and dependencies
└── README.md        # This file
```

---

## Author

Made for college assignment submission.
