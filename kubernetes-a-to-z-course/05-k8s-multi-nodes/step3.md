The cluster has now been initialised with 4 nodes. The Master node will manage the cluster, while the 3 worker nodes will run our container workloads.

## Client config

To manage the Kubernetes cluster, the client configuration and certificates are required. This configuration is created when _kubeadm_ initialises the cluster. The command copies the configuration to the user's home directory and sets the environment variable for use with the CLI.

`sudo cp /etc/kubernetes/admin.conf $HOME/ && sudo chown $(id -u):$(id -g) $HOME/admin.conf &&export KUBECONFIG=$HOME/admin.conf`{{execute HOST1}}

Let's list the ndoes in the cluster:

`kubectl get nodes`{{execute HOST1}}

At this point, the mater node shows as NoReady. This is because the Container Network Interface has not been deployed. This will be fixed within the next step.
