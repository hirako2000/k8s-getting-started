The Container Network Interface (CNI) defines how the different nodes and their workloads should communicate. There are multiple network providers available, some are listed [here](https://kubernetes.io/docs/admin/addons/).

## Networking with WaveWorks

In this scenario we'll use WeaveWorks. The deployment definition can be viewed at `cat /opt/weave-kube`{{execute HOST1}}

This can be deployed using `kubectl apply`.

`kubectl apply -f /opt/weave-kube`{{execute HOST1}}

Weave will now deploy a few Pods on the cluster. The status of this can be viewed using the command `kubectl get pod -n kube-system`{{execute HOST1}}

Visit https://www.weave.works/docs/net/latest/kube-addon/ for details on WaveWorks

Now you may see your the cluster is ready:

`kubectl get nodes`{{execute HOST1}}