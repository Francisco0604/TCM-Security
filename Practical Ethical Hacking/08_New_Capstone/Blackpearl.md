# Blackpearl

check the pg source code 
directory busting

![Screenshot](./assets/056_Blackpearl_1c5d64c5-e0cb-8049-9b89-db99e34bb73c.png)
use -d otherwise wont work


![Screenshot](./assets/057_Blackpearl_1c5d64c5-e0cb-80f2-a3a9-f4076f3d3a9f.png)
We do this to say that balckpeal allocates to that ip address then dns will do its magic

close and open the site on the browser again 

![Screenshot](./assets/058_Blackpearl_1c5d64c5-e0cb-80ad-9aa7-e544d11c46fb.png)

do directory busting again using ffuf but this time use the name of the website which you saved in etc hosts 

type navigate cms exploit on google
Trying metasploit in vid can do manual as well
use metaspolit and again shell on meterpreter
Hav to do privilage escalation now

We got the shell but we can now c username@machinename $ (shell)

![Screenshot](./assets/059_Blackpearl_1c5d64c5-e0cb-80d3-a7e4-e417629fe38e.png)
tty shell can be used 
can google that

![Screenshot](./assets/060_Blackpearl_1c5d64c5-e0cb-80d1-93e8-f102217d07c3.png)

use linpeas to check for privilage escalation

u will find something interesting in SUID 
use the gtfopen to find ways to escalate privilages



---
[Back to New capstone](./README.md)
