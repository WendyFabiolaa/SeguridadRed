## Objetivo
Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/89b371a46702a31aa9931a2a2b12f8bf/pico_img.png).

## Solución
```
┌──(kali㉿kali)-[~/picoctf]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/89b371a46702a31aa9931a2a2b12f8bf/pico_img.png' 
--2023-10-16 12:51:31--  https://jupiter.challenges.picoctf.org/static/89b371a46702a31aa9931a2a2b12f8bf/pico_img.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108795 (106K) [application/octet-stream]
Saving to: ‘pico_img.png’

pico_img.png             100%[=================================>] 106.25K   169KB/s    in 0.6s    

2023-10-16 12:51:32 (169 KB/s) - ‘pico_img.png’ saved [108795/108795]

                                                                                                   
┌──(kali㉿kali)-[~/picoctf]
└─$ exiftool -Artist pico_img.png
Artist                          : picoCTF{s0_m3ta_eb36bf44}
```

## Notas adicionales
- exiftool nos permite analizar los metadatos de diversos formatos de archivos.
## Referencias
