# Helm Charts- Harness Chaos Enterprise

## Usage

### Pre-Requisites

- Install [helm3](https://helm.sh/docs/intro/install/)
- Kubernetes >= 1.17

### Installation Steps

The following steps will help you install hce via helm.

#### Step-1: Add the litmus helm repository

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

#### Step-3: Install the litmus chaos center

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