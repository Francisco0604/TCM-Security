# Actual walkthrough


Enumeration

![Screenshot](./assets/268_Actual_walkthrough_1cfd64c5-e0cb-80c5-9054-d97564e1b53d.png)

After logging in when you get message can edit that on top in url
This led to us being able to do xss

![Screenshot](./assets/269_Actual_walkthrough_1cfd64c5-e0cb-8073-83ca-e5cd8fae0201.png)

Did the same in review 
This is a stored xss which is way more dangerous

![Screenshot](./assets/270_Actual_walkthrough_1cfd64c5-e0cb-8050-9872-f4efa913a3ca.png)

Found an entry point for sql injection in url

![Screenshot](./assets/271_Actual_walkthrough_1cfd64c5-e0cb-802b-9f27-e32229ec6522.png)
Found username and hashes of password from here

Used hashcat to crack the password



---
[Back to Common Web Vulnerabilities](./README.md)
