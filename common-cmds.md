# For kubernetes basics

'''kubernetes
kubectl run redis --image=redis1234 --dry-run=client -o yaml > redis.yaml
'''

- to edit use:

'''kuberenetes
kubectl edit pod redis
'''

- if edited using vi:
'''kuberenetes
kubectl apply -f redis-definition.yaml
'''

# For Replica sets

- If you want to replace replica sets after editing yaml file

'''kubernetes
kubectl replace -f redis-definition.yaml
'''

- Scaling replicasets using command
- 
