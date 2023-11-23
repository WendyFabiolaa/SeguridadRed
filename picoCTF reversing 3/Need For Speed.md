## Objetivo
The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://jupiter.challenges.picoctf.org/static/27dd5548b14661f65ce3ac6a8a8f575b/need-for-speed).
## Solución

```
                                                                          
┌──(kali㉿kali)-[~/NeedForSpeed]
└─$ wget https://jupiter.challenges.picoctf.org/static/27dd5548b14661f65ce3ac6a8a8f575b/need-for-speed
--2023-11-22 23:45:12--  https://jupiter.challenges.picoctf.org/static/27dd5548b14661f65ce3ac6a8a8f575b/need-for-speed
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8888 (8.7K) [application/octet-stream]
Saving to: ‘need-for-speed’

need-for-speed     100%[===============>]   8.68K  --.-KB/s    in 0s      

2023-11-22 23:45:13 (18.3 MB/s) - ‘need-for-speed’ saved [8888/8888]

                      

(gdb) disassemble main
Dump of assembler code for function main:
   0x000000000000091a <+0>:     push   rbp
   0x000000000000091b <+1>:     mov    rbp,rsp
   0x000000000000091e <+4>:     sub    rsp,0x10
   0x0000000000000922 <+8>:     mov    DWORD PTR [rbp-0x4],edi
   0x0000000000000925 <+11>:    mov    QWORD PTR [rbp-0x10],rsi
   0x0000000000000929 <+15>:    mov    eax,0x0
   0x000000000000092e <+20>:    call   0x8d8 <header>
   0x0000000000000933 <+25>:    mov    eax,0x0
   0x0000000000000938 <+30>:    call   0x82f <set_timer>
   0x000000000000093d <+35>:    mov    eax,0x0
   0x0000000000000942 <+40>:    call   0x87d <get_key>
   0x0000000000000947 <+45>:    mov    eax,0x0
   0x000000000000094c <+50>:    call   0x8ac <print_flag>
   0x0000000000000951 <+55>:    mov    eax,0x0
   0x0000000000000956 <+60>:    leave  
   0x0000000000000957 <+61>:    ret    
End of assembler dump.
(gdb) run  
Starting program: /home/tux3000-picoctf/need-for-speed 
warning: Error disabling address space randomization: Operation not permitted
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000055c0a720091e in main ()
(gdb) disassemble main
Dump of assembler code for function main:
   0x000055c0a720091a <+0>:     push   rbp
   0x000055c0a720091b <+1>:     mov    rbp,rsp
=> 0x000055c0a720091e <+4>:     sub    rsp,0x10
   0x000055c0a7200922 <+8>:     mov    DWORD PTR [rbp-0x4],edi
   0x000055c0a7200925 <+11>:    mov    QWORD PTR [rbp-0x10],rsi
   0x000055c0a7200929 <+15>:    mov    eax,0x0
   0x000055c0a720092e <+20>:    call   0x55c0a72008d8 <header>
   0x000055c0a7200933 <+25>:    mov    eax,0x0
   0x000055c0a7200938 <+30>:    call   0x55c0a720082f <set_timer>
   0x000055c0a720093d <+35>:    mov    eax,0x0
   0x000055c0a7200942 <+40>:    call   0x55c0a720087d <get_key>
   0x000055c0a7200947 <+45>:    mov    eax,0x0
   0x000055c0a720094c <+50>:    call   0x55c0a72008ac <print_flag>
   0x000055c0a7200951 <+55>:    mov    eax,0x0
   0x000055c0a7200956 <+60>:    leave  
   0x000055c0a7200957 <+61>:    ret    
End of assembler dump.
(gdb) call (int) get_key()
Creating key...
Finished
$1 = 9
(gdb) call (int) print_flag()
Printing flag:
PICOCTF{Good job keeping bus #1f2ac4ec speeding along!}
$2 = 56
(gdb) 


La bandera es: PICOCTF{Good job keeping bus #1f2ac4ec speeding along!}
```

## Notas adicionales
- podemos hacer un vaciado de memoria con objdump
- gdb es un depurador, ofrece la posibilidad de trazar y modificar la ejecucion de un programa.
## Referencias
