---
title: Distributed Systems - Network Communication and Remote Procedure Calls (RPCs)
published: false
---

### The problem of communication
- Process on Host A wants to talk to process on Host B
- A and B must agree on the meaning of the bits being sent and received at many different levels, including:
  - How many volts is a 0 bit, a 1 bit?
  - How does receiver know which is the last bit?
  - How many bits long is a number?

![The problem of communication](../assets/comm_rpc/comm_rpc_01.png)

- Re-implement every application for every new underlying transmission medium?
- Change every application on any change to an underlying transmission medium?
- No! But how does the Internet design avoid this?
