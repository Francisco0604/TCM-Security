# Password hunting


quick dirty commands for password hunting are

To colour cordinate
This will grab everything that conatins the “PASSWORD=” in files

```bash
grep --color=auto -rnw '/' -ie "PASSWORD=" --color=always 2> dev/null
```

To locate any file with the name password  (we can use many variations instead of password like pass, pwd and many more )

```bash
locate password | more
locate pass | more
```

To hunt down ssh keys (again can use many variations

```bash
find / -name -id_rsa 2> /dev/null
find / -name authorized_keys 2> /dev/null
```

To find password of hidden files 

```bash
grep -r "password" . --include=".*"
```

If too many permission denied and invalid argument

```bash
grep -r "password" . --include=".*" 2>&1 | grep -v "Permission denied" | grep -v "Invalid argument"
```



---
[Back to Initial enumeration](./README.md)
