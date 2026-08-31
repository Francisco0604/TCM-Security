# LazyAdmin


ip= 10.10.17.117

Apache 2.4.18

![Screenshot](./assets/040_LazyAdmin_1d8d64c5-e0cb-804e-9d45-df4f43a5f656.png)

Wepalyzer - OS ubuntu 

![Screenshot](./assets/041_LazyAdmin_1d8d64c5-e0cb-80cf-931b-c97281605194.png)

Did directory busting and found pg by sweet rice

![Screenshot](./assets/042_LazyAdmin_1d8d64c5-e0cb-805e-8aa0-d64bf49680c7.png)

Found this as an exploit by googling

![Screenshot](./assets/043_LazyAdmin_1d8d64c5-e0cb-8018-a2c8-ec93d2babc18.png)

Downloaded the file and found password in hash and a username
(got too focused and fogot to write notes, below is wtever i remember)

There was another directory for log in 
Used that
Put the passward and username in that and got login
There was a place to upload files uploaded a reverse shell there with listner on nc
Got shell
Used sudo -l
Found that i hav privilage of perl and backup with no password
The backup file had a reverse shell listner command like
I put my ip there 
And i got a reverse shell again but this time as root



---
[Back to Capstone](./README.md)
