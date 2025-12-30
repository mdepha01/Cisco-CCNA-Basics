# Conviguring a VLAN from given topology
## > = user exec , # = privileged mode , $ = global config mode , ($-int) = interface level
## Questions 

### Refer to the topology Lab4.png and Lab4.pkt
1. Replicate the topology on your own.
2. Ping All other PCs from another PC to confirm conncetion.
3. Assign PC 1 and PC3 to VLAN1 , PC2 and PC 4 to VLAN2.
4. Try to ping PC3 from PC1, and then try pinging PC2 and PC4 from PC1 vire versa.
5. Why Ping from PC1 to PC3 worked but Ping from PC1 to PC2 and PC4 did not work ?
6. Configure the connetsion from SW1 to SW2 as a trunk connection.
7. Try Step 4 , which PCs were able to ping each other and which ones did not succeed?

## Solutions

2. The results of ping can be seen on Lab4-ping.png : <br>
3. Assigning PC1 and PC3 on VLAN1 and PC2 and PC4 to VLAN 2 : <br>
- We configure VLAN 1 on SW1 and VLAN2 on SW2 : <br>
 __>en__ <br>
 __#conf t__ <br>
 __$int range f0/1__ <br>
 __($-int)switchport mode access__ <br>
 __$witchport access vlan1__ <br>
 __$int f0/2__ <br>
 __($-int) swi mode acc__ <br>
 __($-int) switchport access vlan 2__ <br>

- now SW2 : <br>
__>en__ <br>
__#conf t__ <br>
__$int f0/3__ <br>
__($-int)switchport mode access__ <br>
__$switchport access vlan 1__ <br>
__$int f0/4 __ <br>
__($-int) switchport mode acc__ <br> 
__($-int) switchport access vlan 2__ <br>

### running the show vlan brief : shows if all vlans have been configured correctly

