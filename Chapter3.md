## Chapter 3 Computer Network and the Internet
#### Review Questions Solution

**R1. Suppose the network layer provides the following service. The network layer in the source host accepts a segment of maximum size 1,200 bytes and a des- tination host address from the transport layer. The network layer then guaran- tees to deliver the segment to the transport layer at the destination host. Suppose many network application processes can be running at the destination host.**
a. Design the simplest possible transport-layer protocol that will get applica- tion data to the desired process at the destination host. Assume the operat- ing system in the destination host has assigned a 4-byte port number to each running application process.

b. Modify this protocol so that it provides a “return address” to the destina- tion process.

c. In your protocols, does the transport layer “have to do anything” in the core of the computer network?**

> a The Simple Transport Protocol takes data not exceeding 1196 bytes at the sender side. It accepts four byte of destination port number and host address.The Simple Transport Protocol gives the destination host address and the resulting segment to the network layer.The network layer sends the segment to Simple Transport Protocol at the destination host.The Simple Transport Protocol observes the port number.Abstracts the data from the segment in the Simple Transport Protocol.Finally, send the data to the process recognized by the port number.

> b Consider the two header fields in the segment:
Source port field
Destination port field
The Simple Transport Protocol creates application data, source  and destination port numbers in the segment. It sends the destination host address to the network layer. Then, The Simple Transport Protocol is receiving host  address and provides the process the source port number and the application data.

> c No, the transport layer does not have to do anything in the core.The reason is that, the transport layer "lives" in the end systems.

**R2. Consider a planet where everyone belongs to a family of six, every family lives in its own house, each house has a unique address, and each person in a given house has a unique name. Suppose this planet has a mail service that delivers letters from source house to destination house. The mail service requires that (1) the letter be in an envelope, and that (2) the address of the destination house (and nothing more) be clearly written on the envelope. Suppose each family has a delegate family member who collects and distributes letters for the other family members. The letters do not necessarily provide any indication of the recipients of the letters.**

a. Using the solution to Problem R1 above as inspiration, describe a protocol that the delegates can use to deliver letters from a sending family member to a receiving family member.

b. In your protocol, does the mail service ever have to open the envelope and examine the letter in order to provide its service?

> a Sender has to provide the address of the destination name. It is written by the delegate to the planet’s mail service.After receive the destination address, the envelop the written on the top details.
> b No. The mail service ever have not to open the envelope and examine the letter in order to provide its service.

**R3. How is a UDP socket fully identified? What about a TCP socket? What is the difference between full identification of both sockets?

> An UDP socket is fully identified by a two-tuple consisting of a destination IP address and a destination port number and a TCP socket is identified by a four-tuple: source IP address, source port number, destination IP address, destination port number.

**R4. Describe why an application developer might choose to run an application over UDP rather than TCP?**

> The TCP’(transmission control protocol)  can choke the application’s sending rate at times of bottleneck. The UDP( user datagram protocol) does not keep joining state and does not track any of the limits. Even though data transfer by TCP is dependable, some applications do not need dependable TCP data transfer. So, UDP (user datagram protocol) rather than TCP (transmission control protocol)

**R5. Why is that voice and video traffic is often sent over TCP rather than UDP in today's Internet?**

> Most firewalls are configured to block UDP traffic, using TCP for video and voice traffic lets the traffic though the firewalls. So, that voice and video traffic is often sent over TCP rather than UDP in today’s Internet.

**R6. Is it possible for an application to enjoy reliable datra transfer even when the application runs over UDP? If so, how?**

> Yes.The application developer can put consistent data transfer into the application layer protocol. It contains a significant amount of work and debugging.

**R7. Suppose a process in Host C has a UDP socket with port number 6789. Sup- pose both Host A and Host B each send a UDP segment to Host C with desti- nation port number 6789. Will both of these segments be directed to the same socket at Host C? If so, how will the process at Host C know that these two segments originated from two different hosts?**

> Yes.For each received segment, at the socket interface, the operating system will provide the process with the IP addresses to determine the origins of the individual segments.

**R8. Suppose that a Web server runs in Host C on port 80. Suppose this Web server uses persistent connections, and is currently receiving requests from two different Hosts, A and B. Are all of the requests being sent through the same socket at Host C? If they are being passed through different sockets, do both of the sockets have port 80? Discuss and explain.**

> For each persistent connection, the Web server creates a separate “connection socket”. Each connection socket is identified with a four-tuple: (source IP address, source port number, destination IP address, destination port number). When host C receives and IP datagram, it examines these four fields in the datagram/segment to determine to which socket it should pass the payload of the TCP segment. Thus, the requests from A and B pass through different sockets. The identifier for both of these sockets has 80 for the destination port; however, the identifiers for these sockets have different values for source IP addresses. Unlike UDP, when the transport layer passes a TCP segment’s payload to the application process, it does not specify the source IP address, as this is implicitly specified by the socket identifier

