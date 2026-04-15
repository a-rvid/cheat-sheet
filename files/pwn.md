# Pwn

Make a program do something it's not intended to do.
In this document I'll mostly cover stack-based buffer overflows.

## Table of contents

- [Pwn](#pwn)
  - [Table of contents](#table-of-contents)
  - [Fundamentals](#fundamentals)

## Fundamentals

??? "How does this even work? Basics."
  Buffer overflows occur when a buffer gets filled above it's limit, thus overflowing and if mishandeled, can overwrite other functions potentially leading to vulnerabilities such as arbitrary code execution or unwanted actions.

  Programs store instructions and data in memory during execution, which means that if you could overwrite the instructions, you could execute your own code.

x86 assembly registers:

**Data registers**

| 64-bit | 32-bit | Description                                                                                                                           |
| -------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| RAX    | EAX    | Accumulator used for I/O in arithmetric operations. RAX holds the return value when a function completes and specifies which syscall. |
| RBX    | EBX    | Commonly used for data storage                                                                                                        |
| RCX    | ECX    | Used for the LOOP instruction meaning that LOOP decrements until 0                                                                    |
