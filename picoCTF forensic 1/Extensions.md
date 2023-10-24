## Objetivo 
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?
## Solución
```
┌──(kali㉿kali)-[~/forensic/extensions]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt'
--2023-10-24 00:09:51--  https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 9984 (9.8K) [application/octet-stream]
Saving to: ‘flag.txt’

flag.txt            100%[==================>]   9.75K  --.-KB/s    in 0s      

2023-10-24 00:09:53 (75.4 MB/s) - ‘flag.txt’ saved [9984/9984]

                                                                               
┌──(kali㉿kali)-[~/forensic/extensions]
└─$ ls                  
flag.txt
                                                                               
┌──(kali㉿kali)-[~/forensic/extensions]
└─$ mv flag.txt flag.png
                                                                               
┌──(kali㉿kali)-[~/forensic/extensions]
└─$ open flag.png
                                                                               
┌──(kali㉿kali)-[~/forensic/extensions]
└─$ 

Nos abre una imagen con la bandera
picoCTF{now_you_know_about_extensions}
```
## Notas adicionales
- El archivo descargado nos aparece como un archivo txt pero al preguntarle a linux con el comando file nos dice que es una imagen
- El formato ogg puede contener audio y video
- 
## Referencias
https://en.wikipedia.org/wiki/List_of_file_signatures lista de firmas es usada para identificar el contenido de varios archivos. estas firmas son conocidas como magic bytes.

