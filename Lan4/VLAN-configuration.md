# Conviguring a VLAN from given topology

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
 __$int range f01 -2__ <br>
 __$switchport mode access__ <br>
 __$witchport access VLAN 1__ <br> <br>

now SW2 : <br>
__>en__ <br>
__#conf t__ <br>
__$int range f0/3 -4__ <br>
__$switchport mode access__ <br>
__$switchport access VLAN 2__ <br>
