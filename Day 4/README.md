# Kubernetes Learning Journey

## 🌱 Day 4 – What I Learned on Kubernetes

### 🚀 Overview
Today, I deepened my understanding of Kubernetes, focusing on its core components for managing containerized applications. Kubernetes is essential for orchestrating, scaling, and maintaining containerized applications in a cloud-native environment.

### 📘 What is Kubernetes?
Kubernetes is an open-source container orchestration platform designed to automate the deployment, scaling, and operation of application containers. It allows you to manage your containers in a distributed system, ensuring high availability, scalability, and fault tolerance.

### 📦 Key Concepts Learned


🔹 Pods - The smallest and simplest Kubernetes object that represents a single instance of a running process in the cluster.
🔹 ReplicaSets - Ensures a specified number of replicas of a Pod are running at any given time.
🔹 Deployments - Manages Pods and ReplicaSets, enabling declarative updates to applications.
🔹 Services - Exposes applications running on a set of Pods to the outside world, supporting load balancing.
🔹 Namespaces - Provides a mechanism for isolating resources in a multi-tenant environment.
🔹 ConfigMaps & Secrets - Used for storing and managing application configurations and sensitive information.
🔹 Horizontal Pod Autoscaling - Automatically scales Pods based on observed CPU utilization or custom metrics.
🛠️ Commands Practiced

# ✅ Create a Pod
<pre><code>kubectl run mypod --image=nginx</code></pre>

# ✅ View all running Pods
<pre><code>kubectl get pods</code></pre>

# ✅ Expose a Pod as a Service
<pre><code>kubectl expose pod mypod --port=80 --type=NodePort</code></pre>

# ✅ Scale a deployment
<pre><code>kubectl scale deployment mydeployment --replicas=3</code></pre>

# ✅ View cluster services
kubectl get services

# ✅ Apply a configuration from a YAML file
<pre><code>kubectl apply -f deployment.yaml</code></pre>

# ✅ Check logs of a running Pod
<pre><code>kubectl logs mypod</code></pre>

# 📁 Folder Structure Sample
```plaintext
k8s/
  ├── deployment.yaml        # Kubernetes Deployment YAML file
  ├── service.yaml           # Service configuration for exposing the application
  ├── configmap.yaml         # ConfigMap to manage non-sensitive configurations
  ├── secret.yaml            # Secret configuration for sensitive information
  ├── kubernetes.tf          # Infrastructure as Code file for managing Kubernetes setup
  ```
# 📄 Sample deployment.yaml

apiVersion: apps/v1
kind: Deployment
metadata:
  name: myapp
spec:
  replicas: 3
  selector:
    matchLabels:
      app: myapp
  template:
    metadata:
      labels:
        app: myapp
    spec:
      containers:
      - name: myapp
        image: nginx
        ports:
        - containerPort: 80
        
# 💡 What I Understood

✅ Kubernetes automates container orchestration and deployment.
✅ Pods are the basic building blocks for running containers in Kubernetes.
✅ ReplicaSets ensure high availability by maintaining the desired number of replicas.
✅ Deployments allow for easy management of application updates and rollbacks.
✅ Services expose Pods and provide load balancing for distributed applications.
✅ Namespaces help isolate resources in large, multi-tenant clusters.
✅ ConfigMaps and Secrets offer secure management of application configurations and sensitive data.
✅ Horizontal Pod Autoscaling helps manage resource consumption by scaling Pods based on demand.
