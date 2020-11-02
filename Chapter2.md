## Chapter 2 Application Layer
### Review Questions Solution

**R1. List five nonproprietary Internet applications and the application-layer protocols that they use.**

> 1. The Web: HTTP
> 2. Remote login: Telnet
> 3. Network News: NNTP
> 4. e-mail: SMTP.
> 5. File transfer: FTP

**R2. What is the difference between network architecture and application architecture?**

> **Network architecture**: The process of organizing the communication process into the layers is called network architecture. Or it can be considered as the design of the communication network.
> **Application Architecture**: The architecture which is designed by the application developer is called Application Architecture. This type of architecture dictates the complete or broad structure of an application.

**R3. For a communication session between a pair of processes, which process is the client and which is the server?**

> The process which initiates the communication is the client; the process that waits to be contacted is the server.

**R4. Why are the terms client and server still used in peer-to-peer applications?**

> All communication sessions have a client side and a server side. In a P2P application, the peer that is receiving a file is typically the client and the peer that is sending the file is typically the server.

**R5. What information is used by a process running on one host to identify a process running on another host?**

> The IP address of the destination host and the port number of the destination socket.

**R6. What is the role of HTTP in a network application? What other components are needed to complete a Web application?**

> HTTP used to encode and transport information between client and the server in a network application. To complete a web application, we still need clients, servers and UI components.

**R7. Referring to Figure 2.4, we see that none of the applications listed in Figure
2.4 requires both no data loss and timing. Can you conceive of an application that requires no data loss and that is also highly time-sensitive?**

> Network games, network multimedia applications

**R8. List the four broad classes of services that a transport protocol can provide.
For each of the service classes, indicate if either UDP or TCP (or both) pro- vides such a service.**

>1. Reliable data transfer:- TCP only
>2. A guarantee that a certain value for throughput will be maintained:-Neither TCP nor UDP.
>3. A guarantee that data will be delivered within a specified amount of time:- Neither TCP nor UDP.
>4. Security:- Neither TCP nor UDP. 

**R9. Recall that TCP can be enhanced with SSL to provide process-to-process
security services, including encryption. Does SSL operate at the transport layer or the application layer? If the application developer wants TCP to be enhanced with SSL, what does the developer have to do?**

> SSL operates at the application layer. The SSL socket takes unencrypted data from the application layer, encrypts it and then passes it to the TCP socket. If the application developer wants TCP to be enhanced with SSL, he/she has to include the SSL code in the application.

**R10. What is meant by a handshaking protocol?**

> A protocol uses handshaking if the two communicating entities first exchange control packets before sending data to each other. SMTP uses handshaking at the application layer whereas HTTP does not.

**R11. What does a stateless protocol mean? Is IMAP stateless? What about SMTP?**

> HTTP is a stateless protocl. This means a HTTP server needs not keep track of any state information. IMAP is a state protocl. SMTP is a stateless protocol.

**R12. How can websites keep track of users? Do they always need to use cookies?**

> Websites can track what each user does on their site and what pages they visit by their IP address. When the user first visits the site, the site returns a cookie number. This cookie number is stored on the user's host and is managed by the browser. During each subsequent visit (and purchase), the browser sends the cookie number back to the site. Thus the site knows when this user (more precisely, this browser) is visiting the site.

**R13. Describe how Web caching can reduce the delay in receiving a requested
object. Will Web caching reduce the delay for all objects requested by a user or for only some of the objects? Why?**

> Web caching can bring the desired content "closer" to the user, perhaps to the same LAN to which the user's host is connected. Web caching can reduce the delay for all objects, even objects that are not cached, since caching reduces the traffic on links.

**R14. Telnet into a Web server and send a multiline request message. Include in
the request message the If-modified-since: header line to force a response message with the 304 Not Modified status code.**

> Skipped

**R15. Telnet into a Web server and send a multiline request message. Include in
the request message the If-modified-since: header line to force a response message with the 304 Not Modified status code.**

> There is no constraint on the format of the HTTP body, it can be any format. The message body of SMTP must be in 7-bit ASCII. SMTP can transimit arbitrary data because all the data can be encoded to ASCII. After this, SMTP will send out this message.

**R16. Suppose Alice, with a Web-based e-mail account (such as Hotmail or Gmail),
sends a message to Bob, who accesses his mail from his mail server using POP3. Discuss how the message gets from Alice’s host to Bob’s host. Be sure to list the series of application-layer protocols that are used to move the message between the two hosts.**

> Message is sent from Alice’s host to her mail server over HTTP. Alice’s mail server then sends the message to Bob’s mail server over SMTP. Bob then transfers the message from his mail server to his host over POP3.

