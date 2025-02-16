# For kubernetes basics

```kubernetes
kubectl run redis --image=redis1234 --dry-run=client -o yaml > redis.yaml
```

- to edit use:

```kubernetes
kubectl edit pod redis
```

- if edited using vi:

```kubernetes
kubectl apply -f redis-definition.yaml
```

## For Replica sets

- If you want to replace replica sets after editing yaml file

'''kubernetes
kubectl replace -f redis-definition.yaml
'''

- Scaling replicasets using command

## Here’s a tip

[Reference Bookmark this page for the exam. It will be very handy](https://kubernetes.io/docs/reference/kubectl/conventions/):

### Create an NGINX Pod

'''kubernetes
kubectl run nginx --image=nginx
'''

- Generate POD Manifest YAML file (-o yaml). Don’t create it(–dry-run)

'''kubernetes
kubectl run nginx --image=nginx --dry-run=client -o yaml
'''

### Create a deployment

'''kubernetes
kubectl create deployment --image=nginx nginx
'''

- Generate Deployment YAML file (-o yaml). Don’t create it(–dry-run)

'''kubernetes
kubectl create deployment --image=nginx nginx --dry-run=client -o yaml
'''

- Generate Deployment YAML file (-o yaml). Don’t create it(–dry-run) and save it to a file.

'''kubernetes
kubectl create deployment --image=nginx nginx --dry-run=client -o yaml > nginx-deployment.yaml
'''

- Make necessary changes to the file (for example, adding more replicas) and then create the deployment.

'''kubernetes
kubectl create -f nginx-deployment.yaml
'''

OR

- In k8s version 1.19+, we can specify the –replicas option to create a deployment with 4 replicas.

'''kubernetes
kubectl create deployment --image=nginx nginx --replicas=4 --dry-run=client -o yaml > nginx-deployment.yaml
'''
