## Objetivo
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/b6205dd933ec01c022c4e6acbdf11116/dolls.jpg)
## Solución
```      
┌──(kali㉿kali)-[~/forensic/matryoshka]
└─$ wget 'https://mercury.picoctf.net/static/b6205dd933ec01c022c4e6acbdf11116/dolls.jpg' 
--2023-10-30 20:20:48--  https://mercury.picoctf.net/static/b6205dd933ec01c022c4e6acbdf11116/dolls.jpg
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 651630 (636K) [application/octet-stream]
Saving to: ‘dolls.jpg’

dolls.jpg           100%[==================>] 636.36K   607KB/s    in 1.0s    

2023-10-30 20:20:50 (607 KB/s) - ‘dolls.jpg’ saved [651630/651630]

                                                                               
┌──(kali㉿kali)-[~/forensic/matryoshka]
└─$ binwalk dolls.jpg      

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378950, uncompressed size: 383938, name: base_images/2_c.jpg
651608        0x9F158         End of Zip archive, footer length: 22

                                                                               
┌──(kali㉿kali)-[~/forensic/matryoshka]
└─$ binwalk -e  dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378950, uncompressed size: 383938, name: base_images/2_c.jpg
651608        0x9F158         End of Zip archive, footer length: 22

                                                                               
┌──(kali㉿kali)-[~/forensic/matryoshka]
└─$ ls                     
dolls.jpg  _dolls.jpg.extracted
                                                                               
┌──(kali㉿kali)-[~/forensic/matryoshka]
└─$ cd _dolls.jpg.extracted 
                                                                               
┌──(kali㉿kali)-[~/forensic/matryoshka/_dolls.jpg.extracted]
└─$ ls
4286C.zip  base_images
                                                                               
┌──(kali㉿kali)-[~/forensic/matryoshka/_dolls.jpg.extracted]
└─$ cd base_images         
                                                                               
┌──(kali㉿kali)-[~/forensic/matryoshka/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg
                                                                               
┌──(kali㉿kali)-[~/forensic/matryoshka/_dolls.jpg.extracted/base_images]
└─$ open 2_c.jpg   
                                                                               
┌──(kali㉿kali)-[~/forensic/matryoshka/_dolls.jpg.extracted/base_images]
└─$ binwalk 2_c.jpg        

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196043, uncompressed size: 201445, name: base_images/3_c.jpg
383805        0x5DB3D         End of Zip archive, footer length: 22
383916        0x5DBAC         End of Zip archive, footer length: 22

                                                                               
┌──(kali㉿kali)-[~/forensic/matryoshka/_dolls.jpg.extracted/base_images]
└─$ binwalk -e 2_c.jpg        

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196043, uncompressed size: 201445, name: base_images/3_c.jpg
383805        0x5DB3D         End of Zip archive, footer length: 22
383916        0x5DBAC         End of Zip archive, footer length: 22

                                                                               
┌──(kali㉿kali)-[~/forensic/matryoshka/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg  _2_c.jpg.extracted
                                                                               
┌──(kali㉿kali)-[~/forensic/matryoshka/_dolls.jpg.extracted/base_images]
└─$ cd _2_c.jpg.extracted  
                                                                               
┌──(kali㉿kali)-[~/…/matryoshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ cd base_images       
                                                                               
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ open 3_c.jpg 
                                                                               
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ binwalk -e 3_c.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77651, uncompressed size: 79809, name: base_images/4_c.jpg
201423        0x312CF         End of Zip archive, footer length: 22

                                                                               
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg  _3_c.jpg.extracted
                                                                               
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ cd _3_c.jpg.extracted 
                                                                               
┌──(kali㉿kali)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ cd base_images       
                                                                               
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls          
4_c.jpg
                                                                               
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ open 4_c.jpg

┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ binwalk -e 4_c.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v2.0 to extract, compressed                                                   
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ cd _4_c.jpg.extracted 
                                                                               
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls
136DA.zip  flag.txt
                                                                               
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ cat flag.txt                                              
picoCTF{4f11048e83ffc7d342a15bd2309b47de}                                                                               

```
## Notas adicionales
binwalk es para ver los archivos que pueden estar ocultos en la imagen
binwalk -e es para extraer 
## Referencias
