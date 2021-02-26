# k8s
Config for **Kubernetes** container orchestration.
Generally specific to **Anchorlytics** compute infrastructure.

Most manifests use the [Helm chart CRD](https://rancher.com/docs/k3s/latest/en/helm/).

**Secrets** referenced in these charts are defined in a separate private repo.

## Directory Structure
+ `int/`: manifests for **internal** k8s cluster
+ `ext/`: manifests for **external** k8s cluster
+ `common/`: manifests applicable to **both**
+ `ns/`: manifests to create **namespaces**

## Usage
+ Install **k3s** on cluster nodes with [ho-ansible/k3s](https://github.com/ho-ansible/k3s).
+ Create **namespaces**:
```
kubectl apply -f ns/
```
+ Apply manifests for desired **cluster**:
```
kubectl apply -f int/
```
