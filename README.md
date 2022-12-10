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
