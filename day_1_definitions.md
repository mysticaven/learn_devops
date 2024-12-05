Here’s the formatted version for a GitHub file:

```markdown
# AWS Networking and Compute Basics

## 1. Subnet
A **subnet** is a range of IP addresses within a Virtual Private Cloud (VPC). Subnets divide a VPC into smaller segments and are associated with specific availability zones (data centers within an AWS region).

- **Public Subnet**: Has a route to an Internet Gateway, allowing resources to be accessed from the internet.
- **Private Subnet**: Lacks a direct route to the internet, isolating resources from public access.

Subnets help segregate resources to improve security and manageability.

---

## 2. VPC (Virtual Private Cloud)
A **VPC** is a logically isolated network within AWS. It allows you to launch resources (e.g., EC2 instances, RDS databases) in a customizable virtual network. 

Key Features:
- Define your own IP address range using CIDR.
- Create subnets.
- Configure route tables, gateways, and security rules.

It gives full control over the network environment, enabling secure and flexible architectures.

---

## 3. CIDR (Classless Inter-Domain Routing)
**CIDR** defines IP address ranges in a more efficient way than traditional classes. A CIDR block specifies an IP range using a combination of IP address and prefix length.

Example: `10.0.0.0/16`
- `10.0.0.0`: Base IP.
- `/16`: First 16 bits represent the network, the rest are for host addresses.

CIDR is used in VPCs to allocate private IP ranges.

---

## 4. IP Address
An **IP address** uniquely identifies a device on a network. AWS assigns:
- **Private IPs**: For communication within a VPC (not accessible from the internet).
- **Public IPs**: For resources needing internet access.
- **Elastic IPs (EIPs)**: Static public IPs that can be allocated to resources.

---

## 5. Route
A **route** is a rule that determines where network traffic is directed. For example:
- Traffic destined for `0.0.0.0/0` (all addresses) is routed to an Internet Gateway for public access.

Routes are defined in **route tables**.

---

## 6. Route Table
A **route table** contains rules (routes) that determine the traffic flow in a VPC.

Key Features:
- Each subnet must be associated with a route table.
- A default route table is created for a VPC.

Example Rules:
- Route traffic to local VPC subnets.
- Route internet traffic to an Internet Gateway.

---

## 7. Gateway
A **gateway** connects your VPC to other networks (e.g., the internet or on-premises).

Types:
- **Internet Gateway (IGW)**: Enables internet access for resources in public subnets.
- **NAT Gateway**: Allows private subnet resources to access the internet securely.
- **Virtual Private Gateway**: Connects a VPC to on-premises networks via VPN.

---

## 8. NAT (Network Address Translation)
A **NAT Gateway** or **NAT Instance** allows instances in private subnets to access the internet while blocking inbound traffic.

- **NAT Gateway**: Fully managed, scalable service.
- **NAT Instance**: A manually configured EC2 instance.

---

## 9. Security Group
A **security group** acts as a virtual firewall for AWS resources, controlling inbound and outbound traffic.

Key Features:
- **Stateful**: If traffic is allowed in, the response is automatically allowed out.
- Rules define protocols (e.g., HTTP, SSH), ports, and allowed IPs.

Example Rule:
- Allow inbound SSH traffic from `203.0.113.0/24`.

---

## 10. NACL (Network Access Control List)
A **Network Access Control List (NACL)** provides security at the subnet level.

Key Features:
- **Stateless**: Each direction (inbound/outbound) must be explicitly allowed.
- Rules are numbered and processed in order; the first match determines the action.

Example Rule:
- Block traffic from a malicious IP range.

---

## 11. Peering Connection
A **VPC peering connection** establishes a direct, private connection between two VPCs.

Key Features:
- Traffic stays within AWS’s private network.
- Useful for sharing resources across VPCs in the same or different accounts.

---

## 12. Transitive Peering
**Transitive peering** refers to routing traffic between two VPCs through a third, peered VPC.

AWS does not natively support transitive routing. Alternatives:
- **Transit Gateway**: A fully managed service to connect multiple VPCs and on-premises networks.
- Create separate peering connections for direct communication.

---

## Additional Key Concepts

### Elastic IP (EIP)
- A static, public IP address assigned to AWS resources.
- Allows consistent IP use even if the instance is stopped or restarted.

### Transit Gateway
- A centralized hub for connecting multiple VPCs, on-premises networks, and VPNs.
- Simplifies network management for large-scale architectures.

### VPN (Virtual Private Network)
- Connects your on-premises network securely to a VPC.

### Direct Connect
- Provides a dedicated physical connection from your on-premises network to AWS for consistent and high-speed data transfer.

---

## DHCP (Dynamic Host Configuration Protocol)
**DHCP** is a protocol that dynamically assigns IP addresses and other network configurations.

- AWS automatically provides DHCP services for resources in a VPC.
- **DHCP Options Set**: Specify the domain name and DNS servers for your VPC.

---

## DNS (Domain Name System)
**DNS** translates human-readable domain names (e.g., `example.com`) into IP addresses.

Key Features:
- Managed by **Amazon Route 53**.
- Internal DNS resolver available in every VPC.
- Public and private hosted zones for internet-facing or internal domains.

---

## DNS Gateway
A **DNS Gateway** refers to a DNS resolver that processes DNS queries.

- AWS provides a built-in DNS resolver (`169.254.169.253`) in each VPC.
- **Route 53 Resolver**: Enables DNS forwarding between on-premises networks and AWS.

---

## EC2 (Elastic Compute Cloud)
**EC2** provides resizable virtual servers (instances) in the cloud.

Key Features:
- **Instance Types**: Optimized for compute, memory, storage, or networking.
- **Auto Scaling**: Automatically adjusts the number of instances based on demand.
- **Elastic Load Balancing**: Distributes traffic across multiple instances.
- **AMI (Amazon Machine Images)**: Pre-configured templates for launching instances.

Networking:
- EC2 instances are launched in a VPC and assigned private/public IPs.
- Security Groups and NACLs control traffic.
- Elastic IPs provide persistent public IP addresses.

Storage:
- **EBS**: Persistent storage.
- **Instance Store**: Temporary storage tied to instance lifecycle.

---

## Summary
AWS integrates these networking and compute concepts seamlessly:
- **DHCP** dynamically assigns IPs in VPCs.
- **DNS** resolves domain names via Route 53 and VPC resolvers.
- **DNS Gateway** facilitates DNS query processing.
- **EC2** provides scalable compute resources relying on networking for efficient operation.
```

You can save this as a `.md` file on GitHub for easy readability and documentation. Let me know if you'd like further refinements!
