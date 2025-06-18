# argocd - example
- applications
- project

- desired state = what is in git 
- actual state = cluster

Sync = make desired state into the actual state

Refresh = compare actual with desired

## ArgoCD:
- server (api and webserver) CRUD
- repo = generate k8s manifest
- application controller = get manifest and deploy or hooks

redis, dex, application set controller

install argocd in k8s: ```k -n argocd apply -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml ```

port forward: ```k port-forward svc/argocd-server 8080:443```

install cli: ```brew install argocd```
login: ```argocd login localhost:8080```
pass is from secret argocd-initial-admin-secret

```argocd app create myapp --repo https://github.com/aditug/argocd-example --path k8s-yaml --dest-server https://kubernetes.default.svc --dest-namespace myapp-ns```

Ex: 
- https://github.com/argoproj/argocd-example-apps
- https://github.com/mabusaa/argocd-example-apps