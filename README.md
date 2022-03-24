# Harness Chaos Enterprise

## Usage

### Pre-Requisites

- Install [helm3](https://helm.sh/docs/intro/install/)
- Kubernetes >= 1.17

## Installation via Helm

The following steps will help you install hce via helm.

#### Step-1: Add the harness helm repository

```bash
helm repo add harness https://hce.chaosnative.com

helm repo list
```

Output:
```
NAME            URL
harness     https://hce.chaosnative.com                                                               
```

#### Step-2: Create the litmus namespace

```bash
kubectl create ns litmus
```

#### Step-3: Install the hce chaos center

```bash
helm install -n litmus hce harness/hce
```

Output:
```bash
NAME: hce
LAST DEPLOYED: Mon Dec  6 01:43:14 2021
NAMESPACE: litmus
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
Thank you for installing hce 😀

Your release is named hce and it's installed to namespace: litmus.

Visit https://harness.io to find more info.
```


#### Step-3: Uninstall the Harness Chaos Enterprise

```bash
helm uninstall hce --namespace=litmus
```

Output:
```bash
release "hce" uninstalled
```
---

## Installation via Kubectl


> Master (Latest) Cluster scope. Install in litmus namespace by default.

```bash
kubectl apply -f http://hce.chaosnative.com/manifests/ci/hce-cluster-scope.yaml
```

Or

> Master (Latest) Namespaced scope. Replace `litmus` with the desired namespace.

```bash
export HCE_NAMESPACE="litmus"
kubectl create ns ${HCE_NAMESPACE}
kubectl apply -f http://hce.chaosnative.com/manifests/ci/hce-crds.yaml
wget http://hce.chaosnative.com/manifests/ci/hce-namespace.yaml
envsubst '${HCE_NAMESPACE}' < hce-namespace.yaml > ${HCE_NAMESPACE}-ns-scoped-hce-manifest.yml
kubectl apply -f ${HCE_NAMESPACE}-ns-scoped-hce-manifest.yml -n ${HCE_NAMESPACE}
```

