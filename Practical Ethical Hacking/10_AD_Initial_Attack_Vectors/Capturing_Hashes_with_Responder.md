# Capturing Hashes with Responder


Best time to run responder is early in the morning before everyone logs in
Responder needs to be ran with sudo or as root


```bash
sudo responder -I eth0 -dwPv
```

-I is probably for ip address

![Screenshot](./assets/079_Capturing_Hashes_with_Responder_1c5d64c5-e0cb-8073-942e-f6dc6dbc036f.png)

![Screenshot](./assets/080_Capturing_Hashes_with_Responder_1c5d64c5-e0cb-808d-bfe5-f71b835adcc4.png)

![Screenshot](./assets/081_Capturing_Hashes_with_Responder_1c5d64c5-e0cb-8033-8cfe-c77de6ae9bcc.png)
-v for increased verbosity

After running, always make sure to check if your ip matches and is correct

![Screenshot](./assets/082_Capturing_Hashes_with_Responder_1c5d64c5-e0cb-8012-bf1d-da66eda92b0e.png)

Make sure that all of the following are on

![Screenshot](./assets/083_Capturing_Hashes_with_Responder_1c5d64c5-e0cb-804c-877c-d1c497885156.png)

Tried to gain access to the attacker ip simply to generate traffic 

got the ntlm hash

![Screenshot](./assets/084_Capturing_Hashes_with_Responder_1c5d64c5-e0cb-80c5-b002-e20a85f23f42.png)



---
[Back to Attacking Active Directory: Initial Attack Vectors](./README.md)
