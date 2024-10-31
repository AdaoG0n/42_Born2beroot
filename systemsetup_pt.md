# Configuração do Sistema
### Iniciar sessão no sistema
###### Introduza a password criptografada;<br/>  
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/1.png"><br/>
###### Insira o username e a password; <br/>
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/2.png">

### Instalação do sudo
###### Trocar para o user <kbd> root </kbd>
```
 su
 ```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/3.png"><br/>

### Instalar o `Sudo` <br/>
```
apt install sudo
``` 
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/4.png"><br/>

### Reiniciar a maquina
```
 sudo reboot
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/5.png"><br/>

### Verificar a versão do sudo
###### Inicie novamente sessão.
###### Verifique a versão com o seguinte comando:
```
 sudo -V
```
>[!Note]
> ###### Este comando apresenta a versão atual do sudo
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/6.png">

### Configurar users e grupos
###### Trocar para root
```sh
su
```
###### Criar um novo utilizador
```sh
sudo adduser <login>
```
> [!Note]
> ###### Se ja existir, passe ao proximo passo
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/7.png">

###### Criar um novo grupo `user42`
```
sudo group user42
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/8.png">

###### Adicionar o user aos grupos `user42` e `sudo`
```sh
sudo adduser <user> <groupname>
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/9.png">

###### Verficiar os grupos e seus users:
```sh
getent group
# ou
getent group <group_name>
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/10.png">

### Instalação de SSH
###### Atualize o system package manager:
```sh
sudo apt update
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/11.png">

###### Instalando o OpenSSH
```sh
sudo apt install openssh-server
```
>[!Note]
> ###### Quando pedir confirmação escreva `Y`
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/12.png">

###### Verifique o estado do serviço SSH do sistema
```sh
sudo service ssh status
```
>[!Note]
> ###### O serviço deve ser exibido como Ativo
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/13.png">

### Instalando o vim
######  Execute o comando:
```sh
sudo apt install vim
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/14.png">

### Configurando o SSH
###### Abra o `sshd_config`
```sh
vim /etc/ssh/sshd_config
```
>[!Note]
> ###### Se não estiver em <kbd>root</kbd>, mude com o comando `su`
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/15.png">

###### * Mude `Port 22` para `Port 4242`
###### * Mude `PermitRootLogin` para `PermitRootLogin no`
###### * Salve e feche o arquivo;
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/16.png">

###### Abra o `ssh_config`
```sh
vim /etc/ssh/ssh_config
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/17.png">

###### Defina a Porta como `Port 4242`
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/18.png">

###### Reinicie para atualizar o serviço SSH
```sh
sudo service ssh restart
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/19.png">

###### Verifique o estado do serviço
```
sudo service ssh status
```
>[!Note]
> ###### O serviço deve ser exibido como Ativo
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/20.png">

### Instalando o UFW
###### Instale os pacotes do UFW
```
sudo apt install ufw
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/21.png">

###### Inicie o UFW
```
sudo ufw enable
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/22.png">

###### Configure o firewall para aceitar conexões na porta 4242
```
sudo ufw allow 4242
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/23.png">

###### Verifique o estado atual do firewall
```
sudo ufw status
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/24.png">

### Conectando via SSH
######  Feche a Máquina Virtual e vá para <kbd>Configurações</kbd>
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/26.png">

###### <kbd>Rede</kbd> > Mude de <kbd>NAT</kbd> para <kbd>Adaptador `Bridged`</kbd> 
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/27.png">

> ###### Obtenha o IP da Máquina Virtual
>```
>hostname -I
>```
><img width="700" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/25.png">

###### Abra um terminal fora da VM e conecte-se à VM:
>```sh
>ssh <username>@<IP_Maquina_Virtual> -p 4242
>```

>[!Note]
> ###### Quando perguntar por `YES/NO` digite `Yes`, e depois coloque a `password` do usuário
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/29.png">

###### Deve exibir a seguinte mensagem:
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/30.png">

###### Agora feche a conexão.
>```sh
>exit
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/31.png">

<!-- ###### Feche Conexões Desnecessárias
>```sh
>ss -tunlp
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/32.png">

###### Obtenha o endereço IP
>```sh
>ip --color addr
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/33.png">

###### Obtenha as Interfaces de Rede do Sistema
>```sh
>vim /etc/network/interfaces
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/34.png">

