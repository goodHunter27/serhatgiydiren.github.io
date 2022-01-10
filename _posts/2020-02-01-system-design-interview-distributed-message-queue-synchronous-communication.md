---
layout: default
---

<details><summary>Index</summary>  

  Visit here [Synchronous Communication](system-design-interview-distributed-message-queue-synchronous-communication)   

</details>  

### Synchronous Communication
- When producer makes a call to a consumer, waits for a response. 
- Easier and faster to implement. 
- Harder to deal with consumer service failures. Need to think;
  - When and how to properly retry failed requests? 
  - How not to overwhelm consumer service with too many requests?
  - How to deal with a slow consumer service host? 
