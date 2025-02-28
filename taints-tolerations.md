# Taints and tolerations

- Command to make taint on node

```bash
kubectl taint node node01 spray=mortein:NoSchedule
```

- Command to check if Taint exists

```bash
kubectl describe node node01 | grep Taint
```

- Command to untaint or remove taint is the same but with dash at the end

```bash
kubectl taint nodes controlplane node-role.kubernetes.io/control-plane:NoSchedule-
```

- Yaml file to make a pod toleration

```yaml
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: bee
  name: bee
spec:
  containers:
  - image: nginx
    name: bee
    resources: {}
  tolerations:
  - key: spray
    value: mortein
    effect: NoSchedule
    operator: Equal
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
~                                                                                                                                                      
~                    
```
