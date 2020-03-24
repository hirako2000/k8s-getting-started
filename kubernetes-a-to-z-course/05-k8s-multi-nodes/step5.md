## Node Labelling

We will make use of labels and node selectors. Let's assumume that each worker node is provisioned with infrastructure offering different performance, as such:

- node01: disk
- node02: cpu
- node03: cpu

We would then preferably have our database application and disk deployed on node01, being disk I/O optinized, and have the Kubernetes and ThingsBoard application on the cpu optimized nodes.

### Add labels

We apply the performance=disk label to node01:

`kubectl label nodes node01 performance=disk`{{execute}}

And performance=cpu label to node02 and node03

`kubectl label nodes node02 performance=cpu`{{execute}}

`kubectl label nodes node03 performance=cpu`{{execute}}

### See the labels

`kubectl get nodes --show-labels`{{execute}}
