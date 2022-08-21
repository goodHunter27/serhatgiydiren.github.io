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

### Solution : Layering

![Solution Layering](../assets/comm_rpc/comm_rpc_02.png)

- Intermediate layers provide set of abstractions for applications and media
- New apps or media need only implement for intermediate layer’s interface

### Layering in the Internet 

![Layering in the Internet](../assets/comm_rpc/comm_rpc_03.png)

- Transport: Provide end-to-end communication between processes on different hosts
- Network: Deliver packets to destinations on other (heterogeneous) networks
- Link: Enables end hosts to exchange atomic messages with each other
- Physical: Moves bits between two hosts connected by a physical link

### Logical communication between layers

- How to forge agreement on meaning of bits exchanged b/w two hosts?
- Protocol: Rules that govern format, contents, and meaning of messages
- Each layer on a host interacts with its peer host’s corresponding layer via the protocol interface

![Logical communication between layers](../assets/comm_rpc/comm_rpc_04.png)

### Physical communication

- Communication goes down to the physical network
- Then from network peer to peer
- Then up to the relevant application

![Physical communication](../assets/comm_rpc/comm_rpc_05.png)

