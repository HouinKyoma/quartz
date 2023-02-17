## Stack concept, Hardware Stack VS. SRAM Stack
- Subroutine benefits:
	- reduce source program size
	- modularity
	- instruction flow returns to the instruction following subroutine's call
- existence of a stack is a requirement for supporting nested subroutine
- push() instruction do not explicityly specify the address, but is provided by MCU's stack pointer
- pop() is the same following push()
- if the stack is full, pushing data to the stack will cause the byte to be lost
- 
## AVR Stack Operation
- stack pointer always starts at `0x7FFF` where its the end of SRAM, and expands up(to lower numbers of addresses)
## Subroutines
### Subroutine calls
### Indirect Subroutine calls
**RCALL**
although RCALL has a limited range, it's preferred because its one word shorter and one less clock long than CALL
### Subroutine headers
### Nested Subroutine
- when a subroutine calls another subroutine
- levels of nesting is limited by stack space


