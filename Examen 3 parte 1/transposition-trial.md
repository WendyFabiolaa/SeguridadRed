## Objetivo
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message.Download the corrupted message [here](https://artifacts.picoctf.net/c/191/message.txt).

## Solución
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V6E5926A}4

Pegué el texto en la herramienta para descifrar la bandera:

|0|1|2|
|---|---|---|
|h|e|T|
|f|l||
|g||a|
|s||i|
|i|c|p|
|C|T|o|
|{|7|F|
|4|N|R|
|P|0|5|
|1|N|5|
|_ |1|6|
|_ |3|5|
|P|3|X|
|5|1|N|
|3|_ |V|
|6|E|5|
|9|2|6|
|A|}|4|

Al descifrar nos queda algo así:

|2|0|1|
|---|---|---|
|T|h|e|
||f|l|
|a|g||
|i|s||
|p|i|c|
|o|C|T|
|F|{|7|
|R|4|N|
|5|P|0|
|5|1|N|
|6|_|1|
|5|_|3|
|X|P|3|
|N|5|1|
|V|3|_ |
|5|6|E|
|6|9|2|
|4|A|}|

El texto descifrado es:
The flag is picoCTF{7R4N5P051N6_15_3XP3N51V3_56E6924A}

## Notas adicionales
- En [criptografía](https://es.wikipedia.org/wiki/Criptograf%C3%ADa "Criptografía"), un **cifrado por transposición** es un tipo de [cifrado](https://es.wikipedia.org/wiki/Cifrado_(criptograf%C3%ADa) "Cifrado (criptografía)") en el que unidades de texto plano se cambian de posición siguiendo un [esquema](https://es.wikipedia.org/wiki/Esquema "Esquema") bien definido; las 'unidades de texto' pueden ser de una sola letra (el caso más común), pares de letras, tríos de letras, mezclas de lo anterior. Es decir, hay una [permutación](https://es.wikipedia.org/wiki/Permutaci%C3%B3n "Permutación") de 'unidades de texto
## Referencias
https://tholman.com/other/transposition/ Para descifrar la bandera