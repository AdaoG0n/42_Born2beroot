# Configuração da Máquina Virtual

## Parte 1 - Iniciando sua Máquina Virtual

1. Pressione `Enter` em **Debian GNU/Linux**.
2. Digite sua senha de criptografia que você criou anteriormente.
3. Faça login como o nome de usuário que você criou anteriormente.

## Parte 2 - Configurando sua Máquina Virtual

### Parte 2.1 - Instalando o Sudo

1. Primeiro, digite:
    ```bash
    su
    ```
    para logar como usuário root.

2. Atualize os pacotes com:
    ```bash
    apt-get update -y
    ```

3. Faça a atualização do sistema:
    ```bash
    apt-get upgrade -y
    ```

4. Instale o sudo:
    ```bash
    apt install sudo
    ```

5. Criar um novo grupo chamado **user42**:
   ```bash
   sudo addgroup user42
   ```
   5.1. Para verificar se o grupo foi criado corretamente pode usar o comando
    ```bash
    getent group nome_grupo
    ```

6. Adicione seu usuário ao grupo sudo e user42:
<br/>⚠️ Tem de adicionar o utilizador a ambos os grupos (`user42` e `sudo`)
    ```bash
    sudo adduser username group
    
    EX: sudo adduser adamarqu user42
    ```
    6.1 Para verificar se o usuário está nos grupos, digite:
    ```bash
    getent group group_name
    
    EX: getent group sudo
    ```

### Parte 2.2 - Instalando Git e Vim

1. Para instalar o Git, digite:
    ```bash
    apt-get install git -y
    ```

2. Verifique a versão do Git:
    ```bash
    git --version
    ```

### Parte 2.3 - Instalando e Configurando o SSH

1. Instale o servidor SSH:
    ```bash
    sudo apt install openssh-server
    ```

2. Verifique o status do servidor SSH:
    ```bash
    sudo systemctl status ssh
    ```

3. Abra o arquivo de configuração do SSH:
    ```bash
    nano /etc/ssh/sshd_config
    ```

4. Encontre a linha `#Port 22` e altere para:
    ```plaintext
    Port 4242
    ```
    remova o `#`.
4.1 Encontre a linha `#PermitRootLogin` e altere para:
    ```plaintext
    PermitRootLogin no
    ```
    remova o `#`.

5. Salve e saia do nano.
<br/>`CTRL + O` para guardar
<br/>`CTRL + X` para sair

7. Reinicie o serviço SSH:
    ```bash
    sudo service ssh restart
    ```

8. Verifique se as configurações de porta estão corretas:
    ```bash
    sudo service ssh status
    ```
    Terá de aparecer `ative (Running)` a verde.

### Parte 2.4 - Instalando e Configurando UFW (Firewall Simples)

1. Instale o UFW:
    ```bash
    apt-get install ufw
    ```

2. Ative o UFW:
    ```bash
    sudo ufw enable
    ```

3. Verifique o status do UFW:
    ```bash
    sudo ufw status numbered
    ```

4. Configure as regras:
    ```bash
    sudo ufw allow ssh
    sudo ufw allow 4242
    ```

5. Verifique novamente o status do UFW:
    ```bash
    sudo ufw status numbered
    ```

## Parte 3 - Conectando via SSH

1. Para sair de sua Máquina Virtual e usar o mouse, pressione `Command` no seu teclado Apple, ou `ctrl direito` no ubuntu e o seu rato deve aparecer.
2. Vá para o seu programa VirtualBox.
3. Clique em sua Máquina Virtual e selecione **Configurações**.
4. Clique em **Rede**, depois **Adaptador 1**, em seguida **Avançado** e clique em **Reencaminhamento de Portas**.
5. Altere a Porta do Host e a Porta do Convidado para **4242**.
6. Volte para sua Máquina Virtual.
7. Reinicie o servidor SSH:
    ```bash
    sudo systemctl restart ssh
    ```
