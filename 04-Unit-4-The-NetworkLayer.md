# Network Layer Overview

The **network layer** is responsible for moving data packets from the source to the destination across multiple networks. Its key responsibilities include addressing, routing, and packet forwarding.

## 4.1 Data Plane

The **data plane** focuses on the actual transfer of packets through the router. This is where the router processes incoming packets and forwards them toward their destination.

### 4.1.1 Inside the Router

A router consists of several components that work together to process and forward packets.

#### 4.1.1.1 Input Port Processing and Destination-Based Forwarding

- **Input Port**: Where packets arrive at the router.
- **Processing**:
  - Extracts the packet header to determine the destination address.
  - Consults the forwarding table to decide the next hop.
- **Real-Life Example**: Think of a postal sorting center where a worker reads the address on a letter and decides which conveyor belt (next hop) it should go on.

#### 4.1.1.2 Switching

- **Switching**: The process of moving a packet from an input port to the appropriate output port within the router.
- **Techniques**:
  - **Memory-Based Switching**: Uses the router’s CPU to move packets (slow, used in older routers).
  - **Bus-Based Switching**: All ports share a single communication pathway.
  - **Crossbar Switching**: Allows multiple connections simultaneously.
- **Real-Life Example**: Imagine switching train tracks to direct trains toward their destination.

#### 4.1.1.3 Output Port Processing

- **Output Port**: Prepares packets for transmission to the next network.
- **Tasks**:
  - Adds outgoing link information.
  - Applies QoS (Quality of Service) rules.
- **Real-Life Example**: At an airport gate, passengers (packets) board the plane (next hop) based on their boarding pass information.

#### 4.1.1.4 Queuing

- **Queuing**: Storing packets temporarily if the outgoing link is busy.
- **Types**:
  - **Input Queuing**: Queues packets before they enter the router.
  - **Output Queuing**: Queues packets waiting for transmission.
- **Real-Life Example**: A toll booth with a queue of cars waiting to pass.

#### 4.1.1.5 Packet Scheduling

- **Scheduling**: Determines the order in which packets are transmitted from the queue.
- **Methods**:
  - **FIFO (First In, First Out)**: Packets are sent in the order they arrive.
  - **Priority Scheduling**: High-priority packets are sent first.
  - **Round-Robin Scheduling**: Each flow gets a turn.
- **Real-Life Example**: Emergency vehicles (high-priority packets) are allowed to bypass regular traffic queues.

### 4.1.2 The Internet Protocol (IP)

The **Internet Protocol (IP)** is the foundation of the network layer, handling addressing and packet forwarding.

#### 4.1.2.1 IPv4 Datagram Format

- **IPv4 Datagram Structure**:
  - **Header**: Contains source/destination addresses, TTL (Time to Live), checksum, and more.
  - **Payload**: The actual data.
- **Real-Life Example**: A postal package with a label (header) specifying the sender, receiver, and handling instructions.

#### 4.1.2.2 IPv4 Addressing

- **IPv4 Address**: A 32-bit number divided into four octets (e.g., `192.168.0.1`).
- **Divided Into**:
  - **Network Part**: Identifies the network.
  - **Host Part**: Identifies the device within the network.
- **Real-Life Example**: A home address where the street name is the network part and the house number is the host part.

#### 4.1.2.3 Subnetting

- **Subnetting**: Dividing a large network into smaller, manageable sub-networks.
- **Benefits**:
  - Improved performance.
  - Enhanced security.
- **Real-Life Example**: A company separates its office network into different subnets for departments like HR, IT, and Finance.

#### 4.1.2.4 Network Address Translation (NAT)

- **NAT**: Maps private IP addresses within a local network to a single public IP for communication over the Internet.
- **Benefits**:
  - Conserves public IP addresses.
  - Adds a layer of security.
- **Real-Life Example**: A family shares a single phone number (public IP) but has individual extensions (private IPs) for each member.

#### 4.1.2.5 IPv6

- **IPv6**: A newer protocol with 128-bit addresses to overcome IPv4 address exhaustion.
- **Features**:
  - Simplified headers.
  - Built-in security.
  - Better support for mobile devices.
- **Real-Life Example**: Imagine upgrading a small parking lot (IPv4) to a vast multi-story garage (IPv6) to accommodate more cars (devices).

## 4.2 Control Plane

The **control plane** manages routing decisions and updates the forwarding tables in routers.

### 4.2.1 Routing Algorithms

