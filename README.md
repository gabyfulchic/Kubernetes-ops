# Kubernetes-ops
School project to load balance and make some HA on a cluster Kubernetes installed with kubespray-ops project.

```
     )               (       )               (     
  ( /(        (      )\ ) ( /(      *   )    )\ )  
  )\())  (  ( )\ (  (()/( )\())(  ` )  /((  (()/(  
|((_)\   )\ )((_))\  /(_)|(_)\ )\  ( )(_))\  /(_)) 
|_ ((_) ((_|(_)_((_)(_))  _((_|(_)(_(_()|(_)(_))   
| |/ / | | || _ ) __| _ \| \| | __|_   _| __/ __|  
  ' <| |_| || _ \ _||   /| .` | _|  | | | _|\__ \  
 _|\_\\___/ |___/___|_|_\|_|\_|___| |_| |___|___/  
 ```                                              

>Made by FULCHIC Gaby  

## The project's core
### To launch the project 👨🏼‍💻  

>kubectl create -f hello-world/  

### To stop it 🛑  

>kubectl delete -f hello-world/  


## More infos about Kubernetes for myself
### Global commands

>kubectl version  
>kubectl api-versions  
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

### Proxy

>kubectl proxy  

### Begin with Kubernetes and Docker ;)

Hello-world docker with k8s :  
>kubectl run test1234 --image=library/hello-world --port=8080  

Expose it :  
>kubectl expose deployment test1234 --type=LoadBalancer --port=8080 --target-port=8080  

Get the ip exposed, there are 2 commands :  
>kubectl get svc  
>kubectl get services  

Clean all :  
>kubectl delete deployment test1234  
>kubectl delete svc test1234  
