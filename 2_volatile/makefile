CROSS-COMPILER = arm-none-eabi-

all: test.elf

test.elf: test.c
	$(CROSS-COMPILER)gcc -O1 -Wall -std=c11 -mcpu=cortex-m4 -mthumb -nostartfiles -T empty.ld test.c -o test.elf
	$(CROSS-COMPILER)objdump -D test.elf

volatile: test.c
	$(CROSS-COMPILER)gcc -DUSE_VOLATILE -O1 -Wall -std=c11 -mcpu=cortex-m4 -mthumb -nostartfiles -T empty.ld test.c -o test_volatile.elf
	$(CROSS-COMPILER)objdump -D test_volatile.elf

.PHONY:
clean:
	rm -f *.o *.elf
