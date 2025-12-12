Instructions:
Subnet the 192.168.5.0/24 network to provide sufficient addressing for each LAN.
(Also, the point-to-point connection between R1 and R2).

Assign the first usable address to the PC in each LAN.

Assign the last usable address to the router's interface in each LAN.

Configure static routes on each router so that all PCs can ping each other.

1.	Start by assigning the subnets in descending order, starting with the largest LAN, which is  LAN2, followed by LAN1, LAN3, LAN4, then the point-to-point connection between R1 and R2. Since each LAN has variable number of hosts, I will use VLSM, or variable length subnetting.
2.	LAN2- I will use a /25 prefix length to accommodate the 64 hosts.
a.	LAN2 Network Address: 192.168.5.0 /25
b.	LAN2 Broadcast Address: 192.168.5.127 /25 
c.	R1 g0/1 IP Address: 192.168.5.126 /25 (Last usable address, -1 from broadcast address)
d.	PC2 Gateway: 192.168.5.126
e.	PC2 IP Address: 192.168.5.1 Subnet Mask: 255.255.255.128
3.	LAN1- I will use a /26 subnet mask to accommodate the 45 hosts
a.	LAN1 Network Address: 192.168.5.128 /26 (+1 from LAN2 broadcast address)
b.	LAN1 Broadcast Address: 192.168.5.191 /26
c.	R1 g0/0: 192.168.5.190
d.	PC1 Gateway: 192.168.5.190
e.	PC1 IP Address: 192.168.5.129 
f.	PC 1 Subnet Mask: 255.255.255.192
4.	LAN3- Use /28 to accommodate the 14 hosts. In a real-life scenario, we would want room for growth, but for CCNA test purposes, I will use /28 in this problem.
a.	LAN3 Network Address: 192.168.5.192 /28
b.	LAN3 Broadcast Address: 192.168.5.207 /28
c.	R2 g0/0: 192.168.5.206 255.255.255.240
d.	PC3 Gateway: 192.168.5.206
e.	PC3 IP Address: 192.168.5.193 
f.	PC3 Subnet Mask: 255.255.255.240
5.	LAN4- Use /28 to accommodate the 9 hosts. 
a.	Network Address: 192.168.5.208 /28
b.	Broadcast Address 192.168.5.223
c.	R2 g0/1: 192.168.5.222 255.255.255.240
d.	PC4 Gateway: 192.168.5.222
e.	PC4 IP Address: 192.168.5.209
f.	PC4 Subnet Mask: 255.255.255.240
6.	Point-to-Point R1 to R2: Here we will use the /30
a.	Network Address: 192.168.5.224 /30 
b.	Broadcast Address: 192.168.5.227 /30
c.	R1 G0/0/0 IP Address: 192.168.5.225 255.255.255.252 (first usable address)
d.	R2 G0/0/0 IP Address: 192.168.5.226 255.255.255.252
7.	Configuring Static Routes
a.	R2 IP Route to LAN1:  192.168.5.128 255.255.255.192 192.168.5.225 (next hop)
b.	R2 IP Route to LAN2: 192.168.5.0 255.255.255.128 192.168.5.225 (next hop)
c.	R1 IP Route to LAN3: 192.168.5.192 255.255.255.240 192.168.5.226 (next hop)
d.	R1 IP Route to LAN4: 192.168.5.208 255.255.255.240 192.168.5.226 (next hop)
8.	Successful ping from PC1 to PC4
