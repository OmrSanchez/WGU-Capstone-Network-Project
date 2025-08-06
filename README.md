# WGU-Capstone-Network-Project-PT

<img width="1227" height="656" alt="image" src="https://github.com/user-attachments/assets/e0625f4e-8440-413b-baf4-2137a4471b59" />

### **WGU Capstone: Enterprise Network Design and Implementation**

This repository contains the documentation and Cisco Packet Tracer simulation for my Western Governors University (WGU) capstone project. This project demonstrates a comprehensive approach to designing, implementing, and securing a scalable enterprise network infrastructure from the ground up, showcasing a wide array of network engineering principles and best practices.

### **Project Goal**

The primary objective of this capstone was to design and build a robust, secure, and resilient network for a simulated multi-department enterprise. The goal was to create a functional network topology in Cisco Packet Tracer that not only meets the immediate connectivity and operational needs of the business but is also scalable for future growth. Key objectives included:
* **Ensuring seamless and efficient data flow** between all network segments.
* **Segmenting network traffic** to enhance security and performance.
* **Implementing redundant pathways and protocols** to guarantee high availability and minimize downtime.
* **Securing the network infrastructure** from unauthorized access and common threats.

### **Approach and Technologies Implemented**

To achieve the project's goals, I employed a multi-layered, hierarchical network design and utilized a range of industry-standard networking technologies and protocols.



**1. Hierarchical Network Design:**
I designed a three-layer hierarchical model (**Core, Distribution, and Access**) to provide modularity, scalability, and fault isolation.

* **Access Layer:** Responsible for connecting end-user devices. I utilized **Cisco 2960 Series switches** and implemented **VLANs (Virtual Local Area Networks)** to logically segment traffic between different departments (e.g., Sales, IT, Operations). This segmentation is crucial for security and broadcast domain management.
* **Distribution Layer:** Aggregates traffic from the access layer and handles policy-based connectivity. **Cisco 3560 Series multilayer switches** were implemented here to perform **Inter-VLAN Routing**.
* **Core Layer:** The high-speed backbone of the network. It is responsible for fast and reliable transport between distribution layer switches. **Redundant fiber-optic links** were used to connect the core and distribution layers, ensuring high throughput and availability.

**2. Routing and Redundancy:**
To ensure dynamic, efficient routing and network resilience, I configured the following:

* **OSPF (Open Shortest Path First):** This link-state routing protocol was chosen for its fast convergence and scalability. I configured OSPF across all routers and multilayer switches, allowing the network to dynamically learn routes and automatically re-route traffic in the event of a link failure.
* **HSRP (Hot Standby Router Protocol):** To provide first-hop redundancy for end-user devices, HSRP was implemented. This creates a virtual gateway, ensuring that client traffic can always find a path out of the local network even if a primary router fails.

**3. Security Implementation:**
A defense-in-depth security strategy was a critical component of this project.

* **Access Control Lists (ACLs):** I authored and applied both **standard and extended ACLs** to filter traffic and enforce security policies. These ACLs were used to restrict inter-VLAN communication, secure access to sensitive servers, and block unauthorized protocols.
* **Port Security:** On the access layer switches, port security was configured to limit port access to specific MAC addresses, mitigating unauthorized device connection and MAC spoofing attacks.
* **SSH (Secure Shell):** All network devices (routers and switches) were configured to use SSH for encrypted remote management, while the less secure Telnet protocol was disabled.
* **VPN (Virtual Private Network):** An **IPsec VPN tunnel** was configured between the main office and a remote site, providing a secure and encrypted connection for data traversing the public internet.

### **Challenges and Solutions**

Several technical challenges were encountered and successfully overcome during this project:

* **Challenge:** Correctly configuring Inter-VLAN routing without creating network loops or misconfigurations.
    * **Solution:** I meticulously planned the IP addressing scheme (using RFC1918 private addresses) and VLAN assignments. By carefully configuring the "router-on-a-stick" and multilayer switching functionalities, I ensured that all VLANs could communicate as intended while remaining logically separate.
* **Challenge:** Implementing granular security policies with ACLs without inadvertently blocking legitimate business-critical traffic.
    * **Solution:** I developed a detailed ACL plan before implementation. By using a "least privilege" approach and leveraging extended ACLs, I was able to create specific rules that targeted traffic based on source, destination, protocol, and port. Each ACL was tested incrementally in the simulation to validate its function and prevent unintended consequences.
* **Challenge:** Ensuring seamless and predictable failover for redundant links and gateways.
    * **Solution:** This was addressed by carefully configuring HSRP with appropriate priority settings and by fine-tuning OSPF cost metrics to influence path selection. Extensive testing was performed by manually shutting down interfaces in Packet Tracer to verify that traffic automatically and immediately re-routed as designed.

### **Showcase of Proficiencies**

This capstone project demonstrates my hands-on proficiency in the following key areas of network engineering:

* **Network Design & Architecture:** Ability to design a scalable and resilient hierarchical network for an enterprise environment.
* **Advanced Routing & Switching:** In-depth, hands-on knowledge of configuring Cisco IOS devices, including VLANs, Trunks, EtherChannel, and Inter-VLAN routing.
* **Dynamic Routing Protocols:** Expertise in the implementation, verification, and troubleshooting of OSPF.
* **Network Security Hardening:** Skilled in implementing a layered security model using ACLs, Port Security, and secure remote management with SSH.
* **WAN Technologies:** Proficient in configuring site-to-site IPsec VPNs to enable secure enterprise connectivity.
* **Redundancy & High Availability:** Demonstrated ability to implement gateway and link redundancy using HSRP and redundant trunking to guarantee maximum network uptime.
* **Network Simulation & Troubleshooting:** Proficient in using **Cisco Packet Tracer** to build, configure, and validate complex network topologies, using tools like `ping`, `traceroute`, and various `show` commands to verify functionality.
