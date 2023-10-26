
## Objetivo
Decode this [message](https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav) from the moon.
## Solución

```
                                                                               
┌──(kali㉿kali)-[~/forensic/moonwalk]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav'
--2023-10-25 19:55:32--  https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 11066998 (11M) [application/octet-stream]
Saving to: ‘message.wav’

message.wav         100%[==================>]  10.55M  4.02MB/s    in 2.6s    

2023-10-25 19:55:36 (4.02 MB/s) - ‘message.wav’ saved [11066998/11066998]

                                                                               
┌──(kali㉿kali)-[~/forensic/moonwalk]
└─$ file message.wav 
message.wav: RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, mono 48000 Hz
                                                                               
┌──(kali㉿kali)-[~/forensic/moonwalk]
└─$ open message.wav 
                                                                               
┌──(kali㉿kali)-[~/forensic/moonwalk]
└─$ cd /opt    
                                                                               
┌──(kali㉿kali)-[/opt]
└─$ sudo git clone https://github.com/colaclanth/sstv.git           
[sudo] password for kali: 
Cloning into 'sstv'...
remote: Enumerating objects: 221, done.
remote: Counting objects: 100% (59/59), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 221 (delta 51), reused 49 (delta 49), pack-reused 162
Receiving objects: 100% (221/221), 1.01 MiB | 1.32 MiB/s, done.
Resolving deltas: 100% (139/139), done.
                                                                               
┌──(kali㉿kali)-[/opt]
└─$ cd sstv 
                                                                               
     Ejecutamos el script
┌──(kali㉿kali)-[/opt/sstv]
└─$ sudo python3 setup.py install


┌──(kali㉿kali)-[~/forensic/moonwalk]
└─$ sstv -d message.wav -o result.png 
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [#############################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!

                                                                               
┌──(kali㉿kali)-[~/forensic/moonwalk]
└─$ sstv -d message.wav -o result.png 
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [#############################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                               
┌──(kali㉿kali)-[~/forensic/moonwalk]
└─$ open result.png 

En la imágen viene la bandera: picoCTF{beep_boop_im_in_space}

```


## Notas adicionales
- sstv -d message.wav -o result.png 
-o en donde voy a guardar el resultado
-  Las señales estan decodificadas en sstv.
## Referencias
https://github.com/colaclanth/sstv 
Aqui instalamos la herramienta para 