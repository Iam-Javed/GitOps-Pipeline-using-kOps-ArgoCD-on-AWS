# GitOps Pipeline using kOps, ArgoCD and Kubernetes on AWS

## Project Overview

This project demonstrates a production-like GitOps workflow on AWS using Kubernetes provisioned with kOps and continuous deployment managed by ArgoCD. The application is containerized using Docker, images are stored in DockerHub, and deployments are managed using Helm charts. Prometheus and Grafana are integrated to provide observability and monitoring for the cluster and workloads.

---

## Architecture

```
Developer
    │
    ▼
GitHub Repository
    │
    ▼
ArgoCD
    │
    ▼
Kubernetes Cluster (kOps on AWS)
    │
    ▼
Helm Chart
    │
    ▼
Flask Application Pods
    │
    ▼
Prometheus
    │
    ▼
Grafana
```

---

## Technologies Used

- AWS EC2
- kOps
- Kubernetes
- Docker
- DockerHub
- GitHub
- ArgoCD
- Helm
- Prometheus
- Grafana
- Flask

---

## Features

- Kubernetes cluster provisioning using kOps on AWS
- GitOps workflow with ArgoCD
- Automated deployments from GitHub
- Dockerized Flask application
- Helm-based deployment
- Self-Healing and Drift Detection
- Automatic Synchronization
- Pruning of obsolete resources
- Multi-environment support using Helm values
- Monitoring with Prometheus and Grafana
- Cluster observability and dashboard visualization

---

# Project Structure

```text
GitOps-Pipeline-using-kOps-ArgoCD-on-AWS
│
├── flask-app
│   ├── app.py
│   ├── Dockerfile
│   └── requirements.txt
│
└── gitops
    ├── flask-chart
    │   ├── Chart.yaml
    │   ├── values.yaml
    │   └── templates
    │       ├── deployment.yaml
    │       ├── service.yaml
    │       └── _helpers.tpl
    │
    └── environments
        ├── dev-values.yaml
        ├── stage-values.yaml
        └── prod-values.yaml
```

---

# Workflow

1. Developers push code changes to GitHub.
2. Application image is built and stored in DockerHub.
3. ArgoCD continuously monitors the Git repository.
4. ArgoCD synchronizes the desired state with Kubernetes.
5. Helm templates generate Kubernetes manifests.
6. Kubernetes deploys and manages application pods.
7. Prometheus collects metrics.
8. Grafana visualizes cluster and application health.

---

# GitOps Flow

```text
Developer
    │
    ▼
GitHub
    │
    ▼
ArgoCD
    │
    ▼
Kubernetes Cluster
    │
    ▼
Application Pods
```

---

# Monitoring Architecture

```text
Application
    │
    ▼
Prometheus
    │
    ▼
Grafana
```

---

# Components Installed

## ArgoCD

- Automated synchronization
- Self-Healing
- Pruning
- Drift detection

## Prometheus Stack

- Prometheus
- Grafana
- Alertmanager
- Node Exporter
- kube-state-metrics

---

# Validation

### Verify Kubernetes Nodes

```bash
kubectl get nodes
```

### Verify Application Pods

```bash
kubectl get pods -A
```

### Verify ArgoCD

```bash
kubectl get pods -n argocd
```

### Verify Monitoring Stack

```bash
kubectl get pods -n monitoring
```

---

# Screenshots

## Cluster Nodes

Image Path:

```
images/k8s-nodes.png
```

<img width="919" height="140" alt="image" src="https://github.com/user-attachments/assets/28595339-b563-4ef6-9a73-a21f8fcaf62d" />

---

## ArgoCD Dashboard

Image Path:

```
images/argocd-dashboard.png
```

<img width="1334" height="565" alt="image" src="https://github.com/user-attachments/assets/cb4c82e9-8cdd-4f6f-9fd4-fde25923565e" />

---

## Application Sync Status

Image Path:

```
images/argocd-sync.png
```

<img width="1346" height="637" alt="image" src="https://github.com/user-attachments/assets/300fba66-eebc-4ce6-bdd6-75fab47fb650" />

---

## Application Resource Tree

Image Path:

```
images/resource-tree.png
```

<img width="1129" height="310" alt="image" src="https://github.com/user-attachments/assets/235403e6-4d5d-4ce4-a888-363fa15813c6" />

---

## Flask Application Running

Image Path:

```
images/flask-app.png
```

<img width="1365" height="294" alt="image" src="https://github.com/user-attachments/assets/27528a13-718a-403e-b76d-62637eb80fa2" />

---

## Prometheus Targets

Image Path:

```
images/prometheus-targets.png
```

<img width="1360" height="647" alt="image" src="https://github.com/user-attachments/assets/05471439-9eef-4e4b-a8b1-ad00f0daed27" />

<img width="1331" height="649" alt="image" src="https://github.com/user-attachments/assets/2f477fc5-c7e8-4c6e-a295-3f4e6ee1e837" />

---

## Grafana Dashboard

Image Path:

```
images/grafana-dashboard.png
```

<img width="1363" height="637" alt="image" src="https://github.com/user-attachments/assets/309ebfbd-ff39-4a53-9e51-c91f717a83b5" />

<img width="1351" height="643" alt="image" src="https://github.com/user-attachments/assets/a0b5542a-f3ed-44f5-91b6-c5038ffd98bd" />

---

## Monitoring Stack Pods

Image Path:

```
images/monitoring-pods.png
```
<img width="1343" height="633" alt="image" src="https://github.com/user-attachments/assets/ae41c765-2ad9-4793-82ff-12e41a3f440f" />

<img width="1349" height="641" alt="image" src="https://github.com/user-attachments/assets/225ac3b2-a7a9-411e-afa2-69d61c256998" />

<img width="1359" height="643" alt="image" src="https://github.com/user-attachments/assets/f1118bb3-256c-4ed6-b166-922fa3979c4c" />

<img width="1358" height="664" alt="image" src="https://github.com/user-attachments/assets/a7b46092-110b-49cf-b0d0-98b5f9178dfc" />

<img width="1351" height="431" alt="image" src="https://github.com/user-attachments/assets/7854f159-459b-4203-b07d-e84b7d1af24d" />

<img width="1345" height="640" alt="image" src="https://github.com/user-attachments/assets/a79eb740-2b78-42bc-b298-bf7878dde708" />

<img width="1339" height="647" alt="image" src="https://github.com/user-attachments/assets/ed9061a1-79e8-4f79-93b7-cb84bbae9dc5" />

<img width="1319" height="619" alt="image" src="https://github.com/user-attachments/assets/eef944a4-7f92-4a28-a464-0e9048f2facd" />

---

# Key Learnings

- Kubernetes cluster provisioning using kOps
- GitOps principles and workflows
- Continuous deployment with ArgoCD
- Helm chart management
- Docker image lifecycle
- Configuration drift management
- Self-healing Kubernetes deployments
- Cluster monitoring and observability
- Prometheus metrics collection
- Grafana dashboard visualization

---
