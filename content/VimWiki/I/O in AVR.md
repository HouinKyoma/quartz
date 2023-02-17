#avr

# I/O in AVR

## VPORT and PORT
VPORTn is physically the same register as any PORT registers
However, bit manipulation(`sbi`,`cbi`) are only available on VPORTS, because these operands only have 5 bits for addressing the registers.
Since I/O registers are located low in the memory maps, we can do this with 32 I/O registers we have.

## Structure of a PORT
each port have 4 8-bit registers
- DIR - 0
- OUT - 1
- IN - 2
- INTFLAGS - 3

When addressing a PORT, each ports offsets:
- VPORTA 00
- VPORTB 04
- VPORTC 08
- VPORTD 0C
-and So on

## Configure a Port
Use DIR register of a port to configure whether its inputting or outputting
- DIR set to `1`:pin is output
- DIR set to `0`:pin is input

## Outputting and Inputting to a PORT
