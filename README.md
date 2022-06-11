# Make your own single master kubernetes in 30 min
    1) Rename hosts in inventory file 
    2) Start deploy-k8s-master.yaml
    3) Install cni, for example weave - /usr/bin/kubectl --kubeconfig=/etc/kubernetes/admin.conf apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')" 
    4) Start deploy-k8s-worker.yaml
    5) Enjoy your new cluster

## If you need specific versions of kubernetes and containerd.io

Use variables:
```yaml
    containerd_version: 1.5.10-1
    kube_version: "1.21.3"
```