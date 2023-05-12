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

- Count number of pods running with a certain label
```shell
kubectl get pod --selector env=dev,tier=frontend --no-headers | wc -l
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

- Scale Deployment
```shell
kubectl scale deployment nginx --replicas=4
```

- Change image tag of Deployment
```shell
kubectl set image deployment nginx nginx=nginx:1.18
```

### Service Commands

- Create Service
```shell
kubectl expose pod redis --port=6379 --name=redis-service
```
```shell
kubectl expose deployment redis --port=6379 --name=redis-service
```

### Kube config

- Get current context
```shell
kubectl config current-context
```

- Set context and namespace (this not used to change or switch current context)
```shell
kubectl config set-context $(kubectl config current-context) --namespace=dev
```

- Switch context
```shell
kubectl config use-context dev-aks
```

### Taints and toleration commands

- Create taints on a node
```shell
kubectl taint nodes node01 app=frontend:NoSchedule
```

- Untaint the node
```shell
kubectl taint nodes node01 app=frontend:NoSchedule-
```

### Rolling updates and Rollback commands

- Check rollout status
```shell
kubectl rollout status deployment/myapp-deploy
```

- Check rollout history
```shell
kubectl rollout history deployment/myapp-deploy
```

- Rollback to previous revision
```shell
kubectl rollout undo deployment/myapp-deploy
```