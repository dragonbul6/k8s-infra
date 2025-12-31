# 🚀 K8s-Infra: GitOps with Argo CD & Kustomize

This repository manages my Kubernetes infrastructure and applications using a **GitOps** workflow. It utilizes **Kustomize** for configuration management and **Argo CD** for automated deployments on Minikube.


## 🏗 Project Structure

The repository follows a **Base/Overlay** pattern to keep configurations DRY (Don't Repeat Yourself):

```text
.
├── base/                   # Common resources (Deployments, Services)
│   └── helloworld-api/
├── overlays/               # Environment-specific overrides
│   └── development/
│       └── helloworld-api/ # Development patches (Namespace, Env vars, Suffixes)
├── argo-app/               # Application definitions for Argo CD
│   └── development/        # Managed by the App-of-Apps pattern
└── bootstrap/              # Root Application to initialize the cluster
