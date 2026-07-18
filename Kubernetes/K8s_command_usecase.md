### Create a new pod using nginx image

> kubectl run nginx --image=nginx
---
### Check for the number of pod creation

> kubectl get pods
---
### Check for all the pods in details so that we could check there nodes as well

> kubectl get pods -A -o wide
---

### How to check the replicasets present in the namespace

> kubectl get deployment

> kubectl get deploy
---