8. Verifique o status do SSH:
    ```bash
    sudo service sshd status
    ```

9. Abra um terminal (fora da VM) e digite:
    ```bash
    ssh your_username@127.0.0.1 -p 4242
    ```
10. Caso ocorra um erro, digite:
    ```bash
    rm ~/.ssh/known_hosts
    ```
    e tente novamente:
    ```bash
    ssh your_username@127.0.0.1 -p 4242
    ```
11. Por fim, digite `exit` para sair da conexão SSH.

## Parte 4 - Continuando a Configuração da Máquina Virtual

### Parte 4.1 - Configurando a Política de Senhas

1. Primeiro, instale a biblioteca de verificação da qualidade da senha:
    ```bash
    sudo apt-get install libpam-pwquality
    ```
<!--
	Configuração de senha forte para o sudo 🔒
1 ◦ Vamos criar um ficheiro no caminho /etc/sudoers.d/. Decidi chamar o meu ficheiro sudo_config, pois é aqui que a configuração da senha será armazenada. O comando exacto para criar o ficheiro é touch /etc/sudoers.d/sudo_config.
 
 Devemos criar o directório sudo no caminho /var/log porque cada comando que executamos com o sudo, tanto a entrada como a saída devem ser armazenadas nesse directório. Para o criar utilizaremos o comando mkdir /var/log/sudo.

Captura de pantalla 2022-07-14 a las 21 56 53

3 ◦ Devemos editar o ficheiro criado no passo 1. Como disse antes, pode usar qualquer editor que quiser, mas eu usarei nano. Comando para editar o ficheiro: nano /etc/sudoers.d/sudo_config.

Captura de pantalla 2022-07-14 a las 22 04 10

4 ◦ Uma vez editado o ficheiro, deve introduzir os seguintes comandos para cumprir todos os requisitos do subject.

3. Abra o arquivo de configuração da senha:
    ```bash
    nano /etc/pam.d/common-password
    ```

4. Encontre esta linha:
    ```plaintext
    password requisite pam_deny.so
    ``` 
5. Adicione o seguinte ao final da linha:
    ```plaintext
    minlen=10 ucredit=-1 lcredit=-1 dcredit=-1 maxrepeat=3 reject_username difok=7 enforce_for_root
    ```
6. A linha deve agora se parecer com isso:
    ```plaintext
      password       requisite         pam_pwquality.so retry=3 minlen=10 ucredit=-1 lcredit=-1 dcredit=-1 maxrepeat=3 reject_username difok=7 enforce_for_root
    ```

7. Salve e saia do nano.
A próxima coisa a fazer é voltar atrás e editar um ficheiro e modificar algumas linhas. Faremos nano /etc/pam.d/com palavras-passe comuns.

Captura de pantalla 2022-07-16 a las 3 27 02

5 ◦ Após nova tentativa=3, devemos acrescentar os seguintes comandos:

minlen=10
ucredit=-1
dcredit=-1
lcredit=-1
maxrepeat=3
reject_username
difok=7
enforce_for_root

➤ É assim que a linha deve ser ↙️

Screen Shot 2023-01-03 at 7 41 57 PM

➤ Esta é a aparência que deve ter no ficheiro ↙️

Captura de pantalla 2022-07-16 a las 3 38 08

🤔 O que cada comando does❓

minlen=10 ➤ O número mínimo de caracteres que a senha deve conter.

ucredit=-1 ➤ Deve conter pelo menos uma letra maiúscula. Colocamos o - como deve conter pelo menos um caracter, se colocarmos + queremos dizer no máximo esses caracteres.

dcredit=-1 ➤ Deve conter pelo menos um dígito.

lcredit=-1 ➤ Deve conter pelo menos uma letra minúscula.

maxrepeat=3 ➤ Não se pode ter o mesmo carácter mais de 3 vezes seguidas.

reject_username ➤ Não pode conter o nome do utilizador.

