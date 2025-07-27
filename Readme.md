# Kubernetes Workloads: CronJob, Job, DaemonSet, and StatefulSet

This repository showcases how to use different Kubernetes workload types to manage and run containers based on your application's needs. It includes examples for:

- **CronJob** – For scheduled tasks  
- **Job** – For one-time task execution  
- **DaemonSet** – To run pods on all cluster nodes  
- **StatefulSet** – For stateful applications requiring persistent storage

---

## 📂 Workloads Overview

### 🛠️ StatefulSet

**Use Case**: Deploying a persistent PostgreSQL database  
**Image Used**: `postgres:14-bookworm`

A StatefulSet is used to deploy a PostgreSQL container with persistent storage. This is ideal for stateful applications where stable pod identity and durable data are required.

> Ensure a `PersistentVolume` and `PersistentVolumeClaim` are available in the cluster for data persistence.

---

### ⏰ CronJob

**Use Case**: Scheduled task that runs every 2 minutes  
**Image Used**: `cezeike39/docker:cicd`

The CronJob runs a containerized task on a fixed schedule. The default schedule is every 2 minutes:

```yaml
spec:
  schedule: "*/2 * * * *"
