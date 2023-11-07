## Objetivo 
Let's decrypt this: [ciphertext](https://jupiter.challenges.picoctf.org/static/ee7e2388b45f521b285334abb5a63771/ciphertext)? Something seems a bit small.
## Solución
```
┌──(kali㉿kali)-[~/miniRSA]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/ee7e2388b45f521b285334abb5a63771/ciphertext'
--2023-11-07 00:13:45--  https://jupiter.challenges.picoctf.org/static/ee7e2388b45f521b285334abb5a63771/ciphertext
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 884 [application/octet-stream]
Saving to: ‘ciphertext’

ciphertext         100%[================>]     884  --.-KB/s    in 0s      

2023-11-07 00:13:46 (15.4 MB/s) - ‘ciphertext’ saved [884/884]

                                                                            
  
┌──(kali㉿kali)-[~/miniRSA]
└─$ sudo python3 -m pip install gmpy2
[sudo] password for kali: 
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/PySoundFile-0.9.0.post1-py3.11.egg is deprecated. pip 23.3 will enforce this behaviour change. A possible replacement is to use pip for package installation..  
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/sstv-0.1-py3.11.egg is deprecated. pip 23.3 will enforce this behaviour change. A possible replacement is to use pip for package installation..                 
Collecting gmpy2                                                            
  Downloading gmpy2-2.1.5-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (1.8 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.8/1.8 MB 122.6 kB/s eta 0:00:00
Installing collected packages: gmpy2
Successfully installed gmpy2-2.1.5
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv       
                                                                            
┌──(kali㉿kali)-[~/miniRSA]
└─$ sudo python3 -m pip install pycryptodome
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/PySoundFile-0.9.0.post1-py3.11.egg is deprecated. pip 23.3 will enforce this behaviour change. A possible replacement is to use pip for package installation..  
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/sstv-0.1-py3.11.egg is deprecated. pip 23.3 will enforce this behaviour change. A possible replacement is to use pip for package installation..                 
Collecting pycryptodome                                                     
  Obtaining dependency information for pycryptodome from https://files.pythonhosted.org/packages/00/e6/73931df4046e34a6354d323b4a5b5c18e5184f4a08687806ee3353c81a6b/pycryptodome-3.19.0-cp35-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata
  Downloading pycryptodome-3.19.0-cp35-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (3.4 kB)
Downloading pycryptodome-3.19.0-cp35-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (2.1 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.1/2.1 MB 95.6 kB/s eta 0:00:00
Installing collected packages: pycryptodome
Successfully installed pycryptodome-3.19.0
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv       
                                                                            
┌──(kali㉿kali)-[~/miniRSA]
└─$ cat ciphertext

N: 29331922499794985782735976045591164936683059380558950386560160105740343201513369939006307531165922708949619162698623675349030430859547825708994708321803705309459438099340427770580064400911431856656901982789948285309956111848686906152664473350940486507451771223435835260168971210087470894448460745593956840586530527915802541450092946574694809584880896601317519794442862977471129319781313161842056501715040555964011899589002863730868679527184420789010551475067862907739054966183120621407246398518098981106431219207697870293412176440482900183550467375190239898455201170831410460483829448603477361305838743852756938687673
e: 3

ciphertext (c): 2205316413931134031074603746928247799030155221252519872649649212867614751848436763801274360463406171277838056821437115883619169702963504606017565783537203207707757768473109845162808575425972525116337319108047893250549462147185741761825125 

┌──(kali㉿kali)-[~]
└─$ python3
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from gmpy2 import * 
>>> from Crypto.Util.number import long_to_bytes
>>> 
>>> gmpy2.get_context().precision=2048
>>> e = 3
>>> c = 2205316413931134031074603746928247799030155221252519872649649212867614751848436763801274360463406171277838056821437115883619169702963504606017565783537203207707757768473109845162808575425972525116337319108047893250549462147185741761825125 
>>> 
>>> root, exact = iroot(c,e)
>>> root
mpz(13016382529449106065894479374027604750406953699090365388202874238148389207291005)
>>> print(long_to_bytes(root))
b'picoCTF{n33d_a_lArg3r_e_606ce004}'
>>> 

```
## Notas adicionales
- c - texto cifrado
- n - modulo
- e - exponente (llave publica) 2^16+1=65537
- Un exponente muy pequeño puede afectar  
- c = m^e mod n 
- c = m ^ 3
- m = 3 raiz c 

- la libreri gmpy2 es para utilizar numeros muy grandes con precision.
- 
## Referencias
https://simple.wikipedia.org/wiki/RSA_algorithm RSA