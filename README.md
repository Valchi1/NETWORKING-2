# NETWORKING-2

Task 1: Packet Tracer Initial Simulation



The first task is to build the network pictured below and ensure the services and features shown on the diagram are fully implemented and tested.  To help ensure that you have done everything that is expected of you in this task, please see the checklist below the diagram (downloadable PDF copy of assignment diagrams for you Download downloadable PDF copy of assignment diagrams for you).

diagram provided 

Configuration Checklist:

All IP addresses have a /24 mask unless otherwise marked on the diagram.
Make sure you choose router/layer 3 switch models which will support the number and type of ports as seen on the diagram.
Ensure that every area makes use of HSRP for router/layer 3 switch redundancy.
Ensure that EtherChannel is added to each LAN area and the ISP area where indicated.
Ensure that routers R1, R2 and R3 have suitable default routes added for communication with the ISP.
Ensure that all LAN areas are running EIGRP in AS 1 as a routing protocol and that default routes are correctly redistributed.
In LAN areas where there are VLANs deployed on switches (layer 2 or 3) then the port ranges are as follows:
VLAN 10: Ports 1 – 10
VLAN 20: Ports 11 – 20
VLAN 1: All remaining ports unless trunked or assigned to VLAN 10 or 20 as necessary (see diagram for clarification).
Layer 3 switches will require a VLAN trunking protocol to be set before ports can be made trunks – make sure these are set for 1q for this purpose.
On the ISP Layer 3 switches, those ports which are not taking part in the Etherchannel links should belong to VLAN 100 and should have IP addresses in that VLAN as indicated.
All the ISP routing devices should be running BGP with each device advertising all their directly connected networks and using the following BGP AS numbers:
ISP-R1: 65000
ISP-R2: 5001
ISP-R3: 4001
ISP-R4: 3001
ISP-S2: 5000
ISP-S3: 6000
ISP-S4: 4000
ISP-S5: 3000
ISP-S1 does need to be present but not configured.
The border router R1, R2 and R3 should provide one or more DHCP services for the PCs and wireless devices as needed, and requests should be relayed to these devices for the purpose.
Ensure that dynamic NAT with PAT is implemented on all the border routers R1, R2 and R3 – static NAT is not required for this task.
Test the network thoroughly before proceeding to Task 2.
LAN PCs and layer 3 devices should be able to ping right through to the ISP PC and server, and the s0/0/0 addresses on R1, R2 and R3.
LAN PCs should be able to access the web page stored on the ISP server.
LAN PCs and layer 3 devices should not be able to ping into other LAN areas at this stage.
Rubric


part 2

The second task is to link up the 3 LANs as a single EIGRP AS 1 network and then ensure that links are secure – see the diagram below – again, follow the details on the diagram and ensure your resulting network implements the requirements in the checklist below:



Configuration Checklist:

Change the serial connections over to use the PPP protocol instead of the default HDLC.
Add CHAP authentication to all serial links and use a different authentication key for each one – the choice of keys is yours.
Ensure that R1, R2 and R3 can ping each others s0/0/0
Create 2 GRE tunnels to link the three border routers (see diagram) and add them to EIGRP AS 1 to link the areas up.
Also ensure that you stop the redistribution of default routes in EIGRP to prevent “route flapping”
Once you are sure everything works, add 2 VPN tunnels to protect the GRE traffic. This may mean that internal devices lose contact with the ISP server and PC, this should not be seen as an error.  
VPNParams.png

By the end of this setup, all LAN devices in all 3 areas should be able to communicate with pings and should be able to access internal server web pages.  The ISP end devices should not be able to get any access.

