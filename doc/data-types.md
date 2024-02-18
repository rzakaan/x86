[Main Page](../README.md)

# Data Types

## Instrinsic Data Types

| Type    | Bit | Description         |
| ------- | --- | ------------------- |
| BYTE    |  8  |                     |
|  WORD   |  16 |                     |
|  DWORD  |  32 |                     |
|  QWORD  |  64 |                     |
|  TBYTE  |  80 |                     |
|  REAL4  |  4  | IEEE short real     |
|  REAL8  |  8  | IEEE long real      |
|  REAL10 |  10 | IEEE extended real  |

## Real Number

```asm
 S = Sign
 E = Exponent

  1     8               23
 ____________________________________
| S |   E    |           M           |
|___|________|_______________________|

1.bbbx2^(E-127)
```
