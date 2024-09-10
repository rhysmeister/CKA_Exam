# CKA_Exam
Certified KUberentes Administrator Exam Notes and Cheatsheet

# Certified Kubernetes Administrator (CKA) Exam Curriculum

This document outlines the key knowledge, skills, and abilities a Certified Kubernetes Administrator (CKA) should demonstrate.

## CKA Curriculum

### 25% - Cluster Architecture, Installation & Configuration
- Manage role-based access control (RBAC)
- Use Kubeadm to install a basic cluster
  * [kubeadm](https://kubernetes.io/docs/reference/setup-tools/kubeadm/)
  * [Creating a cluster with kubeadm](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/)

```bash
sudo kubeadm init --apiserver-advertise-address=$IPADDR \
    --apiserver-cert-extra-sans=$IPADDR \
    --pod-network-cidr=$POD_CIDR \
    --node-name $NODENAME
```

||Command part||Description||
|--------------|------------|
|kubeadm init  |Initializes a Kubernetes control-plane node|
|--apiserver-advertise-address|The IP address the API Server will advertise it's listening on. If not set the default network interface will be used|
|--apiserver-cert-extra-sans|Optional extra Subject Alternative Names (SANs) to use for the API Server serving certificate. Can be both IP addresses and DNS names|
|--pod-network-cidr|Specify range of IP addresses for the pod network. If set, the control plane will automatically allocate CIDRs for every node|
|--node-name|Specify the node name|



- Manage a highly-available Kubernetes cluster
- Provision infrastructure to deploy a Kubernetes cluster
- Perform a version upgrade on a Kubernetes cluster using Kubeadm
- Implement etcd backup and restore
- Understand deployments, rolling updates, and rollbacks
- Use ConfigMaps and Secrets to configure applications
- Know how to scale applications
- Understand resource limits and Pod scheduling
- Awareness of manifest management and templating tools
- Understand host networking configuration on cluster nodes
- Understand connectivity between Pods
- Understand ClusterIP, NodePort, LoadBalancer services, and endpoints
- Use Ingress controllers and Ingress resources
- Configure and use CoreDNS
- Choose a container network interface plugin

### 15% - Workloads & Scheduling
- Manage deployments and rolling updates
- Scale workloads
- Manage job and cron job resources
- Manage Pod scheduling, affinity/anti-affinity rules

### 20% - Services & Networking
- Understand service networking
- Implement NetworkPolicies
- Use CoreDNS for service discovery
- Troubleshoot cluster networking issues

### 10% - Storage
- Understand storage classes, persistent volumes, and persistent volume claims
- Configure applications with persistent storage
- Manage storage access modes and reclaim policies

### 30% - Troubleshooting
- Evaluate cluster and node logging
- Monitor applications
- Troubleshoot application failures and cluster components
- Troubleshoot networking issues

---
For more details on the CKA curriculum, refer to the [CNCF official document](https://github.com/cncf/curriculum/blob/master/CKA_Curriculum_v1.30.pdf).

# Practice Lab Questions & Solutions

- https://killer.sh/ The official Lab simulator.
- https://github.com/devopshubproject/cka-lab/ A few years old but a good set of problems and solutions.