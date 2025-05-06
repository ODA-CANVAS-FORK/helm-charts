# helm-repos

Build Helm Repositroies from file system charts


## install

```
helm repo add oda-canvas-fork https://oda-canvas-fork.github.io/helm-charts
helm repo update
```

```
set DOMAIN=ihc-dt.cluster-2.de
helm upgrade --install infoservice oda-canvas-fork/canvas-info-service -n test --create-namespace --set=serverUrl=https://infoservice.%DOMAIN%
helm upgrade --install infosvc-vs charts/virtualservices -n test --create-namespace
```

## Example

### windows:

```
set DOMAIN=ihc-dt.cluster-2.de
helm upgrade --install infoservice charts/canvas-info-service -n test --create-namespace --set=serverUrl=https://infoservice.%DOMAIN%
helm upgrade --install infosvc-vs charts/virtualservices -n test --create-namespace
```

### call in browser

https://infoservice.ihc-dt.cluster-2.de/api-docs/
