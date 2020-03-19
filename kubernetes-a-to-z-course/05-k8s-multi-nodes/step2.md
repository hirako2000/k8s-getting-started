Once the master node has initialised, additional nodes can join the cluster using the token. Tokens may be managed via `kubeadm token`, for example run this command to list the tokens:

`kubeadm token list`{{execute}}

## Join a 2nd node

One the second node, run the command to join the cluster providing the IP address of the Master node.

`kubeadm join --token=102952.1a7dd4cc8d1f4cc5 [[HOST_IP]]:6443`{{execute HOST2}}
