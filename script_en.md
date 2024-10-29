## Script
>[!Warning]
> ###### **Do not** copy the code without studying what each command does. Understand its functionality!
> ###### See the explanation below.

```Bash
#!/bin/bash

# ARCH
arch=$(uname -a)

# CPU PHYSICAL
cpuf=$(grep "physical id" /proc/cpuinfo | wc -l)

# CPU VIRTUAL
cpuv=$(grep "processor" /proc/cpuinfo | wc -l)
  
# RAM
ram_total=$(free --mega | awk '$1 == "Mem:" {print $2}')
ram_use=$(free --mega | awk '$1 == "Mem:" {print $3}')
ram_percent=$(free --mega | awk '$1 == "Mem:" {printf("%.2f"), $3/$2*100}')

# DISK
disk_total=$(df -m | grep "/dev/" | grep -v "/boot" | awk '{disk_t += $2} END {printf ("%.1fGb\n"), disk_t/1024}')
disk_use=$(df -m | grep "/dev/" | grep -v "/boot" | awk '{disk_u += $3} END {print disk_u}')
disk_percent=$(df -m | grep "/dev/" | grep -v "/boot" | awk '{disk_u += $3} {disk_t+= $2} END {printf("%d"), disk_u/disk_t*100}')

# CPU LOAD
cpul=$(vmstat 1 2 | tail -1 | awk '{printf $15}')
cpu_op=$(expr 100 - $cpul)
cpu_fin=$(printf "%.1f" $cpu_op)

# LAST BOOT
lb=$(who -b | awk '$1 == "system" {print $3 " " $4}')

# LVM USE
lvmu=$(if [ $(lsblk | grep "lvm" | wc -l) -gt 0 ]; then echo yes; else echo no; fi)

# TCP CONNEXIONS
tcpc=$(ss -ta | grep ESTAB | wc -l)

# USER LOG
ulog=$(users | wc -w)

# NETWORK
ip=$(hostname -I)
mac=$(ip link | grep "link/ether" | awk '{print $2}')

# SUDO
cmnd=$(journalctl _COMM=sudo | grep COMMAND | wc -l)

wall "	Architecture: $arch
	CPU physical: $cpuf
	vCPU: $cpuv
	Memory Usage: $ram_use/${ram_total}MB ($ram_percent%)
	Disk Usage: $disk_use/${disk_total} ($disk_percent%)
	CPU load: $cpu_fin%
	Last boot: $lb
	LVM use: $lvmu
	Connections TCP: $tcpc ESTABLISHED
    User log: $ulog
    Network: IP $ip ($mac)
	Sudo: $cmnd cmd"

```


## Explanation

```#!/bin/bash```
>[!Note]
> ###### The script starts with #!/bin/bash, known as a shebang, which indicates that Bash is the interpreter for this script.
---

```# ARCH
arch=$(uname -a)
```
>[!Note]
> ###### Uses the command uname -a to capture complete details about the kernel and the operating system architecture, storing it in the variable arch.
---
```
# CPU PHYSICAL
cpuf=$(grep "physical id" /proc/cpuinfo | wc -l)

# CPU VIRTUAL
cpuv=$(grep "processor" /proc/cpuinfo | wc -l)
```
>[!Note]
> ###### This section counts the number of physical and virtual CPUs:
> ###### cpuf counts lines with "physical id" to identify physical CPUs.
> ###### cpuv counts the total number of virtual processors using the term "processor".
---

```# RAM
ram_total=$(free --mega | awk '$1 == "Mem:" {print $2}')
ram_use=$(free --mega | awk '$1 == "Mem:" {print $3}')
ram_percent=$(free --mega | awk '$1 == "Mem:" {printf("%.2f"), $3/$2*100}')
```

>[!Note]
> ###### These variables use the command free --mega to obtain:
> ###### ram_total: Total available RAM.
> ###### ram_use: RAM currently in use.
> ###### ram_percent: Percentage of RAM used, calculated directly.
---

```# DISK
disk_total=$(df -m | grep "/dev/" | grep -v "/boot" | awk '{disk_t += $2} END {printf ("%.1fGb\n"), disk_t/1024}')
disk_use=$(df -m | grep "/dev/" | grep -v "/boot" | awk '{disk_u += $3} END {print disk_u}')
disk_percent=$(df -m | grep "/dev/" | grep -v "/boot" | awk '{disk_u += $3} {disk_t+= $2} END {printf("%d"), disk_u/disk_t*100}')
```

>[!Note]
> ###### This section calculates total disk space and usage in gigabytes:
> ###### disk_total: Total disk space, ignoring the /boot partition.
> ###### disk_use: Disk space currently in use.
> ###### disk_percent: Percentage of disk space in use, based on disk_use and disk_total.

---
```# CPU LOAD
cpul=$(vmstat 1 2 | tail -1 | awk '{printf $15}')
cpu_op=$(expr 100 - $cpul)
cpu_fin=$(printf "%.1f" $cpu_op)
```

>[!Note]
> ###### This section calculates CPU load:
> ###### cpul: The CPU idle value is captured and then subtracted from 100 to get the active load (cpu_op).
> ###### cpu_fin: Stores the active load with one decimal point precision.
---

```# LAST BOOT
lb=$(who -b | awk '$1 == "system" {print $3 " " $4}')
```

>[!Note]
> ###### Uses who -b to find the date and time of the last boot.
---

```# LVM USE
lvmu=$(if [ $(lsblk | grep "lvm" | wc -l) -gt 0 ]; then echo yes; else echo no; fi)
```

>[!Note]
> ###### Checks if LVM (Logical Volume Manager) is in use. If the lsblk command finds logical volumes, lvmu displays "yes", otherwise "no".
---

```# TCP CONNEXIONS
tcpc=$(ss -ta | grep ESTAB | wc -l)
```

>[!Note]
> ###### Counts the number of established TCP connections using the ss -ta command to list connections and grep ESTAB to find only established ones.
---

```# USER LOG
ulog=$(users | wc -w)
```

>[!Note]
> ###### Counts how many users are currently logged into the system.
---

```# NETWORK
ip=$(hostname -I)
mac=$(ip link | grep "link/ether" | awk '{print $2}')
```

>[!Note]
> ###### Obtains the IP address with hostname -I and the MAC address with ip link.
---

```# SUDO
cmnd=$(journalctl _COMM=sudo | grep COMMAND | wc -l)
```

>[!Note]
> ###### Counts how many commands have been executed with sudo using journalctl.
---

```wall "	Architecture: $arch
	CPU physical: $cpuf
	vCPU: $cpuv
	Memory Usage: $ram_use/${ram_total}MB ($ram_percent%)
	Disk Usage: $disk_use/${disk_total} ($disk_percent%)
	CPU load: $cpu_fin%
	Last boot: $lb
	LVM use: $lvmu
	Connections TCP: $tcpc ESTABLISHED
    User log: $ulog
    Network: IP $ip ($mac)
	Sudo: $cmnd cmd"
```

>[!Note]
> ###### The wall command displays all gathered information in an organized and accessible format, using variables to represent data like architecture, CPU usage, and the number of executed sudo commands.
