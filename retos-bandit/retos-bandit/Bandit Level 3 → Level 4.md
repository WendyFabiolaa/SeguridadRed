# Bandit Level 3 → Level 4
## Objetivo
The password for the next level is stored in a hidden file in the **inhere** directory.
## Datos de acceso al nivel
```
bandit3
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```
## Solución
```bash
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Apr 23 18:04 .
drwxr-xr-x 3 root    root    4096 Apr 23 18:04 ..
-rw-r----- 1 bandit4 bandit3   33 Apr 23 18:04 .hidden
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
bandit3@bandit:~/inhere$

```
## Notas adicionales
- Con ls -a mostramos los archivos ocultos
- Con cd abrimos un directorio
- Con ls .. nos muestra los archivos que estan en una carpeta atras del directorio

## Referencias
