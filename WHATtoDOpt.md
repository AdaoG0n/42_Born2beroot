## Links uteis 
[![Debian](https://img.shields.io/badge/Debian_iso-Download-D70A53?style=for-the-badge&logo=debian&logoColor=white)](https://cdimage.debian.org/mirror/cdimage/archive/10.10.0/amd64/iso-cd/debian-10.10.0-amd64-netinst.iso)  [![Virtual Box](https://img.shields.io/badge/VirtualBox-Download-183A61?logo=virtualbox&logoColor=white&style=for-the-badge)](https://www.virtualbox.org/wiki/Downloads)

# Configuração do Ambiente Virtual
> [!TIP]
> ###### Follow this guide  ➡️   [**SETUP VM**](https://github.com/AdaoG0n/42_Born2beroot/blob/main/SetupVM_pt.md)
> 
 ### Escolha e Instalação do Software de Virtualização:
> Utilize VirtualBox obrigatoriamente. Se você estiver em um Mac com chip M1, pode usar o UTM.

### Criação da Máquina Virtual:
> * Instale o sistema operacional escolhido (Debian ou Rocky Linux).


### Sistema Operacional:

> * Debian: Última versão estável é recomendada, especialmente se você é iniciante.
> * Rocky Linux: Última versão estável. Note que é mais complexo e requer configurações específicas como SELinux.

# Configuração do Sistema Operacional
> [!TIP]
> ###### Follow this guide  ➡️   [**Debian Install**](https://github.com/AdaoG0n/42_Born2beroot/blob/main/debianinstall_pt.md)
### Sem Interface Gráfica:
> Não instale X.org ou qualquer outro servidor gráfico. A interface será apenas de linha de comando.

## Segurança e Políticas:

### SELinux/AppArmor:
> * Rocky Linux: Habilite e configure SELinux para atender às necessidades do projeto.
> * Debian: Habilite e configure AppArmor.

### Particionamento:
> Crie pelo menos 2 partições criptografadas usando LVM (Logical Volume Manager).

# Configuração de Rede e Segurança
> [!TIP]
> ###### Follow this guide  ➡️   [**Configuração do sistema**](https://github.com/AdaoG0n/42_Born2beroot/blob/main/systemsetup_pt.md)
### Serviço SSH:
> * Configure o serviço SSH para operar na porta 4242.
> * Restrição: Não permita login como root via SSH.

### Firewall:
> * Debian: Use UFW (Uncomplicated Firewall).
> * Rocky Linux: Use firewalld.
> * Configure o firewall para que apenas a porta 4242 esteja aberta.
> * Assegure-se de que o firewall esteja ativo ao iniciar a máquina virtual.

### Hostname:
> Configure o hostname da máquina virtual para ser seu login seguido de 42 (exemplo: seuLogin42).

# Gestão de Usuários e Sudo

### Política de Senhas:
> * Senhas devem expirar a cada 30 dias.
> * Mínimo de 2 dias antes que uma senha possa ser alterada novamente.
> * Aviso de 7 dias antes da expiração da senha.
> * Senhas devem ter pelo menos 10 caracteres, incluindo letras maiúsculas, minúsculas e números.
> * Não devem conter mais de 3 caracteres idênticos consecutivos ou o nome do usuário.

### Usuários e Grupos:
> * Além do usuário root, crie um usuário com seu login que pertença aos grupos user42 e sudo.

### Configuração do Sudo:
> * Limite a 3 tentativas de autenticação para comandos sudo.
> * Configure uma mensagem personalizada para erros de autenticação.
> * Logs: Armazene logs das ações sudo em /var/log/sudo/.
> * Habilite o modo TTY para segurança.
> * Restrinja os caminhos que sudo pode utilizar (exemplo: /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin).

# Script de Monitoramento

 ### Criação do monitoring.sh:
> Escreva um script em bash que exiba informações do sistema em todos os terminais a cada 10 minutos usando o comando wall.

### Informações a Serem Exibidas:
> * Arquitetura do sistema e versão do kernel.
> * Número de processadores físicos e virtuais.
> * Memória RAM disponível e taxa de utilização.
> * Espaço de armazenamento disponível e taxa de utilização.
> * Utilização dos processadores.
> * Data e hora do último reboot.
> * Status do LVM.
> * Número de conexões ativas.
> * Número de usuários conectados.
> * Endereço IPv4 e endereço MAC do servidor.
> * Número de comandos executados com sudo.

### Configuração do Script:
> * Utilize cron para agendar a execução do script a cada 10 minutos.
> * Assegure-se de que o script funcione sem exibir erros e que possa ser interrompido durante a defesa sem modificações.

# Submissão e Avaliação

### Arquivo signature.txt:
> * Gere o hash SHA1 do arquivo de disco virtual da sua máquina (extensões .vdi ou .qcow2).
> * Insira este hash no arquivo signature.txt e faça o commit no repositório Git na raiz.

### Regras Importantes:
> * Não inclua a máquina virtual no repositório Git.
> * A assinatura será verificada durante a defesa. Assegure-se de que ela permaneça inalterada, duplicando a VM ou utilizando a opção de save state se necessário.

# Parte Bônus (Opcional)

### Tarefas Extras:
> * Configuração de partições conforme um esquema específico.
> * Configuração de um site WordPress utilizando lighttpd, MariaDB e PHP.
> * Configuração de um serviço adicional à sua escolha (excluindo NGINX/Apache2).

### Condições para Avaliação da Bônus:
> * A parte bônus só será avaliada se todas as requisitos obrigatórios estiverem perfeitamente atendidos.

### Resumo das Ações Necessárias:

> * Configurar a máquina virtual com Debian ou Rocky Linux sem interface gráfica.
> * Configurar segurança com SELinux/AppArmor, SSH na porta 4242, e firewall adequado.
> * Gerenciar usuários e políticas de senha conforme as diretrizes.
> * Criar e configurar scripts de monitoramento executados periodicamente.
> * Gerar e submeter a assinatura do disco virtual no repositório Git.
> * (Opcional) Implementar funcionalidades adicionais para a parte bônus.

# Dicas Finais:

> * Documentação: Mantenha um registro detalhado de todas as configurações realizadas. Isso será útil tanto para a defesa quanto para resolver possíveis problemas.
> * Testes: Certifique-se de que todas as configurações estão funcionando corretamente antes da submissão.
> * Segurança: Dê atenção especial às configurações de segurança, já que elas são críticas para o projeto.
> * Backup: Faça backups regulares da sua máquina virtual para evitar perdas de dados.
