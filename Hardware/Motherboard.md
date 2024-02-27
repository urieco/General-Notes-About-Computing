# Table of Contents
1. [Peripherals](#peripherals)
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
  - DIMM, SO-DIMM, FB-DIMM, UDIMM, RDIMM
  - ECC


# Peripherals
**External devices or components that are connected to a computer or other device to extend its functionality** to provide additional capabilities. These devices are typically used to input data, output information, or perform specific tasks, and they can vary widely in form and function. 
Examples:
- Input: Keyboards, mice, trackpads, touchscreens, scanners, webcams...
- Output: Monitors, printers, speakers, headphones, projectors...
- Storage: Hard drives, HDD, SSD, external hard drives, memory cards...
- Others: Networking devices (routers, modems, network adapters), game controllers, barcode readers, biometric scanners. 

# BUS
![Bus Graph](Images/Motherboard%201%20BUS.png)

- BUS slots (expansion slots).
Ex: PCI (Peripheral Component Interconnect), PCIe (PCI Express), AGP (Accelerated Graphics Port) - Connecting old graphics cards, ISA (Industry Standard Architecture). 
- Group of electrical wires that carry a signal:
  + **Data bus**: 32-bit BUS will only send 32-bit data, no more, no less. (The Bus) - The bus transfers data in either the serial or parallel method of data transfer. 
  + **Address bus**: Tell the computer where the data is going. (The Road) - The bus has address lines which match those of the processor. This allows data to be sent to or from specific memory locations. 
  + **Control bus**: Determine when the data is sent or completed. (The traffic light) - The bus provides a system clock signal to synchronize the peripherals attached to it with the rest of the system. 
  + Supply the power. 
- Types: System bus (connects the CPU) + A number of I/O buses. 

## Why 'BUS'?
In the past, computers use pathways to transmit information between components - the CPU and RAMs were not contained within a single IC (integrated circuit). They are mostly separataed in individual cabinets. Information travels from one cabinet to another by bundles of wires called a 'bus bar', later known as 'bus'.

![Old computers](Images/Motherboard%202%20Old%20Computers.png)

An analogy borrowed from the field of electronics and electrical engineering. In this context, a 'bus' is used to describe a communication system that allows the transfer of data between different components within a computer system. **A set of parallel conductors used to transmit electrical signals between various components of a computer system.**
-	A pathway or set of pathways that allows data and signals to travel between components on the motherboard. 
-	 66 MHz bus - Sends data at 66 millions cycles per second. 
-	The higher the bus speed, the faster the performance of the computer. 
-	Front Side Bus - the Connection between the CPU and the northbridge chipset. 

## Serial and Parallel BUS
- Design: **One lane** and **Multiple lanes**
- Architecture:
  + Parallel BUS: Multiple lanes, information is split, more pront to electromagnetic interference. Limited by how accurately you can sync data. 
  + Serial BUS: One channel, one lane, slower (back then), for long range, less expensive. As technology advances, it is replacing the old parallel bus since the clock speed is getting faster. 
- 1 lane !== 1 bit anymore.
- **Serial**: To keep circuits small, **multiplexers** are implemented. This process divided, say a 32-bit address into two halves and then transmitted them over two clock cycles. 
- RAMs, and PCI connected devices use parallel bus. 
- PCIe, SATA, USB, use serial bus. 

![Serial BUS and multiplexers](Images/Motherboard%203%20Multiplexers.png)

# Chipset
- Communications Hub + Traffic Control Centre
- In the past, there are a lot of chips on the motherboard for controlling different components. Nowadays, they condense most chips to only a few chips, now called a chipset. **A chipset is a smaller set of chips that has replaced**
## North Bridge, South Bridge
![North, South Bridge on the motherboard](Images/Motherboard%204%20North%20South%20Bridge.png)
- North Bridge: Closer to the North, facing the CPU socket --> Memory-sensitive components: RAM, GPU (PCIe / AGP), system memory.
- South Bridge: Closer to the South, connecting to the North Bridge, acts as a communication hub for less memory-sensitive components: Storage devices (SATA), USB ports, onboard networking chip, IDE, etc. 
- The North Bridge is faster than the South Bridge.

![Platform Controller Hub replaces North, South Bridge](Images/Motherboard%205%20Platform%20Controller%20Hub.png)
- Now, the North Bridge chip's functions are handled by the CPU while the South Bridge chip's functions are handled by the **Platform Controller Hub** (PCH).
- Less travelling, faster performance

# I/O Interface
![I/O interface](Images/Motherboard%206%20IO%20Interface.png)
## USB
- USB - Universal Serial Bus <-- Many due to there are so many different peripherals that utilize the USB interface + power source.
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
- The video ports link to the built-in video adapters on the motherboard, for CPUs that have integrated graphics cards / **integrated** GPU. 
- The other type of video card is **dedicated** GPU. 
![Video ports](Images/Motherboard%2010%20Video%20ports.png)

## Ethernet port / Network port
- The Ethernet port on a computer's I/O panel is typically connected to the computer's network interface card (NIC) (usually built-in) or network adapter. 

![Ethernet port](Images/Motherboard%2011%20Network%20port.png)
- Some even have a built-in Wifi adapter with two knobs for antennas. 

## Sound ports
The sound ports on a computer's I/O panel connect to the computer's sound card or audio chipset. 

Integrated sound chipset: 
- Lime Green (Line-out): primary output for audio playback (speakers, headphones).
- Pink (Mic-in): Low currents, mic-level. Example: Microphone. 
- Light blue (Line-in): Strong currents, line-level. Example: Piano. Both pink and blue are audio inputs, but they are indicative of the voltage level of the audio signal.
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
- Advice: Check for what kinds of form factors does your PC case supports. 
![Form factors (Left to Right): EATX, ATX, micro-ATX, mini-ITX](Images/Motherboard%2013%20Form%20factors.png)
![Form factors and sizes in PC case](Images/Motherboard%2014%20Form%20factors%20in%20PC%20case.png)

In short: 
- EATX: 30.5 x 33 (cm) - 8 RAM slots. 4 expansion slots
- ATX: 30.5 x 24.4 (cm) - 4 RAM slots. 4 expansion slots
- Micro-ATX (mATX): 24.4 x 24.4 (cm) - 4 RAM slots. Less expansion slots (4 --> 2). Square shape.
- Mini-ITX (Nano-ITX): 17 x 17 (cm). One PCIe (mostly for GPU).

# Storage
## SATA - Serial Advanced Technology Attachment
For the typical consumer desktop and laptop computers, most hard drives use SATA cables for data transfer and power. 
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
**DIMM** (Dual In-Line Memory), a **generic term** used to describe a type of memory module that consists of integrated circuits (ICs) mounted on a small circuit board. DIMMs are used to provide random access memory (RAM) in computers, servers, and other electronic devices: 
- **SO-DIMM** (Small Outline Dual In-Line Memory Module): Designed for space-constraints. It can also be configured to use less power. Used primarily in laptops, notebooks, and small form factor computers where space is limited. 
- **Micro-DIMM**: Even smaller than **SO-DIMM**. It is used in ultra-compact devices such as tablets, handheld devices, and embedded systems where space is extremely limtied. 

- **UDIMM** (Unbuffered DIMM): The most common type of memory module used in consumer-grade desktop and server systems. It is **unbuffered**, meaning that **it does not contain additional memory buffers or registers between the memory chips and the memory controller on the motherboard.**
- **RDIMM** (Registered DIMM): A **buffer or register** is a small amount of memory integrated into the DIMM module itself. Its primary function is to act as intermediary between the memory chips on the DIMM and the memory controller on the motherboard. It helps  improve the stability and reliability of the memory subsystem by isolating the memory chips from the electrical load of the memory controller. Support larger memory configurations by reducing the electrical load on the memory controller. 
- **LRDIMM** (Load-Reduced DIMM): LRDIMMS are similar to RDIMMS, but include additional buffering to reduce electrical load and improve memory capacity. They are commonly used in high-density server configurations and memory-intensive applications.

Other (outdated) types of memory module:
- **SIMM** (Single In-line Memory Module): Older type. Unlike **DIMMs**, which have separate electrical contacts on both sides of the module, SIMMs have a single row of electrical contacts on one side.
- **RIMM** (Rambus In-line Memory Module): Designed for Rambus DRAM (RDRAM). 1990s - Early 2000s. They have a different physical and electrical design compared to DIMMs and are not compatible with standard DDR or DDR2 memory technologies.
- **FB-DIMM** (Fully Buffered DIMM):  FB-DIMM is a specialized type of DIMM that incorporates a buffering or hub component to reduce electrical load and improve memory capacity. FB-DIMMs were used in some high-performance computing systems and servers but have largely been replaced by other memory technologies due to their higher power consumption and complexity. 
- **NVDIMM** (Non-Volatile Dual In-line Memory Module): Similar to a hard drive or SSD in the sense that it provides persistent storage for data even when power is removed from the system. 

## ECC
ECC memory is a type of RAM found in workstations and servers. It’s valued by professionals and businesses with critical data for its ability to automatically detect and correct memory errors, thus fighting data corruption. It’s also supposed to lead to less crashes of a server / workstation over non-ECC memory.

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
**RAM kit**: Consists of multiple RAM sticks (modules) that are sold together as a package and have the same specifications. By purchasing a RAM kit, you ensure that all the RAM sticks in the kit are compatible with each other (validated to work with each other flawlessly) and are designed to work together seamlessly in a multi-channel memory configuration.

![Quad channel RAM kit](Images/Motherboard%2017%20Quad%20channel%20RAM%20kit.png)
- Triple channel kit.
- Dual channel kit.
- Single module.

![Specifications of T-Create Expert 32GB Kit (2 x 16GB) DDR5-6000 PC5-48000 CL30 Dual Channel Desktop Memory Kit](Images/Motherboard%2018%20Memory%20kit%20specification%20example.png)

**RAM slots and Memory channel**
- RAM slots are physical slots on the motherboard where you insert the RAM modules.
- The memory channel refers to the pathway through which data is transferred between the RAM modules and the CPU's memory controller. 
- Memory channel is 64-bit wide. **The memory channel for earlier mainboard is not always 64-bit wide**
- This limitation is primarily determined by the physical design of the memory controller and the memory modules. 
- It is also due to the width provding a good balance between data transfer speed and complexity / cost of implementation. Having a wider memory channel, such as 128-bit or 256-bit, could potentially increase the data transfer rate even further. However, this would require more complex memory controller designs and could significantly increase manufacturing costs. Additionally, the benefits of wider memory channels may be limited by other factors, such as the speed of the memory modules themselves and the overall architecture of the system.

Example: A typical ATX motherboard has four RAM slots and it supports **dual-channel configurations**. The RAM slots are arranged in pairs, color-coded accordingly. Each pair is connected to a separate memory channel. They share the same memory bandwidth that each channel provides. 

--> Each module will be able to send or receive data in 64-bit chunks, but since two modules are sharing the same channel, the memory controller will alternate between accessing each module. So, during each **memory cycle**, only **64 / 2 = 32 bits** fo data from each RAM module can be transferred to or from the memory controller. 


**Memory controller**
- Memory controller, which is typically integrated into the CPU or part of the chipset on the motherboard, manages the communication between the CPU and the RAM modules/sticks. When the CPU needs to access data from RAM, the memory controller retrieves the data from the appropriate memory module(s) and transfers it to the CPU via the memory channel. 
- The data is transferred in chunks of 64 bits (8 bytes) at a time, which corresponds to the width of the memory channel. This process allows the CPU to efficiently access and process data stored in RAM.
- The memory controller is designed to handle data transfers in chunks of a certain size, and in many modern systems, this size is 64 bits per cycle. This means that each transfer between the memory modules and the CPU moves 64 bits of data at a time. This limitation is determined by the architecture of the memory controller and the overall design of the system.
- Memory controllers' bus widths range from 8-bit in earlier systems to 512-bit in more complicated systems nowadays - that means **512 = 64-bit per memory channel x 8 memory channels**

**Dual-channel configruations**


**Dual RAM or Quad RAM**
(Or 1 x 32GB vs 2 x 16GB vs 4 x 8GB)

Usually, most mainboard only supports dual channel, which utilize both channels. If you want to use all channels with 4 x setup, you should make sure that the mainboard supports quad channels.


## Rank
- The width of a memory rank is also referred as the memory bus or memory channel. 
- A memory rank is 64-bit because the memory channel is [64-bit wide](../Computer%20Science/General%20Knowledge.md#bit).
- It can transfer 64 bits of data in parallel in one **memory cycle**. (Different from **Computing cycle** of the CPU).
- A memory rank has not always been 64-bit. Like how memory channel wasn't always 64-bit width. It has increased over time alongside advancements in computer architecture and memory technology.
- A rank can increase from 64-bit to 128-bit rank in the future as technology advances. (<-- A memory channel will increase from 64-bit to 128-bit).
