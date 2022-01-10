---
layout: default
---

### BackEnd Service

- Where and how messages are stored?
  - Newly arrived messages may live in memory for a short period of time or until memory on the backend host is fully utilized.
- How do we replicate data?
  - We will send copies of messages to some other hosts, so that data can survive host hardware or software failures.
- How FrontEnd hosts select backend hosts for both storing messages and retrieving them.
  - We can leverage Metadata service.

- Message comes to the FrontEnd, FrontEnd consults Metadata service what backend host to send data to. Message is sent to a selected backend host and data is replicated.
- When receive message call comes, FrontEnd talks to Metadata service to identify a backend host that stores the data.
- We will consider two options of how backend hosts relate to each other.

[Prev - Metadata Service](system-design-interview-distributed-message-queue-metadata-service)  	

[Next - Option A : Leader - Follower Relationship](system-design-interview-distributed-message-queue-option-a-leader-follower-relationship)  
