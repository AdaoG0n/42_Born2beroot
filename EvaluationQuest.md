>[!Note]
>###### If something does not work as expected or is not clearly explained, stop evaluation.
>###### When you need help with checking something, the student `should be able` to help you.

### Preliminary tests
Git repo cloned successfully.

### General instructions
Git repo contains a signature.txt file.
Check the signature against the students “.vdi” file, make sure it’s identical. 
Clone VM || create a snapshot && open VM.

### Mandatory Part (Questions for the student)
How does a virtual machine work and what is its purpose?
```
Uma máquina virtual (VM) é um ambiente de computação que funciona como um sistema isolado com seus próprios recursos de CPU,
memória,interface de rede e armazenamento, criado a partir de um conjunto de recursos de hardware físico. Veja como ela
funciona e qual é seu propósito:
Funcionamento
Uma máquina virtual é essencialmente um software que emula um computador físico. Ela opera da seguinte forma:

    Um software chamado hipervisor é instalado no computador físico (host).
    O hipervisor gerencia os recursos de hardware e cria ambientes virtualizados isolados (as VMs).
    Cada VM recebe uma alocação de recursos virtuais como CPU, RAM, armazenamento e rede.
    Um sistema operacional é instalado dentro da VM, que funciona como se estivesse em um hardware dedicado.
    O hipervisor gerencia a comunicação entre as VMs e o hardware físico subjacente1
    2
    .

Propósito
As máquinas virtuais têm diversos propósitos e usos, incluindo:
Eficiência de recursos

    Permitem executar múltiplos sistemas operacionais e aplicações em um único servidor físico.
    Otimizam a utilização de hardware, economizando espaço e custos1
    3
    .

Isolamento e segurança

    Fornecem ambientes isolados para testar software ou analisar malware com segurança.
    Criam "sandboxes" para executar aplicações desconhecidas sem risco ao sistema host2
    .

Flexibilidade e portabilidade

    Facilitam a criação, cópia, movimentação e exclusão de ambientes computacionais.
    Permitem ajustar recursos alocados conforme necessário1
    3
    .

Desenvolvimento e testes

    Oferecem ambientes de desenvolvimento isolados para engenheiros.
    Facilitam testes em diferentes configurações de sistema2
    .

Recuperação de desastres

    Permitem criar snapshots para backup e recuperação rápida2
    .

Computação em nuvem

    São amplamente utilizadas por provedores de nuvem para oferecer recursos computacionais escaláveis3
    .

Casos de uso emergentes

    Computação de borda: executam aplicações próximas à fonte de dados.
    Gateways IoT: atuam como interface entre dispositivos IoT e a nuvem.
    IA e aprendizado de máquina: fornecem ambientes flexíveis para cargas de trabalho complexas2
    .

Em resumo, as máquinas virtuais oferecem uma maneira flexível, eficiente e segura de utilizar recursos
computacionais, permitindo que organizações otimizem sua infraestrutura de TI e adaptem-se rapidamente às
mudanças nas demandas de negócios.
```
The basic differences between CentOS and Debian?
```
As duas distribuições Linux, Rocky Linux e Debian, têm algumas diferenças importantes:
Origem e Filosofia

    Rocky Linux: É um fork do Red Hat Enterprise Linux (RHEL), criado como substituto do CentOS, focado em
estabilidade e compatibilidade empresarial1
    .
    Debian: É uma distribuição independente e de código aberto, mantida pela comunidade, com foco em
estabilidade e liberdade de software2
    .

Gerenciamento de Pacotes

    Rocky Linux: Usa o formato de pacote RPM e os gerenciadores YUM/DNF1
    .
    Debian: Utiliza o formato de pacote DEB e os gerenciadores dpkg/APT2
    .

Ciclo de Lançamento

    Rocky Linux: Oferece suporte de longo prazo, seguindo o modelo do RHEL1
    .
    Debian: Lança novas versões estáveis a cada 2 anos aproximadamente2
    .

Usabilidade

    Rocky Linux: Mais voltado para ambientes empresariais e servidores, pode ser mais complexo para iniciantes1
    .
    Debian: Oferece mais opções de personalização e pode ser mais amigável para usuários intermediários2
    .

Interface Gráfica

    Rocky Linux: Possui uma GUI personalizável, com opções como GNOME, KDE e XFCE1
    .
    Debian: Também oferece várias opções de ambiente de desktop, mas com uma abordagem mais minimalista por padrão.

Suporte e Comunidade

    Rocky Linux: Tem uma comunidade crescente, beneficiando-se da experiência de usuários CentOS3
    .
    Debian: Possui uma grande e diversificada comunidade de desenvolvedores e usuários2
    .

Foco de Uso

    Rocky Linux: Mais orientado para servidores e ambientes empresariais3
    .
    Debian: Versátil, adequado tanto para servidores quanto para desktops2
    .

Compatibilidade Empresarial

    Rocky Linux: Altamente compatível com ambientes RHEL, facilitando a migração de sistemas empresariais1
    3
    .
    Debian: Menos focado em compatibilidade RHEL, mas amplamente utilizado em diversos ambientes.

Em resumo, Rocky Linux é mais focado em estabilidade e compatibilidade com ambientes empresariais RHEL,
enquanto o Debian oferece mais flexibilidade e uma gama mais ampla de pacotes. A escolha entre eles
dependerá das necessidades específicas do usuário ou da organização, considerando fatores como experiência
prévia, requisitos de compatibilidade e preferências de gerenciamento de sistema.
```
Their choice of operating system?
```
Há várias razões para escolher o Debian como sistema operacional. Aqui estão alguns dos principais motivos:
Estabilidade e Confiabilidade
O Debian é conhecido por sua notável estabilidade. Cada versão passa por um rigoroso processo de testes antes do
lançamento, garantindo um sistema robusto e livre de bugs críticos1
2
. Isso o torna uma escolha excelente para servidores e ambientes de produção que exigem alta confiabilidade.
Software Livre e Código Aberto
O Debian é totalmente composto por software livre, seguindo uma filosofia de liberdade e transparência1
. Isso permite aos usuários executar, modificar e distribuir o software livremente, além de garantir a independência
de interesses comerciais.
Vasto Repositório de Software
O Debian oferece um dos maiores repositórios de software entre as distribuições Linux, com milhares de pacotes disponíveis2
. Isso significa que os usuários podem encontrar praticamente qualquer aplicação que necessitem sem recorrer a fontes externas.
Suporte de Longo Prazo
As versões estáveis do Debian recebem suporte por um longo período, incluindo atualizações de segurança2
. Isso proporciona uma base sólida para operações de longo prazo, especialmente importante em ambientes empresariais.
Flexibilidade e Personalização
O Debian pode ser adaptado para uma ampla gama de usos, desde servidores até desktops3
. Sua flexibilidade permite que seja configurado de acordo com necessidades específicas.
Segurança
O foco do Debian em segurança é notável. Vulnerabilidades são rapidamente identificadas e corrigidas, com atualizações
sendo disponibilizadas em poucos dias3
. O processo de desenvolvimento também prioriza a identificação e correção de problemas de segurança antes do lançamento
das versões estáveis.
Comunidade Ativa
O Debian possui uma grande e ativa comunidade de desenvolvedores e usuários. Isso resulta em um excelente suporte
comunitário e contínuo desenvolvimento do sistema2
.
Compatibilidade de Hardware
O Debian oferece suporte a uma ampla gama de arquiteturas de hardware, tornando-o versátil para diferentes tipos de equipamentos3
. Em resumo, o Debian é uma escolha excelente para quem busca um sistema operacional estável, seguro, flexível e com uma
forte base comunitária. É particularmente adequado para servidores e ambientes que requerem alta confiabilidade e suporte de longo prazo.
```
If CentOS: what SELinux and DNF are.
If Debian: the difference between aptitude, apt and what APPArmor is.
During the defense, a script must display all information every 10 minutes. Its operation will be checked in detail later.
All explanations are satisfactory (else evaluation stops here).