- **Routing algorithms** determine the best path for a packet to reach its destination.
- **Types**:
  1. **Static Routing**: Pre-configured routes.
     - **Real-Life Example**: A fixed train schedule with pre-planned stops.
  2. **Dynamic Routing**: Adjusts routes based on current network conditions.
     - **Real-Life Example**: GPS navigation that recalculates based on traffic.
- **Common Algorithms**:
  - **Link-State Routing**:
    - Routers share complete network topology information.
    - **Example**: Open Shortest Path First (OSPF).
    - **Real-Life Example**: A detailed city map used to find the shortest route.
  - **Distance-Vector Routing**:
    - Routers share distance to destinations with neighbors.
    - **Example**: Routing Information Protocol (RIP).
    - **Real-Life Example**: A travel agency shares the distances to nearby cities.

# Network Layer: Routing and Control Protocols

This section covers various routing algorithms and control protocols that enable data to travel efficiently across networks.

## 4.2.1 Routing Algorithms

Routing algorithms determine the best path for data packets to travel from the source to the destination.

### 4.2.1.1 The Link-State (LS) Routing Algorithm

- **Overview**: Each router has a complete view of the network topology.
- **How It Works**:
  - Routers share information about their directly connected neighbors.
  - Each router independently calculates the shortest path to all destinations using Dijkstra’s algorithm.
- **Advantages**:
  - Highly accurate routing information.
  - Quick convergence in case of network changes.
- **Real-Life Example**: A GPS system with a detailed map calculates the best route to a destination.

---

### 4.2.1.2 The Distance-Vector (DV) Routing Algorithm

- **Overview**: Routers exchange information with their immediate neighbors.
- **How It Works**:
  - Each router maintains a table of the best-known distances to destinations.
  - Updates are shared periodically to ensure all routers have the latest paths.
- **Advantages**:
  - Simpler than Link-State routing.
- **Drawbacks**:
  - Slower to converge and may encounter issues like routing loops.
- **Real-Life Example**: A group of travelers sharing distances to nearby landmarks to decide the shortest route.

---

## 4.2.2 Intra-AS Routing in the Internet: OSPF

- **OSPF (Open Shortest Path First)**:
  - A **Link-State Protocol** used for routing within a single Autonomous System (AS).
  - Divides the network into areas to improve efficiency.
- **Key Features**:
  - Uses Dijkstra’s algorithm for route calculation.
  - Supports hierarchical routing with multiple areas.
- **Advantages**:
  - Efficient and scalable for large networks.
  - Supports advanced features like load balancing and authentication.
- **Real-Life Example**: A corporate office network with separate routing for departments, managed centrally for efficiency.

---

## 4.2.3 Routing Among the ISPs: BGP

- **BGP (Border Gateway Protocol)**:
  - A protocol used to route data between different Autonomous Systems (AS), such as Internet Service Providers (ISPs).
- **How It Works**:
  - BGP exchanges information about reachable networks and their attributes.
  - Prioritizes policies over the shortest path.
- **Advantages**:
  - Ensures global connectivity across the Internet.
  - Allows ISPs to define routing policies based on business needs.
- **Real-Life Example**: A global courier company choosing routes based on cost, speed, and reliability, rather than distance alone.

---

## 4.2.4 ICMP: The Internet Control Message Protocol

- **Purpose**: Used for error reporting and diagnostic messages in the Internet.
- **Functions**:
  - Reports issues like unreachable destinations or routing loops.
  - Supports tools like `ping` and `traceroute` for network testing.
- **Message Types**:
  - **Echo Request/Reply**: Used by `ping` to test connectivity.
  - **Destination Unreachable**: Indicates that a packet cannot reach its destination.
- **Real-Life Example**: A mail carrier informing the sender about undeliverable mail (e.g., incorrect address).

---

### Summary

- **Link-State Routing**: Offers precise routing by sharing complete network topology.
- **Distance-Vector Routing**: Shares simpler distance information but is slower to adapt.
- **OSPF**: A robust intra-AS routing protocol for efficient and secure internal network management.
- **BGP**: The backbone of Internet routing, enabling global connectivity between ISPs.
- **ICMP**: The Internet's diagnostic tool for error reporting and connectivity testing.

<hr>

## Connect with me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-blue?logo=linkedin&logoColor=white&style=flat-square)](https://www.linkedin.com/in/sushan-khatri-959248259/)
<hr>