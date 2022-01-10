---
layout: default
---

### Message deletion

- There are several options at our disposal.
  - One option is not to delete a message right after it was consumed. In this case consumers have to be responsible for what they already consumed. And it is not as easy as it sounds. As we need to maintain some kind of an order for messages in the queue and keep track of the offset, which is the position of a message within a queue. Messages can then be deleted several days later, by a job. This idea is used by Apache Kafka.
  - The second option, is to do something similar to what Amazon SQS is doing. Messages are also not deleted immediately, but marked as invisible, so that other consumers may not get already retrieved message. Consumer that retrieved the message, needs to then call delete message API to delete the message from a backend host. And if the message was not explicitly deleted by a consumer, message becomes visible and may be delivered and processed twice.

[Prev - Queue creation and deletion](system-design-interview-distributed-message-queue-queue-creation-and-deletion)  	

[Next - Message replication](system-design-interview-distributed-message-queue-message-replication)  
