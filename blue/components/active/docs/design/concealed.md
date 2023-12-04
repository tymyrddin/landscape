# Avoiding honeypot detection

## Automatic honeypot redeployment

Low interaction honeypots are more expensive to develop with built in anti-detection because their scope and functionality are limited in contrast to high interaction honeypots. On [discovery by an attacker](detection.md), modifying an existing honeypot configuration may be too costly. 

One approach for avoiding honeypot detection involves automated redeployment of the honeypot, which in turn reduces the need for anti-detection honeypot configurations. One study that has explored the development and implementation of such a mechanism automatically re-deploys a honeynet when it identifies that an attacker has detected it. 

Inbound and outbound Internet Control Message Protocol (ICMP) packets are monitored and any drop in the number of ICMP packets below a pre-determined threshold indicates that the attacker has disconnected (indicative of the honeypot being discovered). The honeypot is then automatically redeployed with an altered configuration with intent to trap the same attacker. This method reduces setup overheads and development of anti-detection mechanisms for honeypots.   

## Honeypot delay reduction

One detection risk for honeypots comes from the introduction of arbitrary delays in processes that a honeypot mimics that would otherwise not have such delays. For example, authentication via SSH that is delayed due to logging or log forwarding required by a honeypot. These delays enable attackers to detect the honeypot. By reducing the time delay to match more closely that of a real infected host, the risk of detecting the honeypot is lowered. Delay reduction as an optimisation for honeypots has demonstrated its effectiveness in avoiding honeypot’s detection when applied to Honeyd. 

Honeyd is a virtual (software) honeypot that emulates the protocol stack (such as the TCP/IP stack), such that attackers are convinced they are attacking a real vulnerable system. But because Honeyd operates on a virtual network, the link latency can be used to detect the presence of the honeypot. Specifically, end-to-end latency in Honeyd’s design is a multiple of 10 milliseconds. 

By comparing latencies between a physical (real) network and a virtual (honeypot) network we can define a threshold in which the two latencies are different. Using that threshold we can detect honeypot networks that use Honeyd. 

Attackers can use measurements of round trip times (by using ICMP, TCP, or UDP echo-reply) to detect the presence of honeypots. The study found that camouflaging Honeyd by modifying it to have a lower link latency, was effective in avoiding the honeypot system being detected.  

The study concluded that although the method was successful with the Honeyd honeypot system, it can also be broadly applied to other virtual honeypot systems.

## Honeypot process transparency

Another side effect of the way honeypots operate is the lack of transparency that leads to revealing their deceptive design. An example of this can be observed in hybrid honeypot systems. In these types of honeypots, both low and high interaction honeypots are used with a frontend honeypot forwarding connections to a backend honeypot. 

Current TCP connection handover mechanisms in hybrid honeypot systems can easily be detected. One study proposed a transparent TCP connection handover mechanism that uses different ports of an OpenFlow-based switch to isolate honeypots while TCP connection parameters (SEQ, ACK numbers) remain the same. 

The hybrid honeypots require network traffic to be re-directed from the frontends to the backends and this traffic redirection is often not transparent enough to evade detection. An alternative mechanism consists of three phases: 

* Phase one is initiated by an attacker sending a TCP connection request to the target honeypot. The honeypot controller forwards the request to the frontend which performs the TCP three-way handshake to establish a connection with the attacker. 
* Phase two involves transferring the TCP session from the frontend to the backend using a TCP replaying approach. This approach replays the three-way handshake using the saved attacker’s SYN packet. SEQ and ACK numbers are then synchronised leading to the third phase.
* In phase three packets are exchanged directly between the attacker and the backend. 

The study concluded that this approach makes the hybrid honeypot much stealthier, but at the expense of reduced performance. In general, honeypots need to ensure that operations that are being emulated need to maintain transparency. In other words, they need to hide any modified sequence of events that is not realistic.

## Dedicated hardware

Although expensive, the use of dedicated hardware for honeypots can help minimise their detection rate (for example by reducing arbitrary software delays). Additionally, dedicated hardware can also provide an additional layer of security against honeypot compromise. 

These benefits were demonstrated in a study, [An FPGA-based Scalable Platform for High-Speed Malware Collection in Large IP Networks](https://www.esa.informatik.tu-darmstadt.de/assets/publications/materials/2010/2010_FPT.pdf): This architecture implemented honeypots using dedicated hardware instead of a general-purpose processor and it also made use of a high-speed implementation of the IP stack. Additionally, the approach used a specialised stateless TCP hardware. 

The stateless TCP hardware can manage hundreds of thousands of simultaneous connections thereby enabling the system to support large honeynets. An increased speed of execution of TCP operations may reduce the likelihood of a honeypot being detected by an attacker. An additional benefit of implementing honeypot operations in hardware instead of software using general-purpose processors is that it also reduces the risk of the honeypot software being compromised and used for attacks.

## Dynamic intelligence on honeypots

The advent of dynamic approaches to honeypot development as well as novel techniques in machine learning and artificial intelligence provide an opportunity for more diverse honeypots that alter their behaviour depending on the actions of an attacker. The result is a more adaptable honeypot that is more difficult to detect. 

In general, dynamic honeypots have a behaviour that is not fixed, but changes based on some condition and adapts to the current environment. In this case, configuration or re-configuration is not required. An example of such a system is a high interaction honeypot that uses reinforced learning in order to dynamically change its behaviour based on the interaction that it has with an attacker. The honeypot can strategically block program execution, alter program names in order to lure attackers and can deceive attackers with the intent of having them reveal their background, which is especially important for research honeypots.
