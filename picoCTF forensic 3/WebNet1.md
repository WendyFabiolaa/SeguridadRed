## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.
## Solución
```
┌──(kali㉿kali)-[~/forensic/webnet1]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap' 
--2023-10-30 23:33:41--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 92525 (90K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap        100%[==================>]  90.36K  --.-KB/s    in 0.1s    

2023-10-30 23:33:42 (741 KB/s) - ‘capture.pcap’ saved [92525/92525]

                                                                               
┌──(kali㉿kali)-[~/forensic/webnet1]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key'
--2023-10-30 23:34:13--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key        100%[==================>]   1.66K  --.-KB/s    in 0s      

2023-10-30 23:34:14 (39.3 MB/s) - ‘picopico.key’ saved [1704/1704]

                                                                               
┌──(kali㉿kali)-[~/forensic/webnet1]
└─$ wireshark capture.pcap 
 ** (wireshark:150436) 23:36:34.360665 [GUI WARNING] -- FIX Add drag reordering to UAT dialog
 ** (wireshark:150436) 23:37:27.657796 [GUI WARNING] -- FIX Add drag reordering to UAT dialog

            
──(kali㉿kali)-[~/forensic/webnet1]
└─$ strings vulture.jpg
JFIF
Exif
picoCTF{honey.roasted.peanuts}

```
## Notas adicionales
- TLS se utiliza para descifrar trafico TCP
- Se utilizo el wireshark para este reto
## Referencias