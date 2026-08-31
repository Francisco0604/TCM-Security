# Butler


![Screenshot](./assets/052_Butler_1c5d64c5-e0cb-8050-afec-e10b81aeba6b.png)

This machine will help us escalate privilages in windows

search for jenkins exploit (check if can exploit, lot of exploitations are there )
Check if default credentials works google for it
Can do brute force directory busting (won't work but good methodology to hav)

In vid - brute force login using brupsuit using cluster bomb (jenkins:jenkins)

Grovy exploit search on git n then copy paste on script console in jenkins 
Set up a listener using nc 
Download winpeas x64
to bring it to target machine

![Screenshot](./assets/053_Butler_1c5d64c5-e0cb-80ba-b3b5-f9b7c4615794.png)

Lot of interesting things will be found but use the following one

![Screenshot](./assets/054_Butler_1c5d64c5-e0cb-803d-93f0-fbc95f768b2e.png)
Since there are no quotes it won't take the direct path( basically it will check for .exe after every space detected)

Use msfvenom  to generate a payload

![Screenshot](./assets/055_Butler_1c5d64c5-e0cb-8023-9aae-d8aada79026f.png)
Use certutil to transfer it 
If you run it directly it's not use because you wil gain access as normal user not admin
To gain access for admin stop the server first and the restart

Use command 
sc stop 
sc start



---
[Back to New capstone](./README.md)
