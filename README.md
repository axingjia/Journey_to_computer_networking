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

### Nut and Bolt Description

[term]Host/End system: devices that connect to the network, because they host(that is, run)  application programs such as a Web browser program, a Web server program, an e-mail client program, or an e-mail server program. 
  
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

[term]**Internet standards** are developed by the Internet Engineering Task Force (IETF). The IETF standards documents are called **requests for comments (RFCs)** RFC define protocols such as TCP, IP, HTTP, SMTP. There are currently more than 6,000 RFC.

### Service Description
A different angle: an infrastructure that provides services to applications

[term]distributed application: application that involve multiple end systems that exchange data with each other. ex: Web surfing, social networks, instant messaging, Voiceover-IP (VoIP), video streaming, distributed games, peer-to-peer (P2P) file sharing, television over the Internet, remote login

[term]End systems attached to the Internet provide an **Application Programming Interface (API)** that specifies how a program running on one end system asks the Internet infrastructure to deliver data to a specific destination program running on another end system.

[term]Protocol: A protocol defines the format and the order of messages exchanged between two or more communicating entities, as well as the actions taken on the transmission and/or receipt of a message or other event.

[cool] Mastering the field of computer networking is equivalent to understanding the what, why, and how of networking protocols.

[Wild thought]Create a internet end system. Hint: IOT

[now you know]hosts are sometimes further divided into two categoires: clients and servers. Informally, clients tend to be desktop and mobile PCs, smartphones, and so on, whereas servers tend to be more powerful machines that store and distribute Web pages, stream video, relay e-mail, and so on. Nowadays, most of the servers from which we receive search results, e-mail, Web pages, and videos reside in large data centers. For example, Google has 30–50 data centers, with many having more than one hundred
thousand servers

### Access Network

Today, the two most prevalent types of broadband residential access are **digital subscriber line (DSL)** and cable. The old way namely.     
When the downstream and upstream rates are different, the access is said to be asymmetric

[Cool] fiber to the home (FTTH): As the name suggests, the FTTH concept is simple—provide an optical fiber path from the CO directly to the home. 

read to page 17




