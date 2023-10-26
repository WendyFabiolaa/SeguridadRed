## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.
## Solución
```
                                                                               
┌──(kali㉿kali)-[~/forensic/shark2]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap'
--2023-10-25 20:20:29--  https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 112318 (110K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap        100%[==================>] 109.69K   467KB/s    in 0.2s    

2023-10-25 20:20:30 (467 KB/s) - ‘capture.pcap’ saved [112318/112318]

                                                                               
┌──(kali㉿kali)-[~/forensic/shark2]
└─$ file capture.pcap 
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)
                                                                               
┌──(kali㉿kali)-[~/forensic/shark2]
└─$ wireshark capture.pcap 

Seleccionamos un paquete UDP y le damos en seguir strings
en el paquete 32 vemos la palabra start
en el paquete 60 vemos la palabra end
Ambos paquetes comparten el puerto 32
Vamos a filtrar aquellos paquetes cuyo puerto sea el 22

Creamos un script
┌──(kali㉿kali)-[~/forensic/shark2]
└─$ nano exp.py


En es script va este codigo:

from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''
for p in packets:
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag +=  chr(p[UDP].sport - 5000)
print(flag)

ejecutamos 
┌──(kali㉿kali)-[~/forensic/shark2]
└─$ python3 exp.py
picoCTF{p1LLf3r3d_data_v1a_st3g0}
                                 
```
Tomamos un de los primeros paquetes UDP
## Notas adicionales
- Una captura de paquetes es el trafico de red que va viajando en aplicación de servidor.
- En el wireshark la primera columna es el numero de paquete
- 
## Referencias
https://scapy.net/
es modulo de manipulación de paquetes, es capaz de codificar en un amplio rango de protocolos