# Kubernetes-ops
School project to load balance and make some HA on a cluster Kubernetes installed with kubespray-ops project.

>Made by FULCHIC Gaby  

## Some infos about Kubernetes
### Global commands

kubectl version
kubectl get nodes

### Namespaces

kubectl create -f ./gaby-namespace.yaml
kubectl delete namespaces gaby-namespace.yaml
kubectl get namespaces

### Deployment

kubectl run app-name image=image-name:tag --port=XXXX
kubectl get deployments


