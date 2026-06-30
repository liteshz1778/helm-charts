## Overview

**PyCloudOps Application** is a demo cloud-native application designed to demonstrate the deployment and management of a Flask-based web application with a MySQL database using Kubernetes and Helm.

The application allows users to store and manage user information such as **username and email details** and provides a web interface to display the stored data.

This Helm chart packages the complete application stack, including:
- Flask Web Application
- MySQL Database
- Kubernetes Deployment & Services
- Persistent Storage Configuration
- Application Configuration Management
- Secret Management

---

## 🏗️ Architecture

```text
                         👥 End Users
                              |
                              |
                              v
                    +-------------------+
                    |  Kubernetes Node  |
                    |                   |
                    |  NodePort Service |
                    |    Port: 5000     |
                    +-------------------+
                              |
                              |
                              v
                 +-------------------------+
                 |   Flask Web Application |
                 |     (Python Flask)      |
                 |                         |
                 |  Deployment             |
                 |  Replica: 1             |
                 +-------------------------+
                              |
                              |
             +----------------+----------------+
             |                                 |
             v                                 v

+-------------------------+          +-------------------------+
|   ConfigMap             |          |   Kubernetes Secret     |
|                         |          |                         |
| Application Config      |          | MySQL Credentials       |
| DB Host                 |          | Username / Password     |
+-------------------------+          +-------------------------+


                              |
                              |
                              v

                 +-------------------------+
                 |   MySQL Database        |
                 |                         |
                 | StatefulSet             |
                 |                         |
                 | Headless Service        |
                 | Port: 3306              |
                 +-------------------------+
                              |
                              |
                              v

                 +-------------------------+
                 | Persistent Storage      |
                 |                         |
                 | PersistentVolume (PV)   |
                 | PersistentVolumeClaim  |
                 | StorageClass            |
                 +-------------------------+

```

---

## ✨ Features

- ✅ Flask-based Python web application
- ✅ MySQL database integration
- ✅ Kubernetes Deployment & StatefulSet
- ✅ Persistent Volume and Storage Class support
- ✅ ConfigMap based application configuration
- ✅ Kubernetes Secret based credential management
- ✅ Helm based application deployment
- ✅ Easy upgrade and rollback support

---

## 🛠️ Technology Stack

| Component | Technology |
|-----------|------------|
| Application | Python Flask |
| Database | MySQL |
| Container Runtime | Docker |
| Container Orchestration | Kubernetes |
| Package Manager | Helm |
| Configuration | YAML / ConfigMap |
| Secrets Management | Kubernetes Secrets |
| Storage | Persistent Volume (PV/PVC) |

---

## 📦 Helm Chart Installation

### Add Helm Repository
helm repo add liteshz https://liteshz1778.github.io/helm-charts
helm repo update

### Install Application
helm install pycloudops-app liteshz/pycloudops-app

### Upgrade Application Image
helm upgrade pycloudops-app liteshz/pycloudops-app \
--set web.deployment.containers[0].image.tag=v21

---

## Helm Chart Structure

pycloudops-app/
│
├── Chart.yaml
├── values.yaml
│
├── templates/
│   ├── web-deployment.yaml
│   ├── mysql-statefulset.yaml
│   ├── service.yaml
│   ├── configmap.yaml
│   ├── secret.yaml
│   └── pvc.yaml
│
└── README.md

---

👨‍💻 Author

Litesh Zadane
🚀 DevOps Engineer | SRE | Cloud & Platform Engineer

GitHub:
https://github.com/liteshz1778

Docker Hub:
https://hub.docker.com/u/liteshz
