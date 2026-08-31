# SQL injection blind Lab 2


Gonna use burp
Add the site in scope so we do not get unnecesary traffic

One of the main things to pay attention to is the content length of the response

We will copy the request from burp and pastse it in a file

then use sqlmap -r filename
It will tell you if the target is injectable or not 


![Screenshot](./assets/228_SQL_injection_blind_Lab_2_1cdd64c5-e0cb-80ef-8fa3-f01b7c3f5372.png)
Since the sqlmap is saying parameters do not appear to be injectable, we can still go and try manually or download a list of payloads and try to fuzz it
Or we can look for other injection points 

We can also try the injection on the cookie if the web pg is somehow processing it 

This is a blind injection as it will only change the behaviour of the application

Blind injection to check the version mysql

![Screenshot](./assets/229_SQL_injection_blind_Lab_2_1cdd64c5-e0cb-80cb-adc2-cb7b248d6dd4.png)
We need to put the select versiom() in brackets because we need it to resolve  first 

can send to intruder and use sniper to brute force long things like passowrds

Or we can copy the request and put it through the sqlmap
use —level=2 to pass the cokie(it may change overtime so google and c the correct syntax )

We can use this in our report 

![Screenshot](./assets/230_SQL_injection_blind_Lab_2_1cdd64c5-e0cb-805f-b426-e90b3ad06b91.png)

We can use the following command to dump the whole database

![Screenshot](./assets/231_SQL_injection_blind_Lab_2_1cdd64c5-e0cb-8009-b3f0-eab508b05c7c.png)

Do not fire off sql map if the bug bounty programme says 5 req per second or smthng



---
[Back to Common Web Vulnerabilities](./README.md)
