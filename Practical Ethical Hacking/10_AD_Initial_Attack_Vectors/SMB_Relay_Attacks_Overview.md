# SMB Relay Attacks Overview

If hash cant b cracked, can use smb replay if it is enabled or target machine to gain access

![Screenshot](./assets/088_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-80ac-b9a7-cdb831eece17.png)

We can use nmap to check the SMB port. We are mainly looking for “ Message siging enabled but not required “ . This can be used as a proof of concept as well

![Screenshot](./assets/089_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-80ad-8f02-d98000b3125f.png)

Rember we had said everything below should be on, But for this attack we need the SMB and http to be off because we just dont need that to captured but we want to relay them 

![Screenshot](./assets/090_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-8059-bc63-eba5df82c008.png)

Run responder

![Screenshot](./assets/091_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-8085-89aa-e258f630823f.png)

Set up relay

![Screenshot](./assets/092_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-807d-a539-ca311490a53f.png)
When responder catches a hash it will forward that to this 

Make an event to occur

![Screenshot](./assets/093_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-803d-b92f-c21251de9ea7.png)


![Screenshot](./assets/094_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-8049-97ef-d7cf956c8fba.png)

Other alternative wins (pay attention to the commands )

We can add a -I to get an interactive shell

![Screenshot](./assets/095_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-80cb-9dbd-d19027e9bb93.png)


![Screenshot](./assets/096_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-80cc-aac1-d2002e933cf8.png)

The following whoami can be used as proof of concept

![Screenshot](./assets/097_SMB_Relay_Attacks_Overview_1c6d64c5-e0cb-800a-844d-c2ed6e0af801.png)



---
[Back to Attacking Active Directory: Initial Attack Vectors](./README.md)
