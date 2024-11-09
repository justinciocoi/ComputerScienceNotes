**Justin Ciocoi**

**Mar. 7, 2024**

# CSCI 400 Textbook Notes

## Chapter 8: Intrusion Detection

### 8.1: Types of Intruders

- **Cyber Criminals**
  
  - These are either individuals or members of an organized crime group with the goal of financial gain
  
  - The activities of cyber criminals might include
    
    - *Identity Theft*
    
    - *Theft of Financial Credentials*
    
    - *Corporate Espionage*
    
    - *Data Theft*
    
    - *Data Ransoming*
  
  - Underground forums are often used to trade tips, data, and to coordinate attacks

- **Activists**
  
  - These are usually insider threats or members of large external groups
  
  - These attackers are generally motivated by social and political causes
  
  - The technical skill level of this faction of attackers is relatively low
  
  - Usually, their attacks aim to promote and publicize a specific cause, often through the use of denial of service and website defacement 

- **State-Sponsored Organizations**
  
  - These are larger groups of hackers which are sponsored by governments with the purpose of conducting espionage or sabotaging various activities
  
  - They are also known as **Advanced Persistent Threats (APTs)**

- **Skill Levels of Intruders**
  
  - **Apprentice**
    
    - These attackers have minimal technical skills and usually use pre-existing attack toolkits
    
    - This is most likely the largest group of hackers and includes many criminal and activist hackers
    
    - They are also known as *script-kiddies*
  
  - **Journeyman**
    
    - These hackers have more technical skill and are able to modify and extend attack toolkits to attack newly discovered vulnerabilities
    
    - They often adapt tools for use by lower skill level hackers
  
  - **Master**
    
    - These are hackers with high levels of technical skill who are capable of discovering entire new categories of vulnerability
    
    - They can write powerful new attack toolkits
    
    - These attacks are the most difficult to defend against
    
    - These attackers are sometimes employed by state sponsored organizations
  
  - **Common Intruder Behaviors**
    
    - *Target Acquisition and Information Gathering*
    
    - *Initial Access*
    
    - *Privilege Escalation*
    
    - *Information Gathering or System Exploit*
    
    - *Maintaining Access*
    
    - *Covering Tracks*

### 8.2: Intrusion Detection

- **Intrusion Detection** is defined as a hardware or software function that gathers and analyzes information from various areas within a computer or a network to identify possible security intrusions

- **Intrusion Detection Systems (IDS)**
  
  - An IDS can come in a variety of forms, namely
    
    - Host-based IDS
    
    - Network-based IDS
    
    - Distributed/Hybrid IDS
  
  - And each ID consists of three logical components which are
    
    - *Sensors*, which collect data
    
    - *Analyzers* which determine if an intrusion has occurred
    
    - *User Interface* which view output or control system behavior

### 8.3: Analysis Approaches

- There are two main analysis approaches that IDSs use
  
  - **Anomaly Detection**
    
    - This involves collecting user data relating to behavior over a period of time
    
    - This behavioral data is then analyzed to determine the legitimacy of the user
  
  - **Signature/Heuristic Detection**
    
    - Uses a set of known malicious data patterns which are compared to current attack behavior
    
    - Also known as misuse detection
    
    - This is limited by its set of known attack data patterns
  
  - Both have advantages and disadvantages, and a hybrid model is often implemented

### 8.4: Host-Based IDS (HIDS)

- These systems add a specialized layer of security software to vulnerable or sensitive systems
- These systems can use either of the aforementioned analysis approaches
- They monitor activity to detect suspicious behavior

### 8.5: Network-Based IDS (NIDS)

- These systems monitor traffic at selected points on a network

- They will examine network traffic packet-by-packet in real time or close to real time

- May examine network, transport, and/or application-level protocol activity

- Comprised of sensors, one or more servers for NIDS management, and one or more management consoles for the human interface

- Analysis of traffic patterns may be done at the sensor, the management server, or a combination of the two

- A typical NIDS deployment may look like the following
  
  <img title="" src="file:///Users/justin/Pictures/marktextImages/fe5cb35af2d48a160f8b701631ded1911d4f7195.png" alt="" data-align="center" width="432">

### 8.8: Honeypots

- **Honeypots** are decoy systems which are designed with the purpose of
  
  - Luring attackers away from critical systems
  
  - Collecting information about attacker activity
  
  - Encourage attackers to stay on the system long enough for admin to respond

- These systems are usually filled with fabricated information that a legitimate user of the system would not need to access

- A typical honeypot deployment might be seen as follows
  
  <img title="" src="file:///Users/justin/Pictures/marktextImages/231c28bce9014f7fbfeed9d499bd6a18164e7d15.png" alt="" data-align="center" width="354">
