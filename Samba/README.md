## What is Samba?
[Samba](samba.org) is the standard Windows interoperability suite of programs for Linux and Unix. Since 1992, Samba has provided secure, stable and fast file and print services for all clients using the SMB/CIFS protocol, such as all versions of DOS and Windows, OS/2, Linux and many others.

## Installing Samba on Linux
You can install Samba on any of your favourite package manager or distro. However, command to install Samba on Ubuntu is below. Type the command on your Linux Terminal:
```bash
sudo apt install samba
```

## Installing Samba on Windows
- Press Windows Key + R to bring up the run dialog and type: optionalfeatures.
- Expand “SMB 1.0/CIFS File Sharing Support” and then check the box next to “SMB 1.0/CIFS Client“
- Click OK.
- The installation will now proceed and you should be able to access shares using the SMB 1 Protocol.<br><br>
![Samba Install Windows](installSambaWin.png)

## Configuring Samba on Linux
In Linux Terminal go to /etc/samba and create a smb.conf file if there are none.
```console
[wilcy@wilcy-pc ~]$ cd /etc/samba
[wilcy@wilcy-pc samba]$ ls
private  smb.conf
[wilcy@wilcy-pc samba]$
```
Use a text editor to edit the smb.conf file. You can use any text editor like vim,nano,gedit etc.
```console
[wilcy@wilcy-pc samba]$ sudo nano smb.conf
[sudo] password for wilcy:
```
Overwrite the file with following texts:
```
[global]
        server role = standalone server
        map to guest = bad user
        usershare allow guests = yes
        hosts allow = 192.168.0.0/16
        hosts deny = 0.0.0.0/0
```
