### Get Signature

> Shut down the VM;

> Locate the path where the VM is stored;
> Run the following command to get the signature:
>```sh
>sha1sum <vm-name.vdi>
>```
![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/sign1.png)
![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/sign2.png)

> After obtaining the key, we need to create the file signature.txt
> ```sh
> echo <signature_key> > signature.txt
> ```
![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/sign3.png)

> Copy this file to your intra repository
![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/sign4.png)

> ![Warning]
> **Clone** the VM to avoid changing the obtained signature.
> For tests or training allways use the **cloned** VM.
