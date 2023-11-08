## Objetivo
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/2604f8b51a5cc62d38a3736938f19cef/values)
## Solución 
```
                                                                           
┌──(kali㉿kali)-[~/MindYourPs]
└─$ wget 'https://mercury.picoctf.net/static/2604f8b51a5cc62d38a3736938f19cef/values' 
--2023-11-08 09:59:34--  https://mercury.picoctf.net/static/2604f8b51a5cc62d38a3736938f19cef/values
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 206 [application/octet-stream]
Saving to: ‘values’

values             100%[===============>]     206  --.-KB/s    in 0s      

2023-11-08 09:59:37 (60.8 MB/s) - ‘values’ saved [206/206]

                                                                           
┌──(kali㉿kali)-[~/MindYourPs]
└─$ cat values    
Decrypt my super sick RSA:
c: 861270243527190895777142537838333832920579264010533029282104230006461420086153423
n: 1311097532562595991877980619849724606784164430105441327897358800116889057763413423
e: 65537                                                                           
┌──(kali㉿kali)-[~/MindYourPs]
└─$ python3                          
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> c = 861270243527190895777142537838333832920579264010533029282104230006461420086153423
>>> e = 65537
>>> p = 1955175890537890492055221842734816092141
>>> q = 670577792467509699665091201633524389157003
>>> n = p * q
>>> n
1311097532562595991877980619849724606784164430105441327897358800116889057763413423
>>> tn = (p-1)*(q-1)
>>> d = inverse(e,tn)
>>> m = pow(c,d,n)
>>> m
13016382529449106065927291425342535437996222135352905256639573959002849415739773
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_13686679}'

```
## Notas adicionales
c - texto cifrado
n - modulo que comparte la llave publica y la llave privada 
e - exponente publico o llave publica que generalmente es 65537
- Cuando n tiene un valor pequeño puede ser factorizado
- Factorizarlo significa que a partir de n podamos obtener p y q
## Referencias
http://factordb.com/index.php?id=1100000002524435575 factorizar
https://github.com/RsaCtfTool/RsaCtfTool  RsaCtfTool