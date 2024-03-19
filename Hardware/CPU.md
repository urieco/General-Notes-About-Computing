# Table of Contents

[CPU](#CPU)
  - [Structure](#structure)
  - [Clock speed (GHz) and Cycle](#clock-speed-ghz-and-cycle)
  - [32-bit and 64-bit architecture](#32-bit-and-64-bit-architecture)
  - [CPU Registers](#cpu-registers)

# CPU
Ref: [How does Computer Hardware Work?](https://www.youtube.com/watch?v=d86ws7mQYIg) (1:03 - 3:12)

- The CPU communicates directly with the RAM and the GPU through dedicated interfaces, while communication with other I/O interfaces is typically handled by the chipset (with which the CPU will communicate directly. The chipset acts as a hub for communication between the CPU, RAM and other I/O interfaces)

## Structure
- **Integrated heat spreader**, the metal part on top of the circuit.
- Small **metal package** which holds the **integrated circuit**, which is technically called a **Die**.
- The **Die** is mounted on a **printed circuit board**.
- **Printed circuit board** distributes the 1,200 connection points to landing pads that interface with the landing grid array on the motherboard.

![The structure of a CPU](Images/CPU%201%20The%20structure%20of%20a%20CPU.png)
- 10 cores where programs and instructions are run.

![Shared L3 Cache, Ring Interconnect and Integrated Graphics Processor](Images/CPU%202%20Shared%20L3%20Cache,%20Ring%20Interconnect%20and%20Integrated%20Graphics%20Processor.png)

## Clock Speed (GHz) and Cycle
Refer to: [Cycle](../Computer%20Science/General%20Knowledge.md#cycle)
A cycle can be called a clock cycle or CPU cycle. 

In computing, a **computation cycle** typically refers to **one complete execution of a basic operation by the CPU** such as fetching an instruction from memory, performing a calculation, or writing data to memory - how it finishes processing one [32-bit or 64-bit sequence](../Computer%20Science/General%20Knowledge.md#bit) (For 32-bit or 64-bit architectures). It is **different from a memory cycle** of the RAM with BUS speed denoted by unit like DDR4-4400, in which 4400 is usually 4400 MHz - dealing with operations such as reading and writing data to a particular memory location.

Ex: A CPU's clock speed is **2.7 GHz** → It can execute **2.7 billion (10^6) cycles per second**. Each cycle corresponds to one basic operation that the CPU can perform. In the context of a 2.7 GHz CPU, **one cycle occurs every 1 / (2.7 x 10^9) seconds = 0.370 nanoseconds**.

## 32-bit and 64-bit architecture
The most common architectures for today's computer systems. 

In a 32-bit computer architecture, the CPU processes data in [32-bit units](../Computer%20Science/General%20Knowledge.md#bit), which means it can process **32 bits (or 4 bytes) of data** in one CPU cycle. 

In 64-architecture, the CPU can process data in 64-bit units, effectively doubling the amount of data it can handle in a single cycle compared to a 32-bit architecture. If both CPUs of the two architectures are operating at the same clock speed.

**Other differences**:
Category       | 32-bit | 64-bit | Notes 
---|---|---|---
Memory support | 4GB    | 128GB or more | 32-bit system may not be able to utilize the available amount of RAM if it exceeds 4GB.
Performance    | Worse  | It handles larger amounts of register space (memory) and processes more data per clock cycle. It can perform 64-bit integers and floating-point numbers more efficiently.
Compatibility  | Only 32-bit applications | 32-bit AND 64-bit applications | Some 32-bit applications require specific support to combat compatibility issues to run on 64-bit systems. Not all older drivers for 32-bit applications aren't written for 64-bit systems. 
Resource Usage | Consume less resource   | Consume more due to larger data structures and pointers. 

## CPU Registers
The registers are an important component of the processor's micro-architecture. The registers are the high speed memory built into the CPU chip for quick data access. It is also the fastest memory in the memory hierarcy. 