**R9. In our rdt protocols, why did we need to introduce sequence numbers?**

> Sequence numbers are necessary for a receiver to find out whether an arriving packet contains new data or is a retransmission in our rdt protocols.

**R10. In our rdt protocols, why did we need to introduce timers?**

> To handle losses in the channel. If the ACK for a transmitted packet is not received within the duration of the timer for the packet, the packet (or its ACK or NACK) is assumed to have been lost. Hence, the packet is retransmitted. 

**R11. Suppose that the roundtrip delay between sender and receiver is constant and known to the sender. Would a timer still be necessary in protocol rdt 3.0, assuming that packets can be lost? Explain.**

> Yes, a timer still is necessary in protocol rdt 3.0.Reason: Assume the packet is loss, the sender knows the round trip delay time.  It is used for estimate the transfer packet time.

**R12. Visit the Go-Back-N Java applet at the companion Web site.**

a. Have the source send five packets, and then pause the animation before any of the five packets reach the destination. Then kill the first packet and resume the animation. Describe what happens.

b. Repeat the experiment, but now let the first packet reach the destination and kill the first acknowledgment. Describe again what happens.

c. Finally, try sending six packets. What happens?

> A.Have the source send five packets, and then pause the animation before and of the fivepacket reach the destination. Then kill the first packet and resume the animation. Describe what happens.-The packets were received out of order and no packets were acknowledged. The packets werethen retransmitted. Once they were retransmitted and received and ACK was sent to the sender.

> B.Repeat the experiment, but now let the first packet reach the destination and kill the firstACK. Describe what happens.-The first ACK was lost but the others made it to the sender and their timers were stopped.

> C.Finally, try sending six packets. What happens?-It only lets you send 5 packets out at once. Before the sixth packet can be sent you must wait forthe first packet to finish the ACK.

**R13. Repeat R12, but now with the Selective Repeat Java applet. How are Selective Repeat and Go-Back-N different?**

> Selective Repeat java applet protocol:If sender sent more than one packet, it reaches the destionation might be one packet is killed and other packets stored in buffer at end receiver.The receiver  send  acknowldgement to sender, but the sender does not receiver acknowldgement. 
> Go-Bank-N protocol:If sender sent more than one packet, it reaches the destionation might be one packet is killed and other packets reached destination without buffering. The receiver  does not send  acknowldgement to sender, but the sender receive acknowldgement.

**R14. True or False?**
* a. Host A is sending Host B a large file over a TCP connection. Assume Host B has no data to send Host A. Host B will not send acknowledgments to Host A because Host B cannot piggyback the acknowledgments on data. **False**

* b. The size of the TCP rwnd never changes throughout the duration of the connection. **False**

* c. Suppose Host A is sending Host B a large file over a TCP connection. The number of unacknowledged bytes that A sends cannot exceed the size of the receive buffer. **True**

* d.Suppose Host A is sending a large file to Host B over a TCP connection. If the sequence number for a segment of this connection is m, then the sequence number for the subsequent segment will necessarily be m + 1. **False**

* e.The TCP segment has a field in its header for rwnd. **True**

* f. Suppose that the last SampleRTT in a TCP connection is equal to 1 sec. The current value of TimeoutInterval for the connection will neces- sarily be ≥ 1 sec. **False**

* g. Suppose Host A sends one segment with sequence number 38 and 4 bytes of data over a TCP connection to Host B. In this same segment the acknowledgment number is necessarily 42. **False**

**R15. Suppose Host A sends two TCP segments back to back to Host B over a TCP connection. The first segment has sequence number 90; the second has sequence number 110.
a. How much data is in the first segment?
b. Suppose that the first segment is lost but the second segment arrives at B. In the acknowledgment that Host B sends to Host A, what will be the acknowledgment number?**

> a. Consider sequence numbers, First segment = 90,Second segment = 110, data in the first segment = 110 - 90 = 20
> b. Consider the first segment is lost but the second segment arrives at B. In the acknowledgment that Host B sends to Host A, then the acknowledgment number will be first segment of sequence number, that is 90.

**R16. Consider the Telnet example discussed in Section 3.5. A few seconds after the user types the letter ‘C,’ the user types the letter ‘R.’ After typing the letter ‘R,’ how many segments are sent, and what is put in the sequence number and acknowledgment fields of the segments?**

| Segment | Sequence number | Acknowledgment field |
| :-----:| :----: | :----: |
| First segment | seq=43 | ack=80 |
| Second segment | seq=80 | ack=44 |
| Third segment | seq=44 | ack=81 |

**R17. Consider two hosts, Host A and Host

**R18. True or false? Consider congestion control in TCP. When the timer expires at the sender, the value of ssthresh is set to one half of its previous value.**

> False. The slow start threshold(ssthresh) is set to one half of its previous value in the congestion window.