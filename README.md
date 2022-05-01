# kubernetes-ckad-prep

# kubernetes 
## Documentation 
https://kubernetes.io/docs/home/

##Create a new pod with the NGINX image
kubectl run nginx --image=nginx --generator=run-pod/v1

## Delete pod(s)
kubectl delete pods --all

kubectl delete pods pod_name

## Get pods
kubectl get pods

## Describe a particular pod 
kubectl describe pod pod_name

kubectl get pods -o wide 

## Create a new pod with the name 'redis123' and with the image 'redis123'
kubectl run redis --image=redis123 --generator=run-pod/v1
 
## Edit pods
kubectl edit pod pod_name

## Create pods using yaml file
Get the template from the k8s documentation site and use the below command.
     
kubectl create -f hello_pod.yaml

## Extract pod definition to yaml file and edit it.

If you are given a pod definition file, edit that file and use it to create a new pod. If you are not given a pod definition file, you may extract the definition to a file using the below command:

kubectl get pod <pod-name> -o yaml > pod-definition.yaml

Then edit the file to make the necessary changes, delete and re-create the pod.
Use the below command to edit pod properties.
 
kubectl edit pod <pod-name> 
   
## Get all replicasets, describe each replicasets, delete replicasets
kubectl get replicaset

kubectl describe replicaset

kubectl delete replicaset replicaset-1 replicaset-2

## Create replicaset using yaml definition file
kubectl create -f replicaset-definition.yaml

## Edit the replicaset
kubectl edit replicaset new-replicaset-1

## Scaling replicasets
kubectl scale --replicas=3 replicaset.apps/new-replica-set        # Scale a replicaset named 'new-replica-set' to 3

kubectl scale --replicas=3 -f foo.yaml                            # Scale a resource specified in "foo.yaml" to 3

kubectl scale --current-replicas=2 --replicas=3 deployment/mysql  # If the deployment named mysql's current size is 2, scale mysql to 3

kubectl scale --replicas=5 rc/foo rc/bar rc/baz                   # Scale multiple replication controllers

