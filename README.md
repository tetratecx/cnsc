# cnsc
Demo &amp; Artifacts for Cloud Native Security Con

# Demo

## Explaination

* Please go through [this doc](https://docs.google.com/document/d/1ahLcDbFPe04_hJOnnjdfc2YlUhnYTLg24BiqQJpnXeQ/edit) to better understand the demo.

* Video presentations are also available [here](https://drive.google.com/drive/folders/1qbXt2m3JsSEQ_OAg1H3EklkW5IPc3woi).

## Setup

### Creating the apps in each cluster

* Set the `KUBECONFIG` environment variable to the `aks-westus2` cluster
```
export KUBECONFIG=<path-to-kubeconfig>
```

* Apply Kubernetes config for the `ticketing` app
```
kubectl apply -f apps/aks-westus2/ticketing/
```

* Set the `KUBECONFIG` environment variable to the `eks-useast2` cluster
```
export KUBECONFIG=<path-to-kubeconfig>
```

* Apply Kubernetes config for the `ticketing` app as well as `customer-360` app
```
kubectl apply -f apps/eks-useast2/ticketing/
kubectl apply -f apps/eks-useast2/customer360/
```

### Applying TSB Config
```
tctl --config <path-to-tsb-config> apply -f tsb/
```
