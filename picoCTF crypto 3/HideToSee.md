## Objetivo
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/236/atbash.jpg).
## Solución 
```
Descargamos la imagen
Nos vamos a Steganographic Decoder
Abrimos la imagen y le damos en enviar 
al decodificarla nos aparece esto: krxlXGU{zgyzhs_xizxp_zx751vx6}
Es algo similar al formato de la bandera
Nos vamos al cyberchef y pegamos krxlXGU{zgyzhs_xizxp_zx751vx6}
Elegimos atbash cipher para decodificar y obtenemos la bandera:
picoCTF{atbash_crack_ac751ec6}
```
## Notas adicionales
- **Atbash** es un método muy común de [cifrado (criptografía)](https://es.wikipedia.org/wiki/Cifrado_(criptograf%C3%ADa) "Cifrado (criptografía)") del [alfabeto hebreo](https://es.wikipedia.org/wiki/Alfabeto_hebreo "Alfabeto hebreo"). Pertenece a la llamada [criptografía clásica](https://es.wikipedia.org/wiki/Historia_de_la_criptograf%C3%ADa "Historia de la criptografía") y es un tipo de [cifrado por sustitución](https://es.wikipedia.org/wiki/Cifrado_por_sustituci%C3%B3n "Cifrado por sustitución"). Se le denomina también método de espejo, pues consiste en sustituir la primera letra ([álef](https://es.wikipedia.org/wiki/%D7%90 "א")) por la última ([tav](https://es.wikipedia.org/wiki/%D7%AA "ת")), la segunda ([bet](https://es.wikipedia.org/wiki/%D7%91 "ב")) por la penúltima ([shin](https://es.wikipedia.org/wiki/%D7%A9 "ש")) y así sucesivamente

## Referencias
https://futureboy.us/stegano/decinput.html Steganographic Decoder
https://es.wikipedia.org/wiki/Atbash Atbash
