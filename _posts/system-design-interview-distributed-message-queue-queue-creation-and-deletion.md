---
layout: default
---

### Queue creation and deletion

- Queue can be auto-created, for example when the first message for the queue hits FrontEnd service, or we can define API for queue creation.
- API is a better option, as we will have more control over queue configuration parameters.
- Delete queue operation is a bit controversial, as it may cause a lot of harm and must be executed with caution.
- For this reason, you may find examples of well-known distributed queues that do not expose deleteQueue API via public REST endpoint.
- Instead, this operation may be exposed through a command line utility, so that only experienced admin users may call it.

[Prev - In-cluster Manager vs Out-cluster Manager](system-design-interview-distributed-message-queue-in-cluster-manager-vs-out-cluster-manager)

[Next - Message deletion](system-design-interview-distributed-message-queue-message-deletion) 
