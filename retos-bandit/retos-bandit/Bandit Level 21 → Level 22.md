## Bandit Level 21 → Level 22
## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.
## Datos de acceso al nivel
```
bandit21 
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
```
## Solución
```cmd 
bandit21@bandit:~$ cat /etc/crontab
# /etc/crontab: system-wide crontab
# Unlike any other crontab you don't have to run the `crontab'
# command to install the new version when you edit this file
# and files in /etc/cron.d. These files also have username fields,
# that none of the other crontabs do.
SHELL=/bin/sh
# You can also override PATH, but by default, newer versions
inherit it from the environment
#PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin
# Example of job definition:
# .---------------- minute (0 - 59)
# | .------------- hour (0 - 23)
# | | .---------- day of month (1 - 31)
# | | | .------- month (1 - 12) OR jan,feb,mar,apr ...
# | | | | .---- day of week (0 - 6) (Sunday=0 or 7) OR
sun,mon,tue,wed,thu,fri,sat
# | | | | |
# * * * * * user-name command to be executed
17 * * * * root cd / && run-parts --report
/etc/cron.hourly
25 6 * * * root test -x /usr/sbin/anacron || (
cd / && run-parts --report /etc/cron.daily )
47 6 * * 7 root test -x /usr/sbin/anacron || (
cd / && run-parts --report /etc/cron.weekly )
52 6 1 * * root test -x /usr/sbin/anacron || (
cd / && run-parts --report /etc/cron.monthly )

#
bandit21@bandit:~$ ls -la /etc/cron.d
total 56
drwxr-xr-x 2 root root 4096 Jan 11 19:19 .
drwxr-xr-x 108 root root 12288 Jan 11 19:19 ..
-rw-r--r-- 1 root root 62 Jan 11 19:18 cronjob_bandit15_root
-rw-r--r-- 1 root root 62 Jan 11 19:18 cronjob_bandit17_root -rw-r--r-- 1 root root 120 Jan 11 19:18 cronjob_bandit22
-rw-r--r-- 1 root root 122 Jan 11 19:18 cronjob_bandit23 -rw-r--r-- 1 root root 120 Jan 11 19:18 cronjob_bandit24
-rw-r--r-- 1 root root 62 Jan 11 19:18 cronjob_bandit25_root
-rw-r--r-- 1 root root 201 Jan 8 2022 e2scrub_all -rwx------ 1 root root 52 Jan 11 19:19 otw-tmp-dir
-rw-r--r-- 1 root root 102 Mar 23 2022 .placeholder -rw-r--r-- 1 root root 396 Feb 2 2021 sysstat
bandit21@bandit:~$ ls /etc/cron.d
cronjob_bandit15_root cronjob_bandit17_root cronjob_bandit22
cronjob_bandit23 cronjob_bandit24 cronjob_bandit25_root
e2scrub_all otw-tmp-dir sysstat
bandit21@bandit:~$ cat /etc/cron.d/cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh #!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 >
/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
bandit21@bandit:~$ exit
```
## Notas adicionales
## Referencias
