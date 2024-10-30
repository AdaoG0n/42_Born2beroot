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
>This command displays the currently installed version of sudo
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/6.png">

### Configuring groups and users
###### switch to root
###### Create a new user
```sh
sudo adduser <login>
```
> [!Note]
> If already exists, go to the next step
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
>when asking for confirmations type `Y`
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/12.png">

######  check the state of system's SSH service
```sh
sudo service ssh status
```
>[!Note]
>The service must be shown as Active
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
> If not <kbd>root</kbd> switch to it with `su`
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
>The service must be shown as Active
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/20.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/21.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/22.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/23.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/24.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/25.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/26.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/27.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/28.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/29.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/30.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/31.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/32.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/33.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/34.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/35.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/36.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/37.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/38.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/39.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/40.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/41.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/42.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/43.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/44.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/45.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/46.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/47.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/48.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/49.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/50.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/51.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/52.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/53.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/54.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/55.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/56.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/57.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/58.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/59.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/60.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/61.png">
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/62.png">

