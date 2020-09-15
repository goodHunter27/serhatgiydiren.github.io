---
title: System Design Interview - Distributed Message Queue
published: true
---

#### Excerpted from [here](https://youtu.be/iJLL-KPqBpM){:target="_blank"}

-----------------------

### Synchronous Communication
- When producer makes a call to a consumer, waits for a response. 
- Easier and faster to implement. 
- Harder to deal with consumer service failures. Need to think;
  - When and how to properly retry failed requests? 
  - How not to overwhelm consumer service with too many requests?
  - How to deal with a slow consumer service host? 

### Asynchronous Communication
- Queue : Producer sends data to that component and exactly one consumer gets this data to a short time after.
- It is distributed, because data is stored across several machines. 
- Do not confuse queue with topic. In case of a topic, message goes to all subscribers. In case of a queue, message is received by only one consumer. 

-----------------------

### Functional Requirements
- sendMessage(messageBody) 
- receiveMessage() 

### Non-Functional Requirements
- Scalable (handle load increasses, more queues, messages)
- Highly Available (tolerates hardware / network failures)
- Highly Performant (single digit latency, both send and receive operations are fast)
- Durable (once submitted, data is not lost, so persistent)

-----------------------

### High-level Architecture

![High-level Architecture](../assets/dmq_hla.png)

- VIP : Virtual IP : Refers to the symbolic hostname (myWebService.domain.com) that resolves to a load balancer system. 
- Load Balancer : A device that routes client requests across a number of servers. 
- FrontEnd Web Service : A component responsible for initial request processing, like validation, authentication. 
- Queue Metadata : Queue's name, creation date / time, owner and any other configuration settings will be stored in a DB. 
- Metadata service : As a best practice, this metadata DB should be hidden behind some interface, a dedicated web service responsible for handling calls to that DB. 
- BackEnd Web Service : Responsible for message persistence and processing. 

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

