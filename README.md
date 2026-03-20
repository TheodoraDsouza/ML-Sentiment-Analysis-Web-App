# ML-Sentiment-Analysis-Web-App
# 🧠 AI Sentiment Analysis Web Application

A full‑stack web application that analyzes the emotional tone of user text and classifies it as **Positive**, **Negative**, or **Neutral** in real time.

This project demonstrates how Natural Language Processing (NLP) can be integrated into a web product using a lightweight Python backend and a modern responsive frontend.

---

## 🚀 What This Project Demonstrates

* How a **machine learning / NLP model** can be exposed through a web API
* How a **Flask backend** communicates with a frontend using REST APIs
* How real‑time text analysis works in production-style applications
* Clean UI design with modern styling principles

This is a practical beginner-to-intermediate project for AI + Web integration.

---

## 🏗️ Tech Stack

### 🖥️ Frontend

* **HTML5** — Page structure
* **CSS3** — Modern UI styling (gradients, glassmorphism, animations)
* **Vanilla JavaScript** — Handles user interaction and API calls
* **Fetch API** — Sends user text to backend and receives sentiment result

### ⚙️ Backend

* **Python** — Core programming language
* **Flask** — Lightweight web framework for building APIs
* **Flask-CORS** — Enables frontend ↔ backend communication across ports
* **VADER Sentiment Analyzer** — NLP engine for sentiment scoring

---

## 🧠 How the System Works (Architecture Flow)

```
User (Browser UI)
      ↓
Frontend (HTML/CSS/JS)
      ↓  Fetch API (POST request)
Flask Backend (Python API)
      ↓
Sentiment Analyzer (VADER NLP Engine)
      ↓
Score + Label Returned as JSON
      ↓
Frontend Displays Result
```

---

## ⚙️ Role of Each Technology

### 🧩 Flask — Backend Web Framework

Flask is used to create the server that powers the application.

It handles:

* Creating an API endpoint (`/analyze`)
* Receiving user text from the frontend
* Passing text to the sentiment analyzer
* Returning results in JSON format

Why Flask?

* Lightweight and beginner-friendly
* Minimal setup
* Perfect for ML model serving
* Commonly used in AI web apps

---

### 🌐 Flask-CORS — Cross-Origin Communication

The frontend runs on a different port than the backend.
Browsers block such requests by default for security.

Flask-CORS enables:

* Secure frontend → backend communication
* API access from web pages

Without it, the browser would block requests.

---

### 🧠 VADER Sentiment Analyzer — NLP Engine

VADER (Valence Aware Dictionary and sEntiment Reasoner) is a rule-based Natural Language Processing model.

It analyzes text by:

#### 1️⃣ Sentiment Lexicon

A built-in dictionary where words have sentiment strengths.

Examples:

* "great" → strong positive
* "bad" → negative
* "excellent" → very strong positive

#### 2️⃣ Language Rules

VADER understands context using rules like:

* **Intensifiers** → "very good" increases positivity
* **Negations** → "not good" flips sentiment
* **Capitalization** → "AMAZING" adds emphasis
* **Punctuation** → "great!!!" stronger emotion
* **Emojis & slang** → 🙂 😂 🔥 recognized

#### 3️⃣ Score Calculation

It returns four metrics:

* **Positive score** → % of positive tone
* **Neutral score** → % of neutral tone
* **Negative score** → % of negative tone
* **Compound score** → Overall sentiment (-1 to +1)

---

## 📊 Compound Score Interpretation

| Compound Score | Sentiment |
| -------------- | --------- |
| ≥ 0.05         | Positive  |
| ≤ -0.05        | Negative  |
| Between        | Neutral   |

Examples:

* **0.82** → Strong Positive
* **-0.67** → Strong Negative
* **0.01** → Neutral

The app uses the compound score to assign the final sentiment label.

---

## 🔌 API Design

### Endpoint

```
POST /analyze
```

### Request Body

```json
{
  "text": "User input text"
}
```

### Response

```json
{
  "sentiment": "positive",
  "score": 0.8423
}
```

This makes the ML system usable by any frontend or external app.

---

## 📁 Project Structure

```
sentiment-analyzer/
│
├── app.py          # Flask backend server
├── index.html      # Frontend user interface
└── README.md       # Documentation
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```
git clone <repo-url>
cd sentiment-analyzer
```

---

### 2️⃣ Install Dependencies

```
pip install flask flask-cors vaderSentiment
```

If pip fails:

```
python -m pip install flask flask-cors vaderSentiment
```

---

### 3️⃣ Run Backend Server

```
python app.py
```

Server starts at:

```
http://127.0.0.1:5000
```

Keep terminal open.

---

### 4️⃣ Run Frontend

Option A: Open `index.html` directly

Option B (Recommended):

* Install VS Code Live Server
* Right click → Open with Live Server

---

## 🧪 How to Use

1. Enter text in the input field
2. Click **Analyze Sentiment**
3. View:

   * Sentiment label
   * Sentiment score

Example Inputs:

* I loved the event → Positive
* This is the worst experience → Negative
* It was fine → Neutral

---

## 🎨 UI Features

* Modern gradient background
* Glassmorphism card layout
* Animated loading spinner
* Color-coded sentiment badges
* Responsive design

---

## 🛠️ Common Issues

### Imports not resolved in VS Code

* Select correct Python interpreter
* Reinstall using: python -m pip install ...

### Server not reachable

* Ensure Flask server is running
* Check correct port

### Port already in use

```
python app.py --port=5001
```

---


---

## 🎯 Real-World Use Cases

* Customer feedback analysis
* Product review monitoring
* Event evaluation systems
* Chat moderation
* Survey analytics
* Social media sentiment tracking

