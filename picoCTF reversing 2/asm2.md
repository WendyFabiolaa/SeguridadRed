## Objetivo
What does asm2(0x4,0x2d) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/ceac75672637589213b952abe32c84b3/test.S)
## Solución
```
stack

[    ] < esp
[    ]  < ebp - oxc
[0xfe ]  < ebp - 0x8
[0x2d]  < ebp - 0x4
[ebp ]  < ebp
[ret ]  < ebp + 0x4
[0x4 ]  < ebp + 0x8
[0x2d] < ebp + 0xc

registros

[0x4 ] eax

asm2:(0x4,0x2d)
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp

        <+3>:   sub    esp,0x10
        <+6>:   mov    eax,DWORD PTR [ebp+0xc]
        <+9>:   mov    DWORD PTR [ebp-0x4],eax
        <+12>:  mov    eax,DWORD PTR [ebp+0x8]
        <+15>:  mov    DWORD PTR [ebp-0x8],eax
        <+18>:  jmp    0x50c <asm2+31>
        <+20>:  add    DWORD PTR [ebp-0x4],0x1
        <+24>:  add    DWORD PTR [ebp-0x8],0xd1
..      <+31>:  cmp    DWORD PTR [ebp-0x8],0x5fa1
        <+38>:  jle    0x501 <asm2+20>
        <+40>:  mov    eax,DWORD PTR [ebp-0x4]

        <+43>:  leave
        <+44>:  ret




┌──(kali㉿kali)-[~]
└─$ python3
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x4 <= 0x5fa1
True
>>> hex(0x4 + 0x1)
'0x5'
>>> hex(0x2d + 0x1)
'0x2e'
>>> hex(0x2d + 0xd1)
'0xfe'
>>> 0xfe <= 0x5fa1
True
>>> 0x5fa1 / 0xd1
117.13397129186603
Se redondea a 118
>>> int(0x2d)
45
>>> hex(45 + 118)
'0xa3'
>>> 


flag: 0xa3
```
## Notas adicionales
- Podemos acceder áreas de memoria sumando o restando apuntadores
- push mete información de la pila
- pop saca información de la pila
- jle salta si es menor e igual
- Cuando se hace un ciclo debemos dividir el valor al de que debemos llegar entre los aumentos.
## Referencias