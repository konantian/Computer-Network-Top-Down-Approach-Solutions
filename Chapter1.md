## Chapter 1 Review Questions Solution

**R1. What is the difference between a host and end system? List several different types of end system. Is a Web server an end system?**

> There is no difference between a host and an end system.  End systems include PCs, workstations, web servers, mail servers, game consoles. Web server is an end system for sure.

**R2. Describe the protocol that might be used by two people having a telephonic conversation to initiate and end the conversation.**

> Two people may start the telephonic conversation by saying "hello" to each other first. To end the conversation, they have to say "bye" to each other.

**R3. Why are standards important for protocols?**

> Standards are important for protocols so that people can create networking systems and products that interoperate.

**R4. List six access technologies. Classify each one as home access, enterprise access, or wide-aree wireless access.**

> *  Dial-up modem over telephone line - home
> *  DSL over telephone line - home
> *  Cable to HFC - homne
> *  100 Mbps switched Ethernet - enterprise
> *  Wifi (802.11) - home and enterprise
> *  4G and 5G - wide-are wireless

**R5. Is HFC transmission rate dedicated or shared among users? Are collisions possible in a downstream HFC channel?Why or why not?**

> HFC bandwidth is shared among the users. On the downstream channel, all packets emanate from a single source, namely, the head end. Thus, there are no collisions in the downstream channel.

**R6. What access network technologies would be most suitable for providing Internet access in rural areas?**

> 4G and 5G will be most suitable in rural areas. In rural areas, it is hard to use Dial-up modem, DSL, or Cable to HFC. The biggest difference between city and rural is homes in rural areas are much more sparse than city. 4G and 5G does not require any cable to access to internet.

**R7. Dial-up modems and DSL both use the telephone line (a twisted-pair copper cable) as their transmission medium. Why then is DSL much faster than dial-up access?**

> Like dialup, DSL uses the phone line to transfer data. However, unlike dialup, DSL operates at a much higher frequency, so the data doesn’t interfere with the voice data, meaning that you can use the phone and internet at the same time. So, in most of the time, DSL is much faster than dial-up.

**R8. What are some of the physical media that Ethernet can run over?**

> Ethernet most commonly runs over twisted-pair copper wire. It also can run over fibers optic links.

**R9. Dial-up modems, HFC, DSL and FTTH are all used for residential access.
For each of these access technologies, provide a range of  transmission rates and comment on whether the transmission rate is shared or dedicated.**

> Dial up modems: up to 56 Kbps, bandwidth is dedicated; ADSL: up to 24 Mbps downstream and 2.5 Mbps upstream, bandwidth is dedicated; HFC, rates up to 42.8 Mbps and upstream rates of up to 30.7 Mbps, bandwidth is shared. FTTH: 2-10Mbps upload; 10-20 Mbps download; bandwidth is not shared.

**R10. Describe the different wireless technologies you use during the day and their characteristics. If you have a choice between multiple technologies, why do you prefer one over another?**

> There are two popular wireless Internet access technologies today:
> *  Wifi (802.11) In a wireless LAN, wireless users transmit/receive packets to/from an base station (i.e., wireless access point) within a radius of few tens of meters. The base station is typically connected to the wired Internet and thus serves to connect wireless users to the wired network.
> * 4G and gG wide-area wireless access networks. In these systems, packets are transmitted over the same wireless infrastructure used for cellular telephony, with the base station thus being managed by a telecommunications provider. This provides wireless access to users within a radius of tens of kilometers of the base station.

**R11. Suppose there is exactly one packet switch between a sending host and a
receiving host. The transmission rates between the sending host and the switch and between the switch and the receiving host are R1 and R2, respec- tively. Assuming that the switch uses store-and-forward packet switching, what is the total end-to-end delay to send a packet of length L? (Ignore queu- ing, propagation delay, and processing delay.)**

> At time t0 the sending host begins to transmit. At time t1 = L/R1, the sending host completes transmission and the entire packet is received at the router (no propagation delay). Because the router has the entire packet at time t1, it can begin to transmit the packet to the receiving host at time t1. At time t2 = t1 + L/R2, the router completes transmission and the entire packet is received at the receiving host (again, no propagation delay). Thus, the end-to-end delay is L/R1 + L/R2.

**R12. What advantage does a circuit-switched network have over a packet-switched network? What advantages does TDM have over FDM in a circuit-switched network?**

> A circuit-switched network can guarantee a certain amount of end-to-end bandwidth for theduration of a call. Most packet-switched networks today (including the Internet) cannot make any end-to-end guarantees for bandwidth. FDM requires sophisticated analog hardware to shift signal into appropriate frequency bands.

**R13. Suppose users share a 2 Mbps link. Also suppose each user transmits
continuously at 1 Mbps when transmitting, but each user transmits only 20 percent of the time. (See the discussion of statistical multiplexing in Section 1.3.)**

