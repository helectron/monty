# C - Stacks, Queues - LIFO, FIFO

### The Monty language
Monty 0.98 is a scripting language that is first compiled into Monty byte codes (Just like Python). It relies on a unique stack, with specific instructions to manipulate it. The goal of this project is to create an interpreter for Monty ByteCodes files.

#### Monty byte code files
Files containing Monty byte codes usually have the `.m` extension. Most of the industry uses this standard but it is not required by the specification of the language. There is not more than one instruction per line. There can be any number of spaces before or after the opcode and its argument:
```bash
julien@ubuntu:~/monty$ cat -e bytecodes/000.m
push 0$
push 1$
push 2$
  push 3$
                       pall    $
				     push 4$
						         push 5    $
									       push    6        $
pall$
julien@ubuntu:~/monty$
```
Monty byte code files can contain blank lines (empty or made of spaces only, and any additional text after the opcode or its required argument is not taken into account:

```bash
julien@ubuntu:~/monty$ cat -e bytecodes/001.m
push 0 Push 0 onto the stack$
push 1 Push 1 onto the stack$
$
push 2$
  push 3$
                       pall    $
				     $
						     $
								                                $
																		push 4$
																							$
																													    push 5    $
																																		          push    6        $
																																										  $
																															   pall This is the end of our program. Monty is awesome!$

julien@ubuntu:~/monty$

```

#### The monty program

Usage:  `$ monty file`. Where file is the path to the file containing Monty byte code.


## Monty Bytecode Commands
- `push <int>` - pushes an integer onto the top of the stack
- `pop` - removes the top element of the stack
- `swap` - swaps the top two elements of the stack
- `nop` - does nothing


- `pall` - prints all values on the stack
- `pint` - prints the value at the top of the stack
- `pchar` - prints the char at the top of the stack
- `pstr` - prints the string starting at the top of the stack


- `add` - adds the top two elements of the stack
- `sub` - subtracts the top element of the stack from the second element of the stack
- `mul` - multiplies the top two elements of the stack
- `div` - divides the second element of the stack by the top element of the stack
- `mod` - returns the remainder of dividing the second element of the stack by the top element of the stack
- `pchar` - prints the char at the top of the stack, followed by a new line.
- `pstr` - prints the string starting at the TOS, followed by a new line.


### Learning Objectives:
* What do LIFO and FIFO mean
* What is a stack, and when to use it
* What is a queue, and when to use it
* What are the common implementations of stacks and queues
* What are the most common use cases of stacks and queues
* What is the proper way to use global variables

### Resources:
C Programming Language, 2nd Edition: Brian W. Kernighan, Dennis M. Ritchie

### Compilation:
Code files must be compiled this way:
```bash
$ gcc -Wall -Werror -Wextra -pedantic *.c -o monty
```
* Any output must be printed on `stdout`
* Any error message must be printed on `stderr`

### Author:
* Helena Cortés Gómez | [Github](https://github.com/helectron))