[Main](../README.md)

# BIOS Interrupts
The interrupt number must be between 0 and 255 (0x00 - 0xFF)

Syntax
```asm
mov ah, <function>
mov al, <data>
int <interrupt>
```

BIOS Interrupt Table
| Interrupt | ah | al | Description|
| :- | :- | :- | :- |
| 05h |     |     | Executed when Shift-Print screen is pressed, as well as when the BOUND instruction detects a bound failure
| 08h |     |     | This is the real time clock interrupt. It fires 18.2 times/second. The BIOS increments the time-of-day counter during this interrupt
| 09h |     |     | Keyboard interrupt. This is generally triggered when a key on a keyboard is pressed
|     |     |     |
|     |     |     | **Video Services**
|     | 00h |     | set video mode
|     | 01h |     | set cursor shape
|     | 02h |     | set cursor position
|     | 03h |     | get cursor position and shape
|     | 04h |     | get light pen position
|     | 05h |     | set display page
|     | 06h |     | clear / scroll screen up
|     | 07h |     | clear / scroll screen down
|     | 08h |     | read  character and attribute at cursor
|     | 09h |     | write character and attribute at cursor
|     | 0Ah |     | write character at cursor
|     | 0Bh |     | set border color
| 10h | 0Ch |     |write graphics pixel
|     | 0Dh |     | read  graphics pixel
|     | 0Eh |     | write character at TTY mode
|     | 0Fh |     | get video mode
|     | 10h |     | set paletta register (EGA/VGA/SVGA)
|     | 11h |     | character generator
|     | 12h |     | alternate select functions (EGA/VGA/SVGA)
|     | 13h |     | writing string
|     | 1Ah |     | get or set display combination code (VGA / SVGA)
|     | 1Bh |     | get functionality information (VGA / SVGA)
|     | 1Ch |     | save or restore video state (VGA / SVGA)
|     | 4Fh |     | VESA BIOS Extension Function (VGA / SVGA)
| 11h |     |     | return equipment list
| 12h |     |     | return conventional memory size
|     |     |     |
| 13h |     |     | **lov level disk Services**
|     | 00h |     | reset disk drives
|     | 01h |     | check drive status
|     | 02h |     | read sector
|     | 03h |     | write sector
|     | 04h |     | verify sector
|     | 05h |     | format track
|     | 08h |     | get drive parameters
|     | 09h |     | init fixed drive parameters
|     | 0Ch |     | seek to specified track
|     | 0Dh |     | reset fixed disk controller
|     | 15h |     | get drive type
|     | 16h |     | get floppy drive media change status
|     | 17h |     | set disk type
|     | 18h |     | set floppy drive media type
|     | 41h |     | extended disk drive (EDD) installation check
|     | 42h |     | extended read sectors 
|     | 43h |     | extended write sectors 
|     | 44h |     | extended verify sectors 
|     | 45h |     | lock/unlock drive
|     | 46h |     | eject media
|     | 47h |     | extended seek
|     | 48h |     | extended get drive parameters
|     | 49h |     | extended get media change status
|     | 4Eh |     | extended set hardware configuration
|     |     |     |
| 14h |     |     | **serial port services**
|     | 00h |     | serial port initialization
|     | 01h |     | transmit character
|     | 02h |     | receive character
|     | 03h |     | status
|     |     |     |
| 15h |     |     | **miscellaneous system services**
|     | 00h |     | turn on  casette drive motor (IBM PC/PCjr)
|     | 01h |     | turn off casette drive motor (IBM PC/PCjr)
|     | 02h |     | read data blocks from casettte (IBM PC/PCjr)
|     | 03h |     | write data blocks to casettte (IBM PC/PCjr)
|     | 4Fh |     | keyboard intercept
|     | 83h |     | event wait
|     | 84h |     | read joystick
|     | 85h |     | sysreq key callout
|     | 86h |     | wait
|     | 87h |     | move block
|     | 88h |     | get extended memory size
|     | 89h |     | switch protected mode 
|     | C0h |     | get system parameters
|     | C1h |     | get extended BIOS data area segment
|     | C2h |     | pointing device functions
|     | C3h |     | watchdog timer functions - PS/2 system only
|     | C4h |     | programmable option select - MCA bus PS/2 systems only
|     | D8h |     | EISA system functions - EISA bus systems only
|     | E8h | 01h | get extended memory size. give results for memory size above 64mb 
|     | E8h | 20h | query system address map. the information resturned from E820 supersedes what is resturned from the older AX=E801h AH 88h interfaces
|     |     |     |
| 16h |     |     | **keyboard services**
|     | 00h |     | read character
|     | 01h |     | read input status
|     | 02h |     | read keyboard shift status
|     | 05h |     | store keystroke in keyboard buffer
|     | 10h |     | read character extended
|     | 11h |     | read input status extended
|     | 12h |     | read keyboard shift status extended
|     |     |     |
| 17h |     |     | **printer services**
|     | 00h |     | print character to printer
|     | 01h |     | init printer
|     | 02h |     | check printer status
|     |     |     |
| 18h |     |     | execute casette BASIC
| 19h |     |     |
| 1Ah |     |     | real time clock services
|     |     |     |
|     | 00h |     | read RTC
|     | 01h |     | set RTC
|     | 02h |     | read RTC time
|     | 03h |     | set RTC time
|     | 04h |     | read RTC date
|     | 05h |     | set RTC date
|     | 06h |     | set RTC alarm
|     | 07h |     | reset RTC alarm
