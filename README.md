# Kubernetes-ops 🌀
School project to load balance and make some HA on a cluster Kubernetes installed with [kubespray-ops](https://github.com/gabyfulchic/kubespray-ops) project.

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

- with a get pods  
>kubectl get pods --namespace=gaby

### Context to stop using --namespace (<-config)  

>kubectl config view  
>kubectl config current-context  
>kubectl config set-context dev --namespace=yournamespace   
>kubectl config use-context dev  

### Deployments

>kubectl run test1234 image=library/hello-world --port=XXXX  
>kubectl get deployments  

- with a file

>kubectl apply -f deployment.yaml  

### Services

>kubectl expose deployment test1234 --type=LoadBalancer --port=8080 --target-port=8080  
>kubectl get services  
>kubectl describe theservice  

### Labels

You can set Labels in yaml file :D.  
label:  
name: it-prod-apps  
  
With that you can manipulate some services or pods grouping them by their
Labels.  
>kubectl -l name=it-prod-apps get services  

### Quotas / Resources 

You can add quotas by using "resources" in the namespace.yml file.
But you also create a file with a kind : ResourceQuota and you gonna
create it using :
>kubectl create -f ./resourcequota.yml --namespace=namespace  
>kubectl get quota --namespace=namespace  
>kubectl describe quota compute-resources-sample --namespace=namespace  

### Proxy

- To expose the API kube via a proxy  
>kubectl proxy --port=8080  
>curl http://localhost:8080/api/    
- Get the pods from default namespaces for example  
>curl http://localhost:8080/api/v1/namespaces/default/pods   

### Begin with Kubernetes and Docker ✔️

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

### To Monitor 📊

- Konstellate : https://github.com/containership/konstellate  
- Kubelet : https://kubernetes.io/docs/reference/command-line-tools-reference/kubelet/  
- Prometheus : https://coreos.com/operators/prometheus/docs/latest/  
