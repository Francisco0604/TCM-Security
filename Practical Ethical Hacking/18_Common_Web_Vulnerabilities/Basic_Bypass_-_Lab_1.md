# Basic Bypass - Lab 1


basic funtionality: We have to upload and it will show which file are uploaded

![Screenshot](./assets/253_Basic_Bypass_-_Lab_1_1cdd64c5-e0cb-8058-abbc-e4e6a5876d75.png)

Tried to upload a text file but got an error

![Screenshot](./assets/254_Basic_Bypass_-_Lab_1_1cdd64c5-e0cb-808a-a37f-eb0ab1de5071.png)

Opened dev tools and went to the network section
Tired to upload the text file again, but this time looking for system calls on the web server
No checks were found

![Screenshot](./assets/255_Basic_Bypass_-_Lab_1_1cdd64c5-e0cb-8025-a132-cfdbd6f1e95d.png)
This means the check is happening on the client side
We have full control over the client side 
We can just disable JS and the check will not happen OR we can intercept the request and change the file

In this we going to intercept using burp
We upload a img while the burp proxy is on and then send the req to the repeater
Get rid of the img data
Put a simple text 
Change the file name to txt
We got the response that the txt file was uploaded and it reflected on the site as well

![Screenshot](./assets/256_Basic_Bypass_-_Lab_1_1ced64c5-e0cb-80f8-845c-d1dba01d9e7f.png)
There maybe blocklists that might block php files so its always better to do more testing

We then craft our payload

```php
<?php system($_GET['cmd']); ?>
```
- system(): This function executes an external program and displays the output.- $_GET['cmd']: This retrieves the value of the cmd parameter from the URL query string.Security Implications
This code allows an attacker to execute arbitrary system commands by passing them as a query parameter. For example:

```bash
http://example.com/vulnerable.php?cmd=ls
```

Change the file name to an executable
In this changed it to cmd.php 
(.php for executable)

Now we hav to find out where the file is 
We used ffuf to search for directories

![Screenshot](./assets/257_Basic_Bypass_-_Lab_1_1ced64c5-e0cb-80b7-8d42-c6decd34a91c.png)
Found the location and did RCE

![Screenshot](./assets/258_Basic_Bypass_-_Lab_1_1ced64c5-e0cb-8089-9a72-fdc07b454f09.png)

Have been told to upload or find a reverse shell on own for fun



---
[Back to Common Web Vulnerabilities](./README.md)
