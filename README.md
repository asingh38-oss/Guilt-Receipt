# The Guilt Receipt

A week of your habits, handed back to you as a bill.

Enter your driving, food, water, and energy usage — the app converts it into real dollars, real gallons, and real hours of your life. No carbon math, no preachy stats. Just the actual cost of your week.

---

## Running locally

```bash
pip install -r requirements.txt
streamlit run app.py
```

---

## Project structure

```
├── app.py                  # Streamlit frontend — live receipt, comparison charts, history UI
├── requirements.txt
├── test_calculator.py      # Sanity checks on all calculation logic
├── .streamlit/
│   └── config.toml         # Dark theme config
└── utils/
    ├── calculator.py       # Core math — driving, food, water, energy, savings
    ├── constants.py        # All EPA/USDA/EIA conversion factors
    ├── history.py          # Session state receipt history, JSON import/export
    └── pdf_generator.py    # ReportLab PDF receipt generator
```

---

## How the numbers work

All conversion factors are hardcoded from published government sources — no AI, no estimation. Every figure is citable.

| Factor | Source | Value |
|--------|--------|-------|
| Cost per mile (driving) | IRS 2024 | $0.21/mile |
| Water per beef meal | USDA | 660 gal |
| Water per chicken meal | USDA | 330 gal |
| Water per vegetarian meal | USDA | 75 gal |
| Water per shower minute | EPA WaterSense | 2.1 gal/min |
| AC energy use | DOE avg | 1.5 kWh/hr |
| Electricity rate | EIA 2024 US avg | $0.13/kWh |

---

## Team

| Person | Contribution |
|--------|-------------|
| **Aditya** | `app.py` frontend, `calculator.py`, `pdf_generator.py`, Streamlit/backend integration |
| **Nirav** | Repo ownership, deployment to Streamlit Community Cloud, main branch management |
| **Josh** | `history.py` receipt history system, JSON export/import, session state management |

---

## Stack

Python · Streamlit · Plotly · ReportLab · EPA / USDA / EIA data

Built at the Cofoundr × SOE Hackathon, March 2026.
