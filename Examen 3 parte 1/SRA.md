## Objetivo
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...Connect to the program on our server: `nc saturn.picoctf.net 54400`Download the program: [chal.py](https://artifacts.picoctf.net/c/297/chal.py)
## Solución
```
Creamos un archivo de python
con el siguiente codigo:

from pwn import *
import primefac
from itertools import combinations
from Crypto.Util.number import long_to_bytes

#function to generate all the sub lists
def sub_lists (l):
   # initializing empty list
    comb = []

    #Iterating till length of list
    for i in range(1,len(l)+1):
       # Generating sub list
        comb += [list(j) for j in combinations(l, i)]
   # Returning list
    return comb

def divisors(phi):
   print("Give me the divisors of ", phi-1)
  # this is dangerous, but I'm trusting me
   return(eval(input()))

#connect to the server
r = remote('saturn.picoctf.net', 62243)
#get ciphertext
r.recvuntil("anger =")
ciphertext=int(r.recvline())
#get d
r.recvuntil("envy =")
d=int(r.recvline())
print("cipher=",ciphertext)
print("d=",d)
print(r.recvuntil("vainglory?"))
r.recvline()
#since d is e^-1 mod (p-1)*(q-1), d*e=k*(p-1)*(q-1)+1
#so (p-1)*(q-1)*k = d*e-1
factors=divisors(d*65537)
combos = sub_lists(factors)
primes = set()
#try all possible subsets of the list of factors as the factors of (p-1)
for l in combos:
   product = 1
  # multiply them together to get p-1
   for k in l:
      product = product * k
  # if the right length and adding 1 yields a prime, then maybe
   if product.bit_length()==128 and primefac.isprime(product+1):
      primes.add(product+1)
print(primes)
primelist = list(primes)
#try all possible prime pairs
for p in primelist:
   for q in primelist:
      n=p*q
     # decode with this possible n
      plain = pow(ciphertext,d,n)
      try:
         plaintext = long_to_bytes(plain)
        # see if it corresponds to text and if so, try it
         print(plaintext.decode())
         r.sendline(plaintext.decode())
         print(r.recvline())
         print(r.recvline())
         print(r.recvline())
      except:
         continue


Ejecutamos el archivo:

┌──(kali㉿kali)-[~/SRA]
└─$ python3 exp.py      
[+] Opening connection to saturn.picoctf.net on port 60093: Done
/home/kali/SRA/exp.py:26: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("anger =")
/home/kali/SRA/exp.py:29: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("envy =")
cipher= 50968750307133899460353025471823032741303601723264473838217129979058257518400
d= 38212176510026943792397361325700040437878920747899406507266279034608786054769
/home/kali/SRA/exp.py:33: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("vainglory?"))
b'vainglory?'
Give me the divisors of  2504311411937635815322345869202403550177270829055083404266710129091156011671395952
[2, 2, 2, 2, 3, 7, 7, 7, 11, 17, 29, 127, 163, 199, 5261, 8834741, 11497268569, 29543256655611043, 431274520704061712692153200077]
{216430453550117435383072605129630417169, 300916183352097575963697494287674547769, 187457163792423438374826361581307029847, 202689378554071467860899018231647365689, 272112691918432327660274119743717319867, 225983351834066310094891846549553105383, 208232330309582684042804703420174719549, 315397320350614674981491772363615253963}
iGrFE5EnuJHcg2OL
/home/kali/SRA/exp.py:61: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.sendline(plaintext.decode())
iGrFE5EnuJHcg2OL
[*] Closed connection to saturn.picoctf.net port 60093
                                                                               
┌──(kali㉿kali)-[~/SRA]
└─$ nano exp.py
                                                                               
┌──(kali㉿kali)-[~/SRA]
└─$ python3 exp.py
[+] Opening connection to saturn.picoctf.net on port 62243: Done
/home/kali/SRA/exp.py:26: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("anger =")
/home/kali/SRA/exp.py:29: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("envy =")
cipher= 19121644812216084704896483964759158012847166986228342185190875848412557691254
d= 12526362978388659895492473230710800163153470489637743172370103389645082807953
/home/kali/SRA/exp.py:33: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("vainglory?"))
b'vainglory?'
Give me the divisors of  820940250514657603570890218121093710292588995479388774287619465847169791984815760
[2, 2, 2, 2, 3, 5, 7, 17, 41, 163, 4651, 8513, 668253953, 1222691083223, 65344245832189, 2034638607337160128234608172139]
{190604806258312669762752836850337644871, 231510861553315789598423858091658457363, 322237622949116186569585325148676787429, 306462629670228214128347698465248762341}
qIMH6h9sWRIuyXiM
/home/kali/SRA/exp.py:61: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.sendline(plaintext.decode())
b'> qIMH6h9sWRIuyXiM\r\n'
b'Conquered!\r\n'
b'picoCTF{7h053_51n5_4r3_n0_m0r3_38268294}\r\n'
qIMH6h9sWRIuyXiM
[*] Closed connection to saturn.picoctf.net port 62243
                                                                               
┌──(kali㉿kali)-[~/SRA]
└─$ 

Nos pide divisores lo cuales los podemos sacar con una herrramienta en internet.
Al introducirlos nos da la bandera:
picoCTF{7h053_51n5_4r3_n0_m0r3_38268294}
```

## Notas adicionales

## Referencias
https://www.dcode.fr/prime-factors-decomposition
