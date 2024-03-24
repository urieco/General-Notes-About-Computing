# Table of Contents
- [Minor technical terms](#minor-technical-terms)
  - Word
  - Values
  - Numbers: Sign, Exponent and Mantissa
    + Floating-point number problem
    + Arithmetic and operators
  - Strings

- [Bit](#bit)
  - *-bit data
  - Bit and Byte
  - Decimal Prefix and Binary Prefix (Kilo vs Kibi)
- [Cycle](#cycle)
  - Clock and Bus cycle
  - Machine cycle
  - Instruction cycle
- [Programming](#programming)

# Minor technical terms
## Word
A word, in the majority of architectures, is the largest piece of data that can be transferred to and from the working memory in a single operation. 
- The largest possible address size, used to designate a location in memory, is typically called a hardware word.

<details>
  <summary>If a CPU has 16-bit address bus and 8-bit words, how much memory can it address?</summary>
  <br>
  Ref: https://superuser.com/questions/1216428/if-a-cpu-has-a-16-bit-address-bus-and-8-bit-words-how-much-memory-can-it-addres

  So, your CPU will be able to address 64KB (2^16) but will only be able to transfer in a single operation 8 bits.
</details>

## Values
- A typical modern computer has more than 30 billion bits in its volatile data storage (working memory). Non-volatile storage (hard disk) tends to have yet a few orders of magnitude more. 
- To be able to work with such quantities of bits without getting lost, we must separate them into chunks that represent pieces of information. Those chunks are usually called **values** (in JavaScript for example). 
- Every value has a type that determines its role. Some are numbers, pieces of text, some are functions, and so on. 
- To refer to a value, you must invoke its name. 

## Numbers
- Numbers are numeric values. 
- The number of bits a typical modern 64-bit CPU will use to store a single integer value is 64 bits. There can be so many patterns you can make with **64 bits**, which means that the number of different numbers that can be represented is **limited**. --> You can represent **2^64** different numbers, roughly **18,446,744,073,709,551,616 (or 18 quintillion - 18 zeros) numbers**.
  - Computer memory used to be smaller so it’s easier to **overflow** back then. 
  - However, some bits are delegated to indicate **the sign of the number** and **the position of the decimal point**. --> You can store fewer amount of digits, roughly **9 quarillion (15 zeros) numbers**.
    - Since binary numbers can have only two symbols, either 0 or 1 for each position or bit, so it is not possible to add minus or plus symbols in front of a binary number. We represent negative binary numbers using a minus symbol in front of them. **In computer number representation, these numbers can be distinguishable with the help of an extra bit or flag called sign bit or sign flag in the Binary number representation system for signed numbers**. This extra bit is called **sign bit or sign flag** which has a value of sign bit is 0 for positive numbers and 1 for negative binary numbers. Ref: [geeksforgeeks.org](https://www.geeksforgeeks.org/representation-of-negative-binary-numbers/).
    ![Sign bit/flag](Images/General%200.1%20Sign%20bit.png)
    Ex: The first bit is '1' = Negative number. '0' = Positive number.
    - Decimal point: The decimal point location is implicit based on the data type and intepreation of the bits. For numbers with decimal points, computers commonly use a floating-point representation. This separates the number into two parts: **Signifcand (mantissa) - storing the actual digits of the number; and the Exponent - indicating the position of the decimal point by representing the power of 10 to which the significand should be scaled**.
    
    Ex: The number 3.14 can be represented in **IEEE 754** single-precision format: **0-10000000-10010001111010111000011**. Ref: [h-schmidt.net/FloatConverter/IEEE654](https://www.h-schmidt.net/FloatConverter/IEEE754.html)
    - Sign: 0 = +1 (Positive)
    - Exponent: 10000000 = 128 = 2^1
    - Mantissa: 10010001111010111000011 = 4781507 = 1 + 0.5700000524520874
    - (1 + 0.5700000524520874) * (2^1) * (+1) = 3.1400001049041748 (**Computer floating problem**)
    - Error due to conversion: 0.0000001049041748046875
<details>
  <summary>What range of numbers can be represented in a 16-, 32- and 64-bit IEEE-754 systems?</summary>
  <br>
  Ref: https://stackoverflow.com/questions/872544/what-range-of-numbers-can-be-represented-in-a-16-32-and-64-bit-ieee-754-syste 

  For a given IEEE-754 floating point number X, if ```2^E <= abs(X) < 2^(E+1)``` then the distance from X to the next largest representable floating point number (epsilon) is:
  ```
  epsilon = 2^(E-52)    % For a 64-bit float (double precision)
  epsilon = 2^(E-23)    % For a 32-bit float (single precision)
  epsilon = 2^(E-10)    % For a 16-bit float (half precision)
  ```
  In short: 
  64-bit (double-precision): 2^53 = 9 quarillion 
</details>

- Whole numbers (**integers**) calculation, under 9 quadrillion, is always precise. Not with fractional numbers though because of floating point. Ex: ```0.0001 + 0.0002 = 0.00030000000000000003```

### The Floating-point number problem
Why ```0.1 + 0.2 = 0.30000000...1 ?```

- Human does calculation in Base-10 --> ```0.1 + 0.2 = 0.3```
  + Recurring numbers happen: ```1/3 = 0.3333333...```. However, it can still be solved: ```1/3 + 1/3 + 1/3 = 1```. 
  + If we only have a limited amount of memory for the amount of decimals behind the radix point (decimal point), the math calculation would be like this: ```0.333 + 0.333 + 0.333 = 0.999```.
- Computers do calculation in Base-2. All fractional numbers, even the ones that don't result in recurring number, can't be converted to a Base-2 that easily. 
![You can't convert certain decimals to base-2](Images/General%200.2%20You%20can't%20convert%20certain%20decimal%20to%20base-2.png)
  - To computers, ```0.1 = 0.0001100110011...``` (limited memory).
  - At some points, the recurring has to be cut off, to produce a result for the calculation. 
  - It is similar to ```0.333 + 0.333 + 0.333 = 0.999```. The computer doesn't understand recurring like we do. 

### Arithmetic and operators
Ex: (100 + 34) * 11

- The + and * symbols are called "operators".
- Also there are subtraction and division operator (-, /).
- Without parentheses, the order in which they are applied is determined by the precedence of the operators. 
- Remainder operator: 5 % 4 = 1. It is also referred as "modulo".

## Strings
"This is a string".

# Bit
- Inside the computer's world, there is only **data**. All this data is stored as long sequences of **bits**. 
- Bits are any kind of two-valued things, usually 0 and 1. 

Sequence | 0 | 0 | 0 | 0 | 1 | 1 | 0 | 1
---|---|---|---|---|---|---|---|---|
**Bit** | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1

Ex: 13 = 00001101


## *-bit data
Ex: 16-bit data

> 16-bit data typically refers to a data structure or unit of information that consists of 16 binary digits or bits. Each bit can represent either a 0 or a 1. **16 binary digits**: 0101010101010101

## Bit and Byte
- 1 Byte = 8 Bit
- 1 Kilobyte = 8 Kilobit
- 1 Megabyte = 8 Megabit
- 1 Gigabyte = 8 Gigabit

**Role:**
- Bit: Data transfer rate, bits per seconds, Kbps, Mbps, Gbps, measuring data transfer over a network or communication channel. 
- Byte: Storage capabilities, Bytes, kilobytes (KB), Megabytes (MB), Gigabytes (GB), and Terabytes (TB)...

**Why?**
- **Historical context**: Early days of computing. When computer scientists and engineers were developing the binary-based systems, they needed a way to represent the smallest unit of data (the bit) and larger units (bytes) that were more practical for storing and processing information. 
- **Practical Considerations**: 
  + **Bytes** are more intuitive for measuring storage capacities because they align closely with how data is organized and accessed within computer systems. For example, file sizes, memory capacities, and storage devices are commonly measured in bytes and its multiples (kilobytes, megabytes, gigabytes, etc.). 
  + On the other hand, **Bits** are more suitable for measuring data transfer rates because they directly represent the rate at which binary data is transmitted over a network or communication channel. Additionally, bits are often used in telecommunications standards and protocols, where they provide a precise measurement of signal bandwidth and transmission speed.

## Kilobyte vs Kibibyte
- Both are units of **digital information storage**
- Kilobyte: More familiar term, 1 kilobyte = 1,000 bytes of data, more human-friendly, used in everyday language and in marketing materials (larger). 
- Kibibyte (KiB): Newer term (1998) that represents 1,024 bytes of data, based on binary multiples, **which is displayed on the File Explorer**. 
![Table of Decimal Prefix and Binary Prefix](Images/General%201%20Decimal%20and%20Binary%20Prefix.png)
- Other method:
  + kilo: 10^3 - kibi: 1024^1
  + mega: 10^6 - mebi: 1024^2
  + giga: 10^9 - gibi: 1024^3 

# Cycle

Generally, Instruction cycle > Machine cycle > Bus cycle ~ Clock cycle. 

- The CPU will refer to its clock speed as the amount of **computation cycles** it can perform per second - a single computation or arithmetic operation (addition, substraction, multiplication and division).
- A memory module (RAM stick) will refer to its clock speed as the amount of **memory cycles** it can perform per second - A simple read or write operation to memory. 
- You can call "Computation cycle of the CPU" as "CPU clock cycle" and "Memory cycle of the RAM modules" as "RAM clock cycle". 

<details>
  <summary>Consider a 32 – bit microprocessor, with a 16 – bit external data bus, driven by an 8 MHz input clock. Assume that this microprocessor has a bus cycle whose minimum duration equals four input clock cycles. What is the maximum data transfer rate for this microprocessor?</summary>
  <br>
- In a 32-bit microprocessor, with a 16-bit external data bus, data transferred per bus cycle = 2B (2 Bytes)
- Minimum bus cycle = 4 clock cycles.
- Maximum bus cycle rate = 8 MHz / 4 = 2 Mb/sec
- Data transfer rate = bus cycle rate * data per bus cycle = 2 Mb * 2 = 4 * 10^6 Bytes/sec.
</details>

## Clock cycle and Bus cycle
- A computer uses a clock. The frequency of this clock indicates how many (Giga/Mega/Kilo) cycles per second that the clock wave changes. This is the basis of any cycle for the computer. This can be considered a 'clock cycle'.

Ex: A CPU poses a clock speed of 5 GHz, which means 5 x 10^9 cycles per second. 

- The bus cycle is the cycle or time required to to make a single read or write transaction between the CPU and an external device such as external memory. 


## Machine cycle
The amount of cycles needed to do either a fetch, read or write operation. The read or write may be more than a single bus cycle if the transaction between the CPU and memory is longer than the data width fetched or written. 

Ex: On an 8080 machine, the data width is 8 bits. If the CPU needs to fetch or write 16 bits of data, that will require two bus cycles.

## Instruction cycle
The amount of machine cycles needed to complete an instruction. This varies depending on the instruction. 

Ex:  Some instructions after fetching them from memory need to fetch more data to complete the instruction, some need to write data at the end of the instruction cycle, some instructions don't do much at all, like the NOP, which basically fetches the instruction and does nothing for one machine cycle.

# Programming
*Programming* is the act of constructing a *program* – a set of precise instructions telling the computer what to do. 

Computers themselves can do only stupidly straightforward things at an incredibly high speed. 
The art of programming is the skill of controlling complexity. 

Why language matters? The same program can be expressed in both long and short, unreadable and readable ways. 
