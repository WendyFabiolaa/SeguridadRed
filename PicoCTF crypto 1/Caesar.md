## Objetivo
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext).
## Solución
```
                                                                               
┌──(kali㉿kali)-[~/crypto/caesar]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext'
--2023-11-02 01:54:11--  https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 35 [application/octet-stream]
Saving to: ‘ciphertext’

ciphertext          100%[==================>]      35  --.-KB/s    in 0s      

2023-11-02 01:54:12 (33.7 MB/s) - ‘ciphertext’ saved [35/35]

                                                                               
┌──(kali㉿kali)-[~/crypto/caesar]
└─$ cat ciphertext 
picoCTF{ynkooejcpdanqxeykjrbdofgkq} 

Nos vamos a cyberchef y pegamos el texto que viene dentro del formato de bandera que nos dio el archivo que descargamos 
le ponemos en decodificar en root13 y vemos que no tiene sentido, por lo tanto vamos rotando hasta que lo rotamos hasta que nos de sentido el resultado, en este caso fueron 3 veces y nos da esto:
crossingtherubiconvfhsjkou
picoCTF{crossingtherubiconvfhsjkou} 

```
## Notas adicionales
- El cifrado César, también conocido como cifrado por desplazamiento, es una de las formas más antiguas y sencillas de cifrar un mensaje.
Es un tipo de cifrado de sustitución en el que cada letra del mensaje original (que en criptografía se llama texto sin formato) se reemplaza con una letra correspondiente a un cierto número de letras desplazadas hacia arriba o hacia abajo en el alfabeto.

## Referencias
https://privacycanada.net/classical-encryption/caesar-cipher/ cifrado de cesar
