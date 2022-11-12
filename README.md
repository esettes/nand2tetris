# nand2tetris

###### _All files of this project are part of www.nand2tetris.org and the book "The Elements of Computing Systems" by Nisan and Schocken, MIT Press._

### Implement computer's hardware

My solution for the project [nand2tetris](https://www.nand2tetris.org/course). This first part of the project consist to build a basic simulated functional computer with the _Hardware simulator_ tool. 

When this is done, the second part consists to build an operating system for this computer.

## Contents
- [Introduction](#Introduction)
- [Chapters](#Chapters)
    - [Chapter 1: Boolean Logic](#Chapter_1)
    - [Chapter 2: Boolean Arithmetic](#Chapter_2)
    - [Chapter 3: Memory](#Chapter_3)

###### *I will be adding chapters as I progress in the course*

<a name='Introduction'></a>
 
## Introduction

The course provides you with tools and resources to develop the entire project. Each of the modules of the project consists of exercises that must be completed. As the modules are completed, they are used to develop the next one, and so on.

I use [Logisim](http://www.cburch.com/logisim/index.html) tool too to make diagrams to facilitate and better understand my implementations.

<br>

<a name='Chapters'></a>

<a name='Chapter_1'></a>
 
## Chapter 1: Boolean Logic

Starting with one primitive logic gate, [Nand](https://en.wikipedia.org/wiki/NAND_gate), and build all the other necessary logic gates, Not, And, Or, Xor, Mux and DMux.
The target computer will be designed to operate on 16-bit values, then 16-bit versions of the basic gates, like Not16,
And16, and so on, will also be build.

The implementations have been made using basic [HDL](https://en.wikipedia.org/wiki/Hardware_description_language)(Hardware Description Language).

<details>
<summary> Elementary logic gates </summary>

- [x] Not
- [x] And
- [x] Or
- [x] Xor
- [x] Mux (Multiplexer)
- [x] DMux (Demultiplexer)

</details>

<details>
<summary> 16-bit variants </summary>

- [x] Not16
- [x] And16
- [x] Or16
- [x] Mux16

</details>

<details>
<summary> Multi-Way variants </summary>

- [x] Or8Way
- [x] Mux4Way16
- [x] Mux8Way16
- [x] DMux4Way
- [x] DMux8Way

</details>

<br>

<a name='Chapter_2'></a>
 
## Chapter 2: Boolean Arithmetic

The purpose here is to continue implementing chips but a little higher level, and finally build an [ALU](https://en.wikipedia.org/wiki/Arithmetic_logic_unit)(Arithmetic Logical Unit).
The chips implemented here avoids to make arithmetic and bitwise operations.

### Two's complement

<p align="left">

<img align="left" height="300px" src="https://github.com/esettes/nand2tetris/blob/main/diagrams/utils/two_complement.png">

</p>

<p align="right">
If we want to represent signed numbers(negatives), we can use half of the bit representations for it.
</p>
<p align="right">
The two's complement of $\ x$ is defined to be $\ 2^n - x $, where $\ n$ = num of bits.
</p>
<p align="right">
For example, the TC of -5
</p>
<p align="right">
$\ 2^4 - 5$ ---> $\ 16 - 5 = 11 $
</p>
<p align="right">
Regular addition $\ \mod 2^n $
</p>
<p align="right">
With this info, we can make subtraction too. Then if you want to compute $\ -2 + (-5) $
</p>
<p align="right">
$\ 14 + 11 = 25$
</p>
<p align="right">
$\ 25 \mod 16 = 9$ ---> $\ 2^4 - 9 = -7 $
</p>

<br><br>

### ALU

<img align="right" height="310px" src="https://github.com/esettes/nand2tetris/blob/main/diagrams/screenshots/alu_impl.png">

<img align="right" height="140px" src="https://github.com/esettes/nand2tetris/blob/main/diagrams/screenshots/alu_diagram.png">

#### Challenges
- Use 0’s and 1’s for representing numbers
- Use logic gates for realizing arithmetic functions.

#### Functions (f)

- Arithmetic:
    - (x + y), (x - y), (y - x)
    - (x + 1), (y + 1)
    - (x - 1), (y - 1)
- Logical:
    - (x & y), (x | y)
    - (!x), (!y)

The inputs zx, nx, zy, etc... indicate whether these operations are performed or not on the inputs x and y. On each step the 
value of x/y is or not modified.

If you want to compute (out = y - x), where x = 4 and y = 6, the control bits(zx, nx, ...) are in the table.

x = 0100

y = 0110

In pre-setting, the only operation to do is (!y), so:

x = 0100

y = 1001

Next step, select between (+) and (&) is true, then out = x + y:

0100 + 1001 = 1101

And finally the output post-setting is true, then out = !out:

!(1101) = 0010 = 2

<details>
<summary><h4> Chips to implement, including ALU: </h4></summary>

- [x] HalfAdder
- [x] FullAdder
- [x] Add16 (16-bit adder)
- [x] Inc16 (16-bit incrementor)
- [x] ALU

</details>

<br>

<a name='Chapter_3'></a>
 
## Chapter 3: Memory

In the third module the target its to build the computer's main memory unit, also known as Random Access Memory ([RAM](https://en.wikipedia.org/wiki/Random-access_memory)). Going bottom-up frmo elementary flip-flop gates to one-bit registers to n-bit registers to a family of RAM chips. 

Unlike the chips implemented so far, which are based on combinational logic,  the computer's memory logic requires a clock-base secuential logic.

### D-Flip-Flop and 1-bit Register

[DFF](https://www.javatpoint.com/d-flip-flop-in-digital-electronics) is the most elementary sequential gate; outputs the input in the previous time-step $\ (out[t] = in[t - 1])$
