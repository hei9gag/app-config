# What is ArgpCD
Argo CD is a declarative, GitOps continuous delivery tool for Kubernetes.

# Getting Started
https://argo-cd.readthedocs.io/en/stable/getting_started/
## Install Argo CD
1. Open terminal and run `kubectl create namespace argocd`
2. kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/core-install.yaml

## Download Argo CD CLI
1. brew install argocd
2. kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'

## Login Using CLI
1. argocd admin initial-password -n argocd
2. argocd login <ARGOCD_SERVER> (e.g. ARGOCD_SERVER = localhost:8080 [If you host locally])
3. argocd account update-password

## Setup applications
https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/
1. Run command `kubectl apply -f ./applications` to setup application in Argo CD

## Access ArgoCD UI locally
1. Run `kubectl port-forward svc/argocd-server -n {namespace} 8080:443`
2. Open browser and input `http://localhost:8080