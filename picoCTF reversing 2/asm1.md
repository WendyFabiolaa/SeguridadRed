## Objetivo
What does asm1(0x2e0) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/f1c2358ff7d1e9386e41552c549cf2f6/test.S)
## Solución
```
stack

0000

[ ebp ] <- esp
[ ret ] <- ebp + 0x4 
[0x2e0] <- ebp  + 0x8 
fffff

registers

[ 0x2e0 ] eax
asm1:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp

        <+3>:   cmp    DWORD PTR [ebp+0x8],0x3fb
        <+10>:  jg     0x512 <asm1+37>
        <+12>:  cmp    DWORD PTR [ebp+0x8],0x280
        <+19>:  jne    0x50a <asm1+29>
        <+21>:  mov    eax,DWORD PTR [ebp+0x8]
        <+24>:  add    eax,0xa
        <+27>:  jmp    0x529 <asm1+60>
        <+29>:  mov    eax,DWORD PTR [ebp+0x8]
        <+32>:  sub    eax,0xa
        <+35>:  jmp    0x529 <asm1+60>
        <+37>:  cmp    DWORD PTR [ebp+0x8],0x559
        <+44>:  jne    0x523 <asm1+54>
        <+46>:  mov    eax,DWORD PTR [ebp+0x8]
        <+49>:  sub    eax,0xa
        <+52>:  jmp    0x529 <asm1+60>
        <+54>:  mov    eax,DWORD PTR [ebp+0x8]

        <+57>:  add    eax,0xa
        <+60>:  pop    ebp
        <+61>:  ret    




>>> 0x2e0 > 0x3fb
False
>>> 0x2e0 > 0x280
True
>>> hex(0x2e0 - 0xa)
'0x2d6'
>>> 

flag: 0x2d6

```
## Notas adicionales
- lenguaje esamblador es una interfaz mas amigable que el código maquina.
- Los registros son espacios en la memoria para almacenar información temporal
- No puedo hacer operaciones por medio de direcciones de memoria, tengo que hacerlo por medio de registros.
- La pila o stack es el área de memoria que se crea cuando una función main manda llamar una subrutina.

## Referencias
https://www.tutorialspoint.com/assembly_programming/assembly_conditions.htm
