# Web Server Deployment (IIS, HTTP & HTTPS)

##  Objective
To deploy a web server on a Windows Server Virtual Machine using IIS, enable HTTP and HTTPS access, and configure Azure networking for secure external connectivity.

---

##  Environment Details

- Platform: Microsoft Azure
- Server OS: Windows Server 2025
- Web Server: Internet Information Services (IIS)
- Access Method: Public IP (Browser)

---

##  IIS Installation

- Logged into Windows Server via RDP
- Opened Server Manager
- Added Role:
  - Web Server (IIS)
- Selected required features
- Completed installation successfully

---

##  Website Setup

- Navigated to IIS default directory:C:\inetpub\wwwroot

- - Created/modified default HTML file
- Added sample content to verify deployment

---

##  HTTP Configuration (Port 80)

- Default IIS site listens on port 80
- No additional configuration required

### Testing:
- Open browser
- Access: http://<Public-IP>

- Website loaded successfully

---

##  HTTPS Configuration (Port 443)

### Certificate Setup:
- Generated self-signed certificate (for lab/testing)
OR
- Imported SSL certificate

### IIS Binding:
- Opened IIS Manager
- Selected Default Website
- Clicked **Bindings**
- Added new binding:
- Type: HTTPS
- Port: 443
- SSL Certificate: Selected certificate

---

##  HTTPS Testing

- Open browser
- Access:https://<Public-IP>


- Verified:
- Secure connection established
- Browser shows HTTPS (may show warning for self-signed cert)

---

##  Azure Network Security Configuration

Configured inbound rules in Network Security Group (NSG):

### Allowed Ports:

- **80 (HTTP)** → Public web access  
- **443 (HTTPS)** → Secure web access  
- **3389 (RDP)** → Administrative access  

---

##  Connectivity Flow
User Browser → Public IP → NSG (80/443) → IIS Server → Website


---

##  Security Considerations

- Opened only required ports (80, 443, 3389)
- Used HTTPS for secure communication
- Avoided exposing unnecessary services
- Used self-signed certificate for testing (not production-ready)

---

##  Key Learnings

- IIS installation and configuration on Windows Server
- Hosting a website on Azure VM
- Difference between HTTP and HTTPS
- SSL certificate binding in IIS
- Azure NSG configuration for web traffic
- End-to-end web request flow

---

##  Future Improvements

- Use domain name instead of public IP
- Install trusted SSL certificate (e.g., Let's Encrypt)
- Configure DNS mapping
- Implement load balancing
- Harden server security

---

##  Screenshots

(Add screenshots of IIS installation, website access, HTTPS binding, and NSG rules)
