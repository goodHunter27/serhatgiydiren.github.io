---
layout: default
---

### Final Look

- Is our system scalable?
  - Yes. As every component is scalable.
  - When load increases, we just add more load balancers, more FrontEnd hosts, more Metadata service cache shards, more backend clusters and hosts.
- Is our system highly available?
  - Yes. As there is no a single point of failure, each component is deployed across several data centers. Individual hosts may die, network partitions may happen, but with this redundancy in place our system will continue to operate.
- Is our system highly performant?
  - It's actually very well depends on the implementation, hardware and network setup.
  - Each individual microservice needs to be fast.
  - And we need to run our software in high-performance data centers.
- Is our system durable?
  - Sure. We replicate data while storing and ensure messages are not lost during the transfer from a producer and to a consumer. 

[Prev - Monitoring](system-design-interview-distributed-message-queue-monitoring)    
  
[Next - Index](system-design-interview-distributed-message-queue)   
