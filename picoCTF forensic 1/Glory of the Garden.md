## Objetivo
This [garden](https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg) contains more than it seems.
## Solución
```
┌──(kali㉿kali)-[~/forensic/glory]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg'
--2023-10-23 21:17:33--  https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295192 (2.2M) [application/octet-stream]
Saving to: ‘garden.jpg’

garden.jpg          100%[==================>]   2.19M   375KB/s    in 7.6s    

2023-10-23 21:17:42 (295 KB/s) - ‘garden.jpg’ saved [2295192/2295192]

                                                                               
┌──(kali㉿kali)-[~/forensic/glory]
└─$ ls
garden.jpg
                                                                               
┌──(kali㉿kali)-[~/forensic/glory]
└─$ file garden.jpg  
garden.jpg: JPEG image data, JFIF standard 1.01, resolution (DPI), density 72x72, segment length 16, baseline, precision 8, 2999x2249, components 3
                                                                               
┌──(kali㉿kali)-[~/forensic/glory]
└─$ open garden.jpg                                           
                                                                               
┌──(kali㉿kali)-[~/forensic/glory]
└─$ hexeditor garden.jpg

ctrl + w 
buscamos por strings picoCTF

File: garden.jpg                 ASCII Offset: 0x0023056E / 0x00230597 (%100)  
00230560  72 65 20 69  73 20 61 20   66 6C 61 67  20 22 70 69  re is a flag "pi
00230570  63 6F 43 54  46 7B 6D 6F   72 65 5F 74  68 61 6E 5F  coCTF{more_than_
00230580  6D 33 33 74  73 5F 74 68   65 5F 33 79  33 65 42 64  m33ts_the_3y3eBd
00230590  42 64 32 63  63 7D 22 0A                             Bd2cc}".        


```
picoCTF{more_than_m33ts_the_3y3eBdBd2cc}


## Notas adicionales

- Editor hexadecimal: es un programa de computadora que permite la manipulación de los datos binarios fundamentales que constituyen un archivo de computadora.
- Estenografía: es la práctica de ocultar información dentro de otro mensaje u objeto físico para evitar su detección.
- ctrl + w sirve para hacer una busqueda.

## Referencias