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
- create file argocd-repo-creds.yaml

```bash
## argocd-repo-creds.yaml
apiVersion: v1
kind: Secret
metadata:
  name: argoproj-ssh-creds
  namespace: argocd
  labels:
    argocd.argoproj.io/secret-type: repo-creds
stringData:
  url: git@github.com:argoproj-labs
  type: helm
  sshPrivateKey: |
    -----BEGIN OPENSSH PRIVATE KEY-----
    ...
    -----END OPENSSH PRIVATE KEY-----
```

- copy private to argocd-repo-creds.yaml

```bash
kubectl apply -f argocd-repo-creds.yaml
```

- create creds success
