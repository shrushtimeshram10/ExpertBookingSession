# 🚀 Expert Session Booking System

A full-stack **Real-Time Expert Session Booking System** where users can browse experts, view available time slots, and instantly book sessions online.

Built using **React**, **Node.js**, **Express**, **MongoDB**, and **Socket.io** for seamless real-time updates.

---

# ✨ Features

- 🔍 Search experts by name
- 🗂 Filter experts by category
- 📄 Paginated expert listing
- ⏳ Loading and error handling states
- 📅 View available time slots grouped by date
- ⚡ Real-time slot updates using Socket.io
- 🔒 Double booking prevention using MongoDB atomic operations
- 📝 Booking form with validation
- 📬 Track bookings by email
- 📌 Booking status tracking:
  - Pending
  - Confirmed
  - Completed

---

# 🛠 Tech Stack

## Frontend
- React (Vite)
- Socket.io Client

## Backend
- Node.js
- Express.js
- MongoDB
- Mongoose
- Socket.io

---

# 📁 Folder Structure

```bash
PINTEREST/
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── models/
│   │   ├── routes/
│   │   └── index.js
│   ├── .env
│   ├── .env.example
│   └── package.json
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   └── main.jsx
│   ├── .env
│   ├── .env.example
│   ├── index.html
│   ├── vite.config.ts
│   └── package.json
```

---

# ⚙️ Getting Started

## 📌 Prerequisites

Make sure you have installed:

- Node.js v18+
- MongoDB (Local or Atlas)

---

# 1️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/expert-booking-system.git
cd expert-booking-system
```

---

# 2️⃣ Setup Backend

```bash
cd backend
npm install
```

Create a `.env` file using `.env.example`

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
CLIENT_URL=http://localhost:5173
```

Run the backend server:

```bash
npm run dev
```

---

# 3️⃣ Setup Frontend

```bash
cd frontend
npm install
```

Create a `.env` file using `.env.example`

```env
VITE_API_URL=http://localhost:5000
```

Run the frontend:

```bash
npm run dev
```

---

# 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/experts` | Get all experts |
| GET | `/experts/:id` | Get single expert details |
| POST | `/bookings` | Create a new booking |
| PATCH | `/bookings/:id/status` | Update booking status |
| GET | `/bookings?email=` | Get bookings by email |

---

# 🔒 Double Booking Prevention

The system prevents double bookings using **MongoDB atomic operations** with strict conditions.

If two users try booking the same expert, date, and slot simultaneously:

- ✅ One booking succeeds
- ❌ The other receives a conflict error

This ensures complete race-condition safety.

---

# ⚡ Real-Time Updates

Using **Socket.io**, slot availability updates instantly across all connected clients.

When a booking is made:

- The server emits a `slot-booked` event
- All users viewing that expert page instantly see the slot disabled
- No page refresh required

---

# 🌐 Deployment

| Service | Platform |
|---------|----------|
| Frontend | Vercel / Netlify |
| Backend | Render / Railway |
| Database | MongoDB Atlas |

---

# 📬 Contact

## 👩‍💻 Made by Shrushti Meshram

📧 shrushti.meshram@cumminscollege.in

---

# ⭐ Support

If you like this project, consider giving it a ⭐ on GitHub!
