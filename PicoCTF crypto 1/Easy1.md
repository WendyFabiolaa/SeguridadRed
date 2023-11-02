
## Objetivo

The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help `UFJKXQZQUNB` with the key of `SOLVECRYPTO`. Can you use this [table](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) to solve it?.

## Solución 
```
Desgargamos la tabla
En la tabla, vamos a buscar el primer caracter de la llave en la columna vertical y el caracter del cifrado en la columna horizontal y agarramos las letras de la parte de arriba en las que coinciden en cifrado con la llave.
Otra manera es usando el cyberchef, ponemos el cifraado y elegimos vigenere decode y en el ponemos la llave, y asi nos da como resultado: CRYPTOISFUN
Usando el formato de la bandera, nos queda asi: picoCTF{CRYPTOISFUN}
```
## Notas adicionales
- Libreta de un solo uso (one time pad) es una criptografía llamada de un solo uso, es un tipo de [algoritmos](https://es.wikipedia.org/wiki/Algoritmos "Algoritmos") de [cifrado](https://es.wikipedia.org/wiki/Cifrado_(criptograf%C3%ADa) "Cifrado (criptografía)") por el que el [texto en claro](https://es.wikipedia.org/wiki/Texto_en_claro "Texto en claro") se combina con una clave aleatoria o «libreta» igual de larga que el texto en claro y que sólo se utiliza una vez.
- El cifrado Vigenère es un cifrado basado en diferentes series de caracteres o letras del cifrado César formando estos caracteres una tabla, llamada tabla de Vigenère, que se usa como clave.
## Referencias 
https://es.wikipedia.org/wiki/Libreta_de_un_solo_uso one time pad 
https://gchq.github.io/CyberChef