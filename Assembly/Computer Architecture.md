# Computer Architecture

## CPU

No matter what programming language you use it always ends up on the CPU, like natively compiled languages such as C,C++,Rust runs on CPU or python,javascript runs on the CPU with the help of JIT(Just In Time) interpreter.

The logic of the CPU is implemented through the concept of logic gates some basic logic gates are AND, OR, XOR, NOT, NAND, NOR, and XNOR.

The CPU is divided into some parts such as ALU,CU,Registers,Cache

Registers : Small bits of storage units inside the CPU.

Control Unit : Decides what to execute.

Arithmetic Logic Unit : The place where all arithmatic operations occur.

Cache : The data from memory is loaded into the cache units inside the CPU which gets loaded onto registers for the CPU to execute. Caches are really small in size and very expensive but are really fast.
Nowadays there are CPUS with multiple cores so each core has there own cache (L1 cache) and they all share a common cahce (L2 cache).

This model of CPU is called Von Neumann Architecture(Shrinking in size but increasing in speed).
