## Objetivo
We found this [file](https://mercury.picoctf.net/static/7b2d7c26630e977197022d0af09e3aeb/tunn3l_v1s10n). Recover the flag.
## Solución
```
┌──(kali㉿kali)-[~/forensic/tunel]
└─$ wget 'https://mercury.picoctf.net/static/7b2d7c26630e977197022d0af09e3aeb/tunn3l_v1s10n' 
--2023-10-31 01:34:01--  https://mercury.picoctf.net/static/7b2d7c26630e977197022d0af09e3aeb/tunn3l_v1s10n
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2893454 (2.8M) [application/octet-stream]
Saving to: ‘tunn3l_v1s10n’

tunn3l_v1s10n       100%[==================>]   2.76M  60.0KB/s    in 41s     

2023-10-31 01:34:43 (68.7 KB/s) - ‘tunn3l_v1s10n’ saved [2893454/2893454]

                                                                               
┌──(kali㉿kali)-[~/forensic/tunel]
└─$ file tunn3l_v1s10n          
tunn3l_v1s10n: data
                                                                               
┌──(kali㉿kali)-[~/forensic/tunel]
└─$ xxd tunn3l_v1s10n 

┌──(kali㉿kali)-[~/forensic/tunel]
└─$ mv tunn3l_v1s10n tunn3l_v1s10n.bmp 
┌──(kali㉿kali)-[~/forensic/tunel]
└─$ open tunn3l_v1s10n.bmp 
                                                                               
┌──(kali㉿kali)-[~/forensic/tunel]
└─$ exiftool tunn3l_v1s10n.bmp   
ExifTool Version Number         : 12.65
File Name                       : tunn3l_v1s10n.bmp
Directory                       : .
File Size                       : 2.9 MB
File Modification Date/Time     : 2021:03:15 14:24:47-04:00
File Access Date/Time           : 2023:10:31 01:52:41-04:00
File Inode Change Date/Time     : 2023:10:31 01:52:27-04:00
File Permissions                : -rw-r--r--
File Type                       : BMP
File Type Extension             : bmp
MIME Type                       : image/bmp
BMP Version                     : Unknown (53434)
Image Width                     : 1134
Image Height                    : 306
Planes                          : 1
Bit Depth                       : 24
Compression                     : None
Image Length                    : 2893400
Pixels Per Meter X              : 5669
Pixels Per Meter Y              : 5669
Num Colors                      : Use BitDepth
Num Important Colors            : All
Red Mask                        : 0x27171a23
Green Mask                      : 0x20291b1e
Blue Mask                       : 0x1e212a1d
Alpha Mask                      : 0x311a1d26
Color Space                     : Unknown (,5%()
Rendering Intent                : Unknown (826103054)
Image Size                      : 1134x306
Megapixels                      : 0.347
                                                                               

┌──(kali㉿kali)-[~/forensic/tunel]
└─$ hexeditor tunn3l_v1s10n.bmp 

Tenemos que cambirle el tamaño a la imagen y nos va a aparecer la bander en la partede arriba.
picoCTF{qu1t3_a_v13w_2020}
```

## Notas adicionales
exiftool muestra los metadatos

## Referencias

https://fileinfo.com/extension/bmp 
¿Qué es un BMP?