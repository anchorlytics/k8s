# k8s
Config for Kubernetes container orchestration

Clone to `/var/lib/rancher/k3s/server/manifests/` for auto-deployment under k3s.
See ho-ansible/k3s for installing k3s.

These are generally going to be Helm chart resource definitions of the following type:
```
apiVersion: helm.cattle.io/v1
kind: HelmChart
```
Values for the Helm chart are in the `valuesContent` key.
See the
[k3s documentation](https://rancher.com/docs/k3s/latest/en/helm/)
for more info on this CRD.

Secrets referenced in these charts are defined in a separate private repo.

Remember to
[delete the old install pod](https://github.com/rancher/k3s/issues/187)
before applying a modified manifest.
