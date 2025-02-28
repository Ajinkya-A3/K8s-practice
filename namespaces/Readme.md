kubectl create deploy nginx-demo --image=nginx -n demo

kubectl scale --replicas=3 deploy/nginx-demo -n=demo


to access pods from different namespaces using service we have to use fully qualified service name 

eg.
    curl svc-test.default.svc.cluster.local
    for getting response form "svc-test" service from the default namespace

    curl svc-demo.demo.svc.cluster.local
    for getting response form "svc-demo" service from the demo namespace

    if we are accessing the pods in same namespace we only need to use the name of the service 