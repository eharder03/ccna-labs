

# Instructions  
1. Configure the correct IP address/subnet mask on each PC.  
   Set the gateway address as the LAST USABLE address of the subnet.

2. Make three connections between R1 and SW1.  
   Configure one interface on R1 for each VLAN.  
   Make sure the IP addresses are the gateway address you configured on the PCs.

3. Configure SW1's interfaces in the proper VLANs.  
   Remember the interfaces that connect to R1!  
   Name the VLANs  
   (Engineering, HR, Sales)

4. Ping between the PCs to check connectivity.  
   Send a broadcast ping from a PC (ping the subnet broadcast address),  
   and see which PCs devices receive the broadcast  
   (use Packet Tracer's "Simulation Mode")

# Lab Steps  
## 1. First, configure the default gateway, IP address, and subnet mask on each PC.  
   ### a. PC1  
      i. Gateway: 10.0.0.62  
      ii. IP Address: 10.0.0.1  
      iii. Subnet Mask: 255.255.255.192  

  ### b. PC2  
      i. Gateway: 10.0.0.62  
      ii. IP Address: 10.0.0.2  
      iii. Subnet Mask: 255.255.255.192  

 ###  c. PC3  
      i. Gateway: 10.0.0.126  
      ii. IP Address: 10.0.0.65  
      iii. Subnet Mask: 255.255.255.192  

  ### d. PC4  
      i. Gateway: 10.0.0.126  
      ii. IP Address: 10.0.0.66  
      iii. Subnet Mask: 255.255.255.192  

  ### e. PC5  
      i. Gateway: 10.0.0.190  
      ii. IP Address: 10.0.0.129  
      iii. Subnet Mask: 255.255.255.192  

  ### f. PC6  
      i. Gateway: 10.0.0.190  
      ii. IP Address: 10.0.0.130  
      iii. Subnet Mask: 255.255.255.192  

## 2. To make the connections between R1 and SW1, use a straight-through cable.  
   a. SW1 G0/1 to R1 G0/0  
   b. SW1 G1/1 to R1 G0/1  
   c. SW1 G2/1 to R1 G0/2  

## 3. Configure R1 interfaces and enable  
   a. G0/0: ip address 10.0.0.62 255.255.255.192 no shutdown  
   b. G0/1: ip address 10.0.0.126 255.255.255.192 no shutdown  
   c. G0/2: ip address 10.0.0.190 255.255.255.192 no shutdown  
   d. Do `show ip interface brief` to double check configurations.  

## 4. Configure SW1 interfaces  
  ### a. Int range g0/1, f3/1, f4/1 to configure multiple interfaces at once  
      i. switchport access vlan 10 to create and assign interfaces to VLAN 10  

  ### b. Int range g1/1, f5/1, f6/1  
      i. switchport access vlan 20 to create and assign these interfaces to VLAN 20  

###   c. Int range g2/1, f7/1, f8/1  
      i. switchport access vlan 30 to create and assign to VLAN 30  

 ###  d. Do show vlan brief to double check configurations  

## 5. Rename VLANs to corresponding departments  
###   a. VLAN 10  
      i. Name ENGINEERING  

###   b. VLAN 20  
      i. Name HR  

###   c. VLAN 30  
      i. Name SALES  

## 6. Check connectivity by pinging from PC1  
   a. Ping PC3 — successful  
   b. Ping PC5 — successful  

