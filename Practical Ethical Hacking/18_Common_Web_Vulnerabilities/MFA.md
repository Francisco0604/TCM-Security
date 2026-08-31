# MFA

We get the same log in and this time we are given a username and password and told to attack another username
We first enter own credentials, and we are then given a code to enter to log in

The first few things which comes to mind is 
Can use the code to under with another user name
Cause the webpage still has the username section to edit and a code section to put the code

The other method we can use is brute forcing since the code is only 6 digits long and it is only numbers

So we took the mfa code and put it in the section and before sending it we intercept it with burp 
There we change the username and send
And we are successfully in 



---
[Back to Common Web Vulnerabilities](./README.md)
