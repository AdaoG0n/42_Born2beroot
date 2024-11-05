# System Setup
### Login into the system
###### Enter encryption password;<br/>   
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/1.png"><br/>
###### Enter username and password; <br/>
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/2.png">

### Installing sudo
###### Switch to user <kbd> root </kbd>
```
 su
 ```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/3.png"><br/>

### Install `Sudo` <br/>
```
apt install sudo
``` 
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/4.png"><br/>

### Reboot the machine
```
 sudo reboot
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/5.png"><br/>

### Check sudo version
###### Login again with user.
###### Check sudo's version with the command:
```
 sudo -V
```
>[!Note]
> ###### This command displays the currently installed version of sudo
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/6.png">

### Configuring groups and users
###### Switch to root
```sh
su
```
###### Create a new user
```sh
sudo adduser <login>
```
> [!Note]
> ###### If already exists, go to the next step
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/7.png">

###### Create a new group `user42`
```
sudo group user42
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/8.png">

###### Add user to group `user42` and `sudo`
```sh
sudo adduser <user> <groupname>
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/9.png">

###### Check user groups and their users either:
```sh
getent group
# or
getent group <group_name>
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/10.png">

### Installing SSH
###### Update the system package manager:
```sh
sudo apt update
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/11.png">

######  Install OpenSSH
```sh
sudo apt install openssh-server
```
>[!Note]
> ###### When asking for confirmations type `Y`
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/12.png">

######  check the state of system's SSH service
```sh
sudo service ssh status
```
>[!Note]
> ###### The service must be shown as Active
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/13.png">

### Installing vim
######  Run the command:
```sh
sudo apt install vim
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/14.png">

### Configuring SSH
###### Open `sshd_config`
```sh
vim /etc/ssh/sshd_config
```
>[!Note]
> ###### If not <kbd>root</kbd> switch to it with `su`
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/15.png">

###### * Change `Port22` to `Port 4242`
###### * Change `PermitRootLogin` to `PermitRootLogin no`
###### * Save and close file;
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/16.png">

###### Open `ssh_config`
```sh
vim /etc/ssh/ssh_config
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/17.png">

###### Set Port to `Port 4242`
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/18.png">

###### Restart to update the SSH service
```sh
sudo service ssh restart
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/19.png">

###### Check service's state
```
sudo service ssh status
```
>[!Note]
> ###### The service must be shown as Active
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/20.png">

### Installing UFW
###### Install UFW packages
```
sudo apt install ufw
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/21.png">

###### Start UFW
```
sudo ufw enable
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/22.png">

###### Configure Firewall to accept connections on 4242 port
```
sudo ufw allow 4242
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/23.png">

######  Check the current state of the firewall
```
sudo ufw status
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/24.png">

### Connecting via SSH
######  Close the VirtualMachine and go to <kbd>Settings</kbd>
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/26.png">

###### <kbd>Network</kbd> change from <kbd>NAT</kbd> to <kbd>`Bridged` adapter</kbd> 
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/27.png">

> ###### Get VirtualMachine IP
>```
>hostname -I
>```
><img width="700" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/25.png">

###### Open a terminal out of VM and connect to the VM:
>```sh
>ssh <username>@<VirtualMachine_IP> -p 4242
>```

>[!Note]
> ###### When ask for `YES/NO` type `Yes`, than put user `password`
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/29.png">

###### It should display the following message:
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/30.png">

###### Now close the connection.
>```sh
>exit
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/31.png">

<!-- ###### Close Unnecessary Connections
>```sh
>ss -tunlp
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/32.png">

###### Get IP address
>```sh
>ip --color addr
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/33.png">

###### Get System's Network Interfaces
>```sh
>vim /etc/network/interfaces
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/34.png">

###### Editing it by setting `# The primary network interface` from `dhcp` to `static`
>```bash
>iface enp0s inet static
>    address xxx.x.x.x/xx
>    gateway xxx.x.x.xxx
>    netmask xxx.xxx.x.x
>    dns
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/35.png">
-->
### Configuring sudo policies and log
###### Create the following file
>```sh
>touch /etc/sudoers.d/sudo_config
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/36.png">

