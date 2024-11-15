# Unit-2 Application Layer
* 2.1.The Web and HTTP: overview of HTTP, HTTP Message Format, User-Server Interaction: Cookies, Web Caching
* 2.2.Electronic Mail in the Internet : SMTP, Mail Message Formats, Mail Access Protocols
* 2.3.DNS—The Internet’s Directory Service
* 2.4.Peer-to-Peer File Distribution
* 2.5.Video Streaming and Content Distribution Networks5+5


<hr> 

# 2.1 The Web and HTTP overview of HTTP, HTTP Message Format, User-Server Interaction:



# 2.1 The Web and HTTP
* <b>Overview of HTTP</b>
HTTP (Hypertext Transfer Protocol): A request-response protocol used for communication between web clients (browsers) and servers. 
* Features:
    * Stateless: Each request is independent.
    * Methods: Common methods include GET, POST, PUT, DELETE.
* Versions: HTTP/1.1, HTTP/2, HTTP/3 (introduced with QUIC).

# HTTP Message Format
* <b> 1.Request Message:</b>
    * Start-line: Includes method (e.g., GET), URL, and HTTP version.
    * Headers: Meta-information (e.g., Host, User-Agent).
    * Body: Optional, used for POST or PUT data.

* <b> 2. Response Message:</b>
    * Status line: HTTP version, status code (e.g., 200 OK).
    * Headers: Server info, content type, etc.
    * Body: The actual data (HTML, JSON, etc.).

# User-Server Interaction: Cookies
* Cookies: Small text files stored on a user's device by the browser.
* Purpose: Session management, personalization, and tracking.
* Mechanism:
    * Server sends Set-Cookie in an HTTP response.
    * Browser sends cookies back in subsequent requests.

# Web Caching
* Definition: Temporarily storing web content closer to users to reduce latency and server load.
* Types:
    * Browser Cache: Local storage of recently accessed pages.
    * Proxy Cache: Shared by multiple users.


# 2.2 Electronic Mail in the Internet
<b>SMTP (Simple Mail Transfer Protocol)</b>

* Protocol for sending emails from clients to servers and between servers.
* Uses port 25 or 587 for communication.
* Works in a push model (email is pushed to the next server).

<b>Mail Message Formats</b>

* Defined in RFC 5322:
    * Header: Sender, recipient, subject, etc.
    * Body: Text content of the email.
* Can include MIME (Multipurpose Internet Mail Extensions) for attachments.
<b>Mail Access Protocols</b>

* Protocols for retrieving emails:
    * POP3 (Post Office Protocol v3): Downloads emails and deletes from the server.
    * IMAP (Internet Message Access Protocol): Syncs emails between client and server.
    * Webmail: Browser-based access.


# 2.3 DNS—The Internet’s Directory Service
* DNS (Domain Name System): Translates domain names (e.g., www.google.com) into IP addresses.
* Components:
    * Resolvers: Client-side DNS queries.
    * Root Servers: Top-level DNS servers.
    * Authoritative Servers: Provide specific domain IPs.
    * Caching: Speeds up subsequent lookups.
* Record Types: A (IPv4), AAAA (IPv6), MX (Mail Exchange), CNAME (Canonical Name).


# 2.4 Peer-to-Peer File Distribution
Definition: File sharing without a central server; peers act as both clients and servers.
Examples: BitTorrent, Gnutella.
Advantages:
Scalable.
Reduces server load.
Challenges:
Bandwidth consumption.
Legal concerns over copyright infringement.


# 2.5 Video Streaming and Content Distribution Networks (CDNs)
Video Streaming:
Types: On-demand (e.g., Netflix) or live (e.g., Twitch).
Protocols: HTTP-based streaming (HLS, DASH).
Challenges: Bandwidth, latency, buffering.
CDNs:
Networks of servers distributed geographically to deliver content efficiently.
Use caching and load balancing to reduce latency and enhance user experience.
Examples: Akamai, Cloudflare.

