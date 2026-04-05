# Azure Networking (VNet & Subnet Configuration)

##  Objective
To design and configure Azure Virtual Network (VNet) and subnets to support secure communication between resources and enable hybrid connectivity.

---

##  Virtual Network (VNet) Setup

- Created a Virtual Network in Azure
- Defined address space:10.1.0.0/16

  - Selected appropriate region matching the Virtual Machine

---

##  Subnet Configuration

### Default Subnet (for Virtual Machines)
- Subnet name: `default`
- Address range:10.1.0.0/24

- Used for hosting Virtual Machines (Domain Controller)

---

### Gateway Subnet (for VPN Gateway)
- Subnet name: `GatewaySubnet`
- Address range:10.1.255.0/27

- - Dedicated subnet required for VPN Gateway deployment

---

##  IP Address Planning

- Used structured IP addressing within VNet
- Ensured no overlapping subnets
- Separated workloads:
- VM subnet
- Gateway subnet

---

##  Network Security Considerations

- Allowed RDP (3389) for remote access
- Restricted unnecessary inbound traffic
- Used Azure default security configurations

---

##  Connectivity Flow

- Virtual Machines communicate within VNet
- VPN Gateway connects external client (laptop) to Azure network
- Domain services rely on internal network communication

---

##  Key Learnings

- Importance of proper network design before deployment
- Role of subnets in resource isolation
- Azure networking basics for real-world infrastructure
- Foundation for VPN and hybrid connectivity

---

##  Screenshots

(Add screenshots of VNet creation, subnet configuration, and IP planning)
