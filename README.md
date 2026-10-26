# DevOps Capstone Project

Small Flask service used to demonstrate GitHub Actions and Tekton CI.

## Local validation

```bash
pip install -r requirements.txt
flake8 app.py test_app.py
nose2 -v
python app.py
```

The service listens on port 8080 and exposes `/` and `/health`.

## OpenShift deployment

The manifests in `openshift/` deploy the container and expose it through a
Route. The Tekton resources in `.tekton/` provide the cleanup and nose test
tasks used by the CI pipeline.

```bash
oc new-project devops-capstone
oc apply -f openshift/deployment.yml
oc apply -f openshift/service.yml
oc apply -f openshift/route.yml
oc get route devops-capstone
```
