# helm-repos

Build Helm Repositroies from file system charts


## install

### setup repo

```
helm repo add oda-canvas-fork https://oda-canvas-fork.github.io/helm-charts
helm repo update
```

### install for given domain

#### gcp

```
set DOMAIN=ihc-dt.cluster-2.de
helm upgrade --install infoservice oda-canvas-fork/canvas-info-service -n test --create-namespace --set=serverUrl=https://infoservice.%DOMAIN%
helm upgrade --install infosvc-vs oda-canvas-fork/virtual-services -n test --set=domain=%DOMAIN%
```

#### tap

```
set DOMAIN=oda-tst-1.dev.tap.telekom.de
helm upgrade --install infoservice oda-canvas-fork/canvas-info-service -n test --create-namespace --set=serverUrl=https://infoservice.%DOMAIN%
helm upgrade --install infosvc oda-canvas-fork/tap-ingress -n test --set=domain=%DOMAIN%
```

### call in browser

https://infoservice.ihc-dt.cluster-2.de/api-docs/

## uninstall

```
helm uninstall infoservice-vs -n test
helm uninstall infoservice -n test
```
