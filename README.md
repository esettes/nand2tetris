# nand2tetris

### Build the computer hardware

My solution for the project [nand2tetris](https://www.nand2tetris.org/course). This first part of the project consist to build a basic simulated functional computer with the _Hardware simulator_ tool. 

When this is done, the second part consists to build an operating system for this computer.


## Contents
- [Introduction](#Introduction)
- [Chapters](#Chapters)
    - [Chapter 1: Boolean Logic](#Chapter_1)

###### *I will be adding chapters as I progress in the course*

<a name='Introduction'></a>
 
## Introduction

The course provides you with tools and resources to develop the entire project. Each of the modules of the project consists of exercises that must be completed. As the modules are completed, they are used to develop the next one, and so on.

<br>

<a name='Chapters'></a>

<a name='Chapter_1'></a>
 
## Chapter 1: Boolean Logic

Starting with one primitive logic gate, [Nand](https://en.wikipedia.org/wiki/NAND_gate), and build all the other necessary logic gates, Not, And, Or, Xor, Mux and DMux.
The target computer will be designed to operate on 16-bit values, then 16-bit versions of the basic gates, like Not16,
And16, and so on, will also be build.

The implementations have been made using basic [HDL](https://en.wikipedia.org/wiki/Hardware_description_language)(Hardware Description Language). Besides, I make diagrams with the [Logisim](http://www.cburch.com/logisim/index.html) tool to facilitate and better understand my implementations.


###### *Checked logic gates means they are already implemented*

#### Elementary logic gates
- [x] Not
- [x] And
- [x] Or
- [x] Xor
- [x] Mux (Multiplexer)
- [x] DMux (Demultiplexer)

#### 16-bit variants
- [x] Not16
- [x] And16
- [x] Or16
- [x] Mux16

#### Multi-Way variants
- [x] Or8Way
- [x] Mux4Way16
- [ ] Mux8Way16
- [ ] DMux4Way
- [ ] DMux8Way
