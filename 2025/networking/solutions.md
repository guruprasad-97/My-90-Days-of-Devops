# Week 1: Networking Challenge Solutions

Tasks 

## 1. Understanding  OSI & TCP/IP Models
 
### What is OSI Model? - Layers of OSI Model

The OSI (Open Systems Interconnection) Model is a set of rules that explains how different computer systems communicate over a network.The OSI Model consists of 7 layers and each layer has specific functions and responsibilities.This layered approach makes it easier for different devices and technologies to work together.

### Physical Layer (Layer 1) – Bit Transmission

It is responsible for the actual physical connection between the devices.The physical layer contains information in the form of bits,it transmits individual bits from one node to the next.When receiving data, this layer will get the signal received and convert it into 0s and 1s and send them to the Data Link layer, which will put the frame back together.Common physical layer devices are Hub, Repeater, Modem, and Cables.
- Real world use case: Plugging an Ethernet cable / using Wi-Fi
- Role: Transmits raw bits (0s & 1s) as electrical/optical/radio signals
- Protocols/standards: Ethernet (IEEE 802.3), Wi-Fi (IEEE 802.11), Bluetooth

### Data Link Layer (Layer 2) – Local Network Communication

The data link layer is responsible for the node-to-node delivery of the message. The main function of this layer is to make sure data transfer is error-free from one node to another, over the physical layer.
When a packet arrives in a network, it is the responsibility of the DLL to transmit it to the Host using its MAC address.
- Real world use case: Switch sending data to the correct device in a LAN
- Role: Framing, MAC addressing, error detection
- Protocols: Ethernet, ARP, VLAN (802.1Q), STP
  
  
  



