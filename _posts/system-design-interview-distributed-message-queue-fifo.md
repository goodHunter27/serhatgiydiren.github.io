---
layout: default
---

### FIFO

- FIFO stands for first-in, first-out, meaning that the oldest message in a queue is always processed first.
- But in distributed systems, it is hard to maintain a strict order. Message A may be produced prior to message B, but it is hard to guarantee that message A will be stored and consumed prior to message B.
- For these reasons many distributed queue solutions out there either does not guarantee a strict order. Or have limitations around throughput, as queue cannot be fast while it's doing many additional validations and coordination to guarantee a strict order.

[Prev - Push vs Pull](system-design-interview-distributed-message-queue-push-vs-pull)  	

[Next - Security](system-design-interview-distributed-message-queue-security)  
