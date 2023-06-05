# Registers

Registers are very fast,temporary stores for data.

They are inside the cpu.

They are expensive.

You get a lot if general purpose registers and different cpu architectures provides different registers.

eg: x86: eax,ecx,edx,ebx,esp,ebp,esi,edi

    amd64: rax,rcx,rdx,rbx,rsp,rbp,rsi,rdi,r8,r9,10,r11,r12,r13,r14,r15


During intel's 8085 days we had the register ah,al etc.., which were just 8 bit versions and when 16 bit architectures were released they kept the smaller registers and added the registers ax etc, and when 32 bit came along they still maintained backward compatibility and we got eax(extented ax). When 64 bit came we got rax (really extended ax).

al was the old a and ah was added on to it to make ax(16 bit), and then ax got extended and we got eax similarily with amd64 we got rax which really stretched eax.

## Setting Registers

mov rbx,0x539

this assembly instruction(op code), takes the value 0x539 and puts into rbx, data is specified directly in the instruction like this is called immediate value.

you  can also access partial registers

as well 

ie, this sets rax to 0xfffffffffff0539
mov rax,0xfffffffffff
mov ax,0x539

If you write to a 32 bit partial(eax) the CPU will zero out the rest of the register This is done for performance.

ie, This sets rax to 0x000000000000539
mov rax,0xfffffffffff
mov eax,0x539

We can also move data across registers
as follows.

mov rax,0x539
mov rbx,rax

as long as the size is aligned properly, the old data in the register is not destroyed.


Consider:
mov eax,-1

eax is now 0xffffffff(both 4294967295 and -1)

rax is now 0x00000000ffffffff(only 4294967295)

what if you wanted the operate on that -1 in 64-bit land

mov eax,-1
movsx rax,eax

movsx does a sign extending move, preserving the two's complement value(ie,copies the top bit to the rest of the register)

eax is now 0xffffffff(both 4294967295 and -1) but rax is now 0xffffffffffff(both 4294967295 and -1)

## Register Arithmetic

There are tons of arithmetic operations that can be done on registers.

# Special registers

rip -> points to the next instruction
shouldn't change it's value.(instruction pointer).

rsp -> contains the address of a region of memory to store temporary data(sp = stack pointer).






