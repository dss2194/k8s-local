# Argo CD

```bash
helm repo add argo https://argoproj.github.io/argo-helm
helm repo update

helm upgrade --install -n argocd --create-namespace argocd argo/argo-cd -f values-cluster.yaml  --version 9.5.0
```

## get password

```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```
