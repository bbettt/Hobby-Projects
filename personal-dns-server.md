# Pi-hole Project: Enhancing Network Security with DNS Filtering

## Overview

This project demonstrates my ability to implement and configure a network-wide ad-blocking and privacy-enhancing solution using Pi-hole. The Pi-hole acts as a Domain Name System (DNS) sinkhole, blocking advertisements, tracking domains, and potentially malicious traffic at the network level. This practical setup showcases my skills in networking, system administration, and security configurations.

---

## Project Highlights

### Purpose and Goals
- To enhance privacy by blocking tracking domains across the network.
- To improve device performance by reducing unnecessary ad traffic.
- To secure the network by filtering DNS queries and blocking known malicious domains.

### Skills Demonstrated
- **Network Configuration:** Set up and configured DNS services to route traffic through Pi-hole.
- **System Administration:** Installed and managed the Pi-hole on a Raspberry Pi running Linux.
- **Troubleshooting:** Resolved connectivity issues and fine-tuned the DNS blocklists to prevent over-blocking.
- **Monitoring and Reporting:** Utilized the Pi-hole dashboard to analyze blocked queries and optimize network performance.

### Technologies Used
- **Hardware:** Raspberry Zero W.
- **Software:** Raspbian OS, Pi-hole software.
- **Networking Tools:** DHCP server, DNS resolver.

---

## Installation and Configuration Process

1. **Environment Preparation**  
   - Set up a Raspberry Pi with Raspbian OS.
   - Configured the Raspberry Pi to have a static IP address for reliable DNS resolution.

2. **Pi-hole Installation**  
   - Installed Pi-hole via the command line using the official script.  
     ```
     curl -sSL https://install.pi-hole.net | bash
     ```

3. **Integration with Network**  
   - Configured the router to use the Pi-hole as the primary DNS server.  
   - Verified that all network devices were routing DNS traffic through Pi-hole.

4. **Customization and Optimization**  
   - Imported custom blocklists to filter ads and tracking domains effectively.  
   - Adjusted settings to whitelist specific domains to prevent service interruptions.  
   - Enabled logging and monitoring to analyze traffic patterns.

5. **Testing and Validation**  
   - Conducted tests to confirm ad-blocking effectiveness on multiple devices (e.g., smartphones, laptops).  
   - Verified that legitimate traffic was unaffected by the DNS filtering.

---

## Key Takeaways
- Gained hands-on experience in managing a real-world network security solution.
- Learned the importance of balancing privacy, security, and usability when implementing blocklists.
- Demonstrated adaptability by troubleshooting and fine-tuning settings to meet network requirements.