###### Return to the terminal outside the VM.
###### Connect again via SSH
>```sh
>ssh <username>@<VirtualMachine_IP> -p 4242
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/37.png">

###### Switch to user <kbd>ROOT</kbd>
>```sh
>su
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/38.png">

###### Open `sudo_config` to setup policy
>```sh
>vim /etc/sudoers.d/sudo_config
>``
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/39.png">

###### Add the following command to the file and `save` it
```bash
Defaults  passwd_tries=3
Defaults  badpass_message="Wrong password bruh, try again:"
Defaults  logfile="/var/log/sudo/sudo_config"
Defaults  log_input, log_output
Defaults  iolog_dir="/var/log/sudo"
Defaults  requiretty
Defaults  secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/40.png">

###### Than type `exit` > `exit` to close connection
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/41.png">

###### Return no VM and create the following directory
>```sh
>mkdir /var/log/sudo
>``
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/42.png">

### Configuring Password Policy
###### Open `login.defs`
>```sh
>vim /etc/login.defs
>``
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/43.png">

###### Set PASS_MAX_DAYSto 30;
###### Set PASS_MIN_DAYS to 2;
###### Set PASS_WARN_AGE to 7;
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/44.png">

###### Update already created user's password policy

>[!Note]
> ###### The existing users did not receive the changes. To confirm, write the following command:
>```sh
>sudo chage -l <username>
>```
> <img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/45.png">

###### To update the password policy type the following commands:
>```sh
>chage -m <time> <username> 
># and
>chage -M <time> <username>
>```

>[!Note]
> ###### `-m` for minimum days and `-M` for maximum days
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/46.png">

###### Install libpam-pwquality
>```sh
>sudo apt install libpam-pwquality
>```

>[!Note]
> ###### When ask for type `Y/N` type `Y`
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/47.png">

###### Configure libpam-pwquality
>```sh
>sudo vim /etc/pam.d/common-password
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/48.png">

###### On the `per-package modules` section after `retry=3` add the following as inline options
>```bash
>minlen=10
>ucredit=-1
>dcredit=-1
>lcredit=-1
>maxrepeat=3
>reject_username
>difok=7
>enforce_for_root
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/49.png">

### Crontab
###### Edit the crontab file
>```sh
>sudo crontab -u root -e
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/50.png">

###### To make it be precise add the following command:
>```sh
>*/10 * * * * sh /usr/local/bin/sleep.sh; sh /usr/local/bin/monitoring.sh
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/51.png">

###### Create `sleep.sh`
>```sh
>touch /usr/local/bin/sleep.sh
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/52.png">

###### Open `sleep.sh` with vim
>```sh
>vim /usr/local/bin/sleep.sh
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/53.png">

###### Add the following command:
```bash
#!/bin/bash

sleep $(who -b | awk '{ split($4, time, ":"); print time[2]%10 }')m
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/54.png">

###### Create `monitoring.sh`
>```sh
>touch /usr/local/bin/monitoring.sh
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/55.png">

###### Return to the terminal outside the VM.
###### Connect again via SSH
>```sh
>ssh <username>@localhost -p 4242
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/56.png">

###### Switch to user <kbd>ROOT</kbd>
>```sh
>su
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/57.png">

###### Open `monitoring.sh` with vim
>```sh
>vim /usr/local/bin/monitoring.sh
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/58.png">

###### Add the `monitoring` script
>[!Note]
> ###### You can find the script [here](https://github.com/AdaoG0n/42_Born2beroot/blob/main/script_en.md)<br/>
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/59.png">

###### Save the file and close connection
>```sh
>exit
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/60.png">

###### Reboot the VM
>```sh
>sudo reboot
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/61.png">

###### It's done. Now the terminal should display this message every 10 minutes
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/62.png">

# To get signature.txt, follow the next guide
[Signature.txt](https://github.com/AdaoG0n/42_Born2beroot/blob/main/signature_en.md)
