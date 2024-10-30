# 🌀 Instalação do Debian
⚠️ Use a tecla `Command` no **macOS** ou a tecla `Right Ctrl` no **Ubuntu** para capturar ou liberar o mouse na máquina virtual.
<br/>⚠️ Para confirmar uma ação, pressione a tecla **Enter** e use as **Setas** para navegar pelas opções.

# Etapa 1: Preparação da Instalação

> ### Selecionar Versão Sem Interface Gráfica.
>> O projeto Born2beroot exige um ambiente apenas de linha de comando, então escolha a versão sem interface gráfica.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/1.png">

# Etapa 2: Seleção de Idioma e Localização

> ### Idioma da Instalação.
>> Escolha o idioma da instalação. O padrão é Inglês.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/2.png">

> ### Selecionar País e Continente.
>> Escolha seu país ou, se não estiver listado, use a opção "Other" para encontrar o continente e o país.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/3.png">

> ### É hora de selecionar um continente.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/4.png">

> ### Agora, selecione seu país na lista.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/5.png">

> ### Escolha Estados Unidos.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/6.png">

> ### Layout do Teclado.
>> Selecione o layout correto do teclado. Se você usa ANSI, selecione American English. <br/>
>> Se não tiver certeza sobre seu layout, consulte [Layouts de Teclado](https://keyshorts.com/blogs/blog/44712961-how-to-identify-laptop-keyboard-localization).
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/7.png">

# Etapa 3: Configuração de Hostname e Usuário

> ### Hostname.
>> Defina o hostname da máquina como seu login seguido de 42, conforme as diretrizes do projeto.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/8.png">

> ### Nome do Domínio.
>> Deixe este campo em branco, pois o projeto não menciona a necessidade de um domínio.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/9.png">

> ### Senha do Root.
>> Defina uma senha para o root (administrador do sistema) e lembre-se de anotá-la.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/10.png">

> ### Repita o processo novamente para garantir que a digitou corretamente.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/11.png">

> ### Criar Novo Usuário.
>> Crie um usuário adicional com seu login para uso "diário" (não root) e defina uma senha para ele.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/12.png">

> ### Insira a senha do novo usuário.
>> Recomendo sempre usar a mesma senha para facilitar e simplificar.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/14.png"><br/>
> Repita
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/15.png">

# Etapa 4: Configuração do Fuso Horário

> ### Selecionar o Fuso Horário.
>> Escolha a região correspondente ao seu país.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/16.png">

# Etapa 5: Particionamento do Disco

> ### Escolher Método de Particionamento.
>> Selecione “Guided - use entire disk and set up encrypted LVM” para configurar partições com LVM encriptado.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/17.png">

> ### Selecionar Disco.
>> Escolha o disco que deseja particionar (normalmente o único disponível).
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/18.png">

> ### Opção de Particionamento.
>> Escolha `Separate /home partition`.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/19.png">

> ### Escrever Alterações.
>> Selecione “Yes” para confirmar a gravação das alterações.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/20.png">

> ### Configuração do LVM.
>> Clique em “Cancel” para evitar a exclusão de dados no disco.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/21.png">

> ### Definir Senha de Encriptação.
>> Defina uma senha para a encriptação do disco e guarde-a para uso futuro.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/22.png">

> ### Alocar Espaço para o Volume Lógico.
>> Insira “max” ou o valor máximo mostrado para alocar todo o espaço.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/24.png">

# Etapa 6: Finalização do Particionamento

> ### Finalizar e Confirmar Alterações.
>> Selecione `Finish partitioning and write changes to disk` e confirme com `Yes`.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/25.png">

> ### Outras Alterações.
>> Escolha a opção `Yes` para continuar e confirmar que não deseja fazer mais alterações no disco.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/26.png">

# Etapa 7: Configuração de Pacotes

> ### Pacotes Adicionais.
>> Escolha a opção `No`, pois não precisamos de pacotes adicionais.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/27.png">

> ### Configurar Mirror do Debian.
>> Selecione seu país.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/28.png">

> ### Configurar Mirror do Debian.
>> Selecione o mirror `deb.debian.org`.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/29.png">

> ### Deixar Opção Proxy em Branco.
>> Pule a configuração do proxy deixando em branco e clicando em Continue.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/30.png">
<br/>

>> Escolha a opção `No`.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/31.png">

> ### Opções de Pacote.
>> Desmarque todas as opções de pacote usando a barra de espaço e clique em Continuar.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/32.png">

# Etapa 8: Instalação do GRUB Bootloader

> ### Opções de Pacote.
>> Desmarque todas as opções de pacote usando a barra de espaço e clique em Continuar.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/32.png">

> ### Instalar o GRUB.
>> Escolha “Sim” para instalar o GRUB no disco rígido.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/33.png">

> ### Selecionar Dispositivo de Inicialização.
>> Escolha o dispositivo `/dev/sda` para instalar o carregador de inicialização.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/34.png">

# Etapa 9: Finalização

> ### Completar Instalação.
>> Após a instalação do GRUB, selecione Continuar para finalizar o processo.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/35.png">

# Para continuar siga o guia seguinte:
### Configuração do sistema ➔ [🇬🇧](https://github.com/AdaoG0n/42_Born2beroot/blob/main/systemsetup_en.md) [🇵🇹](https://github.com/AdaoG0n/42_Born2beroot/blob/main/systemsetup_pt.md)
