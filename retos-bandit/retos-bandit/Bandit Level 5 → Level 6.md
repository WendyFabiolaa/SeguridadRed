## Bandit Level 5 → Level 6
## Objetivo
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable
## Datos de acceso al nivel
```
bandit5
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```
## Solución
```bash
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere/
bandit5@bandit:~/inhere$ find . -readable -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
## Notas adicionales
- El comando ls -R te lista todas las carpetas y su contenido
- El comando find me permite encontrar un comando donde quiera que este.
- -size me permite encontrar el tamano de un archivo.
- -type me permite especificar que tipo de archivo estoy buscando
- man find es para buscar ayuda
- find --help es tambien para buscar ayuda pero no te muestra tan detalladamente
- 
## Referencias