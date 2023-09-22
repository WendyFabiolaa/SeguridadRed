## Bandit Level 7 → Level 8
## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth**
## Datos de acceso al nivel
```
badit7
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```
## Solución
```cmd
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ grep millionth data.txt
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$

bandit7@bandit:~$ cat data.txt | grep millionth
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP



```
## Notas adicionales
- wc es para contarme las palabras
- nano es un editor de modo texto
- grep busca patrones en cada archivo
- | (pay) este caracter redirige la salida de un comando a otro comando.

## Referencias
   