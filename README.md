# Harness Chaos Engineering Enterprise

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

#### Step-2: Update the harness helm repository

```bash
helm repo update
```

Output:
```
Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "harness" chart repository
Update Complete. ⎈Happy Helming!⎈
```

#### Step-3: Install the HCE chaos center

```bash
helm install -n litmus hce harness/hce --create-namespace
```

Output:
```bash
NAME: hce
LAST DEPLOYED: Fri Apr 22 07:29:30 2022
NAMESPACE: litmus
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
Thank you for installing hce :grinning:
Your release is named hce and it's installed to namespace: litmus.
Visit https://harness.io to find more info.
```

#### Step-4: Uninstall the Harness Chaos Enterprise

```bash
helm uninstall hce --namespace=litmus
```

Output:
```bash
release "hce" uninstalled
```
---

## Installation via Kubectl

### Release version
> 2.8.0 Cluster scope. Install in litmus namespace by default.

```bash
kubectl apply -f https://hce.chaosnative.com/manifests/2.8.0/hce-cluster-scope.yaml
```

Or

> 2.8.0 Namespaced scope. Replace `litmus` with the desired namespace.

```bash
kubectl create ns litmus
kubectl apply -f https://hce.chaosnative.com/manifests/2.8.0/hce-crds.yaml
kubectl apply -f https://hce.chaosnative.com/manifests/2.8.0/hce-namespace.yaml -n litmus
```

### Master version

> Master (Latest) Cluster scope. Install in litmus namespace by default.

```bash
kubectl apply -f https://hce.chaosnative.com/manifests/ci/hce-cluster-scope.yaml
```

Or

> Master (Latest) Namespaced scope. Replace `litmus` with the desired namespace.

```bash
kubectl create ns litmus
kubectl apply -f https://hce.chaosnative.com/manifests/ci/hce-crds.yaml
kubectl apply -f https://hce.chaosnative.com/manifests/ci/hce-namespace.yaml -n litmus
```

---

## To Connect External Agents

External agents can be install via ChaosCTL. Please refer the following resources.

* Installation of ChaosCTL- https://github.com/chaosnative/chaosctl#installation

* Usage of ChaosCTL- https://github.com/chaosnative/chaosctl/blob/main/Usage.md

---