### Simple setup
Ensure that the machine does not have a graphical environment at launch.
Connect to VM as a created user (which isn’t a root)
Ensure the password follows the required policy (2 days min, 7, 30 days max). 
sudo chage -l username
Evaluator checks UFW service is started.
sudo ufw status			//look for status: active
Evaluator checks SSH service is started.
sudo systemctl status ssh

### Evaluator checks the chosen operating system (Debian or CentOS).
lsb_release -a || cat /etc/os-release

### User
The subject requests that a user with the login of the student being evaluated is present on the virtual machine. Check that it has been added and that it belongs to “sudo” and “user42” groups.
getent group sudo
getent group user42

### Password policy check:
Create new user (e.g. user42).
sudo adduser new_username
Assign a password of your choice, respecting subject rules.
getent group sudo
Explanation from student explaining how to implement the password policy. 
Normally there should be one or two modified files. If there is any problem, the evaluation stops here.
With the new user, ask the student to create a group named “evaluating” and assign it to the new user.
sudo groupadd evaluating
sudo usermod -aG evaluating your_new_username
Check if the new user belongs to the “evaluating” group.
getent group evaluating
Ask the student to explain advantages of the password policy (beyond the fact that it is required for the project) 
Ask the student the advantages/disadvantages of the policy implementation.

### Hostname and partitions
Check the hostname of the machine is correctly formatted as follows: login42 (login of the student being evaluated).
hostnamectl
Modify this hostname by replacing the login with yours, then restart VM.
sudo hostnamectl set-hostname new_hostname
sudo reboot
Note:	If on restart, the hostname has not been updated, the evaluation stops here.
Restore the machine to the original hostname, then restart VM.
sudo hostnamectl set-hostname new_hostname
sudo reboot
Ask the student being evaluated how to view the partitions for the VM.
lsblk
Compare the output with the example given in the subject (if there are bonuses, refer to the bonus example).
Ask the student for a brief explanation of LVM and how it works.

### SUDO
Check that the “sudo” program is properly installed on the virtual machine.
dpkg -l | grep sudo
The student being evaluated shows assigning a new user to the “sudo” group.
The subject imposes strict rules for sudo. The student being evaluated must explain the value and operation of sudo using examples of their choice.
sudo visudo ls
Second step, must show the implementation of the rules imposed by the subject.
Verify the “/var/log/sudo/” folder exists and has at least one file. Check the contents of the files in the folder, you should see a history of the commands used with sudo.
Run a command via sudo. See if the file(s) in the “/var/log/sudo/” folder have been updated.

### UFW
Check the “UFW” program is properly installed on the VM and works properly.
sudo ufw status numbered
Ask the student for a basic explanation of UFW and the value of using it.
List the active rules in UFW. A rule must exist for port 4242.
Add a new rule to open port 8080. Check that this one has been added by listing the active rules.
sudo ufw allow 8080
Delete this new rule with the help of the student being evaluated.
sudo ufw delete 4
sudo ufw delete 2

### SSH
Check that the SSH service is properly installed on the VM, and is working properly.
sudo service ssh status 			//check if its active and port 4242
Ask the student for an explanation of what SSH is and the value of using it. (answer: secure shell, allows 2 computers to securely talk to each other)
Verify that the SSH service only uses port 4242.
Ask the student to help you use SSH in order to log in with the newly created user. To do this, you can use a key or simple password, depending on the student being evaluated.
ssh new_user@127.0.0.1 -p 4242
Make sure you cannot use SSH with the “root” user as stated in the subject.
ssh amusso-g42@127.0.0.1 -p 4242 		//should come up as permission denied


### Script Monitoring (questions for the student)
Ask the student how their script works and see their code for it.
Script inputted in the monitoring .sh file to display system information
cd /usr/local/bin && vim monitoring.sh
What is “cron”?
How does the script run every 10 minutes from when the server starts?
Once correct functioning of the script is verified, ask the student to make sure the script runs with dynamic values correctly.
sudo crontab -u root -e (***change 10 value to 1***)
The student being evaluated should make the script stop running when the server has started up, without modifying the script itself. To check this, restart the VM.
sudo cronstop
sudo cronstart
At startup, check if the script still exists in the same place, the rights have remained unchanged and that it has not been modified.
sudo reboot
sudo crontab -u root -e
