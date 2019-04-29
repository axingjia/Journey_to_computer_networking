A new Start. ** Computer Networking: A Top-Down Approach. **.    
Reading it and taking notes

# chapter 1: What is the Internet
Summary: 
* Will look at the network's edge and end systems and network applications
* the core of a computer network as well as the access networks and physical media
* second half of this chapter: boarder and more abstract view: delay, loss and throughput of data in a computer network and provide simple quantitative models for end-to-end throughput and delay: models that take into account transmission, propagation, and queuing delays.
* key architectural principle in computer networking: namely protocol layering and service models
* different attacks and how to make it more secure
* brief history

[term]Host/End system: devices that connect to the network  
  
[term]End systems are connected together by a network of ** communication links ** and **packet switches**. communication link example: physical media including coaxial cable, copper wire, optical fiber and radio spectrum 
   
[term]Packet: the segmented package of information/data that is sent through network
    
[term]Packet switch: take a package arriving on one of its incoming communication links and forwards that packet on one of its outgoing communication links. Ex: **routers** and **link-layer switch**. Link-layer switches are typically used in access networks, wile routers are typically used in the network core.

[term]:route/path: the sequence of communication links and packet switches traversed by a packet from the sending end system to the receiving end system

[term]: End system access the Internet through **Internet Service Providers (ISPs)**, ex: residential ISPs(local cable and telephone companies); corporate ISPs; university ISPs, and ISPs that provide WiFi access in airport, hotels, coffee shops, and other pbulic places. ISPs provide network access to end systems, also well as content providers    
Each ISP network, whether upper-tier or lower-tier, is managed
independently, runs the IP protocol (see below), and conforms to certain naming and address conventions. 

[Cool]: lower-iter ISPs are interconnected through national and international upper-tier ISPs such as Level 3 Communications, AT&T, Sprint, and NTT. An upper-tier ISP consists of high-speed routers interconnected with high-speed fiber-optic links.

[term]Protocol: control the sending and receiving of information within the Internet. **Transmission Control Protocol (TCP)** and **Internet Protocol(IP)** are two of the most important protocols in the Internet. 

[term]Internet Protocol: specifies the format of the packets that are sent and received among routers and end systems

[term]**Internet standards** are developed by the Internet Engineering Task Force (IETF). The IETF standards documents are called **requests for comments (RFCs)**


