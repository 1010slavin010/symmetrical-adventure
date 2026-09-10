# AgroSentry — Farm Ops Dashboard (Streamlit App)

Multi-page dashboard: AI assistant, sensor readings, flood/drought alerts, camera feed, and AI disease detection — behind a shared-password login, with a dark pill-nav theme.

## Run locally
```bash
pip install -r requirements.txt
cp .streamlit/secrets.toml.example .streamlit/secrets.toml
streamlit run Home.py
```

## Login
Set `APP_PASSWORD` in `.streamlit/secrets.toml`. If it is not set, the demo fallback is `farm2026`.

## Hardware
Set the ESP32/Raspberry Pi base URL in the Home sidebar. The expected routes are:
- `GET /data` — sensor JSON
- `GET /capture` — JPEG camera snapshot

## Disease model
Place the trained model under `model/`. The source project expects `model/plant_disease_model.h5` for the current Streamlit disease page.

## Deployment
Use `Home.py` as the Streamlit entry point and configure secrets in the hosting provider rather than committing `secrets.toml`.
