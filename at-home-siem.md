# Wazuh Deployment: Cloud-Based Security Monitoring with Linode

## Overview

This project demonstrates the deployment and configuration of **Wazuh**, an open-source security platform, on **Linode Cloud**. Wazuh provides advanced threat detection, compliance monitoring, and log analysis. The deployment also includes critical server hardening steps to enhance the overall security of the environment. This showcases my ability to secure cloud-based systems while implementing scalable security monitoring solutions.

---

## Project Highlights

### Purpose and Goals
- To deploy a scalable cloud-based **SIEM (Security Information and Event Management)** solution.  
- To enable real-time monitoring of system logs and detection of potential threats.  
- To demonstrate advanced server hardening practices, ensuring a secure deployment environment.

### Skills Demonstrated
- **Cloud Computing:** Set up and managed Linode cloud infrastructure.  
- **Server Hardening:** Secured the server with best practices for SSH, firewall configurations, and resource restrictions.  
- **SIEM Implementation:** Deployed and configured Wazuh for security monitoring.  
- **Incident Detection and Response:** Created alerts for suspicious activities and analyzed logs for potential incidents.  

### Technologies Used
- **Cloud Provider:** Linode (for virtual machine hosting).  
- **Operating System:** Ubuntu 22.04 LTS.  
- **SIEM Tool:** Wazuh.  
- **Additional Tools:** NGINX (for reverse proxy), Elasticsearch, Kibana, UFW (firewall).  

---

## Installation and Configuration Process

### 1. **Cloud Environment Setup**
   - Created a virtual machine on Linode with 2 vCPUs, 4GB of RAM, and 80GB SSD storage.  
   - Configured the VM with a static public IP and secure SSH access.

### 2. **Server Hardening and Security**
   a. **SSH Hardening**
   - Changed the default SSH port to a non-standard port to reduce brute-force attacks.  
   - Disabled root login via SSH for added security.  
   - Enabled **key-based authentication** to replace password-based authentication.  
   - Configured fail2ban to block IPs after multiple failed SSH login attempts.  

     Example SSH configuration (`/etc/ssh/sshd_config`):
     ```bash
     Port 2222
     PermitRootLogin no
     PasswordAuthentication no
     AllowUsers <my-username>
     ```

   b. **Firewall Configuration**
   - Used UFW (Uncomplicated Firewall) to allow only necessary services and block all others.  
   - Restricted SSH access to a specific IP or subnet (e.g., my home IP).  
   - Opened ports only for Wazuh and Elasticsearch services.

     Example UFW commands:
     ```bash
     sudo ufw default deny incoming
     sudo ufw default allow outgoing
     sudo ufw allow from <my-home-IP> to any port 2222 proto tcp
     sudo ufw allow 5601/tcp  # Kibana Dashboard
     sudo ufw allow 1514/udp  # Wazuh Agents
     sudo ufw enable
     ```

   c. **Additional Hardening**
   - Installed and configured **auditd** to monitor unauthorized system changes.  
   - Regularly updated all packages and dependencies with `unattended-upgrades`.  
   - Disabled unused services and ports to minimize the attack surface.

### 3. **Wazuh Server Installation**
   - Installed Wazuh Server using the official Wazuh installation script.  
   - Configured Elasticsearch and Kibana for log storage and visualization.  

   Installation steps:
   ```bash
   curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | sudo apt-key add -
   echo "deb https://packages.wazuh.com/4.x/apt/ stable main" | sudo tee /etc/apt/sources.list.d/wazuh.list
   sudo apt update && sudo apt install wazuh-manager wazuh-api
   ```

### 4. **Wazuh Agent Integration**
   - Deployed Wazuh Agents on various devices to forward logs to the server.  
   - Configured agent-server communication securely using TLS encryption.  

### 5. **Web Interface Setup**
   - Configured NGINX as a reverse proxy for secure and efficient access to the Wazuh dashboard.  
   - Set up SSL/TLS encryption using Let’s Encrypt for all web traffic.

### 6. **Testing and Validation**
   - Simulated potential attacks, such as failed login attempts and unauthorized file modifications, to validate alerting capabilities.  
   - Verified that all traffic to sensitive services was locked down to specific locations.

---

## Key Takeaways
- **Cloud Integration:** Successfully deployed a robust SIEM solution in a cloud environment.  
- **Server Security:** Applied best practices in server hardening to ensure the solution was protected against common threats.  
- **Monitoring and Response:** Learned how to analyze logs and respond to potential security incidents effectively.  
- **Scalability:** Configured the system to handle increased log ingestion while maintaining performance.  
