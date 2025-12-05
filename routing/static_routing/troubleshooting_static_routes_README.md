Troubleshooting Static Routing Lab
This Packet Tracer lab focuses on identifying and correcting configuration errors that prevented end-to-end connectivity between PC1 and PC2. 
Three separate issues were found across three routers.

Summary of Issues and Fixes

1. R1: Incorrect Next-Hop Address
R1 had a static route with the wrong next-hop IP address.
The route was updated to point to the correct next-hop.


2. R2: Incorrect Exit Interface
R2 had a static route configured with an incorrect exit interface.
The route was corrected to use the proper outgoing interface.


3. R3: Incorrect IP Address on an Interface
One of R3’s interfaces had the wrong IP address assigned.
The interface IP was corrected


Verification Steps
After applying the fixes:
show ip route confirmed the routing tables were correct.
show ip interface brief verified proper IP assignments.
A successful ping from PC1 to PC3 confirmed full connectivity.


Skills Demonstrated
Static route troubleshooting
Route table analysis
IP addressing correction

