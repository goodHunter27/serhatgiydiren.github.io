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

![High Level Architecture](https://github.com/serhatgiydiren/serhatgiydiren.github.io/raw/master/assets/dmq_hla.png)

VIP : Virtual IP : Refers to the symbolic hostname (myWebService.domain.com) that resolves to a load balancer system.
Load Balancer : A device that routes client requests across a number of servers.
FrontEnd Web Service : A component responsible for initial request processing, like validation, authentication.
Queue Metadata : Queue's name, creation date / time, owner and any other configuration settings will be stored in a DB.
Metadata service : As a best practice, this metadata DB should be hidden behind some interface, a dedicated web service responsible for handling calls to that DB.
BackEnd Web Service : Responsible for message persistence and processing. 
