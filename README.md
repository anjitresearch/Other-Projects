# Hack Summit 2025
What’s inside

services/api – FastAPI scoring service (/score, /health)

services/dashboard – Streamlit dashboard (risk table + bar chart + quick text scoring)

models – Tiny TF-IDF + Logistic Regression classifier, simple risk engine

ingestion – Scraper stub + ETL normalization

graph – NetworkX demo graph

data – Tamil Nadu sample CSVs (district priors, sample posts)

docker-compose.yml – One command to run API + dashboard

requirements.txt, README.md, LICENSE
----------------------------------------------------------------------------------------------
Run locally
----------
python -m venv .venv && source .venv/bin/activate    # Windows: .venv\Scripts\activate
pip install -r requirements.txt
python models/nlp_classifier.py                       # optional: train tiny model
uvicorn services.api.main:app --reload --port 8000
streamlit run services/dashboard/app.py

Or with Docker
-------------
docker compose up --build


Final:
-----

API → http://localhost:8000

Dashboard → http://localhost:8501
