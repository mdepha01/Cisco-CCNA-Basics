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
   **>enable ** <br>
   **#confifure terminal ** <br>
   **$hostname R1 ** <br>

3. Enabling Password on both routers:
   **$enable password ciscoccna ** <br>

4. viewning the consiguration file:
   **#show running-config. ** <br>
  Unencrypted.png shows the results.
  The passwords are not encrypted after being configured they are saved as plain text.

5. encrypting the passwords:
   **$service password-encryption ** <br>
 The passwords are now encrypted, the future passwords will be encrypted also not saved as plain text.
 Results are shown in Finalresults.png

6. saving configurations to memory:
   **#write memory ** <br>
   **#write ** , can also be used to save changes. <br>
   **#copy running-config startup-config **
