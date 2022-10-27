# nand2tetris

### Build the computer hardware

My solution for the project [nand2tetris](https://www.nand2tetris.org/course). This first part of the project consist to build a basic simulated functional computer with the _Hardware simulator_ tool. 

When this is done, the second part consists to build an operating system for this computer.


## Contents
- [Introduction](#Introduction)
- [Chapters](#Chapters)
    - [Chapter 1: Boolean Logic](#Chapter_1)
    - [Chapter 2: Boolean Arithmetic](#Chapter_2)

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

<a name='Chapter_2'></a>
 
## Chapter 2: Boolean Arithmetic

The purpose here is to continue implementing chips but a little higher level, and finally build an [ALU](https://en.wikipedia.org/wiki/Arithmetic_logic_unit)(Arithmetic Logical Unit).
The chips implemented here avoids to make arithmetic and bitwise operations.

<img align="right" height="220px" src="https://github.com/esettes/nand2tetris/blob/main/diagrams/utils/computer_system.png">

#### ALU functions (f)
- Arithmetic: x + y, x – y, x + 1, x – 1, ...
- Logical: x & y, x | y, !x , ...


#### Challenges
- Use 0’s and 1’s for representing numbers
- Use logic gates for realizing arithmetic functions.

<details>
<summary><h4> Chips: </h4></summary>

- [x] HalfAdder
- [x] FullAdder
- [x] Add16 (16-bit adder)
- [x] Inc16 (16-bit incrementor)
- [ ] ALU

</details>

### Two's complement

<p align="left">

<img align="left" height="300px" src="https://github.com/esettes/nand2tetris/blob/main/diagrams/utils/two_complement.png">

</p>

<p align="right">
If we want to represent signed numbers(negatives), we can use half of the bit representations for it.
</p>
<p align="right">
The two's complement of 'x' is defined to be 2<sup>n</sup> - x, where n = num of bits.
</p>
<p align="right">
For example, the TC of -5 ---> 2<sup>4</sup> - 5 --> 16 - 5 = 11 is the TC.
</p>
<p align="right">
Regular addition -> modulo 2<sup>n</sup>
</p>
<p align="right">
With this info, we can make subtraction too.
</p>
<p align="right">
Then if you want to compute 3 + (-5) ---> 3 + 11 = 14 % 16 = 14 = 2<sup>4</sup> - 14 = -2
</p>
<p align="right">
To compute -2 + (-5) ---> 14 + 11 = 25 % 16 = 9 = 2<sup>4</sup> - 9 = -7
</p>

