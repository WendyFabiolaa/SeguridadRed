## Level 0
## Objetivo
El objetivo de thlevel es que inicies sesión en el juego usando SSH. El host al que necesita conectarse es bandit.labs.overthewire.org, en el puerto 2220. El nombre de usuario es bandit0 y la contraseña es bandit0. Una vez que haya iniciado sesión, vaya a la página de Nivel 1 para averiguar cómo superar el Nivel 1.
## Datos de acceso al nivel
```
Host: bandit.labs.overthewire.org
User: bandit0
Password: bandit0
Port: 2220
```

## Solución
``` cmd
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
## Notas adicionales
| Comando | Descripción |
|------------|--------------|
|pwd|Se indica en el directorio


## Referencias
- [Secure Shell (SSH) on Wikipedia](https://en.wikipedia.org/wiki/Secure_Shell)
- [How to use SSH on wikiHow](https://www.wikihow.com/Use-SSH)
