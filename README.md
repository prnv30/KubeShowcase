# 🚀 KubeShowcase

**KubeShowcase** is a Kubernetes GitOps demo project that deploys the **HipsterShop** application (10+ microservices) with **enterprise-grade production practices**.  
It demonstrates how to manage multi-service Kubernetes deployments using **ArgoCD, Helm, Kustomize, Observability stack, and GitOps workflows**.

---

## 📂 Repository Structure
```
KubeShowcase/
├── argocd/                 # ArgoCD GitOps configuration (ApplicationSet + Project)
├── deployments/            # Application + Infrastructure components (Helm + Kustomize)
│   ├── app/                # HipsterShop microservices
│   ├── certs/              # TLS certificate lifecycle via cert-manager
│   ├── ingress/            # NGINX ingress controller + routes
│   └── observability/      # Full observability stack (Prometheus, Grafana, Loki, Tempo, OTel, Alloy)
├── src/                    # Application source code / extensions
└── README.md               # You are here
```


---

## ⚡ Key Highlights

### 🔹 1. GitOps with ArgoCD
- Single **ApplicationSet** dynamically manages the entire stack.  
- **Auto service discovery** → picks up any new component from `deployments/` and deploys it automatically.  
- **Best practices**: Helm for configuration management + Kustomize for environment overlays (dev, stage, prod).  
- **Guardrails** enforced using ArgoCD **AppProject** (RBAC + namespace restrictions).  
- Enables **zero manual intervention** for cluster bootstrapping.  

---

### 🔹 2. Observability
A full observability pipeline built-in with:

- **Prometheus** → Metrics  
- **Loki** → Logs  
- **Tempo** → Distributed Tracing  
- **Grafana** → Dashboards & Visualization  
- **OpenTelemetry Operator** → Auto-instrumentation of HipsterShop microservices  
- **Alloy** → Unified telemetry agent (aggregates metrics/logs/traces → forwards to backends)  

---

### 🔹 3. Ingress & TLS
- **NGINX Ingress Controller** → Routing + TLS termination  
- **cert-manager** → Automates TLS certificates lifecycle with ClusterIssuers + Certificates  

---

### 🔹 4. Secrets Management
- **External Secrets Operator (ESO)** integrated with **AWS Secrets Manager**  
- Ensures all sensitive configs (**DB creds, API keys, certs**) are pulled securely into the cluster.  

---

## 🏗️ Tech Stack
- **Kubernetes** (multi-service deployment)  
- **ArgoCD** (GitOps)  
- **Helm** (package management)  
- **Kustomize** (environment overlays)  
- **NGINX Ingress Controller**  
- **cert-manager**  
- **External Secrets Operator** (AWS Secrets Manager)  
- **Observability**: Prometheus, Grafana, Loki, Tempo, OpenTelemetry, Alloy  

---

## 🚦 How It Works
1. **Bootstrap ArgoCD** → apply manifests in `argocd/`  
2. **ArgoCD ApplicationSet** detects all components under `deployments/`  
3. Components deployed automatically with **Helm + Kustomize overlays**  
4. **Observability stack** auto-collects metrics, logs, and traces  
5. **Ingress + TLS** ready via **NGINX + cert-manager**  
6. **Secrets synced** securely from AWS Secrets Manager  
7. ✅ Result → A **production-ready, observable, secure Kubernetes application stack** 🚀  

---

## 📌 Future Enhancements
- ✅ Add staging/prod overlays  
- ✅ CI pipeline for automated image builds & promotions  
- ✅ Policy enforcement with **Kyverno / OPA Gatekeeper**  
- ✅ Multi-cluster GitOps management  

---
