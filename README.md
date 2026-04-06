# Sentiment Analysis Server

A lightweight, robust Sentiment Analysis Server built with **Python Flask** and **NLTK (Natural Language Toolkit)**. This server provides an API to analyze the sentiment of one or multiple sentences using the VADER (Valence Aware Dictionary and sEntiment Reasoner) Lexicon.

## 🚀 Live Demo
- **API Endpoint:** [https://sentimentserver.onrender.com](https://sentimentserver.onrender.com)
- **Interactive Web Tester:** [https://sentimentserver.onrender.com/test](https://sentimentserver.onrender.com/test)

## ✨ Features
- **Batch Processing:** Analyze multiple sentences in a single request.
- **Detailed Metrics:** Provides Positive, Negative, Neutral, and Compound scores.
- **Web Interface:** Includes a built-in UI for quick testing.
- **Developer Friendly:** Simple REST API that can be integrated with any frontend or backend.

## 🛠️ Tech Stack
- **Backend:** Flask (Python)
- **Sentiment Engine:** NLTK Vader
- **Frontend:** HTML, Bootstrap, jQuery (for testing interface)
- **Deployment:** Render

## 📥 Local Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Satish-Tiwari/sentiment-server.git
   cd sentiment-server
   ```

2. **Create and activate a virtual environment:**
   ```bash
   python -m venv venv
   # On Windows:
   .\venv\Scripts\activate
   # On macOS/Linux:
   source venv/bin/activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the server:**
   ```bash
   python app.py
   ```
   The server will start at `http://127.0.0.1:5000`.

## 📡 API Usage

### 🔍 Analyze Sentences
- **URL:** `/`
- **Method:** `POST`
- **Headers:** `Content-Type: application/json`
- **Body:** 
  ```json
  {
    "sentences": [
      "I love this project!",
      "This is a bad day.",
      "The weather is neutral today."
    ]
  }
  ```

- **Response:**
  ```json
  [
    { "neg": 0.0, "neu": 0.192, "pos": 0.808, "compound": 0.6696 },
    { "neg": 0.538, "neu": 0.462, "pos": 0.0, "compound": -0.5423 },
    { "neg": 0.0, "neu": 1.0, "pos": 0.0, "compound": 0.0 }
  ]
  ```

## 💻 Code Examples

### Python
```python
import requests

url = "https://sentimentserver.onrender.com"
data = {
    "sentences": ["Python is amazing!", "I am feeling great."]
}

response = requests.post(url, json=data)
print(response.json())
```

### Node.js (Axios)
```javascript
const axios = require('axios');

const url = "https://sentimentserver.onrender.com";
const data = {
    sentences: ["JavaScript is powerful.", "Errors are frustrating."]
};

axios.post(url, data)
    .then(response => console.log(response.data))
    .catch(error => console.error(error));
```

## 📝 License
This project is open-source and available under the [MIT License](LICENSE).
