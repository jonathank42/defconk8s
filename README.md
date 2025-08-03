# defconk8s
The setup and applications run at Defcon Tech for Kubernetes

Guide ignores host setup

Utility cluster:
-note: The utilitiy cluster is set to mimic a cloud environment. This can be used in a home lab, or on-prem with a cncf enterprise solution. The setup of this cluster will require typing passwords into helm charts. Once external-secrets has been setup, all applications will be managed with applicationsets and secrets will be in a SOPS solution

Step 1: Install cluster
-note: This is a single node cluster. If you want a multi-node cluster, see #wikiehere
curl -sfL https://get.k3s.io | INSTALL_K3S_EXEC="server --disable traefik --disable servicelb"  sh -

Step 2: ArgoCD
helm repo add argo https://argoproj.github.io/argo-helm    
helm install argocd argo/argo-cd -n argocd --create-namespace

nginx ingress
lets encrypt 
pihole
external-dns
vaultwarden
external-secrets