# Table of Contents
1. [Bit](#bit)
  - *-bit data
  - Bit and Byte
  - Decimal Prefix and Binary Prefix (Kilo vs Kibi)

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