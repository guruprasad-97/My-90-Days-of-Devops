# Week 1: Networking Challenge Solutions
 ## Task-1.Understanding  OSI & TCP/IP Models
 
### What is OSI Model? - Layers of OSI Model

The OSI (Open Systems Interconnection) Model is a set of rules that explains how different computer systems communicate over a network.The OSI Model consists of 7 layers and each layer has specific functions and responsibilities.This layered approach makes it easier for different devices and technologies to work together.

### Physical Layer (Layer 1) – Bit Transmission

It is responsible for the actual physical connection between the devices.The physical layer contains information in the form of bits,it transmits individual bits from one node to the next.When receiving data, this layer will get the signal received and convert it into 0s and 1s and send them to the Data Link layer, which will put the frame back together.Common physical layer devices are Hub, Repeater, Modem, and Cables.

- Real world use case: Plugging an Ethernet cable / using Wi-Fi
- Protocols/standards: Ethernet (IEEE 802.3), Wi-Fi (IEEE 802.11), Bluetooth

### Data Link Layer (Layer 2) – Local Network Communication

Data Link Layer transfers data between devices on the same network using MAC addresses.The main function of this layer is to make sure data transfer is error-free from one node to another, over the physical layer.
When a packet arrives in a network, it is the responsibility of the DLL to transmit it to the Host using its MAC address.

- Real world use case: Your laptop finds the MAC address of the router using ARP
- Role: Framing, MAC addressing, error detection
- Protocols: Ethernet, ARP, VLAN (802.1Q), STP

### Network Layer (Layer 3) - 
The Network Layer works for the transmission of data from one host to the other located in different networks. It also takes care of packet routing i.e. selection of the shortest path to transmit the packet, from the number of routes available.
The sender and receiver's IP address are placed in the header by the network layer. Segment in the Network layer is referred to as Packet.
Network layer is implemented by networking devices such as routers and switches.

- Real-world usecase: Sending data from your laptop to a server in another country
- Protocols: IP (IPv4 / IPv6),ICMP,Routing protocols (OSPF, BGP)

### Transport Layer (Layer 4)
This layer Ensures end-to-end communication and manages ports.The data in the transport layer is referred to as Segments. It is responsible for the end-to-end delivery of the complete message.The Transport Layer provides services to the application layer and takes services from the network layer
- At the sender's side, the transport layer receives the formatted data from the upper layers, performs Segmentation, and also implements Flow and error control to ensure proper data transmission.
- At the Receiver’s side, Transport Layer reads the port number from its header and forwards the Data which it has received to the respective application. It also performs sequencing and reassembling of the segmented data.

Real-world example:
- Website loads reliably using TCP
- Video streaming or DNS queries using UDP

Protocols: TCP,UDP

### Session Layer (Layer 5)
It is responsible for the establishment of connections, management of connections, terminations of sessions between two devices. It also provides authentication and security.

Real-world example:
- Maintaining an SSH session while executing multiple commands
- Re-establishing session after brief network drop

Protocols: NetBIOS, PPTP

### Presentation Layer (Layer 6)
The Presentation Layer is also called the Translation layer. The data from the application layer is extracted here and manipulated as per the required format to transmit over the network.JPEG, MPEG, GIF, are standards or formats used for encoding data, which is part of the presentation layer’s role.

Real-world example:
- HTTPS encrypts data using TLS
- Browser decodes JSON response from backend

Protocols: TLS (Transport layer security) / SSL (Secure Sockets Layer)

### Application Layer (Layer 7)
At the very top of the OSI Reference Model stack of layers, we find the Application Layer which is implemented by the network applications. These applications produce the data to be transferred over the network.

Real-world example:
- Opening a website (HTTP/HTTPS)
- Sending email (SMTP)
- Logging into server (SSH) 

Protocols: HTTP/HTTPS, FTP/SFTP, SMTP,DNS,SSH 



  
  



