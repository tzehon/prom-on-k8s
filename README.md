# Install Prometheus on a k8s cluster
    kubectl create -f rbac.yml  

    kubectl create configmap prometheus-config --from-file prometheus.yml  

    kubectl create -f prometheus-deployment.yml  

    kubectl create -f prometheus-service.yml  

    kubectl create -f rpc-app-deployment.yml  

    kubectl create -f rpc-app-service.yaml  

Access the UI at `{LOAD_BALANCER_IP}:9090`

Query the API with `curl '{LOAD_BALANCER_IP}:9090/api/v1/query?query=sum(rpc_durations_seconds)'
sum(rpc_durations_seconds)`
