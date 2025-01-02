# Kubernetes Components - Low-Level Overview

Kubernetes is a powerful container orchestration platform designed to automate the deployment, scaling, and management of containerized applications. This document provides an in-depth look at its key components at a low level.

## **Master Node Components**
The master node is responsible for managing the Kubernetes cluster and maintaining its desired state.

### 1. **API Server (`kube-apiserver`):**
- Acts as the central management point for the cluster.
- **Responsibilities:**
  - Exposes the Kubernetes API via RESTful endpoints.
  - Validates and processes API requests (e.g., `kubectl` commands).
  - Serves as the front end for the cluster's control plane.
  - Manages authentication, authorization, and admission control.
- **Communication:**
  - Talks to `etcd` for persistent storage.
  - Serves requests to components like kubelet, controllers, and the scheduler.

### 2. **etcd:**
- A highly available, distributed key-value store.
- **Responsibilities:**
  - Stores all cluster data, including configurations, secrets, and service discovery information.
  - Ensures consistency and availability of cluster state across nodes.
- **Features:**
  - Supports snapshot and restore operations for backup and disaster recovery.
  - Uses the Raft consensus algorithm to maintain consistency.

### 3. **Controller Manager (`kube-controller-manager`):**
- Runs various controllers as separate threads within a single process.
- **Key Controllers:**
  - **Node Controller:** Detects and reacts to node failures.
  - **Replication Controller:** Ensures the specified number of pod replicas are running.
  - **Endpoint Controller:** Updates endpoint objects when services and pods change.
  - **Service Account Controller:** Manages service account tokens.
  - **Persistent Volume Controller:** Manages storage provisioning and binding.
- **Monitoring:** Continuously reconciles the actual state of resources with the desired state.

### 4. **Scheduler (`kube-scheduler`):**
- Assigns pods to nodes based on resource availability and scheduling policies.
- **Responsibilities:**
  - Evaluates node fitness for pods using constraints and predicates like CPU, memory, affinity rules, and taints/tolerations.
  - Implements priorities for fair resource distribution.
  - Continuously watches for unscheduled pods and assigns them to nodes.

## **Worker Node Components**
Worker nodes run application workloads and report their status to the master node.

### 1. **Kubelet:**
- A node-level agent that manages pod operations.
- **Responsibilities:**
  - Ensures containers specified in pod specs are running and healthy.
  - Interacts with the container runtime to start, stop, and monitor containers.
  - Performs health checks (liveness and readiness probes).
  - Fetches pod definitions from the API server or local manifests.

### 2. **Container Runtime:**
- The underlying software responsible for running containers.
- **Examples:** Docker, containerd, CRI-O.
- **Responsibilities:**
  - Pulls container images from registries.
  - Creates and manages container instances.
  - Exposes container runtime interfaces (CRI) to kubelet.

### 3. **Kube-Proxy:**
- Manages networking and service discovery for the cluster.
- **Responsibilities:**
  - Configures network rules (iptables or IPVS) to route traffic to appropriate pods.
  - Implements service-level load balancing within the cluster.
  - Handles communication between cluster services and external clients.

### 4. **cAdvisor (Container Advisor):**
- An integrated monitoring tool within kubelet.
- **Responsibilities:**
  - Collects resource usage data (CPU, memory, disk I/O, network traffic) from containers.
  - Exposes metrics to other monitoring tools like Prometheus.

## **Additional Components**

### 1. **Networking Components:**
- **CNI Plugins:**
  - Implement container networking capabilities, such as IP address management and network isolation.
  - Examples: Flannel, Calico, Weave Net.
- **CoreDNS:**
  - Provides DNS-based service discovery for the cluster.
  - Maps service names to IP addresses, enabling easy inter-service communication.

### 2. **Add-ons:**
- Extend the functionality and observability of Kubernetes.
  - **Metrics Server:** Collects and aggregates resource metrics for horizontal pod autoscaling.
  - **Dashboard:** A web-based UI for managing and visualizing cluster resources.
  - **Ingress Controller:** Handles HTTP(S) traffic routing and exposes services externally.

## **Cluster Workflow Summary**
1. User submits a workload request (e.g., deploy a pod) via the `kubectl` command.
2. The API server authenticates and validates the request, then updates the `etcd` store with the desired state.
3. The scheduler evaluates available nodes and assigns the pod to the most suitable node.
4. The kubelet on the selected node retrieves the pod specification and starts the containers using the container runtime.
5. Networking components (CNI, kube-proxy) ensure connectivity and traffic routing for the pod.
6. Controllers continuously monitor the cluster and perform corrective actions to maintain the desired state.

---
For more detailed insights, refer to the [Kubernetes Documentation](https://kubernetes.io/docs/).
