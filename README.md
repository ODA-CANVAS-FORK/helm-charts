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
helm upgrade --install infoservice -n test --create-namespace oda-canvas-fork/canvas-info-service --set=serverUrl=https://infoservice.%DOMAIN%
helm upgrade --install infosvc-vs -n test oda-canvas-fork/virtual-services --set=domain=%DOMAIN%
```

#### tap

```
set DOMAIN=oda-tst-1.dev.tap.telekom.de
helm upgrade --install infoservice -n test --create-namespace oda-canvas-fork/canvas-info-service --set=serverUrl=https://infoservice.%DOMAIN%
helm upgrade --install infoservice-ing -n test oda-canvas-fork/tap-ingress --set=domain=%DOMAIN%
```

### call in browser

https://infoservice.ihc-dt.cluster-2.de/api-docs/

## uninstall

```
helm uninstall infoservice-vs -n test
helm uninstall infoservice -n test
```
