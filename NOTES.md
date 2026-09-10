# Portfolio Improvement Notes

Status as of **2026-09-10**.

## What was just done

- Added **Electric Grid Load Forecasting** card (time series, Random Forest, 12 PJM regions, 1–168h recursive forecasting, FastAPI + Reflex UI)
- Added **Travel Africa RAG Assistant** card (pgvector, ONNX MiniLM embeddings, DeepSeek, 1,459 hotels across Kenya / Tanzania / Uganda)
- Fixed broken LinkedIn URL in hero and footer (was missing `https://`, so it resolved as a relative path)
- Renumbered ML section card comment markers to run 1–12

---

## The core problem

The portfolio is currently a **catalogue of 12 cards**: a title, a paragraph, and a GitHub link. That's broad but shallow.

Recruiters decide in roughly **90 seconds**. The consistent finding in hiring research is that **3–5 deep projects beat 12 shallow ones** — and that you cannot merely *state* ML ability, you have to *show* it. Right now a recruiter has to leave this site, land on GitHub, read a README, and imagine what was built.

The four pillars hiring teams look for are **data wrangling, visualisation, modelling, and communication**. This portfolio evidences the first three. It shows **zero communication**. That is the gap.

---

## TODO — priority order

### 1. Build 3 case study pages ← biggest win, zero hosting needed

Pick the three strongest projects and give each a **dedicated HTML page**:

- Electric Grid Load Forecasting
- Travel Africa RAG Assistant
- Child Malnutrition Risk Prediction

Each page should cover:

- **The problem** — framed in real-world terms, not "I used Random Forest"
- **The data** — source, size, how messy it was
- **Approach and why** — why RF over LSTM, why a chronological split, why SMOTE
- **Results with numbers** — R², F1, MAE, plus a chart
- **Honest limitations** — a major trust signal, and specifically called out in hiring guides as the impressive part
- **What I'd do next** — signals engineering maturity

Then change the card click target from GitHub to `/projects/<name>.html`.

*Rationale: covers "communication", requires no server, no cost, and converts "here are 12 things I followed" into "here are 3 things I understand".*

### 2. Add at least one live interactive demo

The advice is explicit: **you need at least one live, interactive demo.** Options, cheapest first:

- Embed a **static Plotly forecast curve** for the Grid card — no server required, data as a JSON blob in the page. Screenshots already exist in `SMART_GRID_LOAD_FORECASTING/photos/`
- Deploy the **Travel Africa RAG** assistant as a live chat. FastAPI backends already exist, and `RAG_PROJECT` already has a `render.yaml`

### 3. Fix the 90-second problem (cheap, high return)

- [ ] **Hero stat strip** — e.g. `12 projects · 1M+ rows modelled · 5 deployed APIs · BSc Elec. Eng.`
- [ ] **Clickable tag filters** — the cards already carry tags (Python, FastAPI, RAG…) but they do nothing
- [ ] **"Selected Work" row** — 3 featured cards above the full grid, visually larger
- [ ] **Downloadable CV button** — the PDF is on the Desktop as `Cyrus 2026 Elect Resume.pdf`

### 4. Polish

- [ ] `README.md` is still `# Hello,welcome to my website` — this is a `github.io` repo, so it's the first thing visitors see
- [ ] Add **Open Graph meta tags** so LinkedIn / WhatsApp link previews aren't blank
- [ ] Add **print styles** to the resume page

---

## Local preview

No server needed — it's a self-contained single file:

```
cd D:\Users\user\PycharmProjects\CyrusNdungu_Portfolio
```

Then double-click `index.html`.

Or serve it, if you prefer a real URL:

```bash
python3 -m http.server 8899
```
