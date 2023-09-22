## Bandit Level 22 → Level 23
## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

## Datos de acceso al nivel
```
Datos de acceso: bandit22 - WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
```
## Solución
```cmd
bandit22@bandit:~$ cat /etc/bandit_pass/bandit
cat: /etc/bandit_pass/bandit: No such file or directory
bandit22@bandit:~$
bandit22@bandit:~$ ls /etc/cron.d
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23.sh
cat: /etc/cron.d/cronjob_bandit23.sh: No such file or directory
bandit22@bandit:~$
bandit22@bandit:~$ whoami
bandit22
bandit22@bandit:~$ myname=$(whoami)
bandit22@bandit:~$ echo $myname
bandit22
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ echo I am user $myname
I am user bandit22
bandit22@bandit:~$ echo I am user $myname |md5sum
8169b67bd894ddbb4412f91573b38db3  -
bandit22@bandit:~$ cat /tmp/8169b67bd894ddbb4412f91573b38db3
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
bandit22@bandit:~$
```

## Notas adicionales
- El cron es una forma de automatizar las tareas 
- Los ateriscos dicen que esos archivos se etan ejecutando cada minuto, cada segundo
- whaomi es para decir que usuario soy
- myname=$(whoami)  este comando quiere decir que a la variable le vamos a asignar el usuario que tenemos 
- /etc/bandit_pass es la carpeta en donde estan los password
- 

## Referencias