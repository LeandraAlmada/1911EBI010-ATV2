#CC = arm-none-eabi-gcc
#CFLAGS = -c -mcpu=cortex-m4 -mthumb -Wall -O0

#all: startup.o main.o

#%.o: %.c
#	$(CC) $(CFLAGS) -o $@ $^

#clean:
#	rm -f *.o
	
PROG = blinky

CC = arm-none-eabi-gcc
LD = arm-none-eabi-gcc
CP = arm-none-eabi-objcopy
CFLAGS = -mcpu=cortex-m4 -mthumb -O0 -Wall
LFLAGS = -nostdlib -T stm32f411-rom.ld

OBJS = startup.o \
		main.o
all: $(PROG).elf

$(PROG).elf: $(OBJS)
	$(LD) $(LFLAGS) $^ -o $@
	$(CP) $(PROG).elf -O binary $(PROG).bin

%.o: %.c
	$(CC) -c $(CFLAGS) $< -o $@

clean:
	rm -f $(OBJS) $(PROG).bin $(PROG).elf