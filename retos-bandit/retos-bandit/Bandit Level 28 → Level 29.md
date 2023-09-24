## Bandit Level 28 → Level 29
## Objetivo
There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Clone the repository and find the password for the next level.
## Datos de acceso al nivel
```
-  bandit28
- Password: 0ef186ac70e04ea33b4c1853d2526fa2
```
## Solución
```cmd
bandit27@bandit: mkdir /tmp/bandit28
bandit27@bandit: cd /tmp/bandit28
bandit27@bandit/tmp/bandit-pass28$ cd repo/
bandit27@bandit/tmp/bandit-pass28/repo$ ls
bandit27@bandit/tmp/bandit-pass28/repo$ cat README
the password to the next level is: 0ef186ac70e04ea33b4c1853d2526fa2
```

## Notas adicionales
## Referencias