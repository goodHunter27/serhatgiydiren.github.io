---
layout: default
---

### Message replication

- Messages need to be replicated to achieve high durability. Otherwise, if we only have one copy of data, it may be lost due to unexpected hardware failure.
- Messages can be replicated synchronously or asynchronously.
  - Synchronously means that when backend host receives new message, it waits until data is replicated to other hosts. And only if replication is fully completed, successful response is returned to a producer.
  - Asynchronous replication means that response is returned back to a producer as soon as message is stored on a single backend host.
Message is later replicated to other hosts.
- Both options have pros and cons.
  - Synchronous replication provides higher durability, but with a cost of higher latency for send message operation.
  - Asynchronous replication is more performant, but does not guarantee that message will survive backend host failure.

[Prev - Message deletion](system-design-interview-distributed-message-queue-message-deletion)  	

[Next - Message delivery semantics](system-design-interview-distributed-message-queue-message-delivery-semantics)  
