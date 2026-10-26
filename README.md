# FareCast-ML ✈️

End-to-end machine learning pipeline and Flask web app that predicts flight fares from route, airline, date and time inputs.

## Highlights
- Modular training pipeline: ingestion → transformation → training → evaluation
- Experiment tracking with MLflow (RMSE, MAE, R²)
- Reproducible pipeline stages and data versioning with DVC
- Flask web UI for live fare prediction
- Dockerized, with a CI workflow in `.github/workflows`

## Tech Stack
Python, Pandas, NumPy, Scikit-learn, Seaborn, Matplotlib, Flask, DVC, MLflow, Docker

## Project Structure
```
├── src/FlightPricePrediction/   # components, pipelines, utils, logger
├── Notebook_Experiments/        # EDA and model experiments
├── templates/, static/          # Flask UI
├── app.py                       # web app entry point
├── dvc.yaml                     # pipeline stages
├── Dockerfile
└── requirements.txt
```

## Getting Started
```bash
git clone https://github.com/codeitwithaayush/FareCast-ML.git
cd FareCast-ML
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
python app.py
```
Open http://localhost:5000

### Optional: remote MLflow tracking
```bash
set MLFLOW_TRACKING_URI=<your-mlflow-server-url>
```
If unset, runs are logged locally to `./mlruns`.

### Docker
```bash
docker build -t farecast-ml .
docker run -p 5000:5000 farecast-ml
```

## Credits and License
Based on [KalyanM45/Flight-Fare-Prediction](https://github.com/KalyanM45/Flight-Fare-Prediction). Modified and maintained by [Aayush](https://github.com/codeitwithaayush).

Licensed under the **GNU GPL v3.0**. See `LICENSE`.