
## Objetivo
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/2e739f9e0dc9f4c1556ea6b033c3ec8e/Forensics%20is%20fun.pptm)


## Solucion
```
┌──(kali㉿kali)-[~]
└─$ wget 'https://mercury.picoctf.net/static/2e739f9e0dc9f4c1556ea6b033c3ec8e/Forensics is fun.pptm'

┌──(kali㉿kali)-[~]
└─$ file Forensics\ is\ fun.pptm

┌──(kali㉿kali)-[~]
└─$ unzip Forensics\ is\ fun.pptm

En el visual studio code exploramos los archivos y encontramos el archivo hidden
Copiamos el texto que viene ahi que esta en base 64.

┌──(kali㉿kali)-[~/forensic/macro]
└─$ echo 'Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q' | tr -d " " | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: invalid input


```
picoCTF{D1}
## Notas adicionales

- Macrovirus: Un virus de macros es un virus informático que modifica o sustituye una macro. Esta, a su vez, es un conjunto de comandos que utilizan los programas para llevar a cabo acciones comunes.
- unzip a un archivo de word
Al desempaquetarlo encontramos una serie de archivos que podemos ver desde nuestro navegador de archivos.
- pptm es un archivo de power point 2007
cat hidden slideMaster1.xm
- └─$ sudo dpkg -i code_1.83.1-1696982868_amd64.deb 
	Este comando sirve para instalar una aplicacion
	
- code . es para abrir el visual en la carpeta en la que estamos en consola.
- └─$ echo 'R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q' | tr -d " " 
	con este comando eliminamos los espacios en blanco.


## Referencias
