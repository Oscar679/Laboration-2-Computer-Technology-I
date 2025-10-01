
## Report for laboration 2 - Computer Technology |

  - **My name and LNU credentials:** Oscar Ekberg, oe222ia
  - **Examiner of this report**: Daniel Lundberg

## Task 1
# Minicom output
<img width="650" height="442" alt="image" src="https://github.com/user-attachments/assets/7f71df8f-03cc-4320-bb05-b09e126e09d5" />

# Source code
```assembly
@
@ Assembler program print out "Hello World"
@ using the Pico SDK.
@
@ R0 - first parameter to printf
@ R1 - second parameter to printer
@ R7 - index counter
@

.thumb_func		    @ Necessary because sdk uses BLX
.global main	            @ Provide program starting address to linker

main:
	BL	stdio_init_all	@ initialize uart or usb
	MOVS	R7, #100		@ initialize starting counter to 100
loop:
	LDR	R0, =helloworld	@ load address of helloworld string
	MOV R1, R7 @ Moves the counter in to R1 which is sent to the printf function
	BL	printf		@ Call pico_printf
	SUB R7, R7, #1 @ Subtracts 1 from R7
	CMP R7, #0 @ Compares R7 to 0
	BGE loop @ Branch if Greater than or Equal to 0
	MOVS R7, #100 @ Resets the counter to 100
	B	loop		@ loop forever
		
.data
	       .align  4	@ necessary alignment
helloworld: .asciz   "Hello World %d\n"

```
