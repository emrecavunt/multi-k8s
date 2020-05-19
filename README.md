

kubectl apply -f client.pod.yaml

kubectl apply -f client-node-port.yaml

kubectl apply -f client-deployment.yaml

## print the status of all running pods
kubectl get pods 

## print the status of all running services

kubectl get services

## get minikube ip 
minikube ip


##Get detailed info about an object
                                | optional | 
kubectl describe <object type>  <object name>

kubectl describe pod client-pod

to Update Pod Config 
containers : 1  ### Can't be updated!
name : client ### Can't be updated!
port: 3000 ### Can't be updated!
image: multi-worker  ### Can be update

 | Pods                             | Deployment
------------------------------------------------
- Runs a single set of containers   | - Runs a set of identical pods (one or more)
- Good For one-off dev purposess    | - Monitors the state of each pod, updating as necessary
- Rarely used directly in           | - Good for dev
production                          | - Good for production

    
## Remove an object

kubectl delete -f <config file>

 
 kubectl get deployments

 kubectl delete deployment client-deployment

kubectl get services
kubectl delete service client-node-port
# To get additional infos 
 kubectl get pods -o wide


 #logs of deployments

 kubectl logs client-deployment-85c9c4447b-tsdv5

 # exec it the deployment of docker file

kubectl exec -it client-deployment-85c9c4447b-tsdv5 sh

PVC = Persisten Volume Claims

ClusterIp services
 - it will not allow traffic outside world its not like nodePort
 - Exposes a set of pods to other objects in the ClusterIp
 

 deploy folder 
kubectl apply -f ${folderName}
kubectl apply -f k8s 

Persistent Volume Claims ( PVC )

##Volume in generic container terminology
Some type of mechanism that allows a container to access a filesystem outside itself

##"Volume" in Kubernetes 
An object that allows a container to store data at the pod leve
object = deployment is an object , service is an object

kubectl get storageclass

#
kubectl get pv 

#advertisement of pv 
kubectl get pvc


### SECRET
kubectl create secret generic <secret_name> --from-literal key=value


##Ingress


kubectl apply -f https://raw
.githubusercontent.com/kubernetes/ingress-nginx/controller-0.32.0/depl
oy/static/provider/cloud/deploy.yaml

minikube addons enable ingress

kubectl get svc -n ingress-nginx


## minikube enable Dashboard

minikube dashboard 