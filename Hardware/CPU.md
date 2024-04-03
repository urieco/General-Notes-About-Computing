# Table of Contents

[CPU](#CPU)
  - [Structure](#structure)
  - [Clock speed (GHz) and Cycle](#clock-speed-ghz-and-cycle)
  - [32-bit and 64-bit architecture](#32-bit-and-64-bit-architecture)
  - [Core](#core)
  - [Instruction set architecture](#)
  - [CPU Registers](#cpu-registers)

[History and Types](#types)

# CPU
Ref: [How does Computer Hardware Work?](https://www.youtube.com/watch?v=d86ws7mQYIg) (1:03 - 3:12)
- The Central Processing Unit is like the brain of a computer. It runs the Operating System, executes programs and manages hardwares. It has access to the system's RAM and includes a hierarchy of caches on itself for faster data retrieval. A CPU optimizes for sequential computations that require extensive branching and logic (imagine a navigation software that needs to run an algorithm to compute the shortest possible route between two points - The program will have a lot of if - else statements that can only be computed one by one or sequentially). 
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

In computing, a **computation cycle** typically refers to **one complete execution of a basic operation by the CPU** such as fetching an instruction from memory, performing a calculation, or writing data to memory - how it finishes processing one [32-bit or 64-bit sequence](../Computer%20Science/General%20Knowledge.md#bit) (For 32-bit or 64-bit architectures). It is **different from a memory cycle** of the RAM with BUS speed denoted by a unit like DDR4-4400, in which 4400 is usually 4400 MHz - dealing with operations such as reading and writing data to a particular memory location.

Ex: A CPU's clock speed is **2.7 GHz** → It can execute **2.7 billion (10<sup>6</sup>) cycles per second**. Each cycle corresponds to one basic operation that the CPU can perform. In the context of a 2.7 GHz CPU, **one cycle occurs every 1 / (2.7 x 10<sup>9</sup>) seconds = 0.370 nanoseconds**.

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

## Core
- Modern CPUs have multiple cores which allows them to do work in parallel, which allows you to use multiple applications on your PC at the same time.
- Programmers can write code that does multi-threading to utilize the cores on your machine to run code in parallel.
- **Why not just add more CPU cores?** - CPU cores are expensive. As the cores scale up, so does the power consumption and the heat dissipation requirements, which requires more complex designs for diminishing return.
- As of April of 2024:
  + The high-end Intel Core i9 14900HX possesses a total of 24 cores (8 Performance Cores + 16 Efficient Cores).
  + Apple's M3 Max poses a total of 40 cores.
  + Intel's Professional Grade (for servers and data centers): Intel Xeon line (Intel Xeon E-2436 with only 6 cores to Intel Xeon Platinum 8571N with 52 cores). *The first digit denotes the tier while the second digit denotes the production year - Higher means better*.
  + AMD Ryzen's Workstations: AMD Ryzen Threadripper PRO 7995WX with 96 cores. *Similar to more commercially affordable lines of AMD, the first digit denotes the production year (7 - 2023), the second digit denotes the tier of the chip (9 - Highest)*.
  + The highest Core count on a CPU currently belongs to Intel's next-generation Xeon server processor, code-named Sierra Forest, will include a version that features 288 cores.
 <br>

 - **GPU has more cores, why don't we use GPU over CPU?** - Not all cores are created equal. A single CPU core is far faster than a single GPU core and its architecture can handle complex logic and branching. Whereas, a GPU core is only designed for simple computations. Most of the code out there in the world can't take advantage of the parallelism and opt for running sequentially within a single thread. 

[CPU Cores and GPU Cores](#)

## Instruction set architecture
Ex: x86-64, ARM, RISC-V, MIPS, PowerPC...
- x86-64 and ARM are the most popular ones.
- x86-64 is what you'll find on your modern desktops and computers. The CISC instruction set is much more complex than the RISC. 
- ARM is what you'll find on your mobile devices. RISC is a reduced or simplified instruction set with better power efficiency.
- However, this distinction has gradually changed over the years thanks to the Apple silicone chips which have proven that ARM architecture can also work for high performance computing on laptops and desktops. Even Microsoft is investing on running computers with ARM.
- ARM is also becoming more popular with Cloud Providers such as ARM Neoverse or Amazon's Graviton 3 to compute more stuff with less power consumption. 

## CPU Registers
The registers are an important component of the processor's micro-architecture. The registers are the high speed memory built into the CPU chip for quick data access. It is also the fastest memory in the memory hierarchy. 

# History and Types
(From Oldest to Latest)
- 1936 - Z1: The first programmable computer created by Konrad Zuse, entirely mechanical. It represents binary data with sliding metal sheets. It has a clock rate of 1Hz - 1 instruction per second.
- 1945 - Von Neumann Architecture: It is still used in modern chips nowadays. It's the foundational design that describes how data and instructions are stored in the same memory space then handled by a processing unit. 

[Von Neumann Architecture](#)

- 1947: Invention of the transistor, a semiconductor that can amplify or switch electrical signals.
- 1958: The development of the integrated circuit, allowing multiple transistors to be placed on a single silicon chip.
- 1971: Intel released the first commercially available microprocessor. It is a 4-bit processor, meaning it could handle 4 bits of data at a time with approximately 2,300 transistors. The clock speed was 740 KHz.

## Types
- GPU (Graphics Processing Unit) / Graphic Card: To calculate the appearance of all the lights and shadows in a game on demand. It is highly optimized for parallel computing. Unlike a typical CPU with measly 16 cores, NVIDIA GeForce RTX 4090 has a total of 16384 CUDA cores. Each of these cores can handle a floating point or integer computation per cycle, which in turn, allows games to perform tons of linear algebra in parallel to render Graphics instantly every time you push a button on your controller. GPU is also essential in training deep learning models that perform tons of matrix multiplication on large data sets.
- TPU (Tensor Processing Unit): Similar to GPUs, but designed specifically for tensor operations, like the matrix multiplication required for deep learning. It was developed by Google in 2016 to integrate directly with its tensorflow software. A TPU contains thousands of these things called 'Multiply accumulators' that allow the hardware to perform matrix multiplication without the need to access registers or shared memory like a GPU would. It can save a lot of money to train a neural network that can take weeks or months to be trained. 
- DPU (Data Processing Unit): Designed specifically for Big Data Centers. They are more like a CPU and typically based on the arm architecture but are highly optimized for moving data around. They also handle networking functions like packet processing, routing, security and data storage like compression and encryption. The goal is to relieve the CPU from any data processing jobs so it can focus solely on doing general-purpose Computing.
- QPU (Quantum Processing Unit): It only exists in Theory at the moment. All the other processors deal in bits (0s and 1s). However, quantum computers deal in qubit or quantum bits that can exist in a superposition of both states simultaneously. A qubit can represent multiple possibilities at once, but once it is measured, it will collapse into one of the posisble states. These qubits are subjected to quantum entanglement which means the state of one (Q1) is directly related to the state of another (Q2), no matter that distance between them. 
