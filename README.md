# eJPT-notes
## 1. Introduction
## 2. Networking
* The goal of networking is to transefer **Packets**
* **Packets - Datagrames** are stream of bits works as electric signals in physical medium ,this medium may be wire in case of LAN or the air in case of WiFi,carrieng the information to be transefered.
* every packet are devided into **Header and Payload**
* **Header** ensures that the reciver will recive and deal with the data correctly.
* **Payload** is the actual data to be transefered.
### Example - IP protocol header
![IP protocol header](https://upload.wikimedia.org/wikipedia/commons/thumb/6/60/IPv4_Packet-en.svg/1200px-IPv4_Packet-en.svg.png)
* The first 4 bits identify the IP version. 
* The 32 bits From 96 represent the source address
* The following Four bits represent the Destination address
### Protocol Layers
1. Application Layer.
2. Transport Layer.
3. Network Layer.
4. Data Link Layer.<br>
**these layers work on top of each other and each layer has its own protocol.**
### ISO/OSI 
* it's a theoretical model for network communication consist of 7 layers published by ISO in 1984, it was never implemented but used as reference of actual protos.<br>
* **Encapsulation** it's meaning that the entire upper protocol packet is the payload of the lower one.<br>
* The receiver do the **reverse of the encapsulation**
* **the actual model is called TCP/IP and has 4 layers (Application,Transport,Network and DataLink).**<br>
### IP
* **Internet Protocol** is the protocol used in network layer for identify the different devices.
* IP has two versions IPv4 (Consist of four bytes) and IPv6(Consist of 6 bytes)
#### Reserved IP
* 0.0.0.0 - 0.255.255.255 (representing 'this' network)
* 127.0.0.0 - 127.255.255.255 (representing local host e.g.,ur computer)
* 192.168.0.0 - 192.168.255.255 (reserved for private network)
#### IP/Mask
* **used to fully identify the host** 
* to get the network part from the ip and the mask perform bitwise and between the ip and the mask or use the [subnet calculator](https://www.ipaddressguide.com/cidr).
### Routing
* is finding the best path to reach the host.
* **Routers** are devices connected to different networks and used to transefer datagrams between different networks.
* to find the best path the router look to the routing table which contain the interface and ip.
* the router send the packet to the default address(0.0.0.0) if it doesn't know the host.
* if there are two paths to the same host , the path with lowest metric is selected.
* to see your routing table enter `route print` in cmd.
### Link Layer devices and protocols
* Packet forwarding happens in the lowest layer (Link Layer) with TCP or UDP.
* **Hubs and Switches** are devices forward the packets into a local network and they works with MAC(6 bytes).
* IP is used to identify the host in the network layer but MAC is used to identify the network card in physical layer.
* to discover MAC use `ipconfig /all`.
* if a device A wants to communicate with device B in another network , A will send a packet to the router with header contain
  * destination IP address of B
  * destination MAC of the router
  * source IP of A
  * source MAC of A
<br>**then the router will rewrite the header with**
  * destination Mac address B.
  * source MAC will be the router.
* Switches also have forwarding table
* to segment the network with switch use VLANs
* switch store the table which contains interface,MAC and TTL in RAM. 
* Time To Live (TTL) determines how long an entry stay in the table.
* switches learn new MACs dynamicly while routers use complex protocols to do that.
### Address Resolution Protocol
* when a device A want to send packet to another device B and he know only his IP:
1. A make ARP request containing the IP address of b and FF:FF:FF:FF:FF:FF as destination MAC address 
2. every host in the network receive the request
3. B replies with ARP reply , telling A its MAC address.
4. A will save B MAC in the ARP cache.
* To see ur ARP cache use `arp -a`
<br>**Hubs** is devices used in send packet to all hosts in the network and don't have forwarding table or cache, so it's rarely use.
### TCP - UDP
* **T**ransimission **C**ontrol **P**rotocol and **U**ser **D**atagram **P**rotocol are the most common transefer protocols in internet.
* the computer network is **unreliable** which means that some packet can be lost.
* to establish connection using TCP three steps happend : Three-way handshake (SYN,SYN+ACK,ACK)
#### TCP advantages
1. Connection Oriented , which means it establishes connection before packet transefer.
2. Guarntees packet delivery
#### UDP advantages
1. Higher Throughout (Packets sent per second)
### Ports
* if u want to identify a proccess on a network you must know IP:Port pair.
* Different proccesses of the same app use different ports.
* **daemon** is a program runs a service on someport.
* system admin may change the dafault ports in order to make it hard for the hackers
* to check ur daemons use `netstat -ano` or use TCPView

#### Reserved Ports
* 0 - 1023 for the most common proccess
### Firewalls and Network Defense
* There are many devices to protect network , these devices use **different techniques** and work on **different layers** to perform **access control** and **attack detection and prevention**
* **Firewalls** are specialized software modules running on a computer or network device, they filter coming in and out packets.
* Firewalls can work on different layers , thus providing different features and protections.
* firewall take the dicision to filter the packet dependent on:
  * Source IP 
  * Destination IP
  * Protocol
  * Source Port
  * Destination Port
* You can run packet filter on home DSL routers.
* Packet filter inspect the head of each packet to choose how to treat it, the most common actions:
  1. **Allow**: allow the packet to pass.
  2. **Drop**: drops the packet without notify the source.
  3. **Deny**: drops the packet but notify the source.
* packet filtering just inspect the **header** not the payload.
* application layer exploit can be XSS,Buffer overflow,SQL injection and more.
#### Application Level Firewall
* check the actual content for example:
  1. Drop peer-to-peer application packet
  2. Prevent users from visiting a site.
* installed on seperated hardware
#### IDS
* stands for **I**nstrusions **d**etecting **S**ystems
* detect intrusion not traffic.
* checks for attack vectors like SQL Injection , buffer overflow , port scans and ping sweeps.
* also can identify the traffic generated by a virus or wor by the mean of signatures.
* **signatures** are list of discovered viruses , which meant that the IDS can detect unknown viruses.
* there are false positives. it happened when legit traffic is flagged as millicious.
* IDS is devided into:
  1. **N**etwork **I**nstrusion **D**etection **S**ystems (NIDS)
      * sensors are placed on router or on high instrusion risk like DMZ(Servers Zone).
  2. **H**ost **I**nstrusion **D**etection **S**ystems (HIDS)
      * monitor application logs,file system changes and OS changes by sensors.
#### IPS
* **I**ntrusion **P**revention **S**ystems ddetect and drop millicious requests when detected.
#### Spot on Obstacle
* To know if the company has a firewall-like mechanism:
  * if the firewall is in place , when u sent TCP SYN the reply will be TCP RST/ACK instead of TCP SYN/ACK or there is no reply.
#### NAT and Masquerading
* **N**etwork **A**dress **T**ranslation can be detected by firewalls.

## 9. Information Gathering
1. by using **LinkedIn** you can get inforamtion like phone numbers , real names, email addresses and maybe integrated accounts.
2. **CrunchBase** is an IT startup database where you can find detailed information about founders, investors, employees, buyouts, and acquisitions.
3. You can use **whois** database to find information like (owner name, street address, email address and technical contacts. use it on linux by `whois` cmd.
4. don't forget to navigate the website of the target.
5. if it doesn''t exist try to guess the the email pattern:
   1. name.surname@company.com
   2. surname.name@company.com
   3. [first letter of the name]surname@company.com
   You can try to first:
     • Collect a reasonable number of employee data (name/surname)
     • Try to construct a few possible email formats and apply them to each name/surname pair
     • Try to send an email that does not alert potential victims (e.g., do not put a „phishing test” in subject, but choose something tricky like try to pretend it is just an advertisement)
