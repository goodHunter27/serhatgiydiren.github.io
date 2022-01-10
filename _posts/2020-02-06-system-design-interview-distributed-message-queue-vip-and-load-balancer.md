---
layout: default
---

### VIP and Load Balancer

![VIP and Load Balancer](../assets/dmq_vip_lb.png)

- When domain name is hit, request is transferred to one of the VIPs registered in DNS for our domain name.
- VIP is resolved to a load balancer device, which has a knowledge of FrontEnd hosts.
- Several Points: 
  - First, load balancer seems like a single point of failure. What happens if load balancer device goes down?
  - Second, load balancers have limits with regards to number of requests they can process and number of bytes they can transfer. What happens when our distributed message queue service becomes so popular that load balancer limits are reached? 
- To address high availability concerns, load balancers utilize a concept of primary and secondary nodes. The primary node accepts connections and serves requests while the secondary node monitors the primary. If, the primary node is unable to accept connections, the secondary node takes over. 
- As for scalability concerns, a concept of multiple VIPs (sometimes referred as VIP partitioning) can be utilized. In DNS we assign multiple A-records to the same DNS name for the service. As a result, requests are partitioned across several load balancers.
- And by spreading load balancers across several data centers, we improve both availability and performance. 

[Prev - High-level Architecture](system-design-interview-distributed-message-queue-high-level-architecture) 

[Next - FrontEnd Service](system-design-interview-distributed-message-queue-frontend-service) 
