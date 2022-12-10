# eJPT-notes
## 1.Introduction
## 2.Networking
* The goal of networking is to transefer **Packets**
* **Packets - Datagrames ** are stream of bits works as electric signals in physical medium ,this medium may be wire in case of LAN or the air in case of WiFi,carrieng the information to be transefered.
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
* **Routers** are devices connected to different networks and used to transefer datagrams between two different networks.
* to find the best path the router look to the routing table which contain the interface and ip.
* the router send the packet to the default address(0.0.0.0) if it doesn't know the host.
* if there are two paths to the same host , the path with lowest metric is selected.
* to see your routing table enter `route print` in cmd.
### Link Layer devices and protocols
* Packet forwarding happens in the lowest layer (Link Layer) with TCP or UDP.
* **Hubs and Switches** are devices forward the packets into a local network and they works with MAC(6 bytes).
* IP is used to identify the host in the network layer but MAC is used to identify the network card in physical layer.
* to discover MAC use `ipconfig /all`.
* if a device A wants to communicate with device B in another network , A will make a packet with header contain
  * IP address of B
  * MAC of the router
  * source IP of A
  * source MAC of A
