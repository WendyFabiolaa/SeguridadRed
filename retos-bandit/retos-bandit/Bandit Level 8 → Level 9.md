## Bandit Level 8 → Level 9
## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once
## Datos de acceso al nivel
```
bandit8
TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```
## Solución
```cmd
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ wc data.txt
1001 1001 33033 data.txt
bandit8@bandit:~$ cat data.txt | sort | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit8@bandit:~$
```

## Notas adicionales
- paping es decir la salida de un comando se la mando a otro y para esto se utiliza | la barra vertical.
- Para redirigir una salida a un archivo se utiliza el signo de > mayor que.
- sort es un comando que ordena
- uniq nos cuenta cuantas lineas hay repetidas
## Referencias