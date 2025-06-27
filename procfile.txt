# Procfile (for Heroku deployment)
web: gunicorn app:app

---

# runtime.txt (for Heroku - specify Python version)
python-3.9.18

---

# railway.toml (for Railway deployment)
[build]
builder = "NIXPACKS"

[deploy]
startCommand = "gunicorn app:app"

---

# render.yaml (for Render deployment)
services:
  - type: web
    name: crop-yield-predictor
    env: python
    buildCommand: "pip install -r requirements.txt"
    startCommand: "gunicorn app:app"
    plan: free