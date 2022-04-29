## install argocd

k create namespace argo-cd
k apply -f argocd-deployment/install.yaml -n argo-cd
k apply -f argocd-deployment/ingress.yaml -n argo-cd

## get the password

k -n argo-cd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -D; echo

