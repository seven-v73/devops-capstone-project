# DevOps Capstone Project

Small Flask service used to demonstrate GitHub Actions and Tekton CI.

## Local validation

```bash
pip install -r requirements.txt
flake8 app.py test_app.py
python -m unittest discover -v
python app.py
```

The service listens on port 8080 and exposes `/` and `/health`.
