# Instruction Set

Machine instructions generally fall into three categories: data movement, arithmetic/logic, and control-flow. In this section, we will look at important examples of x86 instructions from each category. This section should not be considered an exhaustive list of x86 instructions, but rather a useful subset.

We use the following notation:

- `<reg32>` Any 32-bit register (EAX, EBX, ECX, EDX, ESI, EDI, ESP, or EBP)
- `<reg16>` Any 16-bit register (AX, BX, CX, or DX)
- `<reg8>` Any 8-bit register (AH, BH, CH, DH, AL, BL, CL, or DL)
- `<reg>` Any register
- `<mem>` A memory address (e.g., [eax], [var + 4], or dword ptr [eax+ebx])
- `<con32>` Any 32-bit constant
- `<con16>` Any 16-bit constant
- `<con8>` Any 8-bit constant
- `<con>` Any 8-, 16-, or 32-bit constant

## Data Movement

### MOV - Move

The mov instruction copies the data item referred to by its second operand (i.e. register contents, memory contents, or a constant value) into the location referred to by its first operand (i.e. a register or memory). While register-to-register moves are possible, direct memory-to-memory moves are not. In cases where memory transfers are desired, the source memory contents must first be loaded into a register, then can be stored to the destination memory address.

Syntax

```asm
mov <reg>, <reg>
mov <reg>, <mem>
mov <mem>, <reg>
mov <mem>, <const>
mov <reg>, <const>
```

Examples

```asm
mov eax, ebx           ; copy the value in ebx into eax
mov byte ptr [var], 5  ; store the value 5 into the byte at location var
```

### PUSH - Push stack

The push instruction places its operand onto the top of the hardware supported stack in memory. Specifically, push first decrements ESP by 4, then places its operand into the contents of the 32-bit location at address [ESP]. ESP (the stack pointer) is decremented by push since the x86 stack grows down - i.e. the stack grows from high addresses to lower addresses.

Syntax

```asm
push <reg32>
push <mem>
push <con32>
```

Examples

```asm
push eax     ; push eax on the stack
push [var]   ; push the 4 bytes at address var onto the stack
```

### POP — Pop stack

The pop instruction removes the 4-byte data element from the top of the hardware-supported stack into the specified operand (i.e. register or memory location). It first moves the 4 bytes located at memory location [SP] into the specified register or memory location, and then increments SP by 4.

Syntax

```asm
pop <reg32>
pop <mem>
```

Examples

```asm
pop edi     ; pop the top element of the stack into EDI.
pop [ebx]   ; pop the top element of the stack into memory at the four bytes starting at location EBX.
```

### LEA - Load Effective Address

The lea instruction places the address specified by its second operand into the register specified by its first operand. Note, the contents of the memory location are not loaded, only the effective address is computed and placed into the register. This is useful for obtaining a pointer into a memory region.

Syntax

```asm
lea <reg32>, <mem>
```

Examples

```asm
lea edi, [ebx+4*esi]  ; the quantity EBX+4*ESI is placed in EDI.
lea eax, [var]        ; the value in var is placed in EAX.
lea eax, [val]        ; the value val is placed in EAX.
```

---

## Links

[Wikipedia Instruction Listings](https://en.wikipedia.org/wiki/X86_instruction_listings)

[Intel IA-32 Architecture Manuels](https://www.intel.com/content/www/us/en/developer/articles/technical/intel-sdm.html)

```

```
