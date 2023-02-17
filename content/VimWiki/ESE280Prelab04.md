## ESE280 Pre-Lab 4
## Zhong 113003581
## R04
## Bench 18
## Prelab 4

<div style="page-break-after: always;"></div>



### Task 1
```asmatmel
start:
	ldi r16, 0xFF
	out VPORTD_DIR, r16
	ldi r16, 0x00
	out VPORTC_DIR, r16
again:
	in r16, VPORTC_IN
	com r16
	out VPORTD_OUT, r16
	rjmp again
```
### Task 2

```asmatmel
start:
	ldi r16, 0xFF
	out VPORTD_DIR, r16
	ldi r16, 0x00
	out VPORTC_DIR, r16
main_loop:
	in r16, VPORTC_IN
	mov r17,r16
	mov r18, r16
	andi r17,0xE0
	andi r18, 0x1C
	lsl r18
	lsl r18
	lsl r18
	andi r16, 0x03
	cpi r16, 0x00
	breq and_fcn
	cpi r16, 0x00
	breq and_fcn
	cpi r16, 0x02
	breq xor_fcn
not_fcn:
	com r17
	mov r18, r17
	rjmp output
and_fcn:
	and r18,r17
	rjmp output
or_fcn:
	or r18,r17
	rjmp output
xor_fcn:
	eor r18,r17
output:
	andi r18, 0xE0
	com r18
	out VPORTD_OUT,r18
	rjmp main_loop

	
```

### Task 3
```asmatmel
start:
	ldi r16, 0xFF
	out VPORTD_DIR, r16
	ldi r16, 0x00
	out VPORTC_DIR, r16
main_loop:
	in r16, VPORTC_IN
	ldi r17,8
	ldi r18, $00
next_bit:
	lsl r16
	brcc dec_bitcounter
	rol r18
dec_bitcounter:
	dec r17
	brne next_bit
	com r18
	out VPORTD_OUT, r18
	rjmp main_loop
	
```