---
layout: default
---

### Push vs Pull

- With a pull model, consumer constantly sends retrieve message requests and when new message is available in the queue, it is sent back to a consumer.
- With a push model, consumer is not constantly bombarding FrontEnd service with receive calls. Instead, consumer is notified as soon as new message arrives to the queue.
- And as always, there are pros and cons. From a distributed message queue perspective pull is easier to implement than a push. But from a consumer perspective, we need to do more work if we pull.

[Prev - Message delivery semantics](system-design-interview-distributed-message-queue-message-delivery-semantics)  	

[Next - FIFO](system-design-interview-distributed-message-queue-fifo)  
