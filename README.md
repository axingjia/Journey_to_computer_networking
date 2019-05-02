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
The network that physically connects an end system to the first router on a path from the end system to any other distant end system.

Today, the two most prevalent types of broadband residential access are **digital subscriber line (DSL)** and cable. The old way namely.     
When the downstream and upstream rates are different, the access is said to be asymmetric

[Cool] fiber to the home (FTTH): As the name suggests, the FTTH concept is simple—provide an optical fiber path from the CO directly to the home. 

[cool]Speed:    
Ethernet: 100Mbps access to the Ethernet switch    
FTTH downstream: 20Mbps   
cable: 13Mbps    
DSL: 5Mbps    
Satelite: 1Mbps    
dial-up access: 56kbps   
Wireless LAN access based on IEEE 802.11 technology: 56 Mbps   

3G: provide packet switched wide-area wireless Internet access at speeds in excess of 1 Mbps.    
LTE: long term evolution: in excess of 10Mbps, downstream of many tens of Mbps

### Physical Media
HFC uses a conbination of fiber cable and coaxial cable     
DSL and Ethernet use copper wire    
mobile access networks use the radio spectrum

[term]physical medium: can takes many shapes and ofrms and doesn't have to be of the same type for each transmitter-receiver pair along the path. Ex: twisted-pair copper wire, coaxial cable, multimode fiber-optic cable, terrestrial radio spectrum, and satellite radio spectrum.    
Physical media fall into two categories: guided media and unguided media.   
With guided media, the waves are guided along a solid medium, such as cable and wire; with unguided media, the waves propagate in the atmosphere and in outer space, such as a wireless LAN or a digital satellite channel.    
phyiscal link is often cheaper than other networking cost. It's the labor cost that is high.

### Twisted-Pair Copper Wire 
used by telephone network    
speed for LANs: 10 Mbps to 10 Gbps, depend on the thickness of the wire and the distance transmitter and receiver    
twisted pair has emerged as the dominant solution for high-speed LAN networking.

### Coaxial Cable
quite common in cable television systems 

### Fiber Optics 
Fiber optics are often used as the preferred long-haul guided transmission media, particularly for overseas links.    
Prevalent in the backbone of the Internet

### Terrestrial Radio Channels
[cool]personal device such as wireless headsets, keyboards, and medical device operate over short distances(one or two meters); the wireless LAN technologies use local-area radio channels (a few hundred meters); the cellular access technologies use wide-area radio channel(tens of kilometers)

### Satellite Radio Channel 
a substrantial signal propagation delay of 280 millisecond    
operate at speeds of hundreds of Mbps    
often used in areas without access to DSL or cable-based Internet access

## The Network Core 
The mesh of packet switches and links that interconnects the Internet's end systems

[term]store-and-forward transmission: means the packet switch must receive the entire packet before it can begin to transmit the first bit of the packet onto the outbound link.

let's calculate how long it takes to transmit using store-and-forward transmission. The source begins to transmit at time 0; at time L/R seconds,  the source has transmitted the entire packet, and
the entire packet has been received and stored at the router (since there is no propagation delay). At time L/R seconds, since the router has just received the entire packet, it can begin to transmit the packet onto the outbound link towards the destination; at time 2L/R, the router has transmitted the entire packet, and the entire packet has been received by the destination. Thus, the total delay is 2L/R. If the switch instead forwarded bits as soon as they arrive (without first receiving the entire packet), then the total delay would be L/R since bits are not held up at the router 

### Queuing delay
If an arriving packet needs to be transmitted onto a link but finds the link busy with the transmission of another packet, the arriving packet must wait in the output buffer. Thus, in addition to the store-and-forward delays, packets suffer output buffer **queuing delays**. 

These delays are variable and depend on the level of congestion in the network. Since the amount of buffer space is finite, an arriving packet may find that the buffer is completely full with other packets waiting for transmission. In this case, **packet loss** will occur—either the arriving packet or one of the already-queued packets will be dropped

### Forwarding Tables and Routing Protocols 
Question: how does the router determine which link it should forward the packet onto?    
Explanation: Packet forwarding is actually done in different ways in different types of computer networks. Here, we briefly describe how it is done in the Internet.

1. When a source end system wants to send a packet to a destination end system, the source includes the destination's IP addressin the packet's header.
2. When a packet arrives at a router in the network, the router examines a portion of the packet's destination address and forward the packet to an adjacent router. 
3. More specifically, each router has a forwarding table that maps destination address(or portions of the destination addresses) to that router's outbound links 
4. When a packet arrives at a router, the router examines the address and searches its forwarding table, using this destination address, to find the appropriate outbound link.
5. The router then directs the packet to this outbound link

