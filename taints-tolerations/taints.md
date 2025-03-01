first node is tainted
```
kubectl taint node multi-container-worker gpu=true:NoSchedule
```
``` 
kubectl describe node multi-container-worker | grep -i taints
```
output: Taints:             gpu=true:NoSchedule

normally pod will not be scheduled on this node because of the taint
if we describe the pod we will see the error

Warning  FailedScheduling  55s   default-scheduler  0/4 nodes are available: 1 node(s) had untolerated taint {node-role.kubernetes.io/control-plane: }, 3 node(s) had untolerated taint {gpu: true}. preemption: 0/4 nodes are available: 4 Preemption is not helpful for scheduling.

to remove the taint we can use the following command
```
kubectl taint node multi-container-worker gpu:NoSchedule-
```
