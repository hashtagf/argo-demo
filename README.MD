# ArgoCD

## Create argocd app-argo

```bash
kubectl apply -f ms.yaml
```

- create app-argo success

## Create Creds

```bash
ssh-keygen -t ed25519 -C "argocd-bot"
```

- Open file .pub and copy to ssh in github

```bash
kubectl apply -f argocd-repo-creds.yaml
```

- create creds success
