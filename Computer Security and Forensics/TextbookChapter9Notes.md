**Justin Ciocoi**

**Mar. 7, 2024**

# CSCI 400 Textbook Notes

## Chapter 9: Firewalls and Intrusion Prevention Systems

### 9.1: The Need for Firewalls

- The need for the internet is obviously very large, but despite the benefits of interconnectivity that this networking provides, it also opens the door to a world of network-based threat actors

- Thus firewalls are in place as an effective means by which to protect an entire Local Area Network (LAN)

- The firewall is inserted between the LAN and the internet in order to establish a controlled link

- This is used as perimeter defense in organizational security 

### 9.2: Firewall Characteristics and Access Policy

- **Characteristics**
  
  - All traffic in both directions must pass through the firewall
  
  - Only traffic that is authorized as per the firewall's security policy will be allowed to pass through 
  
  - The firewall itself is immune to penetration

- **Access Policy**
  
  - A suitable access policy must be in place for a firewall to effectively function
  
  - This policy should be reached as a result of risk analysis and policy assessment
  
  - A firewall could use the following features to filter network traffic]
    
    - *IP Address and Protocol Values*
    
    - *Application Protocol*
    
    - *User Identity*
    
    - *Network Activity*

- **Capabilities**
  
  - Defines a single choke point
  
  - Provides a centralized location for monitoring security events
  
  - Can serve as the platform for IPSec

- **Limitations**
  
  - Cannot protect against attacks which bypass the firewall
  
  - May not fully protect against internal threats
  
  - Portable devices can be compromised outside of the enterprise's network and then used internally, thus bypassing the firewall

### 9.3: Types of Firewalls

- **Packet Filtering Firewalls**
  
  - Applies rules to each incoming and outgoing IP packets which are usually based on matches in the IP or TCP header
  
  - Filtering rules are based on the following information
    
    - *Source/Destination IP Address*
    
    - *Source/Destination Transport Level Address*
    
    - *IP Protocol Field*
    
    - *Interface*
  
  - The two default policies are forwarding and discarding packets based on matches in the rules
  
  - These firewalls are typically fairly simple, but they do not protect against application-specific vulnerabilities
  
  - An example of packet filtering rules might look as follows
    
    | Rule | Direction | Src address | Dest address | Protocol | Dest port | Action |
    | ---- | --------- | ----------- | ------------ | -------- | --------- | ------ |
    | 1    | In        | External    | Internal     | TCP      | 25        | Permit |
    | 2    | Out       | Internal    | External     | TCP      | >1023     | Permit |
    | 3    | Out       | Internal    | External     | TCP      | 25        | Permit |
    | 4    | In        | External    | Internal     | TCP      | >1023     | Permit |
    | 5    | Either    | Any         | Any          | Any      | Any       | Deny   |

- **Stateful Inspection Firewalls**
  
  - This type of firewall tightens the rules for TCP traffic by creating a directory of outbound TCP connections
    
    - Each already established connection has an entry 
  
  - Reviews Packet information but also records packet information about TCP connections
  
  - An example connection state table for a stateful inspection firewall might look as follows
    
    | Source Address | Source Port | Destination Address | Destination Port | Connection State |
    | -------------- | ----------- | ------------------- | ---------------- | ---------------- |
    | 192.168.1.100  | 1030        | 210.9.88.29         | 80               | Established      |
    | 192.168.1.102  | 1031        | 216.32.42.123       | 80               | Established      |
    | 192.168.1.101  | 1033        | 173.66.32.122       | 25               | Established      |
    | 192.168.1.106  | 1035        | 177.231.32.12       | 79               | Established      |
    | 223.43.21.231  | 1990        | 192.168.1.6         | 80               | Established      |
    | 219.22.123.32  | 2112        | 192.168.1.6         | 80               | Established      |
    | 210.99.212.18  | 3321        | 192.168.1.6         | 80               | Established      |
    | 24.102.32.23   | 1025        | 192.168.1.6         | 80               | Established      |
    | 223.21.22.12   | 1046        | 192.168.1.6         | 80               | Established      |

- **Application-Level Gateways**
  
  - Also called an application proxy
  
  - This acts as a relay of application-level traffic
    
    - User contacts gateway using TCP/IP
    
    - User is authenticated
    
    - Gateway contacts application on remote host and relays TCP segments between server and user
  
  - There must be a proxy code for each application, which might limit the application features supported
  
  - These tend to be secure than packet filters
  
  - The disadvantage is the additional processing overhead on each connection

- **Circuit-Level Gateways**
  
  - Sets up two TCP connections
    
    - One between itself and a TCP user on an inner host
    
    - One between itself and a TCP user on an outer host
  
  - Relays TCP segments from one connection to another without examining contents
  
  - The security function comes from determining which connections will be allowed

### 9.4: Firewall Basing

- Firewalls can be based in a variety of ways including on a standalone system running a secure OS or as a software module in a router or LAN switch

- **Bastion Host**
  
  - A bastion host is a system which is identified as a critical strong point in a network's security 
  
  - It serves as a platform for an application-level or circuit-level gateway
  
  - Some common characteristics of bastion hosts include
    
    - *Running Secure OS and Only Essential Services*
    
    - *Requiring User Authentication to Access Proxy or Host*
    
    - *Proxies are Small, Simple, and Tested*
    
    - *Each proxy is independent*
    
    - *Only Read-Only Code is Used*

- **Host-Based Firewalls**
  
  - These firewalls are used to secure an individual host
  
  - They are available as integrated parts of operating systems or can be provided as an add-on package 
  
  - Packet flows are filtered and restricted
  
  - The advantages of host-based firewalls are as follows
    
    - Filtering rules can be precisely tailored
    
    - Protection is provided independent of network topology
    
    - An additional layer of protection is provided

- **Personal Firewalls**
  
  - These control the traffic between a personal computer and either the internet or an enterprise's network 
  
  - They are both for home and corporate use
  
  - Typically, it comes in the form of a software module on a personal computer
  
  -  The primary role of the personal firewall is to deny unauthorized remote access

### 9.5: Firewall Location and Configuration

| Firewall Configuration             | Description                                                                                   |
| ---------------------------------- | --------------------------------------------------------------------------------------------- |
| Host-resident firewall             | Includes personal firewall software and firewall software on servers                          |
| Screening router                   | Single router between internal and external networks with stateless or full packet filtering  |
| Single bastion inline              | Single firewall device between an internal and external router                                |
| Single bastion T                   | Has a third network interface on bastion to a DMZ where externally visible servers are placed |
| Double bastion inline              | DMZ is sandwiched between bastion firewalls                                                   |
| Double bastion T                   | DMZ is on a separate network interface on the bastion firewall                                |
| Distributed firewall configuration | Used by large businesses and government organizations                                         |

### 9.6: Intrusion Prevention Systems

- This is an extension of the IDS discussed in chapter 8 which includes the capability to attempt to block or prevent detected malicious activity 

- This, like an IDS, can be host-based, network-based, or distributed/hybrid, and these models can be thought of in a very similar matter to there IDS counterparts
