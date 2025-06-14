# ArgoCD Demo
Argo CD is a declarative, GitOps continuous delivery tool for Kubernetes.

https://argo-cd.readthedocs.io/en/stable/

## Install ArgoCD
```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

## Get Access to Web UI
To get access to Web UI for demo purpose let's use a port-forwrding

```
kubectl port-forward -n argocd svc/argocd-server  8443:443
```
Now you can open your browser and go to https://localhost:8443.

## Login ArgoCD
Use `admin` as a username. You can find password in the `argocd-initial-admin-secret` secret.
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```

## Demo
https://www.youtube.com/watch?v=IFapxcWrGck