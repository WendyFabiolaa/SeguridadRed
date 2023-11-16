## Objetivo
What does asm3(0xd73346ed,0xd48672ae,0xd3c8b139) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/17c5620fcffa388fe518d31cb4dd99a0/test.S)
## Solución
```
                                                                           
┌──(kali㉿kali)-[~/asm3]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/17c5620fcffa388fe518d31cb4dd99a0/test.S'
--2023-11-16 11:33:40--  https://jupiter.challenges.picoctf.org/static/17c5620fcffa388fe518d31cb4dd99a0/test.S
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 286 [application/octet-stream]
Saving to: ‘test.S’

test.S             100%[===============>]     286  --.-KB/s    in 0s      

2023-11-16 11:33:41 (3.86 MB/s) - ‘test.S’ saved [286/286]

                                                                           
┌──(kali㉿kali)-[~/asm3]
└─$ cat test.S 
asm3:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   xor    eax,eax
        <+5>:   mov    ah,BYTE PTR [ebp+0xa]
        <+8>:   shl    ax,0x10
        <+12>:  sub    al,BYTE PTR [ebp+0xc]
        <+15>:  add    ah,BYTE PTR [ebp+0xd]
        <+18>:  xor    ax,WORD PTR [ebp+0x10]
        <+22>:  nop
        <+23>:  pop    ebp
        <+24>:  ret    

                                                                           
┌──(kali㉿kali)-[~/asm3]
└─$ 

Pegamos el codigo en el emulador
Eliminamos los numeros de linea

start:
	push 0xd3c8b139
	push 0xd48672ae
	push 0xd73346ed
	call asm3

asm3:
        push   ebp
        mov    ebp,esp
        xor    eax,eax
        mov    ah,BYTE PTR [ebp+0xa]
        shl    ax,0x10
        sub    al,BYTE PTR [ebp+0xc]
        add    ah,BYTE PTR [ebp+0xd]
        xor    ax,WORD PTR [ebp+0x10]
        nop
        pop    ebp
        ret    


abrimos una ventana para ver los registros
ejecutamos
y la bandera nos queda asi: 0xc36b
```
## Notas adicionales
- Aqui se hacen direccionamientos de 16 y 8 bits
- El resultado siempre queda en el registro eax
- El primero en entrar a la pila va a ser el ultimo parametro.
## Referencias
https://carlosrafaelgn.com.br/Asm86/ Emulador