# Kubernetes-ops
School project to load balance and make some HA on a cluster Kubernetes installed with kubespray-ops project.

>Made by FULCHIC Gaby  

## Some infos about Kubernetes
### Global commands

>kubectl version  
>kubectl get nodes  

### Namespaces

>kubectl create -f ./gaby.yaml  
>kubectl delete namespaces gaby.yaml  
>kubectl get namespaces  

### Deployments

>kubectl run test1234 image=library/hello-world --port=XXXX  
>kubectl get deployments  

- with a file

>kubectl apply -f deployment.yaml  

### Services

>kubectl get services  
>kubectl expose deployment test1234 --type=LoadBalancer --port=8080 --target-port=8080  
>kubectl describe services/hello-world-loadbalancer  

### Labels

You can set Labels in yaml file :D.
Like label: it-prod-apps :D
With that you can manipulate some services or pods grouping them by their
Labels.  
>kubectl -l run=it-prod-apps get services  

### Quotas / Resources 

You can add quotas by using "resources" in the namespace.yml file.
But you also create a file with a kind : ResourceQuota and you gonna
create it using :
>kubectl create -f ./resourcequota.yml --namespace=namespace  
>kubectl get quota --namespace=namespace  
>kubectl describe quota compute-resources-sample --namespace=namespace  

### Begin with Kubernetes and Docker ;)

hello-world docker with k8s
>kubectl run test1234 --image=library/hello-world --port=8080  

expose it
>kubectl expose deployment test1234 --type=LoadBalancer --port=8080 --target-port=8080  

get the ip exposed
>kubectl get svc  

clean all
>kubectl delete deployment test1234  
>kubectl delete svc test1234  

