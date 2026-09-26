# Customer_Comfort_AI

**Customer Comfort AI** is an AI-powered customer support system that detects customer emotions, identifies urgency, and generates smart support responses and tickets — helping support teams respond faster and with more empathy.

## ✨ Features

- 🧠 **Emotion Detection** — Analyzes customer messages to identify the primary emotion and its intensity (1–10)
- 🚨 **Urgency & Frustration Flagging** — Automatically flags whether a message needs urgent attention or shows signs of frustration
- 💡 **Smart Response Generation** — Suggests a polite, context-aware customer-service reply
- 🌐 **Simple Web Interface** — Lightweight HTML/CSS/JS frontend for submitting and viewing analysis
- ⚡ **FastAPI Backend** — REST API powered by FastAPI, using the Featherless AI (Qwen2.5-7B-Instruct) model for analysis

## 🏗️ Tech Stack

**Backend:** Python, FastAPI, Uvicorn, Requests, python-dotenv
**Frontend:** HTML, CSS, JavaScript
**AI Model:** Qwen2.5-7B-Instruct via [Featherless AI](https://featherless.ai) API

## 📂 Project Structure

```
Customer-Comfort/
├── app.py              # FastAPI backend (emotion analysis API)
├── index.html          # Frontend UI
├── script.js           # Frontend logic
├── style.css           # Frontend styling
├── requirements.txt    # Python dependencies
├── scripts/            # Supporting scripts
├── pack/               # Additional resources
└── .env                # Environment variables (API key) — not committed
```

## ⚙️ Setup & Installation

### Prerequisites
- Python 3.9+
- A [Featherless AI](https://featherless.ai) API key

### 1. Clone the repository
```bash
git clone https://github.com/dasaricharishmaa-19/Customer-Comfort.git
cd Customer-Comfort
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Configure environment variables
Create a `.env` file in the project root:
```
FEATHERLESS_API_KEY= my api key
```

### 4. Run the backend server
```bash
uvicorn app:app --reload
```
The API will be available at `http://127.0.0.1:8000`

### 5. Open the frontend
Open `index.html` in your browser (or serve it with a simple static server) to interact with the app through the UI.

## 🔌 API Reference

### `GET /`
Health check — confirms the backend is running.

**Response:**
```json
{
  "message": "Customer Comfort AI backend is running!",
  "status": "success"
}
```

### `POST /analyze`
Analyzes a customer message and returns emotion, urgency, and a recommended response.

**Request body:**
```json
{
  "text": "I've been waiting three days for a refund and no one has replied!"
}
```

**Response:**
```json
{
  "success": true,
  "input": "I've been waiting three days for a refund and no one has replied!",
  "analysis": "Emotion: Frustration\nIntensity: 8/10\nMood: Negative\nFrustrated: Yes\nUrgent: Yes\nReason: Delayed refund with no communication\nRecommended Response: ..."
}
```

## 🚀 Future Improvements
- Persist analyzed messages and auto-generate support tickets
- Dashboard for support agents to track flagged/urgent conversations
- Multi-language emotion detection
- Authentication for the API


## 🙋 Author
Built by [Anjana Devi](https://github.com/AnjanaDevi2006/)
```
