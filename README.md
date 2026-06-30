## 📦 Helm Chart Repository

### GitHub Repository
🔗 Source Code:
https://github.com/liteshz1778/helm-charts

### Helm Repository
🔗 Helm Chart URL:
https://liteshz1778.github.io/helm-charts/

### Docker Hub Repository
🔗 Docker Hub: https://hub.docker.com/repository/docker/liteshz/python-demo-flask-app/general

---

## 📦 Helm Chart Installation

### Add Helm repository:

```
helm repo add liteshz https://liteshz1778.github.io/helm-charts/
helm repo update
```

### Install PyCloudOps Application:

```
helm install pycloudops-app liteshz/pycloudops-app
```

---

<!---------------------


### Creating package from helm chart
helm package {{ helm_chart_name }}

### Creating index.yaml & also for the newly created helm chart entry to be added in index.yaml file
helm repo index .

### Creating & adding repo to our local system
helm repo add liteshz https://liteshz1778.github.io/helm-charts/

### List out the helm repo's
helm repo list

### Installing Application
helm install pycloudops-app liteshz/pycloudops-app --version 0.5.0

### List out the helm release's
helm list

### Upgrading the pycloudops-app
helm upgrade pycloudops-app liteshz/pycloudops-app --version 0.17.0

### List out the revisions of pycloudops-app release
helm history pycloudops-app

### Rollback to previous revisions
 helm rollback pycloudops-app {{ revision_no }}

### Uninstall Release
helm uninstall pycloudops-app

### Remove repo
helm repo remove liteshz


----------->
