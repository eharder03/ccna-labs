Troubleshooting Static Routing Lab
This Packet Tracer lab focuses on identifying and correcting configuration errors that prevented end-to-end connectivity between PC1 and PC2. 
Three separate issues were found across three routers.

Summary of Issues and Fixes

R1: Incorrect Next-Hop Address
R1 had a static route to 192.168.3.0 0/24 with next-hop 192.168.12.3 which is incorrect.
The configuration was deleted using no command, then the static route was updated to 192.168.3.0 255.255.255.0  192.168.12.2. 


R2: Incorrect Exit Interface
R2 had a static route configured 192.168.3.0 0/24 with exit-interface set to g0/0, which is incorrect.
Incorrect configuration was deleted and updated to correct static route 192.168.3.0 255.255.255.0 g0/0 


R3: Incorrect IP Address on an Interface
R3 g0/0 interface was configured with ip address 192.168.23.3, which is incorrect. 
Interface g0/0 was updated with ip address 192.168.13.3 255.255.255.0


Verification Steps
After applying the fixes:
show ip route confirmed the routing tables were correct.
show ip interface brief verified proper IP assignments.
A successful ping from PC1 to PC3 confirmed full connectivity.


