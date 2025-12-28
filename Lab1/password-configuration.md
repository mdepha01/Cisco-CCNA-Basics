# Questions 

1. Use 2 : 1941 routers.
2. give both routers hostnames (R1 and R2).
3. Enable password "ciscoccna" on both routers.
4. View the running configuration file. Are the passwords encrypted?
5. Enable password encryption Encrypt both passwords.
6. View the running configuration file agan. are the passwords encrypted?
7. Save configurations to memory.

# Solutions:
1. Lab1.png shows the topology of the routers.

2. configuting hostnames: <br>
   __>enable__ <br>
   __#confifure terminal__ <br>
   __$hostname R1__ <br>

3. Enabling Password on both routers:
   __$enable password ciscoccna__ 

4. viewning the consiguration file: <br>
   __#show running-config__ <br>
  Unencrypted.png shows the results. <br>
  The passwords are not encrypted after being configured they are saved as plain text.

5. encrypting the passwords: <br>
   __$service password-encryption__ <br>
 The passwords are now encrypted, the future passwords will be encrypted also not saved as plain text. <br>
 Results are shown in Finalresults.png

6. saving configurations to memory: <br>
   __#write memory__ <br>
   __#write__ , can also be used to save changes. <br>
   __#copy running-config startup-config__
