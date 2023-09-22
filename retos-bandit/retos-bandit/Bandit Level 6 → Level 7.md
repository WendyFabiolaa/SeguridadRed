## Bandit Level 6 → Level 7
## Objetivo
The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size
## Datos de acceso al nivel
```
bandit6
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
## Solución
```cmd
bandit6@bandit:~$ find / -size 33c -user bandit7 -group bandit6 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
bandit6@bandit:~$

```
## Notas adicionales
tree nos muestra una especie de grafico de todos los directorios
find / -size busca en la raiz y size nos dice el tamaño del archivo
man find para ver el manual de find
-user sirve para especificar a que usuario pertence
-group sirve para especificar a que grupo pertenece
el 0 es input el 1 es output y el 2 es el error
2>/dev/null es para que no me muestre los mensajes de error

## Referencias
