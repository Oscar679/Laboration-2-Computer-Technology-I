
## Report for laboration 2 - Computer Technology |

  - **My name and LNU credentials:** Oscar Ekberg, oe222ia
  - **Examiner of this report**: Daniel Lundberg

## Task 1 - Hello World loop
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

## Task 2 - Traffic light
# Output
https://github.com/user-attachments/assets/a4c00085-14e7-4cb0-b4df-dd693df4b2ac

# Source code
```assembly
@
@ Assembler program to flash three LEDs connected to the
@ Raspberry Pi Pico GPIO port using the Pico SDK.
@

	.EQU	LED_PIN1, 0
	.EQU	LED_PIN2, 1
	.EQU	LED_PIN3, 2
	.EQU	GPIO_OUT, 1
	.EQU	sleep_time, 200

.thumb_func	@ Necessary because sdk uses BLX
.global main    @ Provide program starting address

main:
	BL stdio_init_all @ enable USB serial
	
	MOV	R0, #LED_PIN1
	BL	gpio_init
	MOV	R0, #LED_PIN1
	MOV	R1, #GPIO_OUT
	BL	link_gpio_set_dir
	
	MOV	R0, #LED_PIN2
	BL	gpio_init
	MOV	R0, #LED_PIN2
	MOV	R1, #GPIO_OUT
	BL	link_gpio_set_dir
	
	MOV	R0, #LED_PIN3
	BL	gpio_init
	MOV	R0, #LED_PIN3
	MOV	R1, #GPIO_OUT
	BL	link_gpio_set_dir
	
loop:   MOV	R0, #LED_PIN1
	MOV	R1, #1
	BL	link_gpio_put
	LDR	R0, =sleep_time
	BL	sleep_ms
	MOV	R0, #LED_PIN1
	MOV	R1, #0
	BL	link_gpio_put
	MOV	R0, #LED_PIN2
	MOV	R1, #1
	BL	link_gpio_put
	LDR	R0, =sleep_time
	BL	sleep_ms
	MOV	R0, #LED_PIN2
	MOV	R1, #0
	BL	link_gpio_put
	MOV	R0, #LED_PIN3
	MOV	R1, #1
	BL	link_gpio_put
	LDR	R0, =sleep_time
	BL	sleep_ms
	MOV	R0, #LED_PIN3
	MOV	R1, #0
	BL	link_gpio_put
	B       loop

```

## Task 3 - Binary counter
# Output
