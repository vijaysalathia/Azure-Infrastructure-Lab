
# Azure Point-to-Site VPN Setup

This project documents the setup of a **Point-to-Site (P2S) VPN** in Microsoft Azure using **certificate-based authentication**.

---

##  Overview

A secure VPN connection was configured to allow remote access to Azure Virtual Network resources using a client machine.

---

##  Architecture

- Azure Virtual Network (VNet)
- VPN Gateway deployed in GatewaySubnet
- Point-to-Site VPN configuration enabled
- Client connects securely using certificates

---

##  Authentication Method

- Type: **Certificate-based authentication**
- Root Certificate created and uploaded to Azure
- Client Certificate generated from Root Certificate

---

##  Important Certificate Note

When adding the Root Certificate in Azure:

 DO NOT include:
-----BEGIN CERTIFICATE-----
-----END CERTIFICATE-----

✔ Only copy the **Base64 encoded content between these lines**

###  Correct Format Sample

MIIC6TCCAdGgAwIBAgIQLzGdVLDidbpP1HtCEYVt5jANBgkqhkiG9w0BAQsFADAX
MRUwEwYDVQQDDAxBenVyZVZQTlJvb3QwHhcNMjYwNDA1MTEwNzU4WhcNMzYwNDA1
...
9PvD7bIgJlwJUlRfCBzQwoTVHgfqWdFxzaAyne0=

If this is not followed, Azure may throw errors like:
- Error 13801
- Error 798

--- As i spent full day to resolve the issue.

##  Steps Followed

1. Created Root Certificate using PowerShell  
2. Generated Client Certificate from Root Certificate  
3. Exported Root Certificate (public key)  
4. Uploaded Root Certificate to Azure VPN Gateway  
5. Configured Point-to-Site VPN  
6. Downloaded VPN client package from Azure  
7. Extracted .rar file  
8. Imported VPN profile using .xml file  
9. Connected successfully using VPN client  

---In my case I am using 2 different Vnets and if ping to server does not work then create inbound rule for ICMPv4 allow and create Vnet peering between 2 Vnets

##  VPN Client Setup

- Downloaded VPN client from Azure portal  
- Extracted .rar file  
- Imported .xml configuration file  
- VPN connection established  

---

##  Connection Result

✔ VPN connection established successfully  
✔ Secure access to Azure VNet resources  
✔ Certificate authentication working properly  

---

##  Key Learnings

- Certificate-based authentication in Azure VPN  
- Importance of correct certificate format  
- Secure remote access using P2S VPN  
- Azure VPN Gateway configuration  

---

##  Future Improvements

- Add Azure Active Directory authentication  
- Implement Multi-Factor Authentication  
- Configure Always-On VPN  
- Automate using scripts  

---

##  Notes

- Always ensure certificate data is correctly formatted  
- Do not modify the .xml VPN profile manually  
- Use Azure VPN Client for connection  
