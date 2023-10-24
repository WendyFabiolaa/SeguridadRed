## Objetivo 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag
## Solucion
```
┌──(kali㉿kali)-[~/forensic/shark]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap'
--2023-10-23 21:44:43--  https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 239455 (234K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap        100%[==================>] 233.84K   177KB/s    in 1.3s    

2023-10-23 21:44:45 (177 KB/s) - ‘capture.pcap’ saved [239455/239455]

                                                                               
┌──(kali㉿kali)-[~/forensic/shark]
└─$ file capture.pcap 
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)

Nos vamos al wireshark 
Abrimos el archivo que nos dieron 
Agarramos un paquete UDP, damos clic derecho, seleccionamos follow, UDP stream
Cambiamos de stream hasta que aparece la bandera.
picoCTF{StaT31355_636f6e6e}

```


## Notas adicionales
- Captura de paquetes: es un API que nos permite capturar trafico vivo de la red, paquetes de datos que van viajando de las capas 2 y 7 del modelo OSI
- Un archivo pcap es usado para ver trafico en el protocolo TCP/IP Y UDP
- Con el comando file nos muestra que tipo de archivo es.
- wireshark nos permite vaciar y analizar trafico de red, es una interfaz grafica, es una herramienta denominada analizador de protocolos.
- 
## Referencias

