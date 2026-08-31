# Gaining a shell

Couple of methods to do this

we can use metasploit 
With password

![Screenshot](./assets/100_Gaining_a_shell_1c6d64c5-e0cb-8075-9581-eea9fb900370.png)

With hash

![Screenshot](./assets/101_Gaining_a_shell_1c6d64c5-e0cb-80b3-9f59-de63f6e612d1.png)

Metasploit is a bit noisy and in a real time enviroment there is a chance it might get caught

![Screenshot](./assets/102_Gaining_a_shell_1c6d64c5-e0cb-8076-8b07-faac28cb4534.png)

We can use [psexec.py](http://psexec.py/) It wont get detected as much

with password

![Screenshot](./assets/103_Gaining_a_shell_1c6d64c5-e0cb-80f2-a384-c523423ad563.png)

With hash

![Screenshot](./assets/104_Gaining_a_shell_1c6d64c5-e0cb-809e-975a-f6cf8635a154.png)

Always set the payload to x64 on metasploit

If automatic does not work try the others (Native upload works the best)

![Screenshot](./assets/105_Gaining_a_shell_1c6d64c5-e0cb-807f-a0e6-c0d0a4ec4465.png)



---
[Back to Attacking Active Directory: Initial Attack Vectors](./README.md)
