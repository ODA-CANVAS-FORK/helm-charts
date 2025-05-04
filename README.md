# helm-repos

Build Helm Repositroies from file system charts

## Example

### windows:

```
set DOMAIN=ihc-dt.cluster-2.de
helm upgrade --install infoservice charts/canvas-info-service -n test --create-namespace --set=serverUrl=https://infoservice.%DOMAIN%
helm upgrade --install infosvc-vs charts/virtualservices -n test --create-namespace
```

### call in browser

https://infoservice.ihc-dt.cluster-2.de/api-docs/
