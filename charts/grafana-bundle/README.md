# Grafana Bundle Helm Chart

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
helm upgrade --install grafana-bundle castai/grafana-bundle -n=grafana-bundle --create-namespace
```

## Open Grafana dashboard locally

Start cluster proxy server

```sh
kubectl proxy
```

Once proxy server is started go to [dashboard](http://localhost:8001/api/v1/namespaces/grafana-bundle/services/http:grafana:80/proxy/)
