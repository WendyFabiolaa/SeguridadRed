## Objetivo
There is some interesting information hidden around this site [http://mercury.picoctf.net:39698/](http://mercury.picoctf.net:39698/). Can you find it?
## Solución
```
Entras al sitio web
Vas al codigo fuente
En un comentario encontramos la primer parte de la bandera: picoCTF{t
Vamos a la hoja de estilos y encontramos la parte 2: h4ts_4_l0
De aqui nos dirigimos a la url y colocamos al final robots.txt y nos aparece la parte 3 de la bandera: t_0f_pl4c 
Nos da una pista que dice "I think this is an apache server... can you Access the next flag?"
Nos dirigimos nuevamente a la url y al final colocamos el archivo .htaccess, aqui encontramos parte 4 de la bandera: 3s_2_lO0k
Nos da una nueva pista "# I love making websites on my Mac, I can Store a lot of information there."
Nos vamos otra vez a la url y al final colocamos .DS_Store y nos da la ultima parte de la bandera: Part 5: _fa04427c}
Finalmente juntamos todas las partes de la bandera y nos queda asi: 
picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_fa04427c}
```
## Notas adicionales
Hay ciertos archivos que por default estan en un servidor apache uno de ellos es el .htaccess
- En el contexto de las mac existe un archivo que se llama .DS_Store el cual almacena informacion de la configuracion de una carpeta, tal como los opciones de vista, la posicion de los iconos, entre otros
## Referencias
