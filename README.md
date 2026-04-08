# 🏗️ Worker License Dashboard

> **Turn public licensing data into actionable leads.**
> A lightweight dashboard for discovering newly certified blue-collar professionals from public datasets — built to support targeted outreach and service-based businesses.

---

## 💡 Why This Exists

Public datasets (like NYC Open Data) contain **valuable, real-time information** about newly licensed workers — welders, contractors, technicians, and more.

These individuals often need:

* a website
* an online presence
* branding and digital services

But the data is:

* scattered across endpoints
* hard to read
* buried in raw JSON

**This tool solves that.**

---

## 🎯 Use Case

This dashboard was built as a **lead-generation tool**.

**Workflow:**

1. Paste a public data API (e.g. worker license records)
2. Instantly fetch and visualize the data
3. Scan for newly certified professionals
4. Identify potential clients for outreach

👉 Instead of digging through raw JSON or spreadsheets, you get **clean, structured, readable data in seconds**.

---

## ⚡ Features

| Feature                     | Details                                                            |
| --------------------------- | ------------------------------------------------------------------ |
| 🔍 **One-click data fetch** | Paste any JSON endpoint and instantly retrieve live data           |
| 📊 **Auto-rendered tables** | Converts raw JSON into structured, human-readable tables           |
| 📌 **Saved URLs**           | Store frequently used endpoints with `localStorage`                |
| 🗑️ **URL management**      | Add/remove data sources easily                                     |
| 🌐 **Backend proxy**        | Server-side fetching eliminates CORS issues entirely               |
| 🎨 **Custom UI**            | Neobrutalist design with strong visual hierarchy for fast scanning |
| ☁️ **Deploy-ready**         | Includes `Procfile` for Heroku/Railway deployment                  |

---

## 🧠 Key Insight

Most developers treat public data as informational.

This project treats it as **actionable business intelligence**.

It demonstrates how:

* open data → structured insight
* structured insight → targeted outreach
* targeted outreach → real opportunities

---

## 🖥️ Tech Stack

* **Backend:** Python + Flask
* **HTTP Client:** Requests
* **Server:** Gunicorn
* **Frontend:** Vanilla HTML, CSS, JavaScript
* **Storage:** Browser `localStorage`

---

## 🛠️ Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/DanIrl7/matrix.git
cd matrix
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the app

```bash
python matrix.py
```

Then open:
👉 http://localhost:5000

---

## 🔌 API

### `POST /api/fetch-json`

Fetch a remote JSON endpoint via the backend proxy.

**Request:**

```json
{
  "url": "https://data.cityofnewyork.us/resource/example.json"
}
```

**Response:**

```json
{
  "success": true,
  "data": [...]
}
```

---

## 🧩 How It Works

```
Browser → Flask API → External Data Source → Flask → Browser → Table UI
```

The backend acts as a **proxy layer**, ensuring:

* no CORS issues
* consistent data handling
* separation of concerns

---

## 📊 Supported Fields

Optimized for worker license datasets:

* License type / number
* Names (first + last)
* Business name
* Contact info (email, phone)
* Status
* Location (lat/long)

Unmapped fields are still displayed dynamically.

---

## 🎨 UI

Designed for **speed and clarity**:

* bold neobrutalist layout
* high-contrast colors
* structured tables for rapid scanning

---

## 🚀 Deployment

Ready for:

* Heroku
* Railway

```bash
git push heroku main
# or
railway up
```

---

## 🧠 What This Demonstrates

This project highlights:

* Full-stack development (Flask + frontend)
* API design and data handling
* Solving CORS via backend proxy architecture
* Transforming raw data into usable interfaces
* Applying engineering to real-world business problems

---

## 📜 License

Open source — use it, modify it, build on it.

---

<p align="center">Built with ☕ and a focus on real-world utility</p>
