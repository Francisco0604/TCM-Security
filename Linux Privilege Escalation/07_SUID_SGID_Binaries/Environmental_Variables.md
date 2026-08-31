# Environmental Variables

Environment Variables
Environment variables are values that are defined outside of a program (e.g., in the operating system or shell configuration) and are made available to the program. They can be accessed by child processes and shells.
Characteristics
1. System-wide or user-specific: Environment variables can be defined system-wide or specific to a user.1. Inherited by child processes: When a process creates a child process, the child process inherits the environment variables of the parent process.1. Used for configuration: Environment variables are often used to configure the behavior of programs or shells.
To see the environmental variables

```bash
env
```

eg

![Screenshot](./assets/016_Environmental_Variables_1d5d64c5-e0cb-80f0-9dde-c3baa485645b.png)

so we take change this if we have the required suid permissions and use it to elevate our privilages

We use the find to check for suid permissions

```bash
find / -type f -perm -04000 -ls 2>/dev/null
```

We find something interesting

![Screenshot](./assets/017_Environmental_Variables_1d5d64c5-e0cb-80fc-9045-efd4b41a181c.png)
So we run it like that

We use string to run it properly again

```bash
string /usr/local/bin/suid-env
```


![Screenshot](./assets/018_Environmental_Variables_1d5d64c5-e0cb-803b-8d7f-e7ba2b09fa8f.png)

so we c that the service is running and that is like a global variable 

what we will do is

![Screenshot](./assets/019_Environmental_Variables_1d5d64c5-e0cb-80c0-9041-c0ebdc5aef48.png)
we write this c 1 liner
then we compile it using gcc

We then put /temp to some first in path

![Screenshot](./assets/020_Environmental_Variables_1d5d64c5-e0cb-80e6-ba6c-cec231f5984f.png)

We can also use the function (if like direct path like /usr is given when we use the string to check)

![Screenshot](./assets/021_Environmental_Variables_1d5d64c5-e0cb-8008-8ae7-ce85eab45d35.png)


Go to the linux privsec of tcm on THM proper commands will be there



---
[Back to SUID](./README.md)
