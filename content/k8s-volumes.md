Title: Understanding Kubernetes Storage: From Persistent Volumes to Storage Classes
Date: 2024-10-24 20:15
Category: Tech
Tags: k8s
Slug: understanding-kubernetes-storage-persistent-volumes-to-storage-classes
Authors: Ganesh Hubale

In Kubernetes, managing storage for applications running in pods is achieved through **Persistent Volumes (PV)**, **Persistent Volume Claims (PVC)**, and **Storage Classes (SC)**. Here's a quick breakdown:

#### 1. **Persistent Volume (PV)**:
A **Persistent Volume** is a piece of storage in the cluster provisioned by an administrator or dynamically using Storage Classes. It defines where the storage is located.

**Example PV YAML:**

```yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: my-pv
spec:
  capacity:
    storage: 1Gi
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Retain
  storageClassName: manual
  hostPath:
    path: "/mnt/data"
```

This example creates a PV of 1Gi, with **ReadWriteOnce** access, meaning it can be mounted as read-write by a single node. It uses the host's local storage at `/mnt/data`.

#### 2. **Persistent Volume Claim (PVC)**:
A **PVC** is how a pod requests storage. The claim specifies the size and access mode for the required storage.

**Example PVC YAML:**

```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: my-pvc
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 1Gi
  storageClassName: manual
```

This PVC requests 1Gi of storage and matches any PV with the `manual` storage class.

#### 3. **Storage Class (SC) for Dynamic Provisioning**:
A **Storage Class** automates PV provisioning. When a PVC references a Storage Class, Kubernetes creates the PV dynamically.

**Example SC YAML:**

```yaml
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: fast-storage
provisioner: kubernetes.io/aws-ebs  # Replace with your cloud provider or storage type
parameters:
  type: gp2  # AWS EBS volume type, modify for your storage type
  fsType: ext4
reclaimPolicy: Retain
```

This example Storage Class is for AWS EBS (`gp2` volume type) with **ext4** as the file system. You can modify this for other storage backends (e.g., GCE, Azure).

#### 4. **Pod with Persistent Volume (Bound by PVC)**:
A pod accesses a PV through the PVC. Here's an example pod definition:

**Example Pod YAML:**

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: my-pod
spec:
  containers:
    - name: app-container
      image: nginx
      volumeMounts:
        - mountPath: "/usr/share/nginx/html"
          name: my-storage
  volumes:
    - name: my-storage
      persistentVolumeClaim:
        claimName: my-pvc
```

This pod runs an `nginx` container, and the `/usr/share/nginx/html` directory inside the container is mounted from the storage specified by the PVC `my-pvc`.

### Example Flow:

1. **Without Storage Class**:

    - Manually create a PV.
    - Create a PVC to claim that PV.
    - Assign the PVC to a pod, which uses the storage from the PV.

2. **With Storage Class**:

    - Create a PVC referencing a Storage Class.
    - Kubernetes automatically provisions a PV based on the Storage Class.
    - The PVC is bound to the dynamically created PV, and the pod uses this storage.

Using Storage Classes simplifies the process in dynamic environments where storage needs change frequently.

