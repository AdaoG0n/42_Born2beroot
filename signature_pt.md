### Obter Assinatura

> Desligue a VM;

> Localize o caminho onde a VM está armazenada;
> Execute o seguinte comando para obter a assinatura:
>```sh
>sha1sum <nome-da-vm.vdi>
>```
![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/sign2.png)

> Após obter a chave, precisamos criar o arquivo signature.txt
> ```sh
> echo <chave_da_assinatura> > signature.txt
> ```
![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/sign3.png)

Copie este arquivo para o seu repositório intra <br/>
![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/sign4.png) </br>


> [!Warning]
> **Clone** a VM para evitar alterar a assinatura obtida. </br>
> Para testes ou treinamento, use sempre a VM **clonada**.

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/animated%20gifs/madeby.gif)
