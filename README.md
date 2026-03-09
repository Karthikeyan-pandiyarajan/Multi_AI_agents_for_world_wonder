# 🌍 World Wonders AI

AI‑powered travel planning platform built around a collection of specialized agents that work together to research, plan and book trips centered on the world’s greatest wonders. Uses a Groq-based LLM backend for inference.

---

## 🚀 What It Does

Each agent is responsible for a different facet of travel:

- **Wonder Scout** 🔍 – finds and researches wonders (natural, historical, cultural).
- **Itinerary Architect** 📅 – generates optimized, multi‑day travel plans.
- **Culture Chef** 🍽️ – suggests authentic dishes, restaurants, and food tours.
- **Safety Guardian** ⚠️ – supplies current safety, health, and entry advisories.
- **Master Concierge** ✨ – coordinates the others and provides an “all‑in‑one” assistant.
- **Weather Agent**, **Budget Agent**, etc. – extend the core with forecasting, cost estimates, etc.

The app can be driven via CLI or a Streamlit web front‑end.

---

## 🛠️ Installation & Setup

1. **Clone repo**  
   ```bash
   git clone https://github.com/your‑org/world-wonders-ai.git
   cd world-wonders-ai
   ```

2. **Create & activate a virtual env**  
   ```bash
   python -m venv venv
   # Windows
   venv\\Scripts\\activate
   # macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure credentials**  
   Create a `.env` at project root and add your Groq API key (or other service keys):
   ```
   GROQ_API_KEY=sk‑…
   ```

5. **(Optional) Additional config**  
   Modify `config/settings.py` for timeout values, agent parameters, and the LLM switch to Groq.

---

## ▶️ Running the App

| Interface | Command |
|-----------|---------|
| CLI        | `python main.py` |
| Web UI     | `streamlit run app.py` |
| Examples   | see `learning_example*.py` for sample agent workflows |

---

## 🧩 Architecture Overview

```
world-wonders-ai/
├── agents/              # agent classes and logic
│   ├── base_agent.py
│   ├── wonder_scout.py
│   ├── itinerary_architect.py
│   └── … 
├── config/settings.py   # global settings and defaults
├── main.py              # CLI entry point
├── app.py               # Streamlit front‑end
├── requirements.txt
└── README.md            # ← you are here
```

- Agents inherit from `BaseAgent` and implement `act()`/`respond()` patterns.
- `master_concierge.py` orchestrates multi‑agent workflows.
- The examples (e.g. `learning_example_3_agent_as_tools.py`) demonstrate using agents as tools.

---

## 📦 Dependencies

- Python ≥ 3.8
- `groqai` or the chosen Groq SDK for LLM access
- `streamlit` (for web UI)
- Other libs listed in `requirements.txt`

---

## 🧪 Testing & Development

- Add new agents under `agents/` and export them via `__init__.py`.
- Run examples or write unit tests (`pytest`‑based if added).
- Use `python -m pdb main.py` for debugging.

---

## 📄 Contributing

1. Fork, make a feature branch.
2. Add tests/examples.
3. Submit a PR and describe your agent/feature.

---

## 📝 License

MIT License  
See [LICENSE](LICENSE) for details.

---

> 💡 *Tip:* the `AGENTS_AS_TOOLS_GUIDE.md` contains guidance on exposing agents to other processes as callable tools.

