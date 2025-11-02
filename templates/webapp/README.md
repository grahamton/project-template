# Web App Template (FastAPI + HTMX)

A minimal web UI for PromptKit. Run locally, then reverse‑proxy behind your existing site when ready.

## Install (once per machine)

- Create a virtual env (recommended):
  - `python -m venv .venv`
  - `./.venv/Scripts/Activate.ps1` (PowerShell)
- Install web deps:
  - `python -m pip install -e .`
  - `python -m pip install -r templates/webapp/requirements.txt`

## Run

- `uvicorn --app-dir templates webapp.main:app --reload --port 8000`
- Open `http://localhost:8000`

## Deploy (outline)

- Keep the app running on `127.0.0.1:8000` (e.g., `uvicorn` under a service)
- Add a reverse proxy rule on your existing web server to route a path (e.g., `/app`) to `http://127.0.0.1:8000`

## Notes

- Iterate supports optional JSON output. Toggle "JSON (Iterate only)" to see the JSON block and a download button.
- ASCII mode helps avoid Unicode issues in some terminals/browsers.
