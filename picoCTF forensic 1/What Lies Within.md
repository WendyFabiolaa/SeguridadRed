
## Objetivo
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?
## Solución
```
──(kali㉿kali)-[~/forensic/what]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png'
--2023-10-24 00:16:54--  https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 625219 (611K) [application/octet-stream]
Saving to: ‘buildings.png’

buildings.png       100%[==================>] 610.57K   482KB/s    in 1.3s    

2023-10-24 00:16:56 (482 KB/s) - ‘buildings.png’ saved [625219/625219]

                                                                               
┌──(kali㉿kali)-[~/forensic/what]
└─$ file buildings.png 
buildings.png: PNG image data, 657 x 438, 8-bit/color RGBA, non-interlaced
                                                                               
┌──(kali㉿kali)-[~/forensic/what]
└─$ open buildings.png

Nos vamos a la pagina para decodificar imagenes, abrimos la imagen y le damos en decodificar.
Nos arroja la bandera:
picoCTF{h1d1ng_1n_th3_b1t5}

```
## Notas adicionales
- Estenografía: una técnica de estenografía implica ocultar información sensitiva dentro de un archivo, mensaje o binario para no ser detectado.
- Hay diferentes tipos de estenografía: de texto, imágenes, audio, video, en los tonos de color, etc.
- 
## Referencia
https://stylesuxx.github.io/steganography/  Podemos encodificar y decodificar mensajes en archivos.