**R17. Print out the header of an e-mail message you have recently received. How
many Received: header lines are there? Analyze each of the header lines in the message.**

> Skipped

**R18. Assume you have multiple devices, and you connect to your email provider
using POP3. You retrieve messages with the “download and keep” strategy from multiple devices. Can your email client tell if you have already read the message in this scenario?**

> My email client cannot tell if I have already read the message because we retrieve messages with the "download and keep" strategy. For each time we read the email from a new client, there is no way to know if the message has been download on other devices before.

**R19. Why are MX records needed? Would it not be enough to use a CNAME record? (Assume the email client looks up email addresses through a Type A query and that the target host only runs an email server.)**

> Mail Exchange (MX) records are DNS records that are necessary for delivering email to your address. In simple DNS terms, an MX record is used to tell the world which mail servers accept incoming mail for your domain and where emails sent to your domain should be routed to. If your MX records are not pointed to the correct location, you will not receive email. CNAME cannot be used to delivery emails because it used to redirect from your domain's subdomain to another domain/subdomain.

**R20. What is the difference between recursive and iterative DNS queries?**

> **Iterative** DNS queries are ones in which a DNS server is queried and returns an answer without querying other DNS servers, even if it cannot provide a definitive answer. Iterative queries are also called non-recursive queries.
> **Recursive** DNS queries occur when a DNS client requests information from a DNS server that is set to query subsequent DNS servers until a definitive answer is returned to the client. The queries made to subsequent DNS servers from the first DNS server are iterative queries.

**R21. Under what circumstances is file downloading through P2P much faster than through a centralized client-server approach? Justify your answer using Equation 2.2.**

> When there are peers that near to the host and have the files that the host want to download.

**R22. Consider a new peer Alice that joins BitTorrent without possessing any chunks. Without any chunks, she cannot become a top-four uploader for any of the other peers, since she has nothing to upload. How then will Alice get her first chunk?**

> Alice will get her first chunk as a result of she being selected by one of her neighbors as a result of an “optimistic unchoke,” for sending out chunks to her.

**R23. Assume a BitTorrent tracker suddenly becomes unavailable. What are its consequences? Can files still be downloaded?**

> If the tracker fails or is unreachable, the system becomes unavailable to new peers, so they can not obtain the file or contribute resources to the system. Fiels still can be downloaded for old peers.

**R24. CDNs typically adopt one of two different server placement philosophies. Name and briefly describe them.**

> 1. **Enter deep**:
    it is pioneered by Akamai. It deploys server clusters in access ISPs (ISPs direct accessing end users) all over the world.
    The goal of Enter deep is to get close to end users, thereby improving user-perceived delay and throughput by decreasing the number of links.
    Routers between the end user and then CDN cluster from which it receives content. Because of this highly distributed design, the task of maintaining and managing the clusters become challenging.
> 2. **Bring home**:
    It can be taken by Limelight and other CDN companies; it brings the ISPs home by building large clusters at a smaller number of key locations and connecting these clusters using a private high-speed network.
    Instead of getting inside the access ISPs, these CDNs typically place each cluster at a location that is simultaneously near the point of presence of many tier-1 ISPs.
    Compared with the enter-deep design, the bring-home design typically results in lower maintenance and management overhead, possibly at the expense of higher delay and lower throughout to end users.

**R25. Besides network-related considerations such as delay, loss, and bandwidth performance, there are other important factors that go into designing a CDN server selection strategy. What are they?**

> There are many important additional factors available, form those few will be going to considered while designing the cluster selection strategy.
    **ISP delivery cost**
    **Load on the clusters**
    The description of the important factors is The clusters may be chosen based on different cost structures, so that the ISP delivery cost is minimized. In Load on the clusters, we should be bothered when a client is to be directed to a cluster, so that the client is not directed to an overloaded cluster.

**R26. In Section 2.7, the UDP server described needed only one socket, whereas the TCP server needed two sockets. Why? If the TCP server were to support n simultaneous connections, each from a different client host, how many sockets would the TCP server need?**

> The reason is that TCP has two different kinds of state that you want to control, whereas UDP has only one. Still two sockets are needed. The number of sockets needed by TCP does not rely on the number of simulataneous connections.

**R27. For the client-server application over TCP described in Section 2.7, why must the server program be executed before the client program? For the client-server application over UDP, why may the client program be executed before the server program?**

> In TCP, server program has to be executed because server needed to wait 3-way handshaking from the client. In UDP, there is not such 3-way handshaking, it does not matter either the server program or client program executed first.