Networking Project 


Arranging 5 routers(N.B each router forms a network) in the form of a Star topology, where the middle router is the 5th router, the upper right is the 1st, the upper Left is the 2nd, the lower left is the 3rd and the lower right is the 4th.

1. In the 1st network Configure a suitable subnet that'll only serve IP addresses to just 20 users and nothing more.

2. In the 4th network Configure a suitable subnet that'll only serve IP addresses to just 50 users and nothing more.

3. In the 3rd network, configure DHCP and DNS on the router, such that it dishes out only class B IP addresses to users.(N.B: the IP to be dished out shouldn't exceed the particular octet you are taking IP from. i.e., in 255.255.0.0, the 1st and 2nd octet is occupied, only the 3rd and 4th is remaining. So it's either your taking using the 3rd octet or the 4th octet).

4. Interconnect all the networks such that they'll be able to communicate perfectly with each other without any barriers(IP route).

5. For the 2nd network, create a network including a web server, a switch and some numbers of PC's.

6. On any of the networks, be able to reach the server on the 2nd network via URL.


----------------------DOCUNMETATION------------------------------


**Title: Network Configuration Documentation (Using IP Address: 100.200.100.0)

**1. Network Overview

- This network uses the base IP address: 100.200.100.0/24
- Subnet mask: 255.255.255.0
- Gateway/Router IP: 100.200.100.1
- Total PCs configured: 50

**2. Device Roles**

- **Router: Core of the network, connects different subnets.
- **Switches: Distribute network to multiple PCs.
- **PCs: Clients assigned static or dynamic IPs.
- **Server: Static IP, hosts services like DHCP, DNS, or Web.

**3. IP Addressing Plan

- **Router Interface (LAN side): 100.200.100.1
- **PCs (Static): 100.200.100.2 - 100.200.100.51
- **Server: 100.200.100.2

**4. Basic Configuration Commands**

**Router Configuration:**


enable
configure terminal
interface gig0/0
ip address 100.200.100.1 255.255.255.0
no shutdown
exit

**Assigning IP to PCs (Static Method):**

- Open each PC
- Go to Desktop > IP Configuration
- Assign IP manually:
  - IP Address: 100.200.100.5 
  - Subnet Mask: 255.255.255.0
  - Default Gateway: 100.200.100.1

**5. Static Route Example (if connecting multiple routers):


ip route [Destination Network] [Subnet Mask] [Next Hop IP Address]
Example:
ip route 192.168.1.0 255.255.255.0 100.200.100.2

**6. Server Configuration (e.g., Web or DHCP Server):

- Assign Static IP: 100.200.100.9
- Configure services based on project (HTTP, DHCP, etc.)

**7. Testing the Network**

- Use ping command from PC to router and server:

ping 100.200.100.1
ping 100.200.100.9


- Ensure replies are received.

**8. Save Configuration (On Routers/Switches):

write memory
or
copy running-config startup-config


DGL NETWORK

hostname boluwatifenet1
enable secret password: boluwatife11
enable password: boluwatife
enable password: boluwatife
GigabitEthernet0/0/0
IP Address: 100.200.100.1




HARDWARE NETWORK.

Server hostname boluwatifenet1server@
enable secret password: serverboluwatife11
enable password: boluwatife
enable password: boluwatife

IP Address: 100.200.200.0
Server ip address: 100.200.200.2
Server URL: bolu-server.
Gateway:100.200.200.1




MAIN-HUB NETWORK.

DHCP hostname boluwatifeDHCPNetwork4@
enable secret password: boluwatife11dhcp4
enable password: boluwatife
enable password: boluwatife
ip dhcp 
IP Address: 100.200.250.0



NID-2 NETWORK


Net3 hostname boluwatifenet1sNetwork3@
enable secret password: boluwatife11Network3
enable password: boluwatife
enable password: boluwatife
GigabitEthernet0/0/0
IP Address: 100.200.150.0




--CENTER ROUTER--

enable secret password: boluwatife11CenterRouter2 
enable password: boluwatife
enable password: boluwatife

IP Address: 200.200.200.0







**End of**
