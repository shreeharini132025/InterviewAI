# 🧠 InterviewAI — Smart Interview Platform

> AI-powered interview simulation platform with real-time NLP feedback, voice recognition, and performance analytics.

---

## 🏗️ Architecture

```
Frontend (React + Vite)     →  http://localhost:5173
Backend  (Node.js + Express) →  http://localhost:5000
AI Service (Python + Flask)  →  http://localhost:8000
Database (MySQL)             →  localhost:3306
```

---

## ⚡ Quick Start

### 1. Setup MySQL Database

Open MySQL and run:
```sql
SOURCE db/schema.sql;
```

Update `backend/.env` with your MySQL password:
```
DB_PASSWORD=your_actual_password
```

### 2. Start Backend (Node.js)
```bash
cd backend
npm start
```

### 3. Start Frontend (React)
```bash
cd frontend
npm run dev
```

### 4. Start AI Service (Python) — Optional but recommended
```bash
cd backend/ai_service
pip install -r requirements.txt
python app.py
```

> **Note:** If AI service is not running, the backend uses a built-in fallback evaluator. Everything still works!

---

## 🎯 Features

| Feature | Status |
|---------|--------|
| ✅ User Authentication (JWT) | Complete |
| ✅ HR Interview Practice | Complete |
| ✅ Technical Interview Practice | Complete |
| ✅ Behavioral Interview Practice | Complete |
| ✅ AI Answer Evaluation | Complete |
| ✅ Voice-to-Text Answers | Complete |
| ✅ Real-Time Timer | Complete |
| ✅ Keyword Matching | Complete |
| ✅ Detailed Feedback | Complete |
| ✅ Performance Dashboard | Complete |
| ✅ Interview History | Complete |
| ✅ Score Charts (Recharts) | Complete |
| ✅ Python NLP Service | Complete |

---

## 📁 Project Structure

```
SIP/
├── frontend/                 # React + Vite
│   └── src/
│       ├── pages/
│       │   ├── Landing.jsx        # Home page
│       │   ├── Login.jsx          # Login
│       │   ├── Register.jsx       # Register
│       │   ├── Dashboard.jsx      # Analytics dashboard
│       │   ├── InterviewSetup.jsx # Choose interview type
│       │   ├── InterviewSession.jsx # Live interview
│       │   ├── Results.jsx        # Results + feedback
│       │   └── History.jsx        # Past sessions
│       ├── components/
│       │   ├── Navbar.jsx
│       │   ├── Toast.jsx
│       │   └── ProtectedRoute.jsx
│       ├── context/AuthContext.jsx
│       └── api.js
│
├── backend/                  # Node.js + Express
│   ├── routes/
│   │   ├── auth.js           # Login/Register
│   │   ├── questions.js      # Question bank
│   │   ├── interview.js      # Session management + AI eval
│   │   └── dashboard.js      # Analytics API
│   ├── config/db.js          # MySQL connection
│   ├── middleware/auth.js    # JWT middleware
│   ├── ai_service/
│   │   ├── app.py            # Python Flask NLP service
│   │   └── requirements.txt
│   └── server.js
│
└── db/
    └── schema.sql            # MySQL schema + sample questions
```

---

## 🤖 AI Evaluation Logic

The NLP evaluation scores answers on 5 dimensions:

| Dimension | Weight | How |
|-----------|--------|-----|
| Keyword Matching | 35% | Checks for expected industry keywords |
| Content Similarity | 25% | TF-IDF cosine similarity vs ideal answer |
| Answer Length | 20% | Word count quality scoring |
| Structure | 10% | Sentences, examples, numbers |
| Time Management | 10% | Answer within time limit |

---

## 🔐 Environment Variables

```env
# backend/.env
PORT=5000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=sip_db
JWT_SECRET=sip_super_secret_jwt_key_2024
JWT_EXPIRES_IN=7d
PYTHON_SERVICE_URL=http://localhost:8000
```

---

## 🛠️ Tech Stack

- **Frontend:** React 18, Vite, React Router, Recharts, Framer Motion
- **Backend:** Node.js, Express, MySQL2, bcryptjs, JWT
- **AI/NLP:** Python, Flask, NLTK, TF-IDF Algorithm
- **Database:** MySQL
- **Voice:** Web Speech API (Browser native)

---

*Built as a Smart Interview Platform project — Full Stack + AI*
