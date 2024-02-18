[Main Page](../README.md)

# Addressing Mode

```asm

       Addressing
     /     Mode     \
    /       |        \
Register  Immediate  Memory
                       |
                      / \
               Direct     Indirect - Indexed
                         /    |   \
                 Register   Based   Based-Indexed
                 Indirect                |
                                        / \
                                   No       Diplacement
                               Diplacement

```

## Memory

### Direct Memory

A direct memory addressing mode is used when the effective address of a memory operand is obtained by

```asm
.data
var BYTE 10h,

.code
mov al, var
mov al, [var]
```

### Direct Offset

```asm
.data
arrayB BYTE 10h, 20h, 30h, 40h

.code
mov al, arrayB + 1   ; AL = 20h
mov al, [arrayB + 1] ; alternative notation
mov al, arrayB + 3   ; AL = 40h

```

### Indexed

### Indirect

### Regsiter Indirect

### Based

### Based Indexed
