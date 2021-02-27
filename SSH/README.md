## What is SSH?
SSH or Secure Shell is a cryptographic network protocol for operating network services securely over an unsecured network. Typical 
applications include remote command-line, login, and remote command execution, but any network service can be secured with SSH.

## Installing SSH Server on Linux
[OpenSSH](https://www.openssh.com/) is the tool used for remote login with SSH Protocol. Most Linux Distros have this already installed on their system.
But you can use your favourable package manager to install OpenSSH on your system.
Command to install OpenSSH on Ubuntu:
```bash
sudo apt install openssh-server
```
[Click to see SSH Install Demonstration](sshInstallLinux.jpg)
## Installing SSH Client on Windows 10

To install SSH: click on Start -> Settings Apps -> Apps and Features -> Manage Optional Features. Next locate “OpenSSH Client“, then click “Install“.

![Installing SSH Client on Windows](sshInstallWin.gif)

## Checking SSH status on Linux
```console
[wilcy@wilcy-pc ~]$ systemctl status sshd
● sshd.service - OpenSSH Daemon
     Loaded: loaded (/usr/lib/systemd/system/sshd.service; enabled; vendor preset: disabled)
     Active: active (running) since Sat 2021-02-27 10:54:21 +0545; 8min ago
   Main PID: 434 (sshd)
      Tasks: 1 (limit: 3563)
     Memory: 3.3M
     CGroup: /system.slice/sshd.service
             └─434 sshd: /usr/bin/sshd -D [listener] 0 of 10-100 startups
```
You can also start,stop,restart other services like SSH using <b>systemctl</b> or <b>service</b> command on Linux.

## Connecting to Linux PC from Windows 10 using SSH
open command prompt on Windows -> follow the below steps

