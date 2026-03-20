# AdvisorIQ — Portfolio Intelligence

**Hackathon submission: "Data in Finance"**

## VolSSM

## HMM Vol Regime

## Repository Structure

```
advisoriq/
├── config/
│   ├── settings.py       # All parameters: tickers, dates, thresholds, model hyperparams
│   └── clients.py        # 5 client profiles with distinct risk tolerances
├── src/
│   ├── models/
│   │   ├── vol_ssm.py    # Layer A: S5-based volatility forecaster (unchanged from notebook)
│   │   └── hmm_regime.py # Layer B: HMM regime classifier (unchanged from notebook)
│   ├── data/
│   │   ├── pipeline.py   # Data ingestion, cleaning, caching (Steps 1-8)
│   │   ├── features_a.py # 8-channel feature engineering for VolSSM
│   │   └── features_b.py # 6-feature macro engineering for HMM
│   ├── training/
│   │   ├── train_vol_ssm.py  # Per-ticker VolSSM training pipeline
│   │   └── train_hmm.py      # HMM regime classifier training
│   ├── inference/
│   │   ├── signal_engine.py  # IVR computation + regime-dependent thresholds
│   │   └── optimizer.py      # IV-adjusted covariance + portfolio optimisation
│   ├── llm/
│   │   └── narrator.py       # LLM integration for client explanations + chatbot
│   └── app/
│       └── server.py         # FastAPI backend serving all endpoints
├── ui/
│   └── dashboard.jsx         # React dashboard with client cards + chatbot
├── scripts/
│   ├── train.py              # CLI: train all models
│   └── serve.py              # CLI: launch application
├── artifacts/                # Generated: model checkpoints, cached data
└── requirements.txt
```
