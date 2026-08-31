# Blind / Out-of-Band - Lab 2



![Screenshot](./assets/240_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-80ca-b1ab-e87946496cdb.png)
The Search is reflected back in the target
We do not get any more response from the web pg, the Website OK is a status 200


![Screenshot](./assets/241_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-80b4-b624-d64c747eaff1.png)
If we enter any bs then we get Website not found 


```bash
tcm-sec.com; whoami; asd
```
we get Website Found on this

![Screenshot](./assets/242_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-808f-8ac0-f9af4dfe3569.png)
If notice carefully can see that the ‘ ; ‘ is missing in the target even though we searched for it
so what is happening is it is filtering out the semi colons 

To get the proper response of this we will have to set up a webserver (can use netcat or webhooks.site, just do not use webhooks in an actual bug bounty or pentest because we do not wnt to leak data)

Then can try to insert a command with “backticks”

```bash
?'whoami'
```

Can use the following to make request to ourself
Goal of this was to check if can get another line of code execution with \n

![Screenshot](./assets/243_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-8068-80a2-f26b426dd0a7.png)
Set a python server

![Screenshot](./assets/244_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-8069-9e6d-fb22ba247186.png)
Since we know that the semi colon is getting filtered we will avoid using payloads with php

In this case we will try to upload a shell and trigger it

So ya, do this

![Screenshot](./assets/245_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-8019-af37-f7a200e07347.png)

then well, do this 

![Screenshot](./assets/246_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-80c5-a038-e7c4608b305c.png)

open the python webserver in tmp folder since the file is there

![Screenshot](./assets/247_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-804b-a362-dd8b2829c902.png)

Rename file (Not important but he normally uses this)

![Screenshot](./assets/248_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-8091-a649-ff3b937f3304.png)
Set up http server with pyhton in this

Then final step

![Screenshot](./assets/249_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-80b9-80a6-d5696a004f91.png)

This method which was shown above may not work anymore 

{ interrupt
New method

![Screenshot](./assets/250_Blind_Out-of-Band_-_Lab_2_1cdd64c5-e0cb-80e3-9617-f38dadfa24ad.png)
 interrupt over }

We can now set up a listener on netcat
And open the rev.php on localhost
we should get the shell



---
[Back to Common Web Vulnerabilities](./README.md)
