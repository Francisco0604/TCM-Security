# System enumeration


To check the hostname

```bash
hostname
```

Gives more info than hostname (better)

```bash
uname -a
```
This better to find easy exploits
Can search the versions which we get as results in this on google to see if there is any vulnerabilities

Similar to the above one

```bash
cat /proc/version
cat /etc/issue
```

To take a quick peak at the architecture

```bash
lscpu
```
if exploits need 4 cores to work but udk how many cores are part of the cpu then can run this and see

To check what services are running 

```bash
 ps -aux
```



---
[Back to Initial enumeration](./README.md)