difok=7 ➤ Deve ter pelo menos 7 caracteres que não façam parte da senha antiga.

enforce_for_root ➤ Iremos implementar esta política para o utilizador de raiz.

6 ◦ A política de palavras-passe recentemente implementada afecta apenas os novos utilizadores. Portanto, é necessário atualizar as contas de utilizador que foram criadas antes desta política para cumprir os novos requisitos de segurança. Para verificar se o utilizador não está em conformidade com a política, vamos utilizar o comando sudo chage -l username.
-->

8. Em seguida, abra o arquivo de configuração de login:
    ```bash
    nano /etc/login.defs
    ```

9. Encontre a parte:
    ```plaintext
    PASS_MAX_DAYS 9999
    PASS_MIN_DAYS 0
    PASS_WARN_AGE 7
    ```
10. Mude para:
    ```plaintext
    PASS_MAX_DAYS 30
    PASS_MIN_DAYS 2
    ```
11. Mantenha `PASS_WARN_AGE 7` inalterado.
12. Por fim, digite:
    ```bash
    sudo reboot
    ```
    para reiniciar e aplicar as mudanças.
13. Atualizar as contas de utilizador que foram criadas antes.
    Para verificar:
    ```bash
    sudo chage -l username
    ```
    Caso o `minimum` e o `maximum number of days` **permaneça inalterado**, pode ser modificado com o seguinte comando:
    ```bash
    sudo chage -m <time> <username> y sudo chage -M <time> <username>
    ```
    `-m` muda o minimo e `-M` muda o máximo.

### Parte 4.4 - Criando `sudo.log`

1. Navegue até o diretório log:
    ```bash
    cd ~/../../
    ```

2. Acesse o diretório `/var/log`:
    ```bash
    cd var/log
    ```

3. Crie um diretório chamado `sudo` (se já existir, continue para o próximo passo):
    ```bash
    sudo mkdir sudo
    ```

4. Acesse o diretório `sudo` e crie um arquivo `sudo.log`:
    ```bash
    cd sudo && touch sudo.log
    ```

5. Retorne ao diretório anterior:
    ```bash
    cd ~/../
    ```

### Parte 4.5 - Configurando o Grupo Sudoers

1. Abra o arquivo sudoers:
    ```bash
    nano /etc/sudoers
    ```

2. Edite o arquivo sudoers para ficar assim:
    ```plaintext
    Defaults env_reset
    Defaults mail_badpass
    Defaults secure_path="/usr/local/sbin:/usr/local/bin:/usr/bin:/sbin:/bin"
    Defaults badpass_message="Password is wrong, please try again!"
    Defaults passwd_tries=3
    Defaults logfile="/var/log/sudo/sudo.log"
    Defaults log_input, log_output
    Defaults requiretty
    ```

### Parte 4.6 - Configuração do Crontab

1. Instale as ferramentas de rede:
    ```bash
    apt-get install -y net-tools
    ```

2. Navegue até `/usr/local/bin/`:
    ```bash
    cd /usr/local/bin/
    ```

3. Crie um script chamado `monitoring.sh`:
    ```bash
    touch monitoring.sh
    ```

4. Edite o script:
    ```bash
    nano monitoring.sh
    ```

type `chmod 777 monitoring.sh`
    ```bash
    chmod 777 monitoring.sh
    ```

entrar no terminal fora da vm

5. Adicione as seguintes linhas:
    ```bash
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

6. Lastly 

7. Salve e saia.

8. Torne o script executável:
    ```bash
    sudo chmod +x monitoring.sh
    ```

9. Edite o crontab:
    ```bash
    sudo crontab -e
    ```

10. Adicione a linha:
    ```plaintext
    */10 * * * * sh /caminho do script
    ```

### Parte 4.7 - Conclusão

Agora sua máquina virtual está configurada e pronta para ser usada! 
<br/>Certifique-se de testar as configurações que você fez e confirmar se tudo está funcionando como esperado.
