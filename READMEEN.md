# Virtual Environment Setup

### Software Virtualization Choice and Installation:

   > Use VirtualBox without exception. If you are on a Mac with an M1 chip, you can use UTM.

### Creating the Virtual Machine:

 > Install the chosen operating system (Debian or Rocky Linux).

### Operating System:

 > * Debian: The latest stable version is recommended, especially if you are a beginner.
> *  Rocky Linux: Latest stable version. Note that it is more complex and requires specific configurations such as SELinux.

# Operating System Configuration

### Disable Graphical Interface:

  > Do not install X.org or any other graphical server. The interface will be purely command line.

### Security and Policies:

  > SELinux/AppArmor:
   > > * Rocky Linux: Enable and configure SELinux to meet project needs.
   > > * Debian: Enable and configure AppArmor.

### Partitioning:

  > Create at least 2 encrypted partitions using LVM (Logical Volume Manager).

# Network and Security Configuration

### SSH Service:

> * Configure the SSH service to operate on port 4242.
> * Restriction: Do not allow root login via SSH.

### Firewall:

  > * Debian: Use UFW (Uncomplicated Firewall).
  > * Rocky Linux: Use firewalld.
  > * Configure the firewall to only allow port 4242 to be open.
  > * Ensure that the firewall is active upon starting the virtual machine.

### Hostname:

  > Set the hostname of the virtual machine to be your login followed by 42 (e.g., yourLogin42).

# User and Sudo Management

### Password Policy:

  > * Passwords must expire every 30 days.
  > * Minimum of 2 days before a password can be changed again.
  > * Warning of 7 days before password expiration.
  > * Passwords must be at least 10 characters long, including uppercase letters, lowercase letters, and numbers.
  > * Must not contain more than 3 identical consecutive characters or the username.

### Users and Groups:

 > Besides the root user, create a user with your login that belongs to the groups user42 and sudo.

### Sudo Configuration:

 > * Limit to 3 authentication attempts for sudo commands.
 > * Configure a custom message for authentication errors.
 > * Logs: Store logs of sudo actions in /var/log/sudo/.
 > * Enable TTY mode for security.
 > * Restrict the paths that sudo can use (e.g., /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin).

# Monitoring Script

### Creation of monitoring.sh:

> Write a bash script that displays system information on all terminals every 10 minutes using the wall command.

### Information to Display:

 > * System architecture and kernel version.
 > * Number of physical and virtual processors.
 > * Available RAM and utilization rate.
 > * Available storage space and utilization rate.
 > * CPU utilization.
 > * Date and time of last reboot.
 > * Status of LVM.
 > * Number of active connections.
 > * Number of connected users.
 > * IPv4 address and MAC address of the server.
 > * Number of commands executed with sudo.

### Script Configuration:

> * Use cron to schedule the script execution every 10 minutes.
> * Ensure that the script runs without errors and can be interrupted during defense without modifications.

# Submission and Evaluation

### signature.txt File:

> * Generate the SHA1 hash of your virtual machine disk file (.vdi or .qcow2 extensions).
> * Insert this hash into the signature.txt file and commit it in the root of the Git repository.

### Important Rules:

> * Do not include the virtual machine in the Git repository.
> * The signature will be verified during defense. Ensure it remains unchanged by duplicating the VM or using save state option if necessary.

# Bonus Part (Optional)

### Extra Tasks:

> * Partition configuration according to a specific scheme.
> * Setting up a WordPress site using lighttpd, MariaDB, and PHP.
> * Configuring an additional service of your choice (excluding NGINX/Apache2).

### Conditions for Bonus Evaluation:

> The bonus part will only be evaluated if all mandatory requirements are perfectly met.

# Summary of Necessary Actions:

 > * Set up the virtual machine with Debian or Rocky Linux without a graphical interface.
 > * Configure security with SELinux/AppArmor, SSH on port 4242, and appropriate firewall settings.
 > * Manage users and password policies according to guidelines.
 > * Create and configure monitoring scripts executed periodically.
 > * Generate and submit the signature of the virtual disk in the Git repository.
 > * (Optional) Implement additional functionalities for the bonus part.

# Final Tips:

  Documentation: Keep a detailed record of all configurations made. This will be useful for both defense and troubleshooting potential issues.
  Testing: Ensure all configurations are functioning correctly before submission.
  Security: Pay special attention to security configurations, as they are critical for the project.
  Backup: Regularly back up your virtual machine to avoid data loss.
