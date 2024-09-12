# Documentation

This repository contains both content and documentation of modern DevOps project following best practices of CI/CD and GitOps.

## Application Repository

+ [Fastzero API](https://github.com/mateussgubim/fastapi-project)

## Prerequisites

+ [Kubernetes](https://kubernetes.io/docs/setup/)
+ [Helm](https://helm.sh/docs/intro/install/#from-script)

## ArgoCD Installation

Check the [documentation](https://argo-cd.readthedocs.io/en/stable/getting_started/).

### Create namespace

```bash
kubectl create namespace argocd
```

### Install ArgoCD

```bash
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

### Port-Forward

```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

### Access ArgoUI

Access [localhost:8080/](localhost:8080)

  + User: admin
  + Password:
    ```bash
    kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d
    ```