[term]routing protocol: determine the shortest path from each router to each destination and use the shortest path results to configure the forwarding tables in the routers.

### Circuit Switching
There are two fundamental approaches to move data through a network of links and switches: **circuit switching** and **packet switching**

[term]In circuit-switched networks, the resources needed along a path(buffers, link transmission rate) to provide for communication between the end systems are reserved for the duration of the communication session between the end systems. In packet-switched networks, these resources are not reserved. As an analogy, think of a restaurant that needs reservation.

Traditional telephone networks are examples of circuit-switched networks.

[term]A connection for which the switches on the path between the sender and receiver maintain connection state for that connection. In the jargon of telephony, this connection is called a circuit. 

For example, if each link has four circuits, for each each link used by the end-to-end connection, the connection get one fourth of the link's total transmission capacity for the duration of the connection.

### Multiplexing in Circuit-Switched network 
skim

### Package Switch Versus Circuit Switching
Packet switching is not suitable for real-time services(telephone call and video conference calls)    
Although packet switching and circuit switching are both prevalent in today’s telecommunication networks, the trend has certainly been in the direction of packet switching. Even many of today’s circuit-switched telephone networks are slowly migrating toward packet switching. In particular, telephone networks often use packet switching for the expensive overseas portion of a telephone call.

### A Network of Networks
The access ISPs themselves must be interconnected.

Network Structure 1: Interconnects all the access ISPs with a single global transit ISP.    
Since the access ISP pays the global transit ISP, the access ISP is said to be a customer and the global transit ISP is said to be a provider.

Network Structure 2: 
* Now if some company builds and operates a global transit ISP that is profitable, then it is natural for other companies to build their own global transit ISPs and compete with the original global transit ISP.    
* It is a two-tier hierarchy with global transmit providers residing at the top tier and access ISPs at the bottom tier.     
* In reality, although some ISPs do have impressive global coverage and do directly connect with many access ISPs, no ISP has presence in each and every city in the world. Instead, in any given region, there may be a regional ISP to which the access ISPs in the region connect. Each regional ISP then connects to tier-1 ISPs. Tier-1 ISPs are similar to our (imaginary) global transit ISP; but tier-1 ISPs, which actually do exist, do not have a presence in every city in the world. 
* Returning to this network of networks, not only are there multiple competing tier1 ISPs, there may be multiple competing regional ISPs in a region. In such a hierarchy, each access ISP pays the regional ISP to which it connects, and each regional ISP
pays the tier-1 ISP to which it connects. (An access ISP can also connect directly to a tier-1 ISP, in which case it pays the tier-1 ISP). Thus, there is customer-provider relationship at each level of the hierarchy. 
* Note that the tier-1 ISPs do not pay anyone as they are at the top of the hierarchy.
*  To further complicate matters, in some regions,
there may be a larger regional ISP (possibly spanning an entire country) to which the smaller regional ISPs in that region connect; the larger regional ISP then connects to a tier-1 ISP. For example, in China, there are access ISPs in each city, which connect to provincial ISPs, which in turn connect to national ISPs, which finally connect to tier-1 ISPs [Tian 2012]. We refer to this multi-tier hierarchy, which is still only a crude approximation of today’s Internet, as Network Structure 3.

Network Structure 4:
* To build a network that more closely resembles today’s Internet, we must add points of presence (PoPs), multi-homing, peering, and Internet exchange points (IXPs) to the hierarchical Network Structure 3. PoPs exist in all levels of the hierarchy, except for the bottom (access ISP) level. A PoP is simply a group of one or more routers (at the same location) in the provider’s network where customer ISPs can connect into the provider ISP. For a customer network to connect to a provider’s PoP, it can lease a high-speed link from a third-party telecommunications provider to directly connect one of its routers to a router at the PoP. 
* [term] Any ISP (except for tier-1 ISPs) may choose to **multi-home**, that is, to connect to two or more provider ISPs. So, for example, an access ISP may multi-home with two regional ISPs, or it may multi-home with two regional ISPs and also with a tier-1 ISP. Similarly, a regional ISP may multi-home with multiple tier-1 ISPs. When an ISP multi-homes, it can continue to send and receive packets into the Internet even if one of its providers has a failure.
*[term]As we just learned, customer ISPs pay their provider ISPs to obtain global Internet interconnectivity. The amount that a customer ISP pays a provider ISP reflects the amount of traffic it exchanges with the provider. To reduce these costs, a pair of nearby ISPs at the same level of the hierarchy can **peer**, that is, they can directly connect their networks together so that all the traffic between them passes over the direct connection rather than through upstream intermediaries. When two ISPs peer, it is typically settlement-free, that is, neither ISP pays the other. As noted earlier, tier-1 ISPs also peer with one another, settlement-free.
*[term]Along these same lines, a third-party company can create an Internet Exchange Point (IXP) (typically in a stand-alone building with its own switches), which is a meeting point where multiple ISPs can peer together. There are roughly 300 IXPs in the Internet today [Augustin 2009]. We refer to this ecosystem—consisting of access ISPs, regional ISPs, tier-1 ISPs, PoPs, multi-homing, peering, and IXPs—as Network Structure 4.

