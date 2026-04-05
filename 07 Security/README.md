# Security Configuration (NSG & Access Control)

##  Objective
To implement basic security controls in Azure to protect virtual machines, limit exposure, and allow only required traffic.

---

##  Network Security Group (NSG)

- Used Azure Network Security Group (NSG) to control inbound and outbound traffic
- Applied rules at VM/NIC level

---

##  Inbound Security Rules

Configured only required ports:

- **3389 (RDP)** → Remote administration
- **80 (HTTP)** → Web server access
- **443 (HTTPS)** → Secure web access

---

##  Security Approach

- Allowed only necessary ports
- Blocked all other inbound traffic by default
- Followed principle of least privilege

---

##  Access Flow

User → Public IP → NSG Rules → Virtual Machine → Service (RDP / IIS)

---

##  RDP Security

- Used RDP only for administrative access
- Avoided unnecessary exposure of port 3389
- Recommended restricting access to specific IPs (for production)

---

##  Web Server Security

- Enabled HTTPS (SSL) for secure communication
- Avoided using HTTP in production environments
- Ensured secure data transmission

---

##  Key Learnings

- Importance of controlling inbound traffic in cloud environments
- Role of NSG in Azure security
- Difference between open ports and secured access
- Basic server hardening practices

---

##  Future Improvements

- Restrict RDP access using IP whitelisting
- Use Azure Bastion instead of exposing RDP
- Implement Web Application Firewall (WAF)
- Enable Azure Defender / Security Center
- Use private endpoints instead of public IP

---

## 📸 Screenshots

(Add screenshots of NSG rules and port configurations)
