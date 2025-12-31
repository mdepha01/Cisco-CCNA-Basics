# Inter-VLAN Routing
## NB > = user exec mode, # privileged exec mode, $ Global exec mode , ($-int) = interface level
## Questions

1. Ping All PCs from ceach PC to see which PCs can communicate.
2. Move PC1 and PC3 to VLAN 10 , and PC2 and PC4 to VLAN 20.
3. Create a trunk port beteen SW1 and SW2.
4. configure Inter-VLAN routing by using R1's G0/0 sub interface. Use the address 10.0.0.1/25 for VLAN 10 and 10.0.0.129/25 for VLAN 20.
5. Test the connectivity between PCs

## Solutions:
1. Device and IP address : PC1 (10.0.0.5/25), PC2 (10.0.0.130/25), PC3 (10.0.0.15/25), PC4 (10.0.0.131/25) : <br>
- Ping results of PC1 are shown on Inter-VLAN-ping.png

2. Creating VLANS 10 and 20 : <br>
- VLAN 10 and VLAN 20 on SW1 : <br>
 __$int f0/1__ <br>
 __($-int) switchport mode access__ <br>
 __($-int) switchport access vlan 10__ <br>
 __$int f0/2__ <br>
 __($-int) switchport mode access__ <br>
 __($-int) switchport access vlan 20__ <br>
 - VLAN 10 and VLAN 20 configuration on SW2 : <br>
 __$int f0/3__ <br>
 __($-int) sw mode access__ <br>
 __($-int) sw access vlan 10__ <br>
 __$int f0/4__ <br>
 __($-int) sw mode acc__ <br>
 __($-int) sw acc vlan 20__ <br>

3. Configuring trunk port between the SW1 and SW2 : <br>
- SW1  : <br>
__$int g0/1__
__($-int) switchport mode trunk__ <br>
__($-int) switchport trunk allowed vlan add 10, 20 <br>
- SW2  : <br>
__$int g0/1__
__($-int) switchport mode trunk__ <br>
__($-int) switchport trunk allowed vlan add 10, 20__

4. Inter-VLAN configuration on R1 : <br>
__$int g0/0.10__ <br>
__($-int) encapsulation dot1q 10__ <br>
__($-int) ip address 10.0.0.1 255.255.255.128__ <br>
__($-int) int g0/0.20__ <br>
__($-int) encap dot 20__ <br>
__($-int) ip add 10.0.0.129 255.255.255.128__ <br>

5. Testing Connection , results are on intervlan-ping-results.png
   
## In order for R1 to route traffic , we need to create a trunk betweem SW1 and R1 (Run command on SW1):
__$int g0/0__ <br>
__($-int) sw mode tr__ <br>
