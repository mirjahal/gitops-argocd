# Install Argo CD

Quick Start
https://argo-cd.readthedocs.io/en/stable/

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

# List Contexts
```
kubectl config get-contexts
```

### Switch Between Contexts
```
kubectl config use-context <NAME>
```

# Get admin password
```
kubectl get secrets -n argocd
```

```
kubectl get secret argocd-initial-admin-secret -n argocd -o yaml
```

```
echo `echo <PASSWORD_BASE64_ENCODED> | base64 --decode`
echo `echo TjNsNHlWR0dhSlgyTVNJWA== | base64 --decode`
```

Prints: N3l4yVGGaJX2MSIX

# Accessing argocd

```
kubectl get svc -n argocd
```

```
kubectl port-forward svc/argocd-server -n argocd 8080:443
```