static pods:
  static pods are pods defined in the kubelet config file, they are not managed by the kube-apiserver.
  static pods are always bound to the node where they are defined.

static pod location:
  in the kind cluster we can exec into control control-plane thru docker 
  ```
  docker exec -it <kind-control-plane name/id> bash
  cd /etc/kubernetes/manifests
  ls
  ```

  etcd.yaml 
  kube-apiserver.yaml  
  kube-controller-manager.yaml  
  kube-scheduler.yaml

  these are the static pods that are running on the control-plane node.

  