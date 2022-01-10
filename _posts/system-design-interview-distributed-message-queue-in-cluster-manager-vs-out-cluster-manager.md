---
layout: default
---

### In-cluster Manager vs Out-cluster Manager

- In-cluster manager manages queue assignment within the cluster, out-cluster manager manages queue assignment across clusters.
- In-cluster manager needs to know about each and every instance in the cluster. Out-cluster manager may not know about each particular instance, but it needs to know about each cluster.
- In-cluster manager listens to heartbeats from instances. Out-cluster manager monitors health of each independent cluster.
- In-cluster manager deals with host failures and needs to adjust to the fact that instances may die and new instances may be added to the cluster, out-cluster manager is responsible for tracking each cluster utilization and deal with overheated clusters. Meaning that new queues may no longer be assigned to clusters that reached their capacity limits.
- In-cluster manager splits queue into parts (partitions) and each partition gets a leader server. Out-cluster manager may split queue across several clusters. So that messages for the same queue are equally distributed between several clusters.

[Prev - Option B : Small cluster of independent hosts](system-design-interview-distributed-message-queue-option-b-small-cluster-of-independent-hosts)  

[Next - Queue creation and deletion](system-design-interview-distributed-message-queue-queue-creation-and-deletion)  
