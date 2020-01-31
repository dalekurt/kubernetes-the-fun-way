# FluxCD

## Install Helm
> Helm v3 (Tiller component deprecated)
```bash
brew install helm
```

## Deploy Flux and Helm Operator

### Add Flux Charts
```bash
helm repo add fluxcd https://charts.fluxcd.io
```

### Install Flux

```bash
helm upgrade --install flux \
    --values deployments/flux/flux/flux-values.yaml \
    --namespace flux \
    fluxcd/flux
```

### Get your SSH Key and add to your GitHub Profile

```bash
kubectl -n flux logs deployment/flux | grep identity.pub | cut -d '"' -f2
```

### Install Helm Operator

```bash
helm upgrade --install helm-operator \
    --values deployments/flux/helm-operator/flux-helm-operator-values.yaml \
    --namespace flux \
    fluxcd/helm-operator
```

## Something went wrong?

### Debugging

```bash
kubectl -n flux logs deployment.apps/flux
kubectl -n flux logs deployment.apps/helm-operator
```

### Delete Flux and Helm Operator (Run twice)

```bash
helm delete --purge helm-operator ; \
helm delete --purge flux ; \
kubectl delete crd helmreleases.flux.weave.works ; \
kubectl delete crd helmreleases.helm.fluxcd.io
```
