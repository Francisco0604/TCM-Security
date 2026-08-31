# Dom -Lab 1


When we sent information we could see that there was no going or coming back from the server, so since this is happening completly locally and is a vulnerability from the client side it is DOM based 

When type and execute the following to check if it is vulnerable

![Screenshot](./assets/236_Dom_-Lab_1_1cdd64c5-e0cb-80ce-8e28-e858a16e2437.png)
It will not execute
This is because evn tho the code is being added to the page it isnt being called, if this was partof the page when it  was loaded then it would have loaded


```javascript
<img src=x onerror="prompt(1)">
```

When the page tries to find x it will get an error and on error it will load our payload

To forward to another pg

```javascript
<img src=x onerror="windows.location.href='https://siteurl.com'">
```



---
[Back to Common Web Vulnerabilities](./README.md)
