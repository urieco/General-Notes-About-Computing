# Table of Contents
1. [Bit](#bit)
  - *-bit data
  - Bit and Byte
  - Decimal Prefix and Binary Prefix (Kilo vs Kibi)
2. [Cycle](#cycle)
  - Clock and Bus cycle
  - Machine cycle
  - Instruction cycle

# Bit
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
![Table of Decimal Prefix and Binary Prefix](Images/CS%201%20Decimal%20and%20Binary%20Prefix.png)
- Other method:
  + kilo: 10^3 - kibi: 1024^1
  + mega: 10^6 - mebi: 1024^2
  + giga: 10^9 - gibi: 1024^3 

# Cycle

Generally, Instruction cycle > Machine cycle > Bus cycle ~ Clock cycle. 

- The CPU will refer to its clock speed as the amount of **computation cycles** it can perform per second - a single computation or arithmetic operation (addition, substraction, multiplication and division).
- A memory module (RAM stick) will refer to its clock speed as the amount of **memory cycles** it can perform per second - A simple read or write operation to memory. 
- You can call "Computation cycle of the CPU" as "CPU clock cycle" and "Memory cycle of the RAM modules" as "RAM clock cycle". 

## Clock cycle and Bus cycle
- A computer uses a clock. The frequency of this clock indicates how many (Giga/Mega/Kilo) cycles per second that the clock wave changes. This is the basis of any cycle for the computer. This can be considered a 'clock cycle'.

Ex: A CPU poses a clock speed of 5 GHz, which means 5 x 10^9 cycles per second. 

- The bus cycle is the cycle or time required to to make a single read or write transaction between the CPU and an external device such as external memory. 

Ex:

Question: Consider a 32 – bit microprocessor, with a 16 – bit external data bus, driven by an 8 MHz input clock. Assume that this microprocessor has a bus cycle whose minimum duration equals four input clock cycles. What is the maximum data transfer rate for this microprocessor?

Answer: 
- In a 32-bit microprocessor, with a 16-bit external data bus, data transferred per bus cycle = 2B (2 Bytes)
- Minimum bus cycle = 4 clock cycles.
- Maximum bus cycle rate = 8 MHz / 4 = 2 Mb/sec
- Data transfer rate = bus cycle rate * data per bus cycle = 2 Mb * 2 = 4 * 10^6 Bytes/sec.

## Machine cycle
The amount of cycles needed to do either a fetch, read or write operation. The read or write may be more than a single bus cycle if the transaction between the CPU and memory is longer than the data width fetched or written. 

Ex: On an 8080 machine, the data width is 8 bits. If the CPU needs to fetch or write 16 bits of data, that will require two bus cycles.

## Instruction cycle
The amount of machine cycles needed to complete an instruction. This varies depending on the instruction. 

Ex:  Some instructions after fetching them from memory need to fetch more data to complete the instruction, some need to write data at the end of the instruction cycle, some instructions don't do much at all, like the NOP, which basically fetches the instruction and does nothing for one machine cycle.
