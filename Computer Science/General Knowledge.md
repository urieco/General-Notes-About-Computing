# Table of Contents
- [Minor technical terms](#minor-technical-terms)
  - Word
  - Values
  - [Numbers](#numbers): Sign, Exponent and Mantissa
    + Floating-point number problem
    + Arithmetic and operators: Operands
  - [Strings](#strings)

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
  Ref: <a>https://superuser.com/questions/1216428/if-a-cpu-has-a-16-bit-address-bus-and-8-bit-words-how-much-memory-can-it-addres</a>

  So, your CPU will be able to address 64KB (2<sup>16</sup>) but will only be able to transfer in a single operation 8 bits.
</details>

## Values
- A typical modern computer has more than 30 billion bits in its volatile data storage (working memory). Non-volatile storage (hard disk) tends to have yet a few orders of magnitude more. 
- To be able to work with such quantities of bits without getting lost, we must separate them into chunks that represent pieces of information. Those chunks are usually called **values** (in JavaScript for example). 
- Every value has a type that determines its role. Some are numbers, pieces of text, some are functions, and so on. 
- To refer to a value, you must invoke its name. 

## Numbers
- Numbers are numeric values. 
- The number of bits a typical modern 64-bit CPU will use to store a single integer value is 64 bits. There can be so many distinct sequences of 1's and 0's you can make with **64 bits**, which means that the amount of different integers that can be represented is **limited**. You can represent **2<sup>64</sup> - 1 (including the 0)** different (unsigned) whole numbers or positive integers, roughly **18,446,744,073,709,551,616 (or 18 quintillion - 18 * 10<sup>18</sup>) whole numbers**.
  - Computer memory used to be smaller so it’s easier to **overflow** back then. 
  - However, not all 64 bits are solely dedicated to representing the integer, some bits are delegated to signify **the sign of the number** and **the position of the decimal point**. As a result, the actual number of unique integer values that can be stored is lower. You can store fewer amount of digits, **2<sup>53</sup>** combinations, roughly **9 quadrillion (15 zeros) numbers**.
    - Ex: 
    - **Sign**: Since binary numbers can have only two symbols, either 0 or 1 for each position or bit, so it is not possible to add minus or plus symbols in front of a binary number. We represent negative binary numbers using a minus symbol in front of them. **In computer number representation, these numbers can be distinguishable with the help of an extra bit or flag called sign bit or sign flag in the Binary number representation system for signed numbers. They can also be referred to as the most significant bit (MSb)**. This extra bit is called **sign bit or sign flag** which has a value of sign bit is 0 for positive numbers and 1 for negative binary numbers. You can depict **-ceil(2<sup>n</sup>/2) to +floor((2<sup>n</sup>/2) - 1)** integers. Thus, 64-bit can represent any integer within the range from -(2<sup>63</sup>) to (2<sup>63</sup> - 1).
    Ref: [geeksforgeeks.org](https://www.geeksforgeeks.org/representation-of-negative-binary-numbers/).
    ![Sign bit/flag](Images/General%200.1%20Sign%20bit.png)
    Ex: The first bit is '1' = Negative number. '0' = Positive number.
    - **Decimal point**: The decimal point location is implicit based on the data type and interpretation of the bits. For numbers with decimal points, computers commonly use a floating-point representation. This separates the number into two parts: **Significand (mantissa) - storing the actual digits of the number; and the Exponent - indicating the position of the decimal point by representing the power of 10 to which the significand should be scaled**.
    - For the **Double-precision floating-point format** in the IEEE 754-2008 standard (or binary64), 1 bit is designated to be the Sign bit, 11 bits are for the Exponent and the rest 53 bits (52 explicitly stored) are for Significand precision. 
    
Ex: The number 3.14 can be represented in **IEEE 754** single-precision format: **0-10000000-10010001111010111000011**. Ref: [h-schmidt.net/FloatConverter/IEEE654](https://www.h-schmidt.net/FloatConverter/IEEE754.html)
- Sign: 0 = +1 (Positive)
- Exponent: 10000000 = 128 = 2<sup>1</sup>
  + You can probably pinpoint the exact number of this by guessing the highest power of 2 that doesn't exceed the integer's value. Ex: 39 (32 = 2<sup>5</sup>), 300 (256 = 2<sup>8</sup>) 
- Mantissa: 10010001111010111000011 = 4781507 = 1 + 0.5700000524520874
  + You can calculate the approximation of Mantissa by: Integer value / Exponent value (calculated from above) = 3.14 / 2<sup>1</sup> = 1.57 = 1 + 0.57. [However, binary can never display decimal value precisely](#the-floating-point-number-problem). 
- (1 + 0.5700000524520874) * (2<sup>1</sup>) * (+1) = 3.1400001049041748 (**Computer floating problem**)
- Error due to conversion: 0.0000001049041748046875
<br>

<details>
  <summary>What range of numbers can be represented in a 16-, 32- and 64-bit IEEE-754 systems?</summary>
  <br>
  Ref:<a> https://stackoverflow.com/questions/872544/what-range-of-numbers-can-be-represented-in-a-16-32-and-64-bit-ieee-754-syste</a> 

  For a given IEEE-754 floating point number X, if `2^E <= abs(X) < 2^(E+1)` then the distance from X to the next largest representable floating point number (epsilon) is:
  ```
  epsilon = 2^(E-52)    % For a 64-bit float (double precision)
  epsilon = 2^(E-23)    % For a 32-bit float (single precision)
  epsilon = 2^(E-10)    % For a 16-bit float (half precision)
  ```
  In short: 
  64-bit (double-precision): 2<sup>53</sup> = 9 quadrillion 
</details>

- Whole numbers (**integers**) calculation, under 9 quadrillion, is always precise. Not with fractional numbers though because of floating point. Ex: ```0.0001 + 0.0002 = 0.00030000000000000003```

### The Floating-point number problem
Why ```0.1 + 0.2 = 0.30000000...1 ?```

- Human does calculation in Base-10 --> ```0.1 + 0.2 = 0.3```
  + Recurring numbers happen: ```1/3 = 0.3333333...```. However, it can still be solved: ```1/3 + 1/3 + 1/3 = 1```. 
  + If we only have a limited amount of memory for the amount of decimals behind the radix point (decimal point), the math calculation would be like this: ```0.333 + 0.333 + 0.333 = 0.999```.
- Computers do calculations in Base-2. All fractional numbers, even the ones that don't result in recurring numbers, can't be converted to a Base-2 that easily. 
![You can't convert certain decimals to base-2](Images/General%200.2%20You%20can't%20convert%20certain%20decimal%20to%20base-2.png)
  - To computers, ```0.1 = 0.0001100110011...``` (limited memory).
  - At some points, the recurring has to be cut off, to produce a result for the calculation. 
  - It is similar to ```0.333 + 0.333 + 0.333 = 0.999```. The computer doesn't understand recurring like we do. 

**How to solve it:**
```javascript
let x = (0.2 * 10 + 0.1 * 10) / 10;
```

### Arithmetic and operators
Ex: (100 + 34) * 11

- The + and * symbols are called "operators". (The 100, 34 and 11 are 'operands')
- Also there are subtraction and division operators (-, /).
- There is a wide range of programming languages that use ** (Double asterisk) as an operator for exponentiation. 
- Without parentheses, the order in which they are applied is determined by the precedence of the operators. 
- Remainder operator: 5 % 4 = 1. It is also referred to as "modulo".

## Strings
- "This is a string".
- A string is traditionally a sequence of characters, either as a literal constant or as some kind of variable. The latter may allow its elements to be mutated and the length changed, or it may be fixed (after creation). 
- In programming languages, it's a **data type** used to store and manipulate text data. 
- Computers can't understand text directly. They store characters using a character encoding scheme, which assigns a unique binary code (a series of 0s and 1s) to each character. A common encoding scheme is **ASCII (American Standard Code for Information Interchange)**, which uses **7 bits** for most characters.
- A string is often implemented as an **array data structure of bytes** (or [words](#word)) that stores a sequence of elements, typically characters, using some character encoding.
  + Each character in the string is stored at a specific index in the array, allowing for easy access and manipulation of the string's individual characters. This array-based representation makes it possible to perform various string operations, such as concatenation, substring extraction, and modification. 
  + Exceptions: Python, Ruby, Go, Rust, Swift... These languages have their own string representations that are not purely based on arrays of characters. Ex: Strings in Python, are represented as a sequence of Unicode code points, and they are not directly manipulated as arrays of characters. 
- Depending on the programming language and precise data type used, a variable declared to be a string may either cause storage in memory to be **statically allocated (C, Java...)** for a predetermined maximum length or employ **dynamic allocation (JavaScript, PHP, Ruby)** to allow the string to grow or shrink as needed. 

Feature | Statically Allocated Strings | Dynamically Allocated Strings
---|---|---|
Memory Allocation | Compile time  | Runtime
Memory Size       | Fixed size based on declaration | Variable size based on the content
Access Speed      | Faster        | Slower (potential reallocation)
Memory Efficiency | Less efficient (potential waste)| More efficient
Example Languages | C, Java (primitive String) | C++ (std::string), Python (mixed, short strings), JavaScript

- When a string appears literally in source code, it is known as a string literal or an anonymous string. 

# Bit
- Inside the computer's world, there is only **data**. All this data is stored as long sequences of **bits**. 
- Bits are any kind of two-valued things, usually 0 and 1.
- There are 2<sup>n</sup> distinct sequences of 1's and 0's that can be made from n bits. Ex 8 bits = 2<sup>8</sup> distinct sequences.

Sequence | 0 | 0 | 0 | 0 | 1 | 1 | 0 | 1
---|---|---|---|---|---|---|---|---|
**Bit** | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1

Ex: (13)<sub>10</sub> = (00001101)<sub>2</sub>

**To convert binary numbers to decimal**: 
- Write down the binary number.
- List the powers of 2 from right to left, starting with 2<sup>0</sup> (which is 1) and going up to 2 raised to the number of digits minus 1. Similar to how the table above is set.
- Look at each digit in the binary number. If the digit is 1, write down the corresponding power of 2 below it. If the digit is 0, just leave a space.
- Add up all the written powers of 2. That sum is the decimal equivalent of the binary number.

Ex: (000110011)<sub>2</sub> = 1 + 2 + 16 + 32 = (51)<sub>10</sub>

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
  + kilo: 10<sup>3</sup> - kibi: 1024<sup>1</sup>
  + mega: 10<sup>6</sup> - mebi: 1024<sup>2</sup>
  + giga: 10<sup>9</sup> - gibi: 1024<sup>3</sup> 

# Cycle
Generally, Instruction cycle > Machine cycle > Bus cycle ~ Clock cycle. 

- The CPU will refer to its clock speed as the amount of **computation cycles** it can perform per second - a single computation or arithmetic operation (addition, subtraction, multiplication and division).
- A memory module (RAM stick) will refer to its clock speed as the amount of **memory cycles** it can perform per second - A simple read or write operation to memory. 
- You can call "Computation cycle of the CPU" as "CPU clock cycle" and "Memory cycle of the RAM modules" as "RAM clock cycle". 
<br>

<details>
  <summary>Consider a 32 – bit microprocessor, with a 16 – bit external data bus, driven by an 8 MHz input clock. Assume that this microprocessor has a bus cycle whose minimum duration equals four input clock cycles. What is the maximum data transfer rate for this microprocessor?</summary>
  <br>
- In a 32-bit microprocessor, with a 16-bit external data bus, data transferred per bus cycle = 2B (2 Bytes)
- Minimum bus cycle = 4 clock cycles.
- Maximum bus cycle rate = 8 MHz / 4 = 2 Mb/sec
- Data transfer rate = bus cycle rate * data per bus cycle = 2 Mb * 2 = 4 * 10<sup>6</sup> Bytes/sec.
</details>

## Clock cycle and Bus cycle
- A computer uses a clock. The frequency of this clock indicates how many (Giga/Mega/Kilo) cycles per second that the clock wave changes. This is the basis of any cycle for the computer. This can be considered a 'clock cycle'.

Ex: A CPU poses a clock speed of 5 GHz, which means 5 * 10<sup>9</sup> cycles per second. 

- The bus cycle is the cycle or time required to make a single read or write transaction between the CPU and an external device such as external memory. 


## Machine cycle
The amount of cycles needed to do either a fetch, read or write operation. The read or write may be more than a single bus cycle if the transaction between the CPU and memory is longer than the data width fetched or written. 

Ex: On an 8080 machine, the data width is 8 bits. If the CPU needs to fetch or write 16 bits of data, that will require two bus cycles.

## Instruction cycle
The amount of machine cycles needed to complete an instruction. This varies depending on the instruction. 

Ex:  Some instructions after fetching them from memory need to fetch more data to complete the instruction, some need to write data at the end of the instruction cycle, some instructions don't do much at all, like the NOP, which basically fetches the instruction and does nothing for one machine cycle.

# Programming
- **Programming** is the act of constructing a *program* – a set of precise instructions telling the computer what to do. 
- Computers themselves can do only stupidly straightforward things at an incredibly high speed.The art of programming is the skill of controlling complexity. 

Why does language matter? The same program can be expressed in both long and short, unreadable and readable ways. 
