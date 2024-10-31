<!-- https://docs.google.com/document/d/1-BwCO0udUP7MhRh81Y681zz0BalXtKFtte_FHJc6G4s/edit?pli=1&tab=t.0 -->

### Password policy
```sh
sudo chage -l <username>
```

### Check UFW status
```sh
sudo ufw status
```

>[!Note]
>###### look for status: `active`

### Check the chosen operating system
```sh
lsb_release -a || cat /etc/os-release
```

### Check that `user` has been added to `sudo` and `user42` groups
```
getent group sudo
getent group user42
```

### Create new user
```sh
sudo adduser <new_username>
```

### Create a group named “evaluating”
```sh
sudo groupadd evaluating
```

### Add new user to group evaluating
```sh
sudo usermod -aG evaluating <your_new_username>
```

### Check if the new user belongs to the “evaluating” group
```sh
getent group evaluating
```

### Check hostname
```
hostnamectl
```

### Modify the hostname by replacing the login with new one, then restart VM
```sh
sudo hostnamectl set-hostname <new_hostname>
sudo reboot
```

>[!Note]
>###### restore machine to original hostname
>```sh
>sudo hostnamectl set-hostname <new_hostname>
>sudo reboot
>```

### How to view the partitions from the VM
```sh
lsblk
```

### Check that the “sudo” program is properly installed
```sh
dpkg -l | grep sudo
```

### Check sudo rules
```sh
sudo visudo
```

### Check UFW instalation
```sh
sudo ufw status numbered
```

### Add new port to UFW
```sh
sudo ufw allow 8080
```

### Delete this new rule
```sh
sudo ufw delete 4
sudo ufw delete 2
```

### Check that the SSH service is properly installed 
```sh
sudo service ssh status
```

>[!Note]
>###### Check if its active and port 4242

### Verify IP adress
```sh
hostname -I
```

### Open script monitoring.sh
```sh
vim /usr/local/bin/monitoring.sh
```

### Change monitoring from 10min to 1min
```sh
sudo crontab -u root -e
```
>###### change 10 value to 1

### Cron stop
```sh
sudo cronstop
```

### Cron start
```sh
cronstart
```

### Check if the script still exists in the same place
```sh
sudo reboot
sudo crontab -u root -e
```
