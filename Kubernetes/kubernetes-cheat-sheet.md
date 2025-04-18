<h1 align="center">🚀 Kubernetes Cheat Sheet</h1>

🔹 Basic Concepts Cluster: A group of connected computers (nodes) that run applications.

  Node: A single computer in a cluster that runs applications.

  Pod: The smallest unit in Kubernetes that can run one or more containers.

  Namespace: A way to divide resources in a cluster for different projects or teams.

🔁 Workload Management
Deployment: Manages a set of identical pods to ensure the correct number are running.

ReplicaSet: Ensures a specified number of pod copies are running at all times.

DaemonSet: Ensures a pod runs on all or some nodes.

StatefulSet: Manages stateful applications, keeping track of each pod's identity.

Job: Runs a task until it completes successfully.

CronJob: Runs tasks on a scheduled basis.

🔌 Networking & Services
Service: Exposes a set of pods as a network service.

Ingress: Manages external access to services, usually HTTP.

Ingress Controller: Manages ingress resources and routes HTTP/HTTPS traffic.

Headless Service: Service without a cluster IP, used to directly access pods.

LoadBalancer Service: Exposes a service externally using a cloud provider’s load balancer.

ClusterIP Service: Exposes a service internally within the cluster.

🧠 Configuration & Storage
ConfigMap: Stores configuration data as key-value pairs.

Secret: Stores sensitive data like passwords and tokens.

Volume: Provides storage for containers.

PersistentVolume (PV): A piece of storage set up by an administrator.

PersistentVolumeClaim (PVC): A request for storage by a user.

StorageClass: Describes types of storage in the cluster.

🔧 Core Components
Kubelet: The agent that runs on each node to manage pods.

Kube-Proxy: Manages network rules on nodes.

Controller Manager: Manages controllers that regulate the state of the cluster.

Scheduler: Decides which node will run a pod.

Etcd: A key-value store that stores all cluster data.

Kubectl: CLI tool to interact with the Kubernetes API.

Helm: Package manager for Kubernetes.

⚙️ Autoscaling & Affinities
Horizontal Pod Autoscaler: Adjusts number of pods based on CPU/memory usage.

Cluster Autoscaler: Adjusts number of nodes in the cluster.

Affinity / Anti-Affinity: Rules for scheduling pods on specific nodes.

Taints & Tolerations: Prevent or allow pods to run on specific nodes.

🔐 Access & Security
Label: Key-value pairs for organizing objects.

Annotation: Metadata attached to objects.

RBAC (Role-Based Access Control): Manages who can do what.

ServiceAccount: Identity for processes running in pods.

ClusterRole / Role: Permissions across or within a namespace.

RoleBinding / ClusterRoleBinding: Assigns roles to users.

NetworkPolicy: Controls traffic between pods.

PodSecurityPolicy: Defines security rules for pods.

🔁 Reliability
PodDisruptionBudget (PDB): Limits the number of pods that can be down during maintenance.

CoreDNS: DNS server for cluster service discovery.

Init Containers: Run before main containers in a pod.

Sidecar Container: Runs alongside the main container.

🩺 Health Checks
Readiness Probe: Checks if a container is ready to accept traffic.

Liveness Probe: Checks if a container is still running and restarts it if needed.
