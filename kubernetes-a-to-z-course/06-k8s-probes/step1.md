## Init the master node

`kubeadm init --token=102952.1a7dd4cc8d1f4cc6`{{execute HOST1}}

The master node will take a couple of minutes to set up.

## Join the cluster

ssh into node01:

`ssh node01 -oStrictHostKeyChecking=no`{{execute HOST1}}

Then:

`kubeadm join --token=102952.1a7dd4cc8d1f4cc6 [[HOST_IP]]:6443 --discovery-token-unsafe-skip-ca-verification && exit`{{execute NODE1}}

ssh into node02:

`ssh node02 -oStrictHostKeyChecking=no`{{execute HOST1}}

Then:

`kubeadm join --token=102952.1a7dd4cc8d1f4cc6 [[HOST_IP]]:6443 --discovery-token-unsafe-skip-ca-verification && exit`{{execute NODE2}}

ssh into node03:

`ssh node03 -oStrictHostKeyChecking=no`{{execute HOST1}}

Then:

`kubeadm join --token=102952.1a7dd4cc8d1f4cc6 [[HOST_IP]]:6443 --discovery-token-unsafe-skip-ca-verification && exit`{{execute NODE3}}

## Client config

`sudo cp /etc/kubernetes/admin.conf $HOME/ && sudo chown $(id -u):$(id -g) $HOME/admin.conf &&export KUBECONFIG=$HOME/admin.conf`{{execute HOST1}}

## Set up Waveworks

`kubectl create -f "https://cloud.weave.works/k8s/net"`{{execute HOST1}}

## Node labelling

### Add labels and taint

`kubectl label nodes node01 performance=disk`{{execute}}

`kubectl label nodes node02 performance=cpu`{{execute}}

`kubectl label nodes node03 performance=cpu`{{execute}}

`kubectl taint nodes node01 node-role.kubernetes.io/disk=reserved:NoSchedule`{{execute}}
