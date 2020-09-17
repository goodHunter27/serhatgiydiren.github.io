---
title: System Design Interview - Rate Limiting (local and distributed)
published: false
---

#### Excerpted from [here](https://youtu.be/FU4WlwfS3G0){:target="_blank"}

![High-level Architecture](../assets/ns_hla.png)

-----------------------

- 

-----------------------

### Functional Requirements
- createTopic(topicName) 

### Non-Functional Requirements
- Scalable (supports an arbitrarily large number of topics, publishers and subscribers)
- Highly Available (tolerates hardware / network failures, no single point of failure)
- Highly Performant (keep end-to-end latency as low as possible, so that messages are delivered to subscribers as soon as possible)
- Durable (messages must not be lost, each subscriber must receive every message at least once)

-----------------------

### High-level Architecture

