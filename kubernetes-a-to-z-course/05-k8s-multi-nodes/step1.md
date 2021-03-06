Kubeadm has been installed on the host nodes.

The first step is to initialize the cluster via launching the master node. The master is responsible for running the control plane components, etcd and the API server. Clients will communicate to the API to schedule workloads and manage the state of the cluster.

## Init the master node

The command below will initialise the cluster with a defined token to simplify the following steps.

`kubeadm init --token=102952.1a7dd4cc8d1f4cc6`{{execute HOST1}}

The master node will take a couple of minutes to set up.

Note: In production, it is not recommended to pass a token when initializing the master node, it is considering safer to let kubeadm to generate one on your behalf.