###### Edite-o definindo `# The primary network interface` de `dhcp` para `static`
>```bash
>iface enp0s inet static
>    address xxx.x.x.x/xx
>    gateway xxx.x.x.xxx
>    netmask xxx.xxx.x.x
>    dns
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/35.png">
-->
### Configurando políticas e log do sudo
###### Crie o seguinte arquivo
>```sh
>touch /etc/sudoers.d/sudo_config
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/36.png">

###### Retorne ao terminal fora da VM.
###### Conecte-se novamente via SSH
>```sh
>ssh <username>@<IP_Maquina_Virtual>  -p 4242
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/37.png">

###### Mude para o user <kbd>ROOT</kbd>
>```sh
>su
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/38.png">

###### Abra o `sudo_config` para o configurar
>```sh
>vim /etc/sudoers.d/sudo_config
>``
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/39.png">

###### Adicione o seguinte comando ao arquivo e `salve-o`
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

###### Então digite `exit` > `exit` para fechar a conexão
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/41.png">

###### Retorne à VM e crie o seguinte diretório
>```sh
>mkdir /var/log/sudo
>``
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/42.png">

### Configurando a Política de Password
###### Abra o `login.defs`
>```sh
>vim /etc/login.defs
>``
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/43.png">

###### Set PASS_MAX_DAYSto 30;
###### Set PASS_MIN_DAYS to 2;
###### Set PASS_WARN_AGE to 7;
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/44.png">

###### Atualize a política de passwords do usuário já criado

>[!Note]
> ###### Os usuários existentes não receberam as alterações. Para confirmar, escreva o seguinte comando:
>```sh
>sudo chage -l <username>
>```
> <img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/45.png">

###### Para atualizar a política de senhas, digite os seguintes comandos:
>```sh
>chage -m <time> <username> 
># e
>chage -M <time> <username>
>```

>[!Note]
> ###### `-m` para mínimo de dias e `-M` para máximo de dias
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/46.png">

###### Instale o libpam-pwquality
>```sh
>sudo apt install libpam-pwquality
>```

>[!Note]
> ###### Quando perguntar para digitar `Y/N`, digite `Y`
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/47.png">

###### Configure o `libpam-pwquality`
>```sh
>sudo vim /etc/pam.d/common-password
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/48.png">

###### Na seção `per-package modules`, após `retry=3` adicione o seguinte como opções inline
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
###### Edite o arquivo crontab
>```sh
>sudo crontab -u root -e
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/50.png">

###### Para obter precisão nos 10minutos, adicione o seguinte comando:
>```sh
>*/10 * * * * sh /usr/local/bin/sleep.sh; sh /usr/local/bin/monitoring.sh
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/51.png">

###### Criar o script `sleep.sh`
>```sh
>touch /usr/local/bin/sleep.sh
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/52.png">

###### Abrir `sleep.sh` com o vim
>```sh
>vim /usr/local/bin/sleep.sh
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/53.png">

###### Adicionar o seguinte comando:
```bash
#!/bin/bash

sleep $(who -b | awk '{ split($4, time, ":"); print time[2]%10 }')m
```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/54.png">

###### Criar o script `monitoring.sh`
>```sh
>touch /usr/local/bin/monitoring.sh
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/55.png">

###### Retorne ao terminal fora da VM.
###### Conecte-se novamente via SSH
>```sh
>ssh <username>@localhost -p 4242
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/56.png">

###### Mude para o user <kbd>ROOT</kbd>
>```sh
>su
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/57.png">

###### Abra `monitoring.sh` com o vim
>```sh
>vim /usr/local/bin/monitoring.sh
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/58.png">

###### Adicione o codigo do script `monitoring`
>[!Note]
> ###### Você pode encontrar o script [aqui](https://github.com/AdaoG0n/42_Born2beroot/blob/main/script_en.md)<br/>
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/59.png">

###### Salve o arquivo e feche a conexão
>```sh
>exit
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/60.png">

###### Reinicie a VM
>```sh
>sudo reboot
>```
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/61.png">

###### Está feito. Agora o terminal deve exibir esta mensagem a cada 10 minutos
<img width="835" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/systemsetup/62.png">
