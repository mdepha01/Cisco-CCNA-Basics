# Questions 

1. Connect the router together using their GigabitEthernet0/0 interfaces.
2. Give the routers host names R1 and R2.
3. Enable a password on each router "PASSWORD".
4. Enable secret on both routers called "SECRET".
5. Exit to exec mode , Was "PASSWORD" or "SECRET" used to login back to the privileged exec mode?
6. Show the runnin-config file, which was encrypted by default bewtween password and secret?
7. Enable password encryption and view the running configuration file again, what changed?
8. Save the settings to memory after finishing.

# Solutions 
## All the commands were used on both routers
## NB: $ is used to represent Global EXEC mode , # is used privileged EXEC mode , > used for user EXEC mode , negate those symbols when writing the commands!!!

1. The results are shown in Lab2.png file and Lab2.pkt. <br>
2. Configuring hostnames on both routers: <br>
  __$hostname R1__ on first router <br>
  __$hostname R2__ on the second router <br>

3. Configuring passwords on both routers: <br>
 __Senable password PASSWORD__ on R1 and R2 routers.<br>

4. Configuring secret on both routers R1 and R2 : <br>
   __$enable secret SECRET__ <br>

5. Exiting to exec mode on R1 and R2: <br>
 __$exit__ <bR>
 "SECRET" was used to log back to the privileged exec mode, __enable secret__ is chosen over __enable password__ whwn both methods are configured because secret is nore secured.

6. Show running config files : <br>
   __#show running-config__  <br>
   The results are shown on running-config.png. By default __enable secret__ password is encrypted whilst __enable password __ is not encrypted by default but saved in plain text.

7. Enabling password encryption on both routers Ra and R2: <br>
 __$service password-encryption__ <br>
 Both passwords should be encrypted with MD7 for enable password "PASSWORD" and MD5 encryption for enable secret "SECRET". <bR>

 8. Saving to Memory on both Ra and R2 :
    __$do write memory__
