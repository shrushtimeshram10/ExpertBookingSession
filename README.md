##Expert Session Booking System
A full-stack Real-Time Expert Session Booking System where users can browse experts, view available time slots, and book sessions instantly. Built with React, Node.js, Express, and MongoDB — with Socket.io powering live slot updates.

🚀 Tech Stack
Frontend

React (Vite)
Socket.io Client

Backend

Node.js
Express.js
MongoDB + Mongoose
Socket.io


✨ Features

🔍 Search experts by name and filter by category
📄 Paginated expert listing with loading and error states
📅 View available time slots grouped by date on expert detail page
⚡ Real-time slot updates using Socket.io — slots disable instantly when booked by another user
📝 Booking form with full validation (name, email, phone, date, time slot, notes)
🔒 Double booking prevention with race condition handling using MongoDB atomic operations
📬 View all bookings by email with status tracking (Pending / Confirmed / Completed)


📁 Folder Structure
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

⚙️ Getting Started
Prerequisites

Node.js v18+
MongoDB (local or Atlas)

1. Clone the repository
bashgit clone https://github.com/yourusername/expert-booking-system.git
cd expert-booking-system
2. Setup Backend
bashcd backend
npm install
cp .env.example .env
Fill in your .env:
envPORT=5000
MONGO_URI=your_mongodb_connection_string
CLIENT_URL=http://localhost:5173
Then run:
bashnpm run dev
3. Setup Frontend
bashcd frontend
npm install
cp .env.example .env
Fill in your .env:
envVITE_API_URL=http://localhost:5000
Then run:
bashnpm run dev

📡 API Endpoints
MethodEndpointDescriptionGET/expertsGet all experts (pagination + filter)GET/experts/:idGet single expert detailsPOST/bookingsCreate a new bookingPATCH/bookings/:id/statusUpdate booking statusGET/bookings?email=Get bookings by email

🔒 Double Booking Prevention
Bookings are protected against race conditions using MongoDB's atomic findOneAndUpdate with strict conditions. If two users attempt to book the same expert, date, and time slot simultaneously, only one request succeeds and the other receives a clear conflict error.

⚡ Real-Time Updates
Socket.io is used to broadcast slot availability changes across all connected clients. When a booking is made, the server emits a slot-booked event, and all users viewing that expert's detail page see the slot disabled in real time — no page refresh required.

🌐 Deployment

Frontend: Vercel / Netlify
Backend: Render / Railway
Database: MongoDB Atlas


📬 Contact
Made by Shrushti Meshram
shrushti.meshram@cumminscollege.in
