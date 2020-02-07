## Copy

### Copy from pod to local

`kubectl cp thingsboard-xxxxxx:/var/log/thingsboard/install.log ./tb-install.log`

### Copy from local to pod

`kubectl cp ./tb-install.log thingsboard-xxxxxx:/tmp/`

### Cat copied file

`kubectl exec thingsboard-xxxxxx -- cat /tmp/tb-install.log`

## Interactive Shell

## Get bash interfactive shell

`kubectl exec thingsboard-xxxxxx -it bash`

## Exit bash

`exit`{{execute}}