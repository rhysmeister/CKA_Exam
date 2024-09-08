# Kubernetes Certified Administrator Exam Cheatsheet

| **Topic**             | **Command**                                                                                         | **Example**                                                              |
|-----------------------|-----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| **Basic Commands**     | **Get cluster info**                                                                                | `kubectl cluster-info`                                                   |
|                       | **Get nodes**                                                                                       | `kubectl get nodes`                                                      |
|                       | **Get pods in all namespaces**                                                                      | `kubectl get pods --all-namespaces`                                       |
|                       | **Describe resource**                                                                               | `kubectl describe <resource> <name>`                                      |
|                       | **Delete resource**                                                                                 | `kubectl delete <resource> <name>`                                        |
| **Namespaces**         | **Create namespace**                                                                                | `kubectl create namespace <name>`                                         |
|                       | **Set namespace**                                                                                   | `kubectl config set-context --current --namespace=<name>`                 |
| **Pods and Containers**| **Run a pod**                                                                                       | `kubectl run <name> --image=<image>`                                      |
|                       | **Get pod logs**                                                                                    | `kubectl logs <pod-name>`                                                 |
|                       | **Execute a command in a pod**                                                                      | `kubectl exec -it <pod-name> -- <command>`                                |
| **Deployments**        | **Create a deployment**                                                                             | `kubectl create deployment <name> --image=<image>`                        |
|                       | **Scale deployment**                                                                                | `kubectl scale deployment <name> --replicas=<number>`                     |
|                       | **Update image**                                                                                    | `kubectl set image deployment/<name> <container>=<new-image>`             |
|                       | **Rollout status**                                                                                  | `kubectl rollout status deployment/<name>`                                |
|                       | **Rollback a deployment**                                                                           | `kubectl rollout undo deployment/<name>`                                  |
| **Services**           | **Expose a deployment as a service**                                                                | `kubectl expose deployment <name> --type=<type> --port=<port>`            |
|                       | **Get services**                                                                                    | `kubectl get svc`                                                         |
|                       | **Delete a service**                                                                                | `kubectl delete svc <name>`                                               |
| **ConfigMaps & Secrets**| **Create a ConfigMap from file**                                                                   | `kubectl create configmap <name> --from-file=<file>`                      |
|                       | **Create a Secret from literals**                                                                   | `kubectl create secret generic <name> --from-literal=<key>=<value>`       |
|                       | **Get ConfigMaps and Secrets**                                                                      | `kubectl get configmaps` / `kubectl get secrets`                          |
| **Persistent Volumes** | **Create a PersistentVolumeClaim (PVC)**                                                            | `kubectl apply -f <pvc-definition.yaml>`                                  |
|                       | **Get PVCs**                                                                                        | `kubectl get pvc`                                                         |
| **Network Policies**   | **Apply a network policy**                                                                          | `kubectl apply -f <network-policy.yaml>`                                  |
| **Node Maintenance**   | **Cordon a node**                                                                                   | `kubectl cordon <node-name>`                                              |
|                       | **Drain a node**                                                                                    | `kubectl drain <node-name> --ignore-daemonsets`                           |
|                       | **Uncordon a node**                                                                                 | `kubectl uncordon <node-name>`                                            |
| **Security & RBAC**    | **Create a role binding**                                                                           | `kubectl create rolebinding <name> --role=<role-name> --user=<user-name> --namespace=<namespace>`|
|                       | **Create a cluster role binding**                                                                   | `kubectl create clusterrolebinding <name> --clusterrole=<role> --user=<user>`|
| **Resources**          | **Top nodes (get node resource usage)**                                                             | `kubectl top nodes`                                                       |
|                       | **Top pods (get pod resource usage)**                                                               | `kubectl top pods --namespace=<namespace>`                                |
| **ETCD Backup**        | **Backup ETCD**                                                                                     | `ETCDCTL_API=3 etcdctl snapshot save <backup-file> --endpoints=<endpoint>`|
| **Scheduling**         | **View taints on nodes**                                                                           | `kubectl get nodes -o json | jq '.items[].spec.taints'`                 |
|                       | **Apply taints to a node**                                                                          | `kubectl taint nodes <node-name> key=value:NoSchedule`                   |
