# k8s local
IaC repo for local installed k8s. 
For bootstrap setup, a ready k8s cluster is required and initial install for argocd
```bash
# setup Namespace for argocd
kubectl apply -f ns-argocd.yaml
# Install initial ArgoCD
helm install --set configs.params."server\.insecure"=true argo-cd argo-cd/argo-cd -n argocd
# Add git repo to ArgoCD
kubectl apply -f initial.yaml
```