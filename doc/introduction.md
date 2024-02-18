[Main Page](../README.md)

# Instruction

Assembled into machine code by assembler Executed at runtime by the CPU Member of the Intel IA-32 instruction set

## Labels

### Code Labels

It ends with colon. Target of jump and loop instruction.

>

```asm
L1: mov ax, bx
```

### Data Label

Must be unique

>

```asm
MYARR BYTE 10
```

## Reserved Words and Identifiers

Reserved words cannot be used as identifiers

- instruction mnemonic, directives, type attributes, operators, predifined symbols

Identifiers

- 1 - 247 characters, including digits
- case insensitive (by default)
- first character must be a letter \_ @ $

## Mnemonic

### Instrucion Mnemonic

Its reminder

>

```
MOV, ADD, SUB, MUL, INC, DEC
```

## Directive

Commands that are recognized and acted upon by the assembler

>

```asm
.data .code PROC
```

## Operand

## Comment

Single line comment

>

```asm
; comment
```

Block comment

>

```asm
COMMENT !
    multi
    comment line
!
```
