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
