# Nexus AI 🤖

Claude-powered team chat tool built with FastAPI.

🚀 **Live Demo:** https://nexus-ai-production-494b.up.railway.app

## ✨ Features

- 💬 **Chat with AI** — powered by Anthropic Claude
- 📁 **File Upload** — images, PDFs, code files (.py, .js, .json etc), Word (.docx), Excel (.xlsx)
- 🖼️ **Image Vision** — Claude reads and analyzes images
- 📄 **PDF Reading** — Claude reads full PDF documents
- 🧠 **Session Memory** — follow-up questions remember context
- 💾 **Supabase Storage** — chats saved permanently, survive refresh
- 📋 **Copy Button** — copy any AI response instantly
- 🌙 **Dark / Light Mode** — toggle anytime
- 📱 **Fully Responsive** — works on mobile, tablet, desktop
- 🖱️ **Drag & Drop** — drag files directly into chat
- 📋 **Paste Images** — Ctrl+V to paste screenshots

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Backend | FastAPI (Python) |
| Frontend | Vanilla HTML + CSS + JS |
| AI | Anthropic Claude API |
| Database | Supabase (PostgreSQL) |
| Deploy | Render.com |

---

## 📦 Supported File Types

| Type | Extensions |
|---|---|
| Images | `.jpg` `.png` `.gif` `.webp` |
| Documents | `.pdf` `.docx` `.xlsx` |
| Code | `.py` `.js` `.ts` `.html` `.css` `.json` `.sql` and 30+ more |
| Text | `.txt` `.md` `.csv` `.yaml` `.env` |

---

## 🚀 Local Setup

### 1. Clone the repo

```bash
git clone https://github.com/YOUR_USERNAME/nexus-ai.git
cd nexus-ai
```

### 2. Create virtual environment

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Mac/Linux
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Create `.env` file

```env
ANTHROPIC_API_KEY=your_anthropic_api_key
ANTHROPIC_BASE_URL=your_base_url
ANTHROPIC_MODEL=claude-sonnet-4-6
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_KEY=your_anon_public_key
```

### 5. Create Supabase table

Go to your Supabase dashboard → SQL Editor → run:

```sql
create table sessions (
  session_id text primary key,
  name text,
  messages jsonb not null default '[]',
  api_messages jsonb not null default '[]',
  created_at timestamptz default now(),
  updated_at timestamptz default now()
);
```

### 6. Run the server

```bash
uvicorn main:app --reload
```

Open `http://localhost:8000`

---

## ☁️ Deploy on Render

1. Push code to GitHub
2. Go to [render.com](https://render.com) → New → Web Service
3. Connect your GitHub repo
4. Set these:
   - **Build Command:** `pip install -r requirements.txt`
   - **Start Command:** `uvicorn main:app --host 0.0.0.0 --port 10000`
5. Add environment variables (same as `.env`)
6. Deploy ✅

---

## 📁 Project Structure

```
nexus-ai/
├── static/
│   └── index.html      # Frontend (HTML + CSS + JS)
├── main.py             # FastAPI backend
├── requirements.txt    # Python dependencies
├── .env                # API keys (never commit this)
└── .gitignore
```

---

## 🔒 Security Notes

- Never commit `.env` to GitHub
- `.gitignore` already excludes it
- Supabase anon key is safe for client use (row-level security can be added later)

---

## 🗺️ Roadmap

- [x] Chat with Claude
- [x] File upload (image, PDF, code, docx, xlsx)
- [x] Session save/load with Supabase
- [x] Copy message button
- [x] Dark/Light mode
- [x] Fully responsive UI
- [ ] Streaming responses
- [ ] User authentication
- [ ] File download generation (PDF/DOCX output)

---

## 📸 Screenshots

> *Coming soon*

---

## 🎬 Demo Video

> *Coming soon*

---

## 📄 License

MIT License — free to use and modify.
