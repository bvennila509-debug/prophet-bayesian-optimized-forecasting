# Prophet + Bayesian Optimization — Advanced Time Series Forecasting

A production-oriented, reproducible forecasting pipeline that uses **Prophet** for modeling and **Optuna** for Bayesian hyperparameter optimization. Designed to meet assessment requirements: synthetic/real dataset generation, robust rolling-origin cross-validation, efficient optimization, clear comparison vs baseline, and comprehensive documentation.

## Highlights
- Synthetic dataset generator with trend, multiple seasonalities, holidays, regressors.
- Baseline Prophet pipeline and Optuna-based Bayesian optimization with rolling CV.
- Modular code structure and run scripts for reproducibility.
- Comprehensive written report explaining dataset, methodology, hyperparameter search, convergence, performance, and computational cost vs accuracy trade-offs.
- Evaluation checklist matching assignment deliverables for direct submission.

## Quick start
```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# generate dataset
python data/generate_synthetic_ts.py --out data/ts_dataset.csv --n_periods 1200 --freq D

# run baseline (rolling CV)
python src/model_pipeline.py --data data/ts_dataset.csv --mode baseline --out results --n_splits 4 --horizon 30

# run optimization (Optuna)
python src/model_pipeline.py --data data/ts_dataset.csv --mode optimize --out results_opt --trials 50 --n_splits 3 --horizon 30
```

## Files of interest
- `data/generate_synthetic_ts.py` — dataset generator
- `src/model_pipeline.py` — baseline & optimization pipeline (single-file runnable)
- `report/report.md` — evaluation report and submission-ready narrative
- `results/` — generated CV and optimization outputs
- `screenshots/` — assignment screenshots (for reference)

## 350-character description (for README / marketplace)
This project builds a robust forecasting pipeline using Prophet and Bayesian Optimization (Optuna). It generates realistic time series with trend, seasonality, and regressors; uses rolling-origin CV; tunes hyperparameters; and produces a detailed report comparing baseline and optimized models, including computational cost trade-offs.
