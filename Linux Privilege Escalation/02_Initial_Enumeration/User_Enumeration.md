# User Enumeration


We will do this to find out who we are and what permission we are allowed 

To find out who you are

```bash
whoami
```

To check our id (user id, grp id(user/admin)

```bash
id
```

To check what privileges we hav 

```bash
sudo -l
```

To check if can read files
To check all users

```bash
cat etc/passwd
```
To just get the usernames

```bash
cat etc/passwd | cut -d : -f 1
```

To check if we can read sensitive files

```bash
cat etc/shadow
```

To check if there is anything good in history typed before

```bash
history
```



---
[Back to Initial enumeration](./README.md)