**a) When circuit switching is used, how many users can be supported?
b) For the remainder of this problem, suppose packet switching is used. Why
will there be essentially no queuing delay before the link if two or fewer
users transmit at the same time? Why will there be a queuing delay if three
users transmit at the same time?
c) Find the probability that a given user is transmitting.
d) Suppose now there are three users. Find the probability that at any given
time, all three users are transmitting simultaneously. Find the fraction of
time during which the queue grows.**

> * 2 users can be supported because each user requires half of the link bandwidth.
> * Since each user requires 1Mbps when transmitting, if two or fewer users transmit simultaneously, a maximum of 2Mbps will be required. Since the available bandwidth of the shared link is 2Mbps, there will be no queuing delay before the link. Whereas, if three users transmit simultaneously, the bandwidth required will be 3Mbps which is more than the available bandwidth of the shared link. In this case, there will be queuing delay before the link.
> * Probability that a given user is transmitting = 0.2
> * Since the queue grows when all the users are transmitting, the fraction of time during which the queue grows (which is equal to the probability that all three users are transmitting simultaneously) is 0.008. 

**R14. Why will two ISPs at the same level of the hierarchy often peer with each other? How does an IXP earn money?**

>  If the two ISPs do not peer with each other, then when they send traffic to each other they have to send the traffic through a provider ISP (intermediary), to which they have to pay for carrying the traffic. By peering with each other directly, the two ISPs can reduce their payments to their provider ISPs. An Internet Exchange Points (IXP) (typically in a standalone building with its own switches) is a meeting point where multiple ISPs can connect and/or peer together. An ISP earns its money by charging each of the the ISPs that connect to the IXP a relatively small fee, which may depend on the amount of traffic sent to or received from the IXP.

**R15. Why is a content provider considered a different Internet entity today? How does a content provider connect to other ISPs? Why?**

> some content providers created their own network. For example, Google, Google's private network connects together all its data centers, big and small. A content provider connect to other ISPs by using internet access provided by ISPs. For example, Google's data center are close to lower tier ISPs. Therefore, when Google delivers content to a user, it often can bypass higher tier ISPs. 

**R16. Consider sending a packet from a source host to a destination host over a fixed route. List the delay components in the end-to-end delay. Which of these delays are constant and which are variable?**

> The delay components are processing delays, transmission delays, propagation delays, and queuing delays. All of these delays are fixed, except for the queuing delays, which are variable.

**R17. Visit the Transmission Versus Propagation Delay applet at the companion
Web site. Among the rates, propagation delay, and packet sizes available, find a combination for which the sender finishes transmitting before the first bit of the packet reaches the receiver. Find another combination for which the first bit of the packet reaches the receiver before the sender finishes transmitting.**

> 1. Length 10 km, Rate 100 Mbps Packet size 100 bytes
> 2. Length 10 km, Rate 1 Mbps Packet size 100 bytes

**R18. A user can directly connect to a server through either long-range wireless or a twisted-pair cable for transmitting a 1500-bytes file. The transmission rates of the wireless and wired media are 2 and 100 Mbps, respectively. Assume that the propagation speed in air is 3 x 10^8 m/s, while the speed in the twisted pair is 2 x 10^8 m/s. If the user is located 1 km away from the server, what is the nodal delay when using each of the two technologies?**

> The nodal delay = process delay + transmission delay + queueing delay + proppagation delay. We assume that process delay and queueing delyis negligible here. Nodal delay for long-rang wireless is 1500/(2x125000) + 1000/(3x10^8) = 0.006 + 0.00000333 = 6.003 ms. Nodal delay for twisted-par cable is 1500/(100*125000) + 1000/(2x10^8) = 0.123 ms

**R19. Suppose Host A wants to send a large file to Host B. The path from Host A to Host B has three links, of rates R1 = 500 kbps, R2 = 2 Mbps, and R3 = 1 Mbps.**

**a) Assuming no other traffic in the network, what is the throughput for the file transfer?**
**b) Suppose the file is 4 million bytes. Dividing the file size by the throughput,roughly how long will it take to transfer the file to Host B?**
**c) Repeat (a) and (b), but now with R2 reduced to 100 kbps.**

> * (a) 500kbs
> * (b) 4x10^6 / (500*125) = 64 seconds 
> * (c) 100kps 4*10^6 / (100x125) = 320 seconds

**R20.  Suppose end system A wants to send a large file to end system B. At a very high level, describe how end system A creates packets from the file. When one of these packets arrives to a packet switch, what information in the packet does the switch use to determine the link onto which the packet is forwarded? Why is packet switching in the Internet analogous to driving from one city to another and asking directions along the way?**

>  End system A breaks the large file into chunks. It adds header to each chunk, thereby generating multiple packets from the file. The header in each packet includes the IP address of the destination (end system B). The packet switch uses the destination IP address in the packet to determine the outgoing link. Asking which road to take is analogous to a packet asking which outgoing link it should be forwarded on, given the packet’s destination address.



