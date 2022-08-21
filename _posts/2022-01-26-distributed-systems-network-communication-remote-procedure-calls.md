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

### Communication between peers

- How do peer protocols coordinate with each other?
- Layer attaches its own header (H) to communicate with peer
- Higher layers’ headers, data encapsulated inside message
- Lower layers don’t generally inspect higher layers’ headers

![Communication between peers](../assets/comm_rpc/comm_rpc_06.png)

### Network socket-based communication

- Socket: The interface the OS provides to the network
  - Provides inter-process explicit message exchange
- Can build distributed systems atop sockets: send(), recv()
  - e.g.: put(key,value) -> message

![Network socket-based communication](../assets/comm_rpc/comm_rpc_07.png)

### Socket programming: still not great

```C
// Create a socket for the client
if ((sockfd = socket (AF_INET, SOCK_STREAM, 0)) < 0) {
perror(”Socket creation");
exit(2);
}

// Set server address and port
memset(&servaddr, 0, sizeof(servaddr));
servaddr.sin_family = AF_INET;
servaddr.sin_addr.s_addr = inet_addr(argv[1]);
servaddr.sin_port = htons(SERV_PORT); // to big-endian

// Establish TCP connection
if (connect(sockfd, (struct sockaddr *) &servaddr, sizeof(servaddr)) < 0) {
perror(”Connect to server");
exit(3);
}

// Transmit the data over the TCP connection
send(sockfd, buf, strlen(buf), 0);
```
