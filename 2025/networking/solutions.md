# Week-1: Networking Challenge Solutions
 ## Task-1: Understanding OSI & TCP/IP Models
 
### What is OSI Model? - Layers of OSI Model

The OSI (Open Systems Interconnection) Model is a set of rules that explains how different computer systems communicate over a network.The OSI Model consists of 7 layers and each layer has specific functions and responsibilities.This layered approach makes it easier for different devices and technologies to work together.

### 1. Physical Layer (Layer 1) – Bit Transmission

It is responsible for the actual physical connection between the devices.The physical layer contains information in the form of bits,it transmits individual bits from one node to the next.When receiving data, this layer will get the signal received and convert it into 0s and 1s and send them to the Data Link layer, which will put the frame back together.Common physical layer devices are Hub, Repeater, Modem, and Cables.

- Real world use case: Plugging an Ethernet cable / using Wi-Fi
- Protocols/standards: Ethernet (IEEE 802.3), Wi-Fi (IEEE 802.11), Bluetooth

### 2. Data Link Layer (Layer 2) – Local Network Communication

Data Link Layer transfers data between devices on the same network using MAC addresses.The main function of this layer is to make sure data transfer is error-free from one node to another, over the physical layer.
When a packet arrives in a network, it is the responsibility of the DLL to transmit it to the Host using its MAC address.

- Real world use case: Your laptop finds the MAC address of the router using ARP
- Protocols: Ethernet, ARP, VLAN (802.1Q), STP

### 3. Network Layer (Layer 3) - Packet Routing

The Network Layer works for the transmission of data from one host to the other located in different networks. It also takes care of packet routing i.e. selection of the shortest path to transmit the packet, from the number of routes available.
The sender and receiver's IP address are placed in the header by the network layer. Segment in the Network layer is referred to as Packet.
Network layer is implemented by networking devices such as routers and switches.

- #### Real-world usecase: Sending data from your laptop to a server in another country
- #### Protocols: IP (IPv4 / IPv6),ICMP,Routing protocols (OSPF, BGP)

### 4. Transport Layer (Layer 4) - End-to-end Delivery

This layer Ensures end-to-end communication and manages ports.The data in the transport layer is referred to as Segments. It is responsible for the end-to-end delivery of the complete message.The Transport Layer provides services to the application layer and takes services from the network layer

- At the sender's side, the transport layer receives the formatted data from the upper layers, performs Segmentation, and also implements Flow and error control to ensure proper data transmission.
- At the Receiver’s side, Transport Layer reads the port number from its header and forwards the Data which it has received to the respective application. It also performs sequencing and reassembling of the segmented data.

#### Real-world example:
- Website loads reliably using TCP
- Video streaming or DNS queries using UDP

#### Protocols: TCP,UDP

### 5. Session Layer (Layer 5) - Session management

It is responsible for the establishment of connections, management of connections, terminations of sessions between two devices. It also provides authentication and security.

#### Real-world example:
- Maintaining an SSH session while executing multiple commands
- Re-establishing session after brief network drop

#### Protocols: NetBIOS, PPTP

### 6. Presentation Layer (Layer 6) - Format & Encryption

The Presentation Layer is also called the Translation layer. The data from the application layer is extracted here and manipulated as per the required format to transmit over the network.JPEG, MPEG, GIF, are standards or formats used for encoding data, which is part of the presentation layer’s role.

#### Real-world example:
- HTTPS encrypts data using TLS
- Browser decodes JSON response from backend

#### Protocols: TLS (Transport layer security) / SSL (Secure Sockets Layer)

### 7. Application Layer (Layer 7) - User Services

At the very top of the OSI Reference Model stack of layers, we find the Application Layer which is implemented by the network applications. These applications produce the data to be transferred over the network.

#### Real-world example:
- Opening a website (HTTP/HTTPS)
- Sending email (SMTP)
- Logging into server (SSH) 

#### Protocols: HTTP/HTTPS, FTP/SFTP, SMTP,DNS,SSH 

## TCP/IP Model

The TCP/IP model is a practical, layered framework defining how data is organized and transmitted across the internet, combining functions into four (or five) layers: Application, Transport, Internet (Network), and Network Access (Link/Physical), providing end-to-end communication by handling packetization, addressing, routing, and reliable delivery, making it the backbone of modern networking.

### Layers of OSI Model (4-Layer)

1. Application Layer: Where user applications interact; handles protocols like HTTP, DNS, FTP.
2. Transport Layer: Ensures reliable data transfer; uses TCP (guaranteed delivery) or UDP (faster, less reliable).
3. Internet Layer: Manages addressing (IP) and routing of data packets across networks.
4. Network Access Layer (Link/Host-to-Network): Deals with physical transmission over hardware (Ethernet, Wi-Fi).

### Key Functions & How It Works

- Packetization: Data is broken into packets at the Application layer.
- Addressing & Routing: The IP protocol assigns addresses and guides packets across networks.
- Reliable Delivery: TCP segments data, manages flow, and reassembles it at the destination.
- Physical Transmission: The lowest layers handle the actual hardware connection.

## Task-2: Explaining the importance of Ports & protocols and their relevance in Devops Workflow

