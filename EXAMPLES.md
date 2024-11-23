# kubectl Example

## Create a Service Account

Create a service account, customer role and binds the service account to the role.

```bash
kubectl create serviceaccount pvviewer
kubectl create clusterrole pvviewer-role --verb=list --resource=persistentvolumes
kubectl create clusterrolebinding pvviewer-role-binding --clusterrole=pvviewer-role --user=pvviewer
```

## Query node Internal IP Addresses

Uses a JSON Path query to print out only the node addresses of type "InternalIP". All output is on one line.

```bash
kubectl get nodes -o=jsonpath='{.items[*].status.addresses[?(@.type=="InternalIP")].address}' > /root/CKA/node_ips
```

### A Simple Network Policy allowing port 80 access

```yaml
---
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: ingress-to-nptest
  namespace: default
spec:
  podSelector:
    matchLabels:
      run: np-test-1
  policyTypes:
  - Ingress
  ingress:
  - ports:
    - protocol: TCP
      port: 80
```