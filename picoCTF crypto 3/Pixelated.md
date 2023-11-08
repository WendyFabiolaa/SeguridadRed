## Objetivo
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/e8054e22552c6aba591cdf7440eb25e4/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/e8054e22552c6aba591cdf7440eb25e4/scrambled2.png)
## Solución 
```
                                                                           ┌──(kali㉿kali)-[~]
└─$ mkdir pixelated 
                                                                           
┌──(kali㉿kali)-[~]
└─$ cd pixelated 
                                                                           
┌──(kali㉿kali)-[~/pixelated]
└─$ wget 'https://mercury.picoctf.net/static/e8054e22552c6aba591cdf7440eb25e4/scrambled1.png'
--2023-11-08 10:50:39--  https://mercury.picoctf.net/static/e8054e22552c6aba591cdf7440eb25e4/scrambled1.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197173 (193K) [application/octet-stream]
Saving to: ‘scrambled1.png’

scrambled1.png     100%[===============>] 192.55K   157KB/s    in 1.2s    

2023-11-08 10:50:41 (157 KB/s) - ‘scrambled1.png’ saved [197173/197173]

                                                                           
┌──(kali㉿kali)-[~/pixelated]
└─$ wget 'https://mercury.picoctf.net/static/e8054e22552c6aba591cdf7440eb25e4/scrambled2.png'
--2023-11-08 10:50:49--  https://mercury.picoctf.net/static/e8054e22552c6aba591cdf7440eb25e4/scrambled2.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197172 (193K) [application/octet-stream]
Saving to: ‘scrambled2.png’

scrambled2.png     100%[===============>] 192.55K  56.0KB/s    in 3.4s    

2023-11-08 10:50:54 (56.0 KB/s) - ‘scrambled2.png’ saved [197172/197172]

                                                                           
┌──(kali㉿kali)-[~/pixelated]
└─$ open scrambled1.png 
                                                                           
┌──(kali㉿kali)-[~/pixelated]
└─$ cd ../opt   
cd: no such file or directory: ../opt
                                                                           
┌──(kali㉿kali)-[~/pixelated]
└─$ cd..     
cd..: command not found
                                                                           
┌──(kali㉿kali)-[~/pixelated]
└─$ cd ..    
                                                                           
┌──(kali㉿kali)-[~]
└─$ cd /opt
                                                                           
┌──(kali㉿kali)-[/opt]
└─$ sudo wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar 
[sudo] password for kali: 
--2023-11-08 10:53:36--  http://www.caesum.com/handbook/Stegsolve.jar
Resolving www.caesum.com (www.caesum.com)... 216.234.165.33
Connecting to www.caesum.com (www.caesum.com)|216.234.165.33|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 312271 (305K) [application/x-java-archive]
Saving to: ‘stegsolve.jar’

stegsolve.jar      100%[===============>] 304.95K  25.4KB/s    in 13s     

2023-11-08 10:53:50 (24.2 KB/s) - ‘stegsolve.jar’ saved [312271/312271]

                                                                           
┌──(kali㉿kali)-[/opt]
└─$ sudo chmod +x stegsolve.jar 
                                                                           


                                                                           
┌──(kali㉿kali)-[~]
└─$ cd pixelated
                                                                           
┌──(kali㉿kali)-[~/pixelated]
└─$ java -jar /opt/stegsolve.jar 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true

Nos aparece un una ventana, nos vamos a file y abrimos la primera imagen
luego nos vamos a analyse y seleccionamos la opcion de combinar imagen y abrimos la segunda imagen.
Vamos pasando las opciones con las flechas y en la opcion ADD nos aparece una imagen con la bandera.
picoCTF{d72ea4af}

```
## Notas adicionales
- **La criptografía visual** es una técnica [criptográfica](https://en.wikipedia.org/wiki/Cryptography "Criptografía") que permite cifrar información visual (imágenes, texto, etc.) de tal manera que la información descifrada aparezca como una imagen visual.
## Referencias
criptografía visual
https://en.wikipedia.org/wiki/Visual_cryptography 