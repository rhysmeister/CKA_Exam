A few notes from the, excellent, [CKA Course](https://www.udemy.com/course/certified-kubernetes-administrator-with-practice-tests/)

#Reference (Bookmark this page for exam. It will be very handy):

https://kubernetes.io/docs/reference/kubectl/conventions/

# Create an NGINX Pod

```bash
kubectl run nginx --image=nginx
```

# Generate POD Manifest YAML file (-o yaml). Don't create it(--dry-run)

```bash
kubectl run nginx --image=nginx --dry-run=client -o yaml
```

# Create a deployment

```bash
kubectl create deployment --image=nginx nginx
```

# Generate Deployment YAML file (-o yaml). Don't create it(--dry-run)

```bash
kubectl create deployment --image=nginx nginx --dry-run=client -o yaml
```

# Generate Deployment YAML file (-o yaml). Don’t create it(–dry-run) and save it to a file.

```bash
kubectl create deployment --image=nginx nginx --dry-run=client -o yaml > nginx-deployment.yaml
```

# Make necessary changes to the file (for example, adding more replicas) and then create the deployment.

```bash
kubectl create -f nginx-deployment.yaml
```

OR

In k8s version 1.19+, we can specify the --replicas option to create a deployment with 4 replicas.

```bash
kubectl create deployment --image=nginx nginx --replicas=4 --dry-run=client -o yaml > nginx-deployment.yaml
```

# 3 Examples for generating services with kubectl

## ClusterIP (default type)

```bash
kubectl create service clusterip my-service --tcp=80:80 --dry-run=client -o yaml
```

## NodePort

```bash
kubectl create service nodeport my-service --tcp=80:80 --dry-run=client -o yaml --type=NodePort
```

## LoadBalancer

```bash
kubectl create service loadbalancer my-service --tcp=80:80 --dry-run=client -o yaml --type=LoadBalancer
```

