[Main Page](../README.md)

# Register

Modern (i.e 386 and beyond) x86 processors have eight 32-bit general purpose registers. The register names are mostly historical. For example, EAX used to be called the accumulator since it was used by a number of arithmetic operations, and ECX was known as the counter since it was used to hold a loop index. Whereas most of the registers have lost their special purposes in the modern instruction set, by convention, two are reserved for special purposes, the stack pointer (ESP) and the base pointer (EBP).

| x64 | x86 | 16  | 8     |     | Description                           |
| :-- | :-- | :-- | :---- | :-- | :------------------------------------ |
| rax | eax | ax  | ah,al |     | accumulator, arithmetic, return value |
| rbx | ebx | bx  | bh,bl |     | base reg, used as a pointer to data   |
| rcx | ecx | cx  | ch,cl |     | counter, shift/rotate loops           |
| rdx | edx | dx  | dh,dl |     | data, arithmetic, I/O operations      |
| -   | -   | -   |       |     | -                                     |
| rbp | ebp | bp  | bpl   |     | base of stack                         |
| rsp | esp | sp  | spl   |     | pointer to the top of stack pointer   |
| rsi | esi | si  | sil   |     | destination index                     |
| rdi | edi | di  | dil   |     | source index                          |

![](./x86-registers.png)

For the EAX, EBX, ECX, and EDX registers, subsections may be used. For example, the least significant 2 bytes of EAX can be treated as a 16-bit register called AX. The least significant byte of AX can be used as a single 8-bit register called AL, while the most significant byte of AX can be used as a single 8-bit register called AH. These names refer to the same physical register. When a two-byte quantity is placed into DX, the update affects the value of DH, DL, and EDX. These sub-registers are mainly hold-overs from older, 16-bit versions of the instruction set. However, they are sometimes convenient when dealing with data that are smaller than 32-bits (e.g. 1-byte ASCII characters).

When referring to registers in assembly language, the names are not case-sensitive. For example, the names EAX and eax refer to the same register.

- General registers (EAX EBX ECX EDX)
- Segment registers (CS DS ES FS GS SS)
- Index and pointers (ESI EDI EBP EIP ESP)
- CS --> Code segment (points to a segment in which the program code resides) 
- DS --> Data segment (points to a segment in which the program is expected to store its data)
- ES --> Extra segment register used for addressing memory without modifying other registers, for example DS.

## Segment Registers

| REG |     | Description     |
| :-- | :-- | :-------------- |
| CS  |     | Code Segment    |
| DS  |     | Data Segment    |
| SS  |     | Stack Segment   |
| ES  |     | Extra Segment   |
| FS  |     | More Extra Data |
| GS  |     | More Extra Data |

CS : Holds the Code segment in which your program runs. Changing its value might make the computer hang.

DS : Holds the Data segment that your program accesses. Changing its value might give erronous data.

ES, FS, GS : These are extra segment registers available for far pointer addressing like video memory and such.

SS : Holds the Stack segment your program uses. Sometimes has the same value as DS. Changing its value can give unpredictable results, mostly data related.

## EFLAG Registers

```asm
je rel8     ; equals ZF = 1
jz          ; zero   ZF = 1

js          ; sign SF = 1
jc          ; carry CF = 1
jg          ; greater ZF = 0, SF = 0
jo          ; overflow OF = 1
jp          ; parity PF = 1


```

| Index | REG | Description       |                        |
| :---- | :-- | :---------------- | :--------------------- |
| 0     | CF  | Carry Flag        | addition, substraction |
| 2     | PF  | Parity Flag       |                        |
| 4     | AF  | Adjust Flag.      | Adjust Flag.           |
| 6     | ZF  | Zero Flag         |                        |
| 7     | SF  | Sign Flag         | Negative Value         |
| 8     | TF  | Trap Flag         | Debug                  |
| 9     | IF  | Interruption Flag |                        |
|       |     |                   |                        |
