# Kubernetes dashboard Helm Chart

## Prerequisites

Make sure you have Helm [installed](https://helm.sh/docs/using_helm/#installing-helm).

## Get Repo Info

```sh
helm repo add castai https://castai.github.io/official-addons
helm repo update
```

_See [helm repo](https://helm.sh/docs/helm/helm_repo/) for command documentation._


## Deploy

```bash
helm upgrade --install kubernetes-dashboard castai/kubernetes-dashboard -n=kubernetes-dashboard --create-namespace
```
