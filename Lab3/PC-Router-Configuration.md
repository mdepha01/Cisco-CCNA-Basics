# Lab3 shows the basics of configuring a PC and a router together.
## Questions 
1. Connect PC1 port RS-232 to R1 console port.
2. Use Console connection and configure R1 from PC1.
3. Enable secret on R1 "SECRET".
4. Enable password "PASSWORD" on R1, make the password required to connect to R1 via console port. <br>
   - 4.1 Check the running configuration file. <br>
   - 4.2. was the Password encrypted?
5. Enable Password Encryption on R1. <br>
   - 5.1. Verify the encryption using the running config.
   - 5.2. save the configurations on memory.

## Solutions 

1. Connecting PC to R1 is shown on Lab3.png / Lab3.pkt <br>
2. Changing router hostname to R1: <br>
 __$hostname R1__ <br>
 3. Enabling secret on R1: <br>
  __$enable secret SECRET__ <br>
4. Setting a Console Password (this password is used to login to the privileged EXEC mode when using console) : <br>
 __$line console 0__ <br> 
 __($-int) password PASSWORD__ <br>
 __($-int) login__ , this command ensures that console password not secret is used when loging in via console
__($-int) exit__ , used to exit the console interface then back to Global config mode <br>

- 4.1. checking the running-config : <br>
  __$do show running-config__ <br>
- 4.2. The password is not encrypted by default.
 
 5. Enabling Password Encryption : <br>
 __$service password-encryption__ <br>

  - 5.1. showing the running configuration file:
    __#show run__ <br>
  - 5.2. Saving changes to memory: <br>
  __#write__
