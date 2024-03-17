# Table of Contents

[RAM](#ram)
- [Types](#types): DIMM, SO-DIMM, FB-DIMM, UDIMM, RDIMM, SIMM, RIMM, NVDIMM
- [RAM Kit](#ram-kit)
- [RAM Bus Speed](#ram-bus-speed)
- [Generations](#generations)
- [ECC](#ecc)
- [Memory channel](#memory-channel)
- [Rank](#rank)
- [DPC](#dpc)

# RAM
## Types
**DIMM** (Dual In-Line Memory), a **generic term** used to describe a type of memory module that consists of integrated circuits (ICs) mounted on a small circuit board. DIMMs are used to provide random access memory (RAM) in computers, servers, and other electronic devices: 
- **SO-DIMM** (Small Outline Dual In-Line Memory Module): Designed for space-constraints. It can also be configured to use less power. Used primarily in laptops, notebooks, and small form factor computers where space is limited. 
- **Micro-DIMM**: Even smaller than **SO-DIMM**. It is used in ultra-compact devices such as tablets, handheld devices, and embedded systems where space is extremely limited. 

- **UDIMM** (Unbuffered DIMM): The most common type of memory module used in consumer-grade desktop and server systems. It is **unbuffered**, meaning that **it does not contain additional memory buffers or registers between the memory chips and the memory controller on the motherboard.**
- **RDIMM** (Registered DIMM): A **buffer or register** is a small amount of memory integrated into the DIMM module itself. Its primary function is to act as intermediary between the memory chips on the DIMM and the memory controller on the motherboard. It helps  improve the stability and reliability of the memory subsystem by isolating the memory chips from the electrical load of the memory controller. Support larger memory configurations by reducing the electrical load on the memory controller. 
- **LRDIMM** (Load-Reduced DIMM): LRDIMMS are similar to RDIMMS, but include additional buffering to reduce electrical load and improve memory capacity. They are commonly used in high-density server configurations and memory-intensive applications.

**Other (outdated) types of memory module:**
- **SIMM** (Single In-line Memory Module): Older type. Unlike **DIMMs**, which have separate electrical contacts on both sides of the module, SIMMs have a single row of electrical contacts on one side.
- **RIMM** (Rambus In-line Memory Module): Designed for Rambus DRAM (RDRAM). 1990s - Early 2000s. They have a different physical and electrical design compared to DIMMs and are not compatible with standard DDR or DDR2 memory technologies.
- **FB-DIMM** (Fully Buffered DIMM):  FB-DIMM is a specialized type of DIMM that incorporates a buffering or hub component to reduce electrical load and improve memory capacity. FB-DIMMs were used in some high-performance computing systems and servers but have largely been replaced by other memory technologies due to their higher power consumption and complexity. 
- **NVDIMM** (Non-Volatile Dual In-line Memory Module): Similar to a hard drive or SSD in the sense that it provides persistent storage for data even when power is removed from the system. 

## RAM Kit
**RAM kit**: Consists of multiple RAM sticks (modules) that are sold together as a package and have the same specifications. By purchasing a RAM kit, you ensure that all the RAM sticks in the kit are compatible with each other (validated to work with each other flawlessly) and are designed to work together seamlessly in a multi-channel memory configuration.

![Quad channel RAM kit](Images/RAM%201%20Quad%20channel%20RAM%20kit.png)
- Triple channel kit.
- Dual channel kit.
- Single module.

![Specifications of T-Create Expert 32GB Kit (2 x 16GB) DDR5-6000 PC5-48000 CL30 Dual Channel Desktop Memory Kit](Images/RAM%202%20Memory%20kit%20specification%20example.png)

## RAM Bus Speed
- The frequency at which the RAM operates, typically measured in MHz (megahertz) or GHz (gigahertz). This frequency indicates how quickly the RAM can transfer data. It can also be referred to as **"transfer rate"**.

![DDR4 RAM Bus Speed](Images/Motherboard%2022%20DDR4%20RAM%20Speed.png)

Ex: 
- Memory speed (Friendly name) DDR4-4400 --> 4400 MHz --> 4.4 GHz --> 1 **memory cycle** per (1 / (4.4 x 10^9)) of a second.
- (Industry name) PC4-35200 --> 35200 MB/s

## Generations
- Each generation of RAM **increases speed and frequency while decreasing power consumption**. Since computer hardware is all connected and interdependent, this can lead to speed increases in other components, too, which is why upgrading your memory is a great way to fix a slow computer. 
- Memory is not compatible across all motherboards. Generally speaking, motherboards are built to support only one type of memory. **So, you can't mix and match SDRAM, DDR, DDR2, DDR3, DDR4, or DDR5 memory on the same motherboard, as they won't function. They may not even fit in the same sockets.**
- However, RAM systems are industry-wise standardized, so you can choose whichever manufacturer. 
- Data Rate (MT/s): Numbers of mega-transfers per second. Ex: 3200MT/s = 3200 x 10^6 transfers per second. 
- Transfer Rate (GB/s): Amount of data that can be transferred per second. Ex: 38.4GB/s.

--> You can think that Data Rate refers to how fast the RAM module can transfer data and Transfer Rate refers to how much the module can transfer data. 

Ex: DDR5 specifications: 
- Data Rate: 3200 - 6400 (MT/s)
- Transfer Rate: 38.4 - 51.2 (GB/s)

--> In one second, the module can perform 3200 x 10^6 transfers at the minimum and 6400 x 10^6 transfers at the maximum. The module can 'carry' 38.4 GB at the minimum and 51.2 GB at the maximum. 

Gen | Year | Rate | Note
---|---|---|---|
SDRAM | 1988 | **Prefetch: 1-bit; Data Rate (MT/s): 100 - 166; Transfer Rate (GB/s): 0.8 - 1.3** | Synchronous dynamic random-access memory (SDRAM), computers built before 2002. The 'synchronous' means the SDRAm modules are designed to automatically synchronize with the timing of the CPU. 
DDR   | 2000 | **Prefetch: 2-bit; Data Rate (MT/s): 266 - 400; Transfer Rate (GB/s): 2.1 - 3.2** | Double data rate (DDR). DDR transfer data to the processor on both the downbeat and upbeat of the clock signal, so twice per cycle. Using both beats to transfer data makes DDR memory significantly faster than SDR memory, which uses only one edge of the clock signal to transfer data. 
DDR2  | 2003 | **Prefetch: 4-bit; Data Rate (MT/s): 533 - 800; Transfer Rate (GB/s): 4.2 - 6.4; Memory chip: 2 - 4 GB** | Same internal clock speed but improved input/output bus signal. 
DDR3  | 2007 | **Prefetch: 8-bit; Data Rate (MT/s): 1066 - 1600; Transfer Rate (GB/s): 8.5 - 14.9; Memory chip: 4 - 8 GB** | 2x the bandwidth and transfer rates of DDR2, but a significant reduction in power consumption - roughly 40% compared to DDR2. Great memory option for laptops. 
DDR4  | 2014 | **Prefetch: Bit per Bank; Data Rate (MT/s): 2133 - 5100; Transfer Rate (GB/s): 17 - 25.6; Memory chip: 8 - 16 GB** | DDR4 processes 4 data rates per cycle. It also consumes less power and is faster and more efficient than DDR3. This newer generation also introduced **bank groups** to avoid having a prefetch of 16, which isn't desirable. With bank groups, each group can execute 8-bits of data independently from the other, so DDR4 can process multiple data requests with a clock cycle. 
DDR5  | 2021  | **Prefetch: 16-bit; Data Rate (MT/s): 3200 - 6400; Transfer Rate (GB/s): 38.4 - 51.2; ; Memory chip: 16 - 64 GB?** | The most recent generation with the biggest jump in memory technology we've seen since SDRAM. DDR5 brings better channel efficiency, improved power management, and optimized performance - enabling next-generation multi-core computing systems. DDR5 launch speeds deliver nearly double the bandwidth of DDR4. DDR5 memory standard is a denser memory stick and equates to more memory capacity in your system. In comparison, the DDR4 stopped at 16-gigabit memory chips, but DDR5 offers up to 64-gigabit memory chips. 

## ECC
ECC memory is a type of RAM found in workstations and servers. It’s valued by professionals and businesses with critical data for its ability to automatically detect and correct memory errors, thus fighting data corruption. It’s also supposed to lead to less crashes of a server/workstation over non-ECC memory.

How it works:
1. Error detection: ECC memory uses additional bits, known as parity or checksum bits, to store redundant information alongside the actual data. These parity bits are calculated based on the data bits and are used to detect errors that may occur during data storage or transmission.
2. Error Correction: When data is read from memory, the ECC mechanism checks the parity bits to determine if any errors have occurred. If an error is detected, the ECC mechanism can use the redundant information stored in the parity bits to correct the error automatically, without requiring intervention from the operating system or applications.

Considerations:
- This is not a sure-fire way to deal with all errors completely.
- **8 chips for storing data + 1 for error detection and correction.**
- 0.09% failure rate, compared to 0.6% of non-ECC. However, ECC memory is generally 0.25% slower.
- **Needs mainboards that support ECC** (ex: Threadripper).
- The 9th chip holds a mathematical process that ensures the data stored in the memory is correct. If there is an error, then it will recreate the correct data in real time. 
- **All registered memory is ECC.**
- **Non-ECC = non-buffered memory.**

![ECC and Non-ECC memory](Images/RAM%203%20ECC%20and%20Non-ECC%20RAM.png)
![More ECC and Non-ECC memory](Images/RAM%204%20ECC%20and%20Non-ECC%20RAM%202.png)

## Memory channel
**RAM slots and Memory channel**
- RAM slots are physical slots on the motherboard where you insert the RAM modules.
- The memory channel refers to the **logical pathways** or interfaces through which data is transferred between the RAM modules and the CPU's memory controller. 
  + The physical pathways through which data travels on the motherboard are typically referred to as a bus lines or traces - conductive pathways etched onto the circuit board. 
- Memory channel is 64-bit wide in modern systems. **The memory channel for earlier mainboard is not always 64-bit wide**. This refers to the amount of data that can be transferred at once, and it's typically measured in bits. 
- This limitation is primarily determined by the physical design of the memory controller and the memory modules. 
- It is also due to the width provding a good balance between data transfer speed and complexity (cost of implementation). **A memory channel can be designed to have more than 64-bit width**. Having a wider memory channel, such as 128-bit or 256-bit, could potentially increase the data transfer rate even further. However, this would require more complex memory controller designs and could significantly increase manufacturing costs. Additionally, the benefits of wider memory channels may be limited by other factors, such as the speed of the memory modules themselves and the overall architecture of the system.

Ex: A typical ATX motherboard has four RAM slots and it supports **dual-channel configurations**. The RAM slots are arranged in pairs, color-coded accordingly. For each pair, two slots of RAM connects to **two 64-bit interfaces (memory channels)** - The channels are NOT connected to each other. Rather, they operate in parallel, allowing the system to read from or write to both modules simultaneously under the right conditions. 

--> Each module will be able to send or receive data in 64-bit chunks, the memory controller will alternate between accessing each module. So, during each **memory cycle**, 64 bits of data from each RAM module can be transferred to or from the memory controller. 

In quad-channel configurations, often found in high-end workstations and servers, there are four slots connected to four separate channels. 

==> Multiple channels running parallel is similar to how Parallel BUS works (see also [Parallel BUS](#serial-and-parallel-bus)). The data is divided into smaller chunks, which are then sent down separate paths or channels. This allows for more data to be transferred at the same time, increasing the overall throughput of the system. However, one of the challenges with a parallel bus is synchronizing the data between different lines. Rather than relying on precise timing between different lines, each memory channel operates independently, with its own clock signal. This can help to reduce the issues associated with skew, since the data on each channel is synchronized locally.

==> You can perceive that each channel is utilizing a Serial BUS approach. In modern systems, the memory interface typically uses a high-speed serial communication protocol, such as DDR (Double Data Rate) SDRAM, which allows for fast and efficient data transfer over a single line or differential pair. Each memory channel operates independently, with its own dedicated interface and clock signal, allowing it to transfer data to and from the memory controller independently of the other channels. This means that one channel can be transferring data to the memory controller while another channel is receiving data from a different source, such as the CPU or an input/output peripheral.

**Memory controller**
- Memory controller, which is typically integrated into the CPU or part of the chipset on the motherboard, manages the communication between the CPU and the RAM modules/sticks. When the CPU needs to access data from RAM, the memory controller retrieves the data from the appropriate memory module(s) and transfers it to the CPU via the memory channel. 
- The data is transferred in chunks of 64 bits (8 bytes) at a time, which corresponds to the width of the memory channel. This process allows the CPU to efficiently access and process data stored in RAM.
- The memory controller is designed to handle data transfers in chunks of a certain size, and in many modern systems, this size is 64 bits per cycle. This means that each transfer between the memory modules and the CPU moves 64 bits of data at a time. This limitation is determined by the architecture of the memory controller and the overall design of the system.
- Memory controllers' bus widths range from 8-bit in earlier systems to 512-bit in more complicated systems nowadays - that means **512 = 64-bit per memory channel x 8 memory channels**

**Multi-channel configuration (memory architecture)**

The technology that increases the data transfer rate between the DRAM memory and the memory controller by adding more channels of communication between them. Theoretically, this multiplies the data rate by exactly the number of channels present:

Ex: Dual-channel memory employs two channels. Modern high-end desktop and workstation processors such as the AMD Ryzen Threadripper series and the Intel Core i9 Extreme Edition lineup support **quad-channel memory**. Server processors from the AMD Epyc series and the Intel Xeon platforms give support to memory bandwidth starting from quad-channel module layout to up to **octa-channel layout**.

Scenario: 1 x 32 GB < 2 x 16 GB?
- Dual-channel memory allows the motherboard to access two memory modules simultaneously, effectively doubling the data transfer rate between the memory and the CPU. This means that the system can read and write data faster when using two RAM modules compared to one. 
- Improved Memory Bandwidth: 
- Balanced Load: The memory controller can evenly distribute the workload between the modules, optimizing performance. In contrast, a single 32 GB RAM stick would require the memory controller to handle all the data transfers, potentially leading to bottlenecks and reduced efficiency. **You can think of single-core CPU and multi-core CPU**. 

Ex: Memory channel can efficiently fetch 64-bit data (going through a 64-bit channel) from one module in one single cycle. In the same cycle, the other module can be utilized for other tasks, such as handling inputs from the keyboard and mouse or fetching data from applications stored on the hard drives. 
- Redundancy and Fault Tolerance: With two RAM sticks, you have a fail-safe solution for when one of your RAM modules turns bad. 

**Dual RAM or Quad RAM**
(Or 1 x 32GB vs 2 x 16GB vs 4 x 8GB)

Usually, most mainboards only support dual-channel configuration, which utilize both channels. If you want to use all channels with 4 x setup, you should make sure that the mainboard supports quad channels.

## Rank
- A memory rank is 64-bit because the memory channel is [64-bit wide](../Computer%20Science/General%20Knowledge.md#bit).
  + It can transfer 64 bits of data in parallel in one **memory cycle**. (Different from **Computing cycle** of the CPU).
  + A memory rank has not always been 64-bit. Like how memory channel wasn't always 64-bit width. It has increased over time alongside advancements in computer architecture and memory technology.
  + A rank can increase from 64-bit to 128-bit rank in the future as technology advances. (<-- A memory channel will increase from 64-bit to 128-bit).

![DRAM Ranks](Images/RAM%205%20DRAM%20Ranks.png)
- Dual rank is always faster than a single rank. 
- 1 Dual-rank module of 32 GB = 2 Single-rank modules of 16 GB (Applying the same setup of dual-channel configurations mentioned above). **Again, we can refer to the analogy of single-core CPU and multi-core CPU.**

Ex: 
- 8GB 1Rx8: 8 GB RAM Single Rank, 8 chips, 8-bit per chip x 8 = 64-bit

![Single Rank, 8 chips](Images/RAM%206%20Single%20Rank%20&%208%20Chips.png)

- 8GB 2Rx8: 8 GB RAM, Dual Rank, 8 chips, 16-bit per chip x 8 = 128-bit (2 ranks)

![Dual Rank, 8 chips](Images/RAM%207%20Dual%20Rank%20&%208%20Chips.png)

## DPC

