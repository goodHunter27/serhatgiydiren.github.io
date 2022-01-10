---
layout: default
---

### FrontEnd Service

- FrontEnd is a lightweight web service, consisting of stateless machines located across several data centers. 
- FrontEnd service is responsible for:
  - Request validation : Helps to ensure that all the required parameters are present in the request and values of these parameters honor constraints. For example, in our case we want to make sure queue name comes with every send message request. And message size does not exceed a specified threshold.
  - Authentication and authorization : During authentication check we verify that message sender is a registered customer of our distributed queue service. And during authorization check we verify that sender is allowed to publish messages to the queue it claims.
  - SSL termination : TLS is a protocol that aims to provide privacy and data integrity. TLS termination refers to the process of decrypting request and passing on an unencrypted request to the backend service. And we want to do TLS termination on FrontEnd hosts because TLS on the load balancer is expensive. Termination is usually handled by not a FrontEnd service itself, but a separate HTTP proxy that runs as a process on the same host.
  - Server-side data encryption : Because we want to store messages securely on backend hosts, messages are encrypted as soon as FrontEnd receives them. Messages are stored in encrypted form and FrontEnd decrypts them only when they are sent back to a consumer.
  - Caching : Cache stores copies of source data. In FrontEnd cache we will store metadata information about the most actively used queues. As well as user identity information to save on calls to authentication and authorization services.
  - Rate limiting (Throttling) : Rate limiting or throttling is the process of limiting the number of requests you can submit to a given operation in a given amount of time. Throttling protects the web service from being overwhelmed with requests. Leaky bucket algorithm is one of the most famous.
  - Request dispatching : FrontEnd service makes remote calls to at least two other web services: Metadata service and backend service. FrontEnd service creates HTTP clients for both services and makes sure that calls to these services are properly isolated. It means that when one service let's say Metadata service experiences a slowdown, requests to backend service are not impacted. There are common patterns like bulkhead and circuit breaker that helps to implement resources isolation and make service more resilient in cases when remote calls start to fail.
  - Request deduplication : It may occur when a response from a successful send message request failed to reach a client. Lesser an issue for 'at least once' delivery semantics, a bigger issue for 'exactly once' and 'at most once' delivery semantics, when we need to guarantee that message was never processed more than one time. Caching is usually used to store previously seen request ids to avoid deduplication.
  - Usage data collection : When we gather real-time information that can be used for audit. 
- And even though FrontEnd service has many responsibilities, the rule of thumb is to keep it as simple as possible. 

[Prev - VIP and Load Balancer](system-design-interview-distributed-message-queue-vip-and-load-balancer) 

[Next - Metadata Service](system-design-interview-distributed-message-queue-metadata-service) 
