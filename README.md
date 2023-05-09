# kubernetes-cheat-sheet

### Pod Commands

- Create a pod
```shell
kubectl run nginx --image=nginx
```

- Export k8s objects to yaml file
```shell
kubectl run nginx --image=nginx --dry-run=client -o yaml > pod.yaml
```

- Edit created pod
```shell
kubectl edit pod nginx
```

- Delete multiple pods
```shell
kubectl delete pod nginx nginx1 nginx2
```

### ReplicaSet Commands

- Scale ReplicaSet object without modifying the yaml file
```shell
kubectl scale --replicas=6 -f rs.yaml
```
```shell
kubectl scale rs new-replica-set --replicas=2
```

### Deployment Commands

- Create deployment
```shell
kubectl create deployment nginx --image=nginx
```

- Export deployment with 4 replicas to yaml file
```shell
kubectl create deploy httpd-frontend --image=httpd:2.4-alpine --replicas=3 --dry-run=client -o yaml > deploy.yaml
```