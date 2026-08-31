# SSH keys


For this we are either 1 looking for the following files if we get both then more good 

![Screenshot](./assets/009_SSH_keys_1d2d64c5-e0cb-80bc-ba35-e3a18e0912c9.png)

In the video we found an rsa key 

We copied the rsa key to a file and chmod it to 600
then we ran ssh

```bash
ssh -i id_rsa root@machine_ip
```

![Screenshot](./assets/010_SSH_keys_1d2d64c5-e0cb-8063-a6b6-ccdd7648b9c6.png)



---
[Back to Passwords & File Permissions](./README.md)
