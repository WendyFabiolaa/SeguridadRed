## Objetivo
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 13758`.

## Solución
```
Nos conectamos al puerto
┌──(kali㉿kali)-[~/crypto/waves]
└─$ nc jupiter.challenges.picoctf.org 13758  
-------------------------------------------------------------------------------
kdablvnh wulu th odql xmvb - xluyquako_th_k_deul_mvpicv_caenxlnvoq
-------------------------------------------------------------------------------
wvetab wvc hdpu ntpu vn po cthfdhvm jwua ta mdacda, t wvc ethtnuc nwu iltnthw pqhuqp, vac pvcu huvlkw vpdab nwu iddsh vac pvfh ta nwu mtilvlo lubvlctab nlvahomevatv; tn wvc hnlqks pu nwvn hdpu xdlusadjmucbu dx nwu kdqanlo kdqmc wvlcmo xvtm nd wveu hdpu tpfdlnvaku ta cuvmtab jtnw v adimupva dx nwvn kdqanlo. t xtac nwvn nwu cthnltkn wu avpuc th ta nwu uznlupu uvhn dx nwu kdqanlo, rqhn da nwu idlculh dx nwluu hnvnuh, nlvahomevatv, pdmcvetv vac iqsdetav, ta nwu ptchn dx nwu kvlfvnwtva pdqanvtah; dau dx nwu jtmcuhn vac muvhn sadja fdlntdah dx uqldfu. t jvh adn vimu nd mtbwn da vao pvf dl jdls btetab nwu uzvkn mdkvmtno dx nwu kvhnmu clvkqmv, vh nwulu vlu ad pvfh dx nwth kdqanlo vh oun nd kdpfvlu jtnw dql dja dlcavaku hqleuo pvfh; iqn t xdqac nwvn ithnltng, nwu fdhn ndja avpuc io kdqan clvkqmv, th v xvtlmo jumm-sadja fmvku. t hwvmm uanul wulu hdpu dx po adnuh, vh nwuo pvo luxluhw po pupdlo jwua t nvms deul po nlveumh jtnw ptav.


┌──(kali㉿kali)-[~/crypto/waves]
└─$ nc jupiter.challenges.picoctf.org 13758 | xclip -selection c

lo que nos sale aqui lo pegmos en la pagina de guballa
nos da la bandera

```
## Notas adicionales
- En [criptografía](https://en.wikipedia.org/wiki/Cryptography "Criptografía") , un **cifrado de sustitución** es un método de [cifrado](https://en.wikipedia.org/wiki/Encrypting "Cifrado") en el que unidades de [texto sin formato](https://en.wikipedia.org/wiki/Plaintext "Texto sin formato") se reemplazan con el [texto cifrado](https://en.wikipedia.org/wiki/Ciphertext "Texto cifrado") , de manera definida, con la ayuda de una clave; las "unidades" pueden ser letras individuales (las más comunes), pares de letras, tríos de letras, mezclas de las anteriores, etc. El receptor descifra el texto realizando el proceso de sustitución inversa para extraer el mensaje original.
- 
## Referencias
https://en.wikipedia.org/wiki/Substitution_cipher cifrado de sustitucion
https://www.guballa.de/substitution-solver guballa
