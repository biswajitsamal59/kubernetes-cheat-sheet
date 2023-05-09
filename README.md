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

### ReplicaSet Commands
- Scale ReplicaSet object without modifying the yaml file
```shell
kubectl scale -replicas=6 -f rs.yaml
```
