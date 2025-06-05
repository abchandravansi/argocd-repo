# ARGOCD-REPO
This repository will hold the configuration files
# Step 1: 
## We need to create namespace argocd - And start creating the resources for argocd installation 
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
# Step 2:
## We need to start - Install the argo cd - application .yaml 
## This will configure the github repo for observing changes. 
## Configuration for argo cd - are added into application yaml 
kubectl apply -f application.yaml

# Step 3:
## To check the UI for ARGO CD 
kubectl port-forward svc/argocd-server 8080:443 -n argocd


## Step 4: 
## Open browser for localhost and access the UI - See argocd in action. 
## Whenever their will be change in repository the pods will change and get updated accordingly 
https://127.0.0.1:8080/

