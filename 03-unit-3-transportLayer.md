# Unit-3: Transport Layer
* 3.1.Introduction and Transport-Layer Services
    * 3.1.1.Relationship Between Transport and Network Layers
    * 3.1.2.Overview of the Transport Layer in the Internet
* 3.2.Multiplexing and De-multiplexing
* 3.3.Connectionless Transport: UDP
    * 3.3.1.UDP Segment Structure
    * 3.3.2.UDP Checksum
* 3.4.Principles of Reliable Data Transfer
    * 3.4.1.Go-Back-N (GBN)
    * 3.4.2.Selective Repeat (SR)
* 3.5.Connection-Oriented Transport: TCP
    * 3.5.1.Round-Trip Time Estimation and Timeout
    * 3.5.2.Reliable Data Transfer
    * 3.5.3.Flow Control
    * 3.6.TCP Congestion Control

<b>Practical Works: </b>

* Wireshark Lab: Exploring TCP and UDP

<hr>
lexing: Delivering received data to the correct application using port numbers.
3.3 Connectionless Transport: UDP
UDP: Lightweight, faster, but offers no reliability or congestion control.
3.3.1 UDP Segment Structure
Contains:
Source/Destination Ports
Length
Checksum
Data
3.3.2 UDP Checksum
A simple mechanism to detect errors in transmitted data.
3.4 Principles of Reliable Data Transfer
Reliable data transfer ensures data is delivered accurately and in order.

3.4.1 Go-Back-N (GBN)
Sender can transmit multiple packets (window size).
If one packet is lost, all subsequent packets are retransmitted.
3.4.2 Selective Repeat (SR)
Sender retransmits only the lost packets, not the entire sequence.
3.5 Connection-Oriented Transport: TCP
TCP is the cornerstone of reliable communication in the Internet.

3.5.1 Round-Trip Time (RTT) Estimation and Timeout
Measures the time for a segment to travel to the receiver and back.
Adjusts retransmission timeout dynamically based on RTT.
3.5.2 Reliable Data Transfer
Ensures data arrives at the receiver correctly using:
Acknowledgments (ACKs).
Sequence Numbers.
3.5.3 Flow Control
Matches the sender’s transmission rate to the receiver’s capacity using the receiver’s window size.
3.6 TCP Congestion Control
Prevents network congestion by adjusting the sender's data rate dynamically.
Slow Start: Gradually increases data rate.
Congestion Avoidance: Avoids sending excessive data.
Fast Retransmit: Quickly retransmits lost packets.
