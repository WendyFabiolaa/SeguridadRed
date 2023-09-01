## Bandit Level 2 → Level 3
## Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory
## Datos de acceso al nivel
```
bandit2
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```
## Solución
```bash
bandit2@bandit:~$ pwd
/home/bandit2
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat spaces in this filename
cat: spaces: No such file or directory
cat: in: No such file or directory
cat: this: No such file or directory
cat: filename: No such file or directory
bandit2@bandit:~$ cat "spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$ cat spaces\ in\ this\ filename
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$
```
## Notas adicionales
- Para abrir un archivo con espacios podemos poner cat enseguida de las primeras letras del archivo y dar tab.
- Tambien podemos poner cat y entre comillas el nombre del archivo.
## Referencias
[Google Search for “spaces in filename”](https://www.google.com/search?q=spaces+in+filename)