Ports and protocols are fundamental networking concepts that play a critical role in the DevOps workflow by enabling connectivity, managing security, and facilitating seamless communication between the various tools, services, and environments involved in modern software development and deployment.

### Relevance of Ports & Protocols in DevOps

Ports are essential for distinguishing between different services running on the same host, allowing a single machine to host multiple applications simultaneously.while Protocols define the rules of communication, ensuring that data is exchanged correctly and securely between different systems.
- Service Accessibility: Services require dedicated ports to be accessible. Common examples in DevOps include:
  - Port 80/443 (HTTP/HTTPS): Used by web servers (like Nginx or Apache) to serve web applications to end-users.
  - Port 22 (SSH): Critical for secure remote access to servers and containers, enabling automation and management tasks in CI/CD pipelines.
  - Specific Application Ports: Databases (e.g., PostgreSQL on 5432, MySQL on 3306), monitoring tools (e.g., Prometheus), and container orchestration systems (e.g., Kubernetes API server) all rely on specific ports to function and communicate.

- Containerization & Orchestration: In environments like Docker and Kubernetes, port mapping is essential. The host machine's ports are mapped to internal container ports, allowing external traffic to reach the services running inside containers. This configuration is often automated in pipeline scripts and configuration files.
- Load Balancing & Routing: Load balancers use port numbers to distribute incoming network traffic across multiple instances of a service, ensuring high availability and efficient resource utilization, which is a core tenet of DevOps practices.

## Task-3: step-by-step guide on how to create and configure Security Groups(AWS)

### Step 1: Log in to AWS Console

1. Go to AWS Management Console

2. Navigate to EC2 → Security Groups

### Step 2: Create a New Security Group

Click Create security group

Enter:
  - Security group name: web-sg
  - Description: Allow HTTP/HTTPS & SSH
  - VPC: Select your VPC

Note: SG's are VPC-specific

### Step 3: Configure Inbound Rules
Inbound rules control incoming traffic.

| Type  | Protocol | Port | Source    | Purpose             |
| ----- | -------- | ---- | --------- | ------------------- |
| SSH   | TCP      | 22   | My IP     | Secure admin access |
| HTTP  | TCP      | 80   | 0.0.0.0/0 | Public web access   |
| HTTPS | TCP      | 443  | 0.0.0.0/0 | Secure web access   |

Best Practice:
 - Never open SSH (22) to 0.0.0.0/0
 - Use My IP / Bastion Host

### Step 4: Configure Outbound Rules
Outbound rules control traffic leaving the instance.

- Default is often "Allow All".
- Edit to restrict (deny all, then add specific allow rules).

Click Create security group,now security group is created.

### Step 4: Apply

Associate the created security group with your EC2 instance(s).

## Task-4: Explaining the purpose and usage of Essential Networking commands



| **Command** | **Purpose** | **Usage Example** | **Notes / Tips** |
|-------------|-------------|-------------------|------------------|
| `ping` | Test connectivity to a host | `ping google.com` | Useful for checking if a server is reachable; can be blocked by firewalls. |
| `traceroute` / `tracert` | Show path packets take to destination | `traceroute google.com` | Linux uses `traceroute`, Windows uses `tracert`. Helps identify routing issues. |
| `curl` | Transfer data from/to a server | `curl -I https://example.com` | Great for testing APIs, HTTP headers, and endpoints. |
| `wget` | Download files from web | `wget https://example.com/file.zip` | Often used in automation scripts to fetch packages. |
| `netstat` | Display network connections, routing tables, and ports | `netstat -tulnp` | Deprecated in some systems; use `ss` instead. |
| `ss` | Socket statistics, modern replacement for `netstat` | `ss -tuln` | Faster and more detailed than `netstat`. |
| `nslookup` | Query DNS records | `nslookup example.com` | Simple DNS lookup tool; replaced by `dig` in many Linux distros. |
| `dig` | Detailed DNS queries | `dig example.com ANY` | Preferred for DNS troubleshooting; shows TTL, record types. |
| `telnet` | Test connectivity to specific port | `telnet example.com 80` | Deprecated due to lack of encryption; use `nc` instead. |
| `nc` (netcat) | Debug and test network connections | `nc -zv example.com 22` | Powerful tool for port scanning and debugging. |
| `ifconfig` | Show or configure network interfaces | `ifconfig eth0` | Deprecated; use `ip addr` in modern Linux. |
| `ip` | Manage IP addresses, routes, and interfaces | `ip addr show` | Versatile replacement for `ifconfig` and `route`. |
| `route` | Show or manipulate routing table | `route -n` | Deprecated; use `ip route` instead. |
| `ip route` | Display/manage routing table | `ip route show` | Essential for debugging routing issues. |
| `scp` | Securely copy files between hosts | `scp file.txt user@host:/path/` | Uses SSH for secure transfer; good for automation. |
| `rsync` | Sync files/directories across systems | `rsync -avz /local user@host:/remote` | More efficient than `scp` for large or repeated transfers. |
| `tcpdump` | Capture and analyze network packets | `tcpdump -i eth0 port 80` | Requires root; useful for deep packet inspection. |
| `nmap` | Network exploration and security auditing | `nmap -p 1-65535 example.com` | Powerful for port scanning and service detection. |







  
  



