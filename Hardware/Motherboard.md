# Table of Contents
1. [Technical Terms](#technical-terms)
  - Peripherals
  - Circuit board
  - Lines / wires / traces
2. [BUS](#bus)
  - Why 'BUS'?
  - Serial and Parallel BUS
3. [Chipset](#chipset)
  - North Bridge, South Bridge
  - Platform Controller Hub
4. [I/O Interface](#io-interface)
  - USB
  - Video ports --> Video cards / Video adapters 
  - Ethernet port --> Network interface card / Network adapter / Wifi adapter
  - Sound ports --> Integrated sound chipset / Đeicated sound card
  - I/O Shield
5. [Form factors](#form-factors)
6. [Storage](#storage)
  - SATA
  - SAS
7. [RAM](#ram)
  - Types: DIMM, SO-DIMM, FB-DIMM, UDIMM, RDIMM, SIMM, RIMM, NVDIMM
  - RAM Kit
  - RAM Bus Speed
  - Generations
  - ECC
  - Memory channel
  - Rank
  - DPC

[CPU](#CPU)
  - Structure
  - Clock speed (GHz) and Cycle
  - 32-bit and 64-bit architecture

[How the computer functions](#how-the-computer-functions)

# Technical Terms

## Peripherals
**External devices or components that are connected to a computer or other device to extend its functionality** to provide additional capabilities. These devices are typically used to input data, output information, or perform specific tasks, and they can vary widely in form and function. 
- Input: Keyboards, mice, trackpads, touchscreens, scanners, webcams...
- Output: Monitors, printers, speakers, headphones, projectors...
- Storage: Hard drives, HDD, SSD, external hard drives, memory cards...
- Others: Networking devices (routers, modems, network adapters), game controllers, barcode readers, biometric scanners...

## Circuit Board
- Made of non-conductive materials, such as fiberglass or plastic, and is used as a base to hold the electronic components and connect them together. 
- The conductive traces on the circuit board are made of a thin layer of metal, typically copper, that is deposited onto the surface of the board using a process called etching.
- The combination of the non-conductive board and the conductive traces creates a structure that allows electrical signals to be routed between different components in a controlled and precise manner.

## Lines / wires / traces
- Individual electrical pathways or wires that make up the [bus](#bus). Each line can carry one bit of data at a time, so an 8-bit bus has 8 lines, 16-bit bus has 16 lines. 
  + Wires that make up the bus are actually small conductive **traces etched onto the circuit board**. These traces are typically made of copper and are very thin, allowing them to be packed closely together to create a dense network of connections. 
  + These traces are much smaller than traditional wires, but they serve the same purpose of carrying electrical signals between different components on the motherboard. 
- The number of lines in a bus determines how much data can be transferred at once between different components in the system. 

Ex: 8-bit bus can transfer 8 bits (or 1 byte) of data at a time, while a 32-bit bus can transfer 32 bits (or 4 bytes) of data at a time. 
- The wider the bus, the more data can be transferred at once, which generally leads to **better performance**. However, wider buses also **require more physical space and can be more expensive to implement**.

## Physical pathway VS. Logical pathway
- Logical path is a high-level representation. It refers to the way data is organized and transmitted over the physical pathway. It's a set of protocols that govern how data is formatted, addressed, and transferred between different components in the system. 
- The physical path is the actual route, tangible components that make up the data communication path, such as the wires, cables, connectors, and other hardware components. 

# BUS
![Bus Graph](Images/Motherboard%201%20BUS.png)

Ref: [ecomputernotes.com](https://ecomputernotes.com/fundamental/introduction-to-computer/bus)

- Group of electrical wires that carry a signal:
  + **Data bus**: 32-bit BUS will only send 32-bit data, no more, no less. **(The Bus)**** - The bus transfers data in either the serial or parallel method of data transfer. A data bus width is measured by the number of bits that can travel on it at once. The speed at which its bus can transmit words, that is, its bus BANDWIDTH, crucially determines the speed of any digital device. One way to make a bus faster is to increase its width. 
  
  Ex: A 16-bit bus can transmit two 8-bit words at once, 'side-by-side', and so carries 8-bit data twice as fast as an 8-bit bus can. 
  + **Address bus**: Tell the computer where the data is going. **(The Road)** - The bus has address lines which match those of the processor. This allows data to be sent to or from specific memory locations. 
  + **Control bus**: Determine when the data is sent or completed. **(The traffic light)** - The bus provides a system clock signal to synchronize the peripherals attached to it with the rest of the system. 
  + **Expansion bus**: If your computer has expansion slots, there’s an **expansion bus**. Messages and information pass between your computer and the add-in boards you plug in over the expansion bus. 

  Ex: PCI (Peripheral Component Interconnect), PCIe (PCI Express), AGP (Accelerated Graphics Port - Old graphic cards).
  + It can also be used to supply the power. 

- "BUS" generally refers to a set of lines or wires that connect different components in a computer systems, **not necessarily (or compulsorily) meant how only the CPU is connected with other components**.
  + When a CPU is advertised as being 32-bit, it means it can process data in 32-bit chunks, and it typically has a 32-bit data bus. However, the size of the data bus can vary depending on the specific CPU architecture and the system design.
  + In general, a 32-bit CPU will have a 32-bit data bus, which allows it to transfer 32 bits of data at a time between the CPU and other components such as memory or I/O devices. However, some CPUs may have a wider data bus, such as 64 bits, which allows for faster data transfer rates. (Refer to statement (1) right below). 

  Ex: [80386 Microprocessor](https://electronicsdesk.com/80386-microprocessor.html) is a 32-bit processor that holds the ability to carry out 32-bit operations in one cycle. It has a data bus of 32-bit, address bus of 32-bit. 

- Although this is a bit confusing, these different buses are sometimes together called simply "the bus." A user can think of the computer’s “bus” as one unit made up of three parts: data, address, and control, even though the three electrical pathways do not run along each other (and therefore don’t really form a single "unit") within the computer. 
- A PC's CPU will typically contain several buses, often of differing widths, that connect its various subunits. **It is common for modern CPUs to use on-chip buses that are wider than the bus they use to communicate with external devices such as memory** , and the speed difference between on- and off-chip operations must then be bridged by keeping a reservoir of temporary data in a CACHE. **(1)**
- An 8-bit bus carries data along 8 parallel lines. A 16-bit bus, also called **ISA (Industry Standard Architecture)**, carries data along 16 lines. A 32-bit bus, classified as **EISA (Enhanced Industry Standard Architecture)** or **MCA (Micro Channel Architecture)**, can carry data along 32 lines.
  + 8-bit bus: 8 lines solely for data transfering. 
  + **Separate sets of lines** (buses) designated to be address buses and control buses. 

  Ex: Scenario: A motherboard is advertised to have 8-bit 

- A bus transfers electrical signals from one place to another. An actual bus appears as an endless amount of [etched copper circuits](#lines--wires--traces). on the motherboard's surface. The bus connected to the CPU through the **BUS Interface Unit**. 
  + Data travels between the CPU and memory along the data bus. The location (address) of that data is carried along the address bus. A clock signal which keeps everything in synch travels along the control bus.
  + The clock acts like a traffic light for all the PC’s components; the "green light" goes on with each clock tick. A PC’s clock can "tick" anywhere from 20 to 65 million times per second, which makes it seem like a computer is really fast. But since **each task (such as saving a file) is made up of several programmed instructions**, and each of those instructions takes several clock cycles to carry out, a person sometimes has to sit and wait for the computer to catch up.


## Why 'BUS'?
In the past, computers use pathways to transmit information between components - the CPU and RAMs were not contained within a single IC (integrated circuit). They are mostly separated in individual cabinets. Information travels from one cabinet to another by bundles of wires called a 'bus bar', later known as 'bus'.

![Old computers](Images/Motherboard%202%20Old%20Computers.png)

An analogy borrowed from the field of electronics and electrical engineering. In this context, a 'bus' is used to describe a communication system that allows the transfer of data between different components within a computer system. **A set of parallel conductors (lines) used to transmit electrical signals between various components of a computer system.**
-	A pathway or set of pathways that allows data and signals to travel between components on the motherboard. 
-	66 MHz bus - Sends data at 66 millions cycles per second. 
-	The higher the bus speed, the faster the performance of the computer. 
-	Front Side Bus - the Connection between the CPU and the northbridge chipset. 

## Serial and Parallel BUS
- Design: **One lane** and **Multiple lanes**
- Architecture:
  + Parallel BUS: Multiple lanes, information is split, more prone to electromagnetic interference. Limited by how accurately you can sync data. 
  + Serial BUS: One channel, one lane, slower (back then), for long range, less expensive. As technology advances, it is replacing the old parallel bus since the clock speed is getting faster. 
- 1 lane !== 1 bit anymore.
- **Serial**: To keep circuits small, **multiplexers** are implemented. This process divided, say a 32-bit address into two halves and then transmitted them over two clock cycles. 
- RAMs, and PCI connected devices use parallel bus. 
- PCIe, SATA, USB, use serial bus. 

![Serial BUS and multiplexers](Images/Motherboard%203%20Multiplexers.png)

# Chipset
- Communications Hub + Traffic Control Centre
- In the past, there were a lot of chips on the motherboard for controlling different components. Nowadays, they condense most chips to only a few chips, now called a chipset. **A chipset is a smaller set of chips that has replaced**.
- The CPU's communication with other I/O interfaces is typically handled by the chipset (The CPU has communicated directly with the RAM and the GPU through dedicated interfaces).

## North Bridge, South Bridge
![North, South Bridge on the motherboard](Images/Motherboard%204%20North%20South%20Bridge.png)
- North Bridge: Closer to the North, facing the CPU socket --> Memory-sensitive components: RAM, GPU (PCIe / AGP), system memory.
- South Bridge: Closer to the South, connecting to the North Bridge, acts as a communication hub for less memory-sensitive components: Storage devices (SATA), USB ports, onboard networking chip, IDE, etc. 
- The North Bridge is faster than the South Bridge.

![Platform Controller Hub replaces North, South Bridge](Images/Motherboard%205%20Platform%20Controller%20Hub.png)
- Now, the North Bridge chip's functions are handled by the CPU while the South Bridge chip's functions are handled by the **Platform Controller Hub** (PCH).
- Less traveling, faster performance

# I/O Interface
![I/O interface](Images/Motherboard%206%20IO%20Interface.png)

## USB
- USB - Universal Serial Bus <-- There are many types of USB due to the large number of peripherals that utilize the USB interface + power source.
- A standard connection interface  that enables communication between devices and a host controller such as a personal computer.

![USB Types](Images/Motherboard%207%20USB%20Types.png)
![USB Types 2](Images/Motherboard%208%20USB%20Types%202.png)
- USB Type A: Common, really universal.
- USB Type B: Old, for printers.
- Mini USB (Type A, B): Camera, MP3 Player. Replaced by Micro USB.
- Micro USB: Android phone, bluetooth headset, external battery, smartwatch. Some are replaced by USB C.
- USB C: Used with Thunderbolt 3 (40Gbps).

**Generations**
- 1.0: 1.5 Mbps.
- 1.1: 12 Mbps.
- 2.0: 480 Mbps - Flash drives, mice, keyboards.
- 3.0: 5 Gbps - 3.1 Gen 1 (Blue), 3.2 Gen 1 (Red).
- 3.1: 10 Gbps - 3.2 Gen 2 (Red).
- 3.2: 20 Gbps - 3.2 Gen 2 x 2.
- 4.0: 40 Gbps - USB, 4K, 16K, Thunderbolt 4.

![USB Gens and How confusing they are](Images/Motherboard%209%20USB%20Gens.png)

## Video ports
- Some also have built-in video adapters. Old: DVI, VGA; New: HDMI, DisplayPort. 
- The video ports link to the built-in video adapters on the motherboard, for CPUs that have integrated graphics cards (**integrated** GPU). 
- The other type of video card is **dedicated** GPU. 

![Video ports](Images/Motherboard%2010%20Video%20ports.png)

## Ethernet port (Network port)
- The Ethernet port on a computer's I/O panel is typically connected to the computer's network interface card (NIC) (usually built-in) or network adapter. 

![Ethernet port](Images/Motherboard%2011%20Network%20port.png)
- Some even have a built-in Wifi adapter with two knobs for antennas. 

## Sound ports
The sound ports on a computer's I/O panel connect to the computer's sound card or audio chipset. 

Integrated sound chipset: 
- Lime Green (Line-out): primary output for audio playback (speakers, headphones).
- Pink (Mic-in): Low currents, mic-level. Ex: Microphone. 
- Light blue (Line-in): Strong currents, line-level. Ex: Piano. Both pink and blue are audio inputs, but they are indicative of the voltage level of the audio signal.
- Orange (CS-Out/Center/Subwoofer): When you have a dedicated subwoofer or a center. Front speakers or a soundbar.
- Black (RS-Out): Rear speakers. 
- White (SS-Out): Side speakers.

There are also dedicated sound cards that can be used for:
- Improved audio quality: digital-to-analog converters (DACs) and analog-to-digital converters (ADCs), resulting in better sound reproduction and higher fidelity audio output. Good for **instruments' inputs**. 
- Enhanced audio features: surround sound processing, virtualization effects, equalization controls, and advanced signal processing algorithms. 
- Low latency sound. 
- Multiple Input/Output ports.

## I/O Shield
![I/O Shield](Images/Motherboard%2012%20IO%20Shield.png)
- Protects against electromagnetic interference (EMI) between your motherboard and the components you are connecting to the IO panel (USB, HDMI, ethernet, etc).
- Acts as another physical barrier on the back of the case (against dust and potentially insects).
- Comes with the motherboard.
- Installed before the motherboard.
- Replacement --> Call the supplier. 

# Form factors
- Standardization of sizes, arrangements, (amount of) expansion slots...
- Most common form: ATX.
- Advice: Check for what kind of form factor does your PC case supports. 

![Form factors (Left to Right): EATX, ATX, micro-ATX, mini-ITX](Images/Motherboard%2013%20Form%20factors.png)
![Form factors and sizes in PC case](Images/Motherboard%2014%20Form%20factors%20in%20PC%20case.png)

In short: 
- EATX: 30.5 x 33 (cm) - 8 RAM slots. 4 expansion slots
- ATX: 30.5 x 24.4 (cm) - 4 RAM slots. 4 expansion slots
- Micro-ATX (mATX): 24.4 x 24.4 (cm) - 4 RAM slots. Less expansion slots (4 --> 2). Square shape.
- Mini-ITX (Nano-ITX): 17 x 17 (cm). One PCIe (mostly for GPU).

# Storage
## SATA - Serial Advanced Technology Attachment
For the typical consumer desktop and laptop computers. Most hard drives use SATA cables for data transfer and power. 
- Cheaper.
- Used for archiving.
- Connects to a dozen or so storage devices.
- SATA generations
  + SATA I: 1.5 Gbps.
  + SATA II: 3.0 Gbps.
  + SATA: III: 6.0 Gbps.
- Alternatives: SAS, Older (IDE, PATA (Parallel ATA)).

## SAS - Serial Attached SCSI
- Pricier but faster.
- Connects more devices than SATA, 128 devices. 
- Good for storage devices used in **servers** (most common usage). 

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

![Quad channel RAM kit](Images/Motherboard%2017%20Quad%20channel%20RAM%20kit.png)
- Triple channel kit.
- Dual channel kit.
- Single module.

![Specifications of T-Create Expert 32GB Kit (2 x 16GB) DDR5-6000 PC5-48000 CL30 Dual Channel Desktop Memory Kit](Images/Motherboard%2018%20Memory%20kit%20specification%20example.png)

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

![ECC and Non-ECC memory](Images/Motherboard%2015%20ECC%20and%20Non-ECC%20RAM.png)
![More ECC and Non-ECC memory](Images/Motherboard%2016%20ECC%20and%20Non-ECC%20RAM%202.png)

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

![DRAM Ranks](Images/Motherboard%2019%20DRAM%20Ranks.png)
- Dual rank is always faster than a single rank. 
- 1 Dual-rank module of 32 GB = 2 Single-rank modules of 16 GB (Applying the same setup of dual-channel configurations mentioned above). **Again, we can refer to the analogy of single-core CPU and multi-core CPU.**

Ex: 
- 8GB 1Rx8: 8 GB RAM Single Rank, 8 chips, 8-bit per chip x 8 = 64-bit
![Single Rank, 8 chips](Images/Motherboard%2020%20Single%20Rank%20&%208%20Chips.png)

- 8GB 2Rx8: 8 GB RAM, Dual Rank, 8 chips, 16-bit per chip x 8 = 128-bit (2 ranks)
![Dual Rank, 8 chips](Images/Motherboard%2021%20Dual%20Rank%20&%208%20Chips.png)

## DPC



# CPU
- The CPU communicates directly with the RAM and the GPU through dedicated interfaces, while communication with other I/O interfaces is typically handled by the chipset.
## Structure
- Integrated Heat Spreader, the metal part on top of the circuit.
- Metal package which holds the integrated circuit.
- Integrated circuit = Die is mounted on a printed circuit board.
- Printed circuit board that distributes the 1,200 connection points on landing pads that interface with the landing grid array on the motherboard.

![The structure of a CPU](Images/Motherboard%2023%20The%20structure%20of%20a%20CPU.png)
- A bunch of transistors.

![Shared L3 Cache, Ring Interconnect and Integrated Graphics Processor](Images/Motherboard%2024%20Shared%20L3%20Cache,%20Ring%20Interconnect%20and%20Integrated%20Graphics%20Processor.png)

## Clock Speed (GHz) and Cycle
Refer to: [Cycle](../Computer%20Science/General%20Knowledge.md#cycle)

In computing, a **computation cycle** typically refers to **one complete execution of a basic operation by the CPU** - how it finishes processing [32-bit or 64-bit sequences](../Computer%20Science/General%20Knowledge.md#bit). (Differentiating from a memory cycle of the RAM with BUS speed denoted by MHz like DDR4-4400)

Ex: A CPU's clock speed is **2.7 GHz** → It can execute **2.7 billion (10^6) cycles per second**. Each cycle corresponds to one basic operation that the CPU can perform. In the context of a 2.7 GHz CPU, **one cycle occurs every 1 / (2.7 x 10^9) seconds = 0.370 nanoseconds**.

## 32-bit and 64-bit architecture
In a 32-bit computer architecture, the CPU processes data in 32-bit units, which means it can process **32 bits (or 4 bytes) of data - a sequence of either zeros or ones (01010101000001000… - 32-character-long)** in one CPU cycle. 
In 64-architecture, the CPU can process data in 64-bit units, effectively doubling the amount of data it can handle in a single cycle compared to a 32-bit architecture. If both CPUs of the two architectures are operating at the same clock speed, the 64-bit CPU can process 64-character-long sequences of either zeros or ones. 

**Other differences**:
Category       | 32-bit | 64-bit | Notes 
---|---|---|---
Memory support | 4GB    | 128GB or more | 32-bit system may not be able to utilize the available RAM if it exceeds 4GB.
Performance    | Worse  | It handles larger amounts of register space (memory) and processes more data per clock cycle. It can perform 64-bit integers and floating-point numbers more efficiently.
Compatibility  | Only 32-bit applications | 32-bit AND 64-bit applications | Some 32-bit applications require specific support to combat compatibility issues to run on 64-bit systems. Some older drivers for 32-bit applications aren't written for 64-bit systems. 
Resource Usage | Consume less resource   | Consume more due to larger data structures and pointers. 


# How the computer functions
Ex: I click on the icon of the application called **Firefox**

1. The mouse sends an input signal to the computer's motherboard, which is received by the input/output controller hub (ICH) in the chipset.
2. The ICH forwards the input signal to the CPU, which processes it and determines that the user has clicked on the Firefox icon. 
  - The **File Explorer** (or **Windows Explorer** on Windows OS) is responsible for managing the graphical user interface (GUI) of the OS, including desktop and its icons. It starts on startup.
  - It determines that the Firefox icon that I click on refers to the application Firefox.exe.
3. The CPU sends a request to the memory controller (typically integrated on the CPU itself), to retrieve the data for the Firefox application (in the hard drive) from the system's RAM.  
4. The memory controller instructs the RAM modules to forward the data to itself and then the CPU to process. 
5. The CPU processes the data for the Firefox application (.exe file with instructions on how to run it) and sends instructions to responsible components, particularly the GPU, to render the application's graphical user interface (GUI) on the computer's display.
6. The GPU receives the instructions and retrieves the necessary textures, shaders, and other graphical data from its own dedicated video memory (VRAM).
7. The GPU processes the graphical data and sends the resulting video signal to the computer's display, which shows the Firefox application's GUI.
