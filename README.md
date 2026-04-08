# 🏗️ Worker License Dashboard

> **Paste a URL. Hit fetch. Watch the data roll in.** A slick, no-nonsense dashboard for exploring JSON data — built specifically for NYC Open Data worker license records (but flexible enough to handle any JSON endpoint you throw at it).

---

## ✨ What Is This?

The **Worker License Dashboard** is a lightweight Flask web app that acts as your personal data explorer. Drop in any JSON API endpoint, click **Fetch Data**, and instantly get a clean, readable table with human-friendly column labels, emoji-tagged headers, and zebra-striped rows that make scanning data a joy.

No spreadsheets. No copy-pasting into Excel. Just you, a URL, and your data.

---

## 🚀 Features

| Feature | Details |
|---|---|
| 🔍 **One-click data fetch** | Paste any JSON endpoint URL and fetch live data instantly |
| 📌 **Saved URLs** | Bookmark your favourite endpoints in localStorage — they survive page reloads |
| 🗑️ **URL management** | Delete saved URLs you no longer need |
| 📊 **Auto-rendered table** | Fields are automatically mapped to readable, emoji-labelled column headers |
| 🎨 **Bold, playful UI** | Neobrutalist design — thick borders, punchy orange & navy palette, satisfying button clicks |
| 🌐 **Backend proxy** | The Flask server fetches JSON server-side, so you never have to worry about CORS |
| ☁️ **Deploy-ready** | Ships with a `Procfile` for instant Heroku / Railway deployment |

---

## 🖥️ Tech Stack

- **Backend:** Python 3 + [Flask](https://flask.palletsprojects.com/)
- **HTTP Client:** [Requests](https://docs.python-requests.org/)
- **Production Server:** [Gunicorn](https://gunicorn.org/)
- **Frontend:** Vanilla HTML/CSS/JavaScript (zero dependencies, zero bloat)
- **Storage:** Browser `localStorage` for saved URLs

---

## 🛠️ Getting Started

### Prerequisites

- Python 3.8+
- `pip`

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

Then open your browser and head to **http://localhost:5000** 🎉

---

## 🌍 Deploying to Heroku / Railway

The `Procfile` is already set up. Just push and go:

```bash
# Heroku
heroku create
git push heroku main

# Railway
railway up
```

The app reads the `PORT` environment variable automatically, so no extra config needed.

---

## 🔌 API Reference

### `POST /api/fetch-json`

Fetches a remote JSON endpoint server-side and returns the data.

**Request body:**
```json
{
  "url": "https://data.cityofnewyork.us/api/v3/views/t8hj-ruu2/query.json?pageNumber=1&pageSize=500&app_token=BHkxm74M2ivCagGkeGmAhbtjb"
}
```

**Success response:**
```json
{
  "success": true,
  "data": [ ... ]
}
```

**Error response:**
```json
{
  "success": false,
  "error": "Connection timed out"
}
```

---

## 📋 Supported Data Fields

The dashboard knows how to label these fields out of the box (great for NYC Open Data worker license endpoints):

| Raw Field | Display Label |
|---|---|
| `license_type` | 📂 License Type |
| `license_number` | 🪪 License No. |
| `first_name` / `last_name` | 👤 Name |
| `business_name` | 🏢 Business Name |
| `license_status` | ✅ Status |
| `business_email` | 📧 Email |
| `business_phone_number` | 📞 Phone |
| `lat` / `long` | 🌐 Coordinates |
| …and more! | — |

Any fields not in the mapping are still displayed as-is.

---

## 📁 Project Structure

```
matrix/
├── matrix.py          # Flask app — routes & backend proxy logic
├── requirements.txt   # Python dependencies
├── Procfile           # Process file for Heroku/Railway deployment
└── templates/
    └── index.html     # Single-page frontend (HTML + CSS + JS)
```

---

## 🧠 How It Works

```
Browser  ──POST /api/fetch-json──▶  Flask (matrix.py)
                                         │
                                         │  requests.get(url)
                                         ▼
                                    Remote JSON API
                                         │
                                         │  JSON response
                                         ▼
Browser  ◀──── JSON data ────────  Flask (matrix.py)
    │
    │  renderTable()
    ▼
 📊 Formatted HTML table
```

The backend acts as a proxy — this means **no CORS issues**, ever. The frontend never touches the remote API directly.

---

## 🎨 UI Preview

The dashboard sports a bold **neobrutalist** aesthetic:

- 🟠 **Orange** (`#FF6B35`) — primary action colour
- 🔵 **Navy** (`#004E89`) — structural colour, table headers
- 🟡 **Amber** (`#F77F00`) — accents and shadows
- 🟤 **Warm cream** (`#FFFBF0`) — table row backgrounds

Thick borders, hard drop shadows, and snappy button transitions make every interaction feel satisfying.

---

## 🤝 Contributing

Got an idea? Found a bug? PRs are welcome!

1. Fork the repo
2. Create a feature branch: `git checkout -b feature/my-cool-idea`
3. Commit your changes: `git commit -m 'Add my cool idea'`
4. Push and open a PR

---

## 📜 License

This project is open source. Do cool things with it. 🚀

---

<p align="center">Built with ☕ and a love for clean data</p>
