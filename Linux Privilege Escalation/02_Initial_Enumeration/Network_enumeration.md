# Network enumeration


To check ip 

```bash
ifconfig
ip a
```

To check the route

```bash
route
ip route
```
Another way to look at this is by arp table

```bash
arp -a
ip neigh
```

To identify what ports are open and what communications exist

```bash
netstat -ano
```
(hacker mind : when see 2 machine communicating try to find and exploit which can use against them )
Another thing we want to identify is if there are any open ports that we did not pick up on earlier and what are they doing



---
[Back to Initial enumeration](./README.md)
