Once the master node has initialised, additional nodes can join the cluster using the token. Tokens may be managed via `kubeadm token`, for example run this command to list the tokens:

`kubeadm token list`{{execute HOST1}}

## Join nodes to the cluster

ssh into the first node

`ssh node01 -oStrictHostKeyChecking=no`{{execute HOST1}}
And run this command to join the cluster providing the IP address of the Master node and the token to join:

`kubeadm join --token=102952.1a7dd4cc8d1f4cc6 [[HOST_IP]]:6443 --discovery-token-unsafe-skip-ca-verification`{{execute NODE1}}

Logout of that node:
`exit`{{execute NODE1}}

## Join a 3rd node

ssh into the second node:

`ssh node02 -oStrictHostKeyChecking=no`{{execute HOST1}}

and run the command to join the cluster:

`kubeadm join --token=102952.1a7dd4cc8d1f4cc6 [[HOST_IP]]:6443 --discovery-token-unsafe-skip-ca-verification`{{execute NODE2}}

Logout of that node:
`exit`{{execute NODE2}}

## Join a 4th node

ssh into the third node:

`ssh node03 -oStrictHostKeyChecking=no`{{execute HOST1}}

and run the command to join the cluster:

`kubeadm join --token=102952.1a7dd4cc8d1f4cc6 [[HOST_IP]]:6443 --discovery-token-unsafe-skip-ca-verification`{{execute NODE3}}

Logout of that node:
`exit`{{execute NODE3}}
