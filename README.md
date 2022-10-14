# nand2tetris

### Build the computer hardware

My solution for the project nand2tetris. This first part of the project consist to build a basic simulated functional computer with the _Hardware simulator_ tool.



## Chapters
- [Chapter 1: Boolean Logic](#Chapter_1)
- [Chapter 2: Boolean Arithmetic](#Chapter_2)

*I will be adding topics as I progress in the course*

<a name='Chapter_1'></a>
 
## Chapter 1: Boolean Logic

Starting with one primitive logic gate, [Nand](https://en.wikipedia.org/wiki/NAND_gate), and build all the other necessary logic gates, Not, And, Or, Xor, Mux and DMux.
The target computer will be designed to operate on 16-bit values, then 16-bit versions of the basic gates, like Not16,
And16, and so on, will also be build.

The implementations have been made using basic [HDL](https://en.wikipedia.org/wiki/Hardware_description_language)(Hardware Description Language). Besides, I make diagrams with the [Logisim](http://www.cburch.com/logisim/index.html) tool to facilitate and better understand my implementations.


###### *Checked logic gates means they are already implemented*

#### Basic Logic Gates
- [x] Not
- [x] And
- [x] Or
- [x] Xor
- [x] Multiplexer (Mux)
- Demultiplexer (DMux)

#### Multi-Bit Versions of Basic Gates
- [x] Multi-bit Not
- [x] Multi-bit And
- [x] Multi-bit Or
- Multi-bit Xor
- Multi-bit multiplexer

#### Multi-Way Versions of Basic Gates
- Multi-way Or
- Multi-way/Multi-bit multiplexer
- Multi-way/Multi-bit demultiplexer
