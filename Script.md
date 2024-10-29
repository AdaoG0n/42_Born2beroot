## Script
>[!Warning]
> ###### **Não** copie o código sem estudar o que faz cada um dos comandos. Entenda o seu funcionamento!
> ###### Têm a explicação mais a baixo.
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


## Explicação

```#!/bin/bash ```
>[!Note]
> ###### O script começa com #!/bin/bash, o shebang, que indica que o Bash é o interpretador do script.
---
```# ARCH
arch=$(uname -a)
```
>[!Note]
> ###### Usa o comando uname -a para capturar detalhes completos sobre o kernel e a arquitetura do sistema operacional, armazenando-o na variável arch.
---
```
# CPU PHYSICAL
cpuf=$(grep "physical id" /proc/cpuinfo | wc -l)

# CPU VIRTUAL
cpuv=$(grep "processor" /proc/cpuinfo | wc -l)
```
>[!Note]
> ###### Aqui, o script conta o número de CPUs físicas e virtuais:
> ###### cpuf conta linhas com "physical id" para identificar as CPUs físicas.
> ###### cpuv conta o número total de processadores virtuais usando a palavra "processor".
---
```  
# RAM
ram_total=$(free --mega | awk '$1 == "Mem:" {print $2}')
ram_use=$(free --mega | awk '$1 == "Mem:" {print $3}')
ram_percent=$(free --mega | awk '$1 == "Mem:" {printf("%.2f"), $3/$2*100}')
```
>[!Note]
> ###### Estas variáveis usam o comando free --mega para obter:
> ###### ram_total: Total de RAM disponível.
> ###### ram_use: RAM em uso.
> ###### ram_percent: Percentual de RAM usada, calculada diretamente.
---
```
# DISK
disk_total=$(df -m | grep "/dev/" | grep -v "/boot" | awk '{disk_t += $2} END {printf ("%.1fGb\n"), disk_t/1024}')
disk_use=$(df -m | grep "/dev/" | grep -v "/boot" | awk '{disk_u += $3} END {print disk_u}')
disk_percent=$(df -m | grep "/dev/" | grep -v "/boot" | awk '{disk_u += $3} {disk_t+= $2} END {printf("%d"), disk_u/disk_t*100}')
```
>[!Note]
> ###### Esta seção calcula o espaço total e o uso de disco em gigabytes:
> ###### disk_total: Espaço total em disco, ignorando a partição /boot.
> ###### disk_use: Espaço em uso no disco.
> ###### disk_percent: Percentual do disco em uso, com base em disk_use e disk_total.
---
```
# CPU LOAD
cpul=$(vmstat 1 2 | tail -1 | awk '{printf $15}')
cpu_op=$(expr 100 - $cpul)
cpu_fin=$(printf "%.1f" $cpu_op)
```
>[!Note]
> ###### Esta seção calcula a carga de uso da CPU:
> ###### cpul: O valor de ociosidade da CPU é capturado, e depois subtraído de 100 para obter a carga ativa (cpu_op).
> ###### cpu_fin: Armazena a carga ativa com uma precisão de uma casa decimal.
---
```
# LAST BOOT
lb=$(who -b | awk '$1 == "system" {print $3 " " $4}')
```
>[!Note]
> ###### Usa who -b para encontrar a data e a hora do último boot.
---
```
# LVM USE
lvmu=$(if [ $(lsblk | grep "lvm" | wc -l) -gt 0 ]; then echo yes; else echo no; fi)
```
>[!Note]
> ###### Verifica se o LVM (Logical Volume Manager) está em uso. Se o comando lsblk encontrar volumes lógicos, lvmu exibe "yes", caso contrário, "no".
---
```
# TCP CONNEXIONS
tcpc=$(ss -ta | grep ESTAB | wc -l)
```
>[!Note]
> ###### Conta o número de conexões TCP estabelecidas, usando o comando ss -ta para listar conexões e grep ESTAB para encontrar apenas conexões estabelecidas.
---
```
# USER LOG
ulog=$(users | wc -w)
```
>[!Note]
> ###### Conta quantos usuários estão atualmente conectados no sistema.
---
```
# NETWORK
ip=$(hostname -I)
mac=$(ip link | grep "link/ether" | awk '{print $2}')
```
>[!Note]
> ###### Obtém o endereço IP com hostname -I e o endereço MAC com ip link.
---
```
# SUDO
cmnd=$(journalctl _COMM=sudo | grep COMMAND | wc -l)
```
>[!Note]
> ###### Conta quantos comandos foram executados com sudo utilizando o journalctl.
---
```
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
>[!Note]
> ###### O comando wall exibe todas as informações obtidas em um formato organizado e acessível, usando variáveis para representar dados como arquitetura, uso de CPU e rede, e o número de comandos sudo executados.
