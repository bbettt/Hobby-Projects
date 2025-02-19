# Home Lab Setup: Advanced Network Segmentation & Security Monitoring

## Overview
I designed and implemented a home lab environment to simulate a realistic enterprise network. This project demonstrates my hands-on skills in network configuration, segmentation, and security monitoring. The lab is built to incorporating multiple security layers, threat detection, and proactive monitoring.

## Infrastructure & Technologies Used
- **Next Generation Firewall:**
  - **Device:** Unifi Dream Machine Pro  
  - **Role:** Deployed at the network edge to manage and filter all incoming and outgoing traffic and setup all East-West traffic flow.

- **Network Segmentation:**
  - Configured **three distinct networks** (`Safe`, `Unsafe`, and `Guest`) using **VLAN tagging and network segmentation** to segregate traffic.
  - **Wi-Fi Access:** Provided via **Unifi AP Pro** for each network segment.
  - **Device Isolation:** Enabled on select segments to ensure secure communication and prevent lateral movement.

- **Advanced Security Controls:**
  - **Intrusion Prevention System (IPS):** Implemented advanced IPS capabilities to monitor and block suspicious activities.
  - **Custom Firewall Rules:** Configured specific rules to manage and restrict internal communication between segments.

- **DNS Security:**
  - **Tool:** PiHole  
  - **Role:** Configured as the primary **DNS server** to filter out unwanted domains and block ads/malicious sites across the network.

- **Honeypots Deployment:**
  - Deployed **honeypots** on each network segment to simulate vulnerable targets, capturing potential attack vectors for analysis.

- **Traffic Capture & Analysis:**
  - Utilized **tcpdump** on the **Dream Machine Pro** to capture full network traffic.
  - Conducted in-depth **threat hunting exercises** by analyzing these captures with **Wireshark**.
  - **Remote Monitoring:** Setup Wazuh to monitor the Dream Machine Pro.

## Skills Demonstrated
- **Network Configuration & Segmentation:**  
  - Designed and implemented a **multi-VLAN environment**, ensuring robust isolation and secure segmentation of traffic.
  
- **Security Tool Deployment:**  
  - Installed and configured key security solutions (**Unifi Dream Machine Pro, PiHole, and honeypots**) to enhance overall network security.

- **Threat Hunting & Incident Response:**  
  - Captured and analyzed network traffic to **identify anomalies and potential threats**, using tools like **tcpdump**, **Wireshark** and **Wazuh**.

- **Advanced Security Measures:**  
  - Developed **custom firewall rules** and enabled **advanced IPS functionalities** to monitor and control internal communications effectively.

- **System Monitoring & Analysis:**  
  - Leveraged detailed **network logs** and **honeypot data** to continuously refine security measures and ensure proactive threat detection.

## Project Impact
This home lab setup not only reflects my technical abilities but also illustrates my commitment to **creating secure environments, simulating real-world scenarios for better threat analysis, and continuously improving network defenses**. The detailed documentation—including configuration scripts, firewall rules, and threat hunting analysis—is available in this repository to showcase my **practical experience and problem-solving approach**.