Network Structure 5:
* Network Structure 5, builds on top of Network Structure 4 by adding content provider networks. 
* ex: Google has 30 to 50 data centers distributed across North America, Europe, Asia, South America, and Australia.
*  By creating its own network, a content provider not only
reduces its payments to upper-tier ISPs, but also has greater control of how its services are ultimately delivered to end users.


### Delay, Loss and Throughput in Packet-Switched Networks
[term]throughput the amount of data per second that can be transferred    
[term]nodal processing delay:     
[term]queuing delay:    
[term]transmission delay    
[term]propagation delay
[term]total nodal delay:

SKIM 

### Protocol Layers and Their Service Models
Five-layer Internet Protocol stack:    
Application     
Transport    
Network    
Link    
Physical

Application: implemented in software in the end system;  
Transport: implemented in software in the end system;  
Network: The network layer is often a mixed implementation of hardware and software.     
Link: Because the physical layer and data link layers are responsible for handling communication over a specific link, they are typically implemented in a network interface card (for example, Ethernet or WiFi interface cards) associated with a given link.
Physical: Because the physical layer and data link layers are responsible for handling communication over a specific link, they are typically implemented in a network interface card (for example, Ethernet or WiFi interface cards) associated with a given link.

Application HTTP, SMTP, FTP    
Transport: TCP, UDP     
Network: IP, routing protocol   
Link: Ethernet, Wifi, cable access network's DOCSIS protocol     
Physical: twisted-pair copper wire, single-mode fiber optics

Application packet of information at this layer as a message    
Transport: packet of information as segment     
Network: packet as datagram    
Link: packet as frame    
Physical: bit

The OSI model    
SKIP

### Encapsulation
routers and link-layer switches are both packet switches    
link-layer switches implement layers 1 and 2 physical and link    
routers implement layers 1 through 3: physical, link, network    
We’ll see later that while link-layer switches do not recognize IP addresses, they are capable of recognizing layer 2 addresses, such as Ethernet addresses. 

SKIM explanation

### Networks Under attack 
malware    
DDos attack    
packet sniffer 
IP spoofing  /end-point masquerading    
man in the middle     
    
SKIM

### History of Network
development of packet switching:1961-1972    
proprietary network and internetworking： 1972-1980
A Proliferation of Networks: 1980-1990 
The Internet Explosion: 1990
The New Millennium

SKIM


## *Done Chapter 1!!! A pad on my back*
(One thing about studying comp sci, the review questions are tough..they are a mix of new concept, creativity, math, and understanding of the material. One good point of why studying it in a lecture would be torturing)

# Chapter 2: Application Layer

### Network Application Architectures
Two predominant application architectural paradigm: client-server architecture or the peer-to-peer architecture

Client-server architecture:    
client do not directly communicat with each other    
Example: google with its data center

P2P architecture
minimal(or no) reliance on dedicated server 
Many of today's most popular and traffic-intensive applications are based on P2P. Ex: BitTorrent(file sharing), Xunlei(peer-assisted download acceleration), Skype(Internet Telephony), Kankan and PPstream(IPTV)

some applications have hybrid architectures, combining both client-server and P2P elements. For example, for many instant messaging applications, servers are used to track the IP addresses of users, but user-to-user messages are sent directly between user hosts (without passing through intermediate servers).

One of the most compelling features of P2P architectures is their self-scalability. For example, in a P2P file-sharing application, although each peer generates workload by requesting files, each peer also adds service capacity to the system by distributing files to other peers. P2P architectures are also cost effective, since they normally don’t require significant server infrastructure and server bandwidth (in contrast with clients-server designs with datacenters). 

future P2P applications face three major challenges:    
ISP Friendly
Security   
Incentives