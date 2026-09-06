# smart-habit-tracker
# 🌱 Smart Habit Tracker

A full-stack **MERN-based Habit & Mood Tracking application** designed to help users build consistent habits, track daily progress, monitor mood, and understand their personal growth through analytics.

The application provides a simple and interactive dashboard where users can create and manage habits, mark daily completion, maintain streaks, record their mood, and visualize their progress over time.

---

## 🚀 Project Overview

**Smart Habit Tracker** is a productivity and self-improvement web application built using the **MERN Stack**.

Many people start good habits but struggle to maintain consistency because they don't have a simple way to track their progress. This application solves that problem by providing a centralized platform for:

* Creating and managing daily habits
* Tracking habit completion
* Maintaining current and longest streaks
* Recording daily moods
* Viewing habit completion statistics
* Analyzing mood trends
* Visualizing progress using charts and heatmaps
* Switching between Dark and Light themes

The project follows a **separated frontend and backend architecture**, with React handling the user interface and Express/MongoDB handling the backend and data storage.

---

## ✨ Key Features

### 🔐 1. User Authentication

The application provides secure user authentication using **JWT (JSON Web Token)**.

Users can:

* Create a new account
* Log in securely
* Stay authenticated using JWT
* Access protected application routes
* Log out from their account

Passwords are securely hashed using **bcryptjs** before being stored.

---

### ✅ 2. Habit Management

Users can create and manage their personal habits.

Each habit can contain:

* Habit name
* Icon
* Color
* Target frequency
* Completion status

Users can:

* Create habits
* Edit habits
* Delete habits
* Archive habits
* Track their progress

This makes it easy to organize different areas of daily life such as:

* 📚 Study
* 🏃 Exercise
* 💧 Drinking Water
* 📖 Reading
* 🧘 Meditation
* 💻 Coding

---

### 📅 3. Daily Habit Check-ins

Users can mark whether they completed a habit on a particular day.

The application keeps track of daily completion records, allowing users to understand how consistently they are following their habits.

Users can toggle a habit as:

**Completed → Not Completed**

for a specific date.

---

### 🔥 4. Streak Tracking

One of the main features of the application is **habit streak tracking**.

The application calculates:

* Current streak
* Longest streak
* Habit completion history

Streaks encourage users to stay consistent and avoid breaking their progress.

For example:

> 🔥 Current Streak: 12 Days
> 🏆 Longest Streak: 25 Days

---

### 😊 5. Mood Journal

Users can record their mood on a daily basis.

The mood system supports a **1–5 rating scale** and allows users to add an optional note.

For example:

> Mood: 😊 4/5
> Note: Had a productive day and completed most of my tasks.

This helps users connect their habits with their emotional well-being.

---

### 📊 6. Analytics Dashboard

The application includes an analytics section that helps users understand their progress.

Analytics include:

* Habit completion rate
* Mood trends
* Habit performance
* Progress over time
* Habit heatmaps

Charts are implemented using **Recharts** to make the data easier to understand visually.

---

### 🌡️ 7. Habit Heatmap

The application provides a visual representation of habit activity using a heatmap.

Users can quickly identify:

* Consistent days
* Missed days
* Active periods
* Overall habit consistency

This gives users a GitHub-style visual overview of their habit activity.

---

### 🌙 8. Dark / Light Theme

The application supports both:

* ☀️ Light Mode
* 🌙 Dark Mode

The selected theme is persisted using `localStorage`, so the user's preference remains available after refreshing the application.

---

### 🗄️ 9. MongoDB Database

The application uses **MongoDB with Mongoose** for storing application data.

Main database models include:

* `User`
* `Habit`
* `HabitLog`
* `Mood`

This allows the application to maintain structured and persistent user data.

---

### 🌱 10. Demo Data / Seed Script

The project includes a seed script that can generate a demo user along with realistic habit and mood history.

This makes it easier to test the application and demonstrate the analytics features.

---

## 🛠️ Tech Stack

### Frontend

* **React.js**
* **Vite**
* **React Router**
* **Tailwind CSS**
* **Axios**
* **Recharts**
* **Lucide React**

### Backend

* **Node.js**
* **Express.js**
* **MongoDB**
* **Mongoose**
* **JWT**
* **bcryptjs**
* **CORS**
* **dotenv**

### Development Tools

* **Nodemon**
* **Concurrently**
* **npm**

---

## 🏗️ Project Architecture

The project follows a **client-server architecture**.

```text
                 ┌──────────────────────┐
                 │      User / Browser  │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │   React Frontend     │
                 │   Vite + Tailwind    │
                 └──────────┬───────────┘
                            │
                       REST API
                            │
                            ▼
                 ┌──────────────────────┐
                 │   Express Backend    │
                 │   Node.js            │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │ MongoDB + Mongoose   │
                 └──────────────────────┘
```

---

## 📁 Project Structure

```text
smart-habit-tracker/
│
├── client/
│   ├── src/
│   │   ├── api/
│   │   │   └── client.js
│   │   │
│   │   ├── components/
│   │   │   ├── HabitCard.jsx
│   │   │   ├── HabitModal.jsx
│   │   │   ├── Layout.jsx
│   │   │   ├── MoodSelector.jsx
│   │   │   ├── Navbar.jsx
│   │   │   ├── ProtectedRoute.jsx
│   │   │   ├── Sidebar.jsx
│   │   │   └── StatCard.jsx
│   │   │
│   │   ├── context/
│   │   │   ├── AuthContext.jsx
│   │   │   └── ThemeContext.jsx
│   │   │
│   │   ├── lib/
│   │   │   └── constants.js
│   │   │
│   │   ├── pages/
│   │   │   ├── Login.jsx
│   │   │   ├── Register.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   └── Analytics.jsx
│   │   │
│   │   ├── App.jsx
│   │   ├── index.css
│   │   └── main.jsx
│   │
│   └── vite.config.js
│
├── server/
│   ├── config/
│   │   └── db.js
│   │
│   ├── controllers/
│   │   ├── analyticsController.js
│   │   ├── authController.js
│   │   ├── habitController.js
│   │   ├── logController.js
│   │   └── moodController.js
│   │
│   ├── middleware/
│   │   └── auth.js
│   │
│   ├── models/
│   │   ├── User.js
│   │   ├── Habit.js
│   │   ├── HabitLog.js
│   │   └── Mood.js
│   │
│   ├── routes/
│   │   ├── authRoutes.js
│   │   ├── habitRoutes.js
│   │   ├── logRoutes.js
│   │   ├── moodRoutes.js
│   │   └── analyticsRoutes.js
│   │
│   ├── utils/
│   │   └── date.js
│   │
│   ├── seed.js
│   └── server.js
│
├── package.json
├── pnpm-lock.yaml
└── README.md
```

---

## 🔄 How the Application Works

### Step 1 — Registration

A new user creates an account.

The backend:

1. Receives registration data
2. Validates the user
3. Hashes the password using bcrypt
4. Stores the user in MongoDB
5. Generates authentication information

---

### Step 2 — Login

The user enters their credentials.

The backend verifies the credentials and generates a **JWT token**.

The token is then used to access protected APIs.

---

### Step 3 — Create Habits

The user creates habits from the dashboard.

Habit information is sent from the React frontend to the Express API and stored in MongoDB.

---

### Step 4 — Daily Tracking

The user marks habits as completed each day.

A habit log is created/updated for the selected date.

---

### Step 5 — Streak Calculation

The backend processes habit completion history and calculates the user's:

* Current streak
* Longest streak

---

### Step 6 — Mood Tracking

The user selects a mood rating from 1–5 and can optionally write a note.

The mood entry is stored in MongoDB.

---

### Step 7 — Analytics

The backend aggregates habit and mood data.

The frontend receives the analytics data and displays it using charts and visualizations.

---

## 🔌 API Endpoints

### Authentication

| Method | Endpoint             | Description          |
| ------ | -------------------- | -------------------- |
| POST   | `/api/auth/register` | Create a new account |
| POST   | `/api/auth/login`    | Login user           |
| GET    | `/api/auth/me`       | Get current user     |

### Habits

| Method | Endpoint          | Description                     |
| ------ | ----------------- | ------------------------------- |
| GET    | `/api/habits`     | Get user habits with statistics |
| POST   | `/api/habits`     | Create a habit                  |
| PUT    | `/api/habits/:id` | Update a habit                  |
| DELETE | `/api/habits/:id` | Delete a habit                  |

### Habit Logs

| Method | Endpoint           | Description                        |
| ------ | ------------------ | ---------------------------------- |
| POST   | `/api/logs/toggle` | Toggle habit completion for a date |

### Mood

| Method | Endpoint     | Description                |
| ------ | ------------ | -------------------------- |
| GET    | `/api/moods` | Get mood entries           |
| POST   | `/api/moods` | Create/update today's mood |

### Analytics

| Method | Endpoint                  | Description              |
| ------ | ------------------------- | ------------------------ |
| GET    | `/api/analytics/overview` | Get aggregated analytics |

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/smart-habit-tracker.git

cd smart-habit-tracker
```

---

### 2. Install Dependencies

Install root dependencies:

```bash
npm install
```

Then install dependencies for both client and server:

```bash
npm run install:all
```

---

## 🔐 Environment Variables

### Backend

Create:

```text
server/.env
```

Add:

```env
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
JWT_EXPIRES=7d
PORT=5000
CLIENT_URL=http://localhost:5173
```

### Frontend

Create:

```text
client/.env
```

Add:

```env
VITE_API_URL=http://localhost:5000/api
```

> Never upload your actual `.env` files or database credentials to GitHub.

---

## 🌱 Optional Demo Data

You can generate demo data using:

```bash
npm run seed
```

The seed script creates sample habit and mood history for testing the analytics features.

---

## ▶️ Run the Application

### Run Frontend + Backend Together

From the project root:

```bash
npm run dev
```

Frontend:

```text
http://localhost:5173
```

Backend:

```text
http://localhost:5000
```

---

## 📈 Future Improvements

Some features that can be added in future versions:

* 🔔 Habit reminders and notifications
* 📱 Mobile application
* 📧 Email reminders
* 🏆 Achievement and reward system
* 👥 Social habit challenges
* 📤 Export progress as PDF/CSV
* ☁️ Cloud deployment
* 📊 More advanced analytics
* 🤖 AI-based habit recommendations

---

## 🎯 What I Learned From This Project

Building this project helped me strengthen my understanding of:

* Full-stack web development
* MERN architecture
* React component development
* REST API development
* JWT authentication
* Password hashing and security
* MongoDB database design
* Mongoose models
* Protected routes
* CRUD operations
* State management using React Context
* Data visualization using Recharts
* Frontend-backend integration using Axios
* Environment variable management
* Git and GitHub project organization

---

## 💡 Why This Project?

The main goal of Smart Habit Tracker is to make habit building **simple, measurable, and motivating**.

Instead of only maintaining a checklist, the application combines:

**Habits + Streaks + Mood + Analytics**

This allows users to understand not only whether they completed their habits, but also how their consistency and mood change over time.

---

## 👩‍💻 Author

**Rinkle**

B.Tech Computer Science & Engineering Student

Interested in:

* Full-Stack Development
* MERN Stack
* Software Development
* Problem Solving
* Building practical web applications

---


