# 1. What is an IP address? (100 words)  
  
- Why do we need IP addresses?  
-An IP address is a unique numerical identifier assigned to each device on a network acting like a physical mailing address so data knows where to go. We need them because without a unique ID our routers wouldn't be able to distinguish between billions of connected devices to deliver packets. 
- What is the relation between TCP and IP?  
-TCP (Transmission Control Protocol) sits on top of IP; while IP handles the actual delivery TCP ensures that the data arrives in the correct order and without errors
- What is a socket? Have you heard of different types of sockets?  
-A socket is a software abstraction used to establish a connection between a client and a server, typically defined by an IP address and a port number. I’ve heard of standard TCP sockets, which can be hard to program, and ØMQ sockets, which are much more robust and handle things like automatic reconnection and queuing.
- What is up with the address `127.0.0.1`?  
-The address 127.0.0.1 is the "localhost" or loopback address; it's used when a program wants to communicate with itself on the same machine
  
# 2. What does a client-server architecture mean? (150 words)  
Client-Server (or 2-tier) architecture is a style where a system is divided into two distinct roles: clients that request services and servers that provide them. The intent is to manage shared resources and services in a central location to improve modifiability and reuse.

- Give a concrete example of where you would encounter this in real life.  
-A classic example is a web browser (the client) requesting a webpage from a web server
- How do you decide who is the server and who is the client?  
-The distinction is based on the initiation of the interaction; the client is the component that sends a "Request," and the server is the one that manages the resources and sends a "Reply"
  
# 3. What is the difference between client-server architecture and the broker architecture? (100 words)  
The main difference is that Broker architecture introduces an intermediary component between the client and server. In a standard client-server setup, the client usually needs to know the server's identity or location. In a Broker system, the client sends a request to the broker, which then dynamically locates and forwards the request to an appropriate server

- What are the benefits to the broker pattern?  
-It provides location transparency, meaning clients don't need to know where the service provider is. It also improves availability, as the broker can dynamically choose a replacement if a server goes down.
- What could be potential downsides?  
-It adds complexity and potential latency because every message must pass through an extra hop
  
# 4. What does Peer-to-Peer mean? (150 words)  
Peer-to-Peer is a decentralized style where all "peers" have the same significance and interact directly without a central server. Unlike the asymmetrical client-server model, any peer can act as both a service provider and a consumer

- What are the main characteristics of this architecture?  
-High scalability and availability because there is no single point of failure; if one peer leaves, the network remains healthy
- Have you encountered it anywhere online?  
-Torrenting
- Does Peer-to-Peer applications mean that there are no servers and only clients?  
-Generally, no, but some architectures use "super-peers" for specialized tasks like routing or indexing to help other peers discover each other
- What benefits could there be to using this pattern?  
-Massive scalability and robustness
- What downsides could there be to this pattern?
-Finding resources can be slower because requests are often propagated through multiple peers rather than a central index