# 🤖 Saarthi AI
### Autonomous Multi-Agent Research and Report Generation System

> Built by **Shreyash Padwal**

Saarthi AI is a powerful AI-powered research assistant that can take any question and autonomously search the web, analyze sources, and generate a detailed, well-structured research report — all in one click. It uses multiple AI agents working together behind the scenes powered by Groq LLMs and Tavily web search.

---

## ✨ What It Does

You type a question like *"What are the latest breakthroughs in quantum computing?"* and Saarthi AI:

1. 🧠 **Plans** the research strategy
2. 🔍 **Searches** the web using Tavily
3. 📖 **Reads & summarizes** multiple sources
4. 🗜️ **Compresses** the research findings
5. ✍️ **Writes** a full detailed report
6. 📄 **Exports** it as a colorful PDF — in seconds

---

## 🖥️ Features

- **Beautiful Web UI** — Clean, modern interface with dark/light theme
- **5 Pages** — Home, Research, History, About, Settings
- **Research History** — All reports saved permanently in browser
- **PDF Export** — Colorful, branded PDF with cover page, tables, headings
- **Copy & Download** — Copy report text or download as `.md` file
- **Multi-Agent Pipeline** — Multiple specialized AI agents working in parallel
- **Groq Powered** — Super fast inference using Groq LLMs
- **Tavily Search** — Real-time web search for up-to-date information

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **AI Agents** | LangGraph (multi-agent orchestration) |
| **LLM** | Groq (`openai/gpt-oss-120b`) |
| **Web Search** | Tavily API |
| **Backend** | LangGraph Server (Python) |
| **Frontend** | Vanilla HTML/CSS/JS (no framework needed) |
| **PDF Generation** | jsPDF + jsPDF-AutoTable (browser-side) |

---

## 🚀 Getting Started

### 1. Clone the repo
```bash
git clone https://github.com/shreyashpadwal/SaarthiAI.git
cd SaarthiAI
```

### 2. Create virtual environment & install dependencies
```bash
uv venv
.venv\Scripts\activate       # Windows
# or
source .venv/bin/activate    # Mac/Linux

uv sync
```

### 3. Set up your API keys
```bash
cp .env.example .env
```

Edit `.env` and add your keys:
```
GROQ_API_KEY=your_groq_api_key_here
TAVILY_API_KEY=your_tavily_api_key_here
```

> Get your free keys at:
> - Groq → https://console.groq.com
> - Tavily → https://app.tavily.com

### 4. Start the backend (AI agents server)
```bash
.venv\Scripts\langgraph.exe dev --allow-blocking
```
Backend runs at → `http://127.0.0.1:2024`

### 5. Start the frontend (Web UI)
Open a new terminal:
```bash
cd ui
python -m http.server 8080
```
Open your browser → `http://localhost:8080`

---

## 📁 Project Structure

```
SaarthiAI/
├── src/
│   └── open_deep_research/
│       ├── deep_researcher.py   # Main agent graph
│       ├── configuration.py     # Model & search config
│       ├── prompts.py           # Agent prompts
│       ├── state.py             # Graph state
│       └── utils.py             # Helper utilities
├── ui/
│   └── index.html               # Full Saarthi AI web interface
├── .env.example                 # Environment variables template
├── langgraph.json               # LangGraph config
├── pyproject.toml               # Python dependencies
└── README.md
```

---

## 🎨 UI Preview

The Saarthi AI interface includes:

- **Home Page** — Stats, features, how-it-works guide
- **Research Page** — Chat interface for asking questions
- **History Page** — All past research reports (saved in browser)
- **About Page** — Tech stack info and FAQ
- **Settings Page** — Model selection and configuration

### PDF Export
Every report can be exported as a colorful PDF with:
- Gradient cover page with Saarthi AI branding
- Color-coded headings (Purple H1, Teal H2, Orange H3)
- Auto-formatted tables with purple headers
- Bullet points, numbered lists, blockquotes
- Page numbers and branded footer on every page

---

## ⚙️ Configuration

You can configure these settings from the **Settings page** in the UI:

| Setting | Default | Description |
|---|---|---|
| Research Model | `groq:openai/gpt-oss-120b` | Main research agent LLM |
| Summarization Model | `groq:openai/gpt-oss-120b` | Summarizes search results |
| Concurrent Searches | `1` | Parallel search queries |
| Allow Clarification | `false` | Ask before researching |

---

## 🤝 How the Agents Work

```
User Question
      ↓
  Planner Agent        ← Decides what to search
      ↓
  Search Agent         ← Searches web via Tavily
      ↓
  Summarizer Agent     ← Reads and summarizes sources
      ↓
  Compression Agent    ← Condenses findings
      ↓
  Writer Agent         ← Writes the final report
      ↓
  Beautiful Report + PDF
```

---

## 📝 License

MIT License — feel free to use and modify.

---

## 👨‍💻 Author

**Shreyash Padwal**
- GitHub: [@shreyashpadwal](https://github.com/shreyashpadwal)

---

*Made with ❤️ using LangGraph, Groq, and Tavily*
