# kubernetes-cheat-sheet

## Create a pod
kubectl run nginx --image=nginx

## Export k8s objects to yaml file
kubectl run nginx --image=nginx --dry-run=client -o yaml > pod.yaml

## Edit created pod
kubectl edit pod nginx
