## Objetivo
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev_this). Can you reverse the flag.
## Solucion
```
┌──(kali㉿kali)-[~/reverseCipher]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev'                                           
--2023-11-22 22:55:52--  https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16856 (16K) [application/octet-stream]
Saving to: ‘rev’

rev                100%[===============>]  16.46K  --.-KB/s    in 0s      

2023-11-22 22:55:54 (166 MB/s) - ‘rev’ saved [16856/16856]

                                                                           
┌──(kali㉿kali)-[~/reverseCipher]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev_this' 
--2023-11-22 22:56:04--  https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev_this
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24 [application/octet-stream]
Saving to: ‘rev_this’

rev_this           100%[===============>]      24  --.-KB/s    in 0s      

2023-11-22 22:56:04 (33.8 MB/s) - ‘rev_this’ saved [24/24]
                                                                           
┌──(kali㉿kali)-[~/reverseCipher]
└─$ nano bandera.py

Dentro de bandera escribi el siguiente codigo:
cifrado = open('rev_this','r').read()  
print(cifrado)  
  
flag = ''  
  
for i in range(8, len(cifrado)-1):  
       if i & 1 == 0:  
               flag +=chr(ord(cifrado[i])-5)  
       else:  
               flag += chr(ord(cifrado[i])+2)  
  
print(flag)


Guarde y ejecute

┌──(kali㉿kali)-[~/reverseCipher]
└─$ python3 bandera.py 
picoCTF{w1{1wq84fb<1>49}
r3v3rs36ad73964

La bandera queda asi: picoCTF{r3v3rs36ad73964}
```
## Notas adicionales

## Referencias