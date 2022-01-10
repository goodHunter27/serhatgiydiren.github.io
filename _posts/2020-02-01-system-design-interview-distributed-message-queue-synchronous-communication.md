---
title: System Design Interview - Distributed Message Queue - Synchronous Communication
published: true
---

[1 - Synchronous Communication](system-design-interview-distributed-message-queue-synchronous-communication)  
[2 - Synchronous Communication](system-design-interview-distributed-message-queue-synchronous-communication)  

### Synchronous Communication
- When producer makes a call to a consumer, waits for a response. 
- Easier and faster to implement. 
- Harder to deal with consumer service failures. Need to think;
  - When and how to properly retry failed requests? 
  - How not to overwhelm consumer service with too many requests?
  - How to deal with a slow consumer service host? 
