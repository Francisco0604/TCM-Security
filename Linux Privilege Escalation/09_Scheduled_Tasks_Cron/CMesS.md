# CMesS

THM box
ip = 10.10.30.433

1. Manual enumerationWent to site and saw a search bar
tried to enter basic html,command,sql and xss injection, it failed.
Apache server 2.4.18 (webpalizer)

1. nampport 22 OpenSSH 7.2p2
port 80 Apache httpd 2.4.18  

1. Directory enumeration0                   
01                    
1                       
1x1                
about                  
About               
.htpasswd     
.htaccess      
admin                  
.hta                  
api        
assets               
author          
blog            
category  
cm              
feed    
fm             
index            
Index                  
lib      
log              
login                 
robots.txt         
search                
Search                  
server-status        
sites                   
src                    
tags                    
tag                   
themes                
tmp                  
1. Subdomain
```bash
ffuf -w /usr/share/wordlists/dnsmap.txt -u http://cmess.thm -H "Host: FUZZ.cmess.thm" -fs 3877
```
Found dev only
Wrote this in /etc/host

Manually went to dev.cmess.thm

Found password of andre
Got access to admin panel with that
Found the:
Gila CMS version 1.10.9 

then i did some stored passowrd enumeration and found a hidden password file, it contained the password of andre
Used that to ssh as andre
Saw the crontab, and found out that there is a process running every 2 mins and has a wildcard on it



---
[Back to Scheduled tasks](./README.md)
