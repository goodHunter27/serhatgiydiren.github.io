---
layout: default
---

### Message delivery semantics

- There are three main message delivery guarantees.
  - At most once, when messages may be lost but are never redelivered.
  - At least once, when messages are never lost but may be redelivered.
  - And exactly once, when each message is delivered once and only once.
- Will anyone ever want other than exactly once delivery? The simple answer is that it is hard to achieve exactly once delivery in practice.
- In a distributed message queue system there are many potential points of failure. Producer may fail to deliver or deliver multiple times, data replication may fail, consumers may fail to retrieve or process the message.
- All this adds complexity and leads to the fact that most distributed queue solutions today support at-least-once delivery, as it provides a good balance between durability, availability and performance.

[Prev - Message replication](system-design-interview-distributed-message-queue-message-replication)  	

[Next - Push vs Pull](system-design-interview-distributed-message-queue-push-vs-pull)  
