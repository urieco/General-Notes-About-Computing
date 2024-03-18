# Table of Contents
1. [Technical Terms](#technical-terms)
  - Peripherals
  - Circuit board
  - Lines / wires / traces
2. [BUS](#bus)
  - Types
  - How it works
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

[How the computer functions](#how-the-computer-functions)

# Technical Terms

## Peripherals
**External devices or components that are connected to a computer or other device to extend its functionality** to provide additional capabilities. These devices are typically used to input data, output information, or perform specific tasks, and they can vary widely in form and function. 
- Input: Keyboards, mice, trackpads, touchscreens, scanners, webcams...
- Output: Monitors, printers, speakers, headphones, projectors...
- Storage: Hard drives, HDD, SSD, external hard drives, memory cards...
- Others: Networking devices (routers, modems, network adapters), game controllers, barcode readers, biometric scanners...

## Circuit board
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
## Types
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

## How it works
- "BUS" generally refers to a set of lines or wires that connect different components in a computer systems, **not necessarily (or compulsorily) meant how only the CPU is connected with other components**.
  + When a CPU is advertised as being 32-bit, it means it can process data in 32-bit chunks, and it typically has a 32-bit data bus. However, the size of the data bus can vary depending on the specific CPU architecture and the system design.
  + In general, a 32-bit CPU will have a 32-bit data bus, which allows it to transfer 32 bits of data at a time between the CPU and other components such as memory or I/O devices. However, some CPUs may have a wider data bus, such as 64 bits, which allows for faster data transfer rates. (Refer to statement (1) right below). 

  Ex: [80386 Microprocessor](https://electronicsdesk.com/80386-microprocessor.html) is a 32-bit processor that holds the ability to carry out 32-bit operations in one cycle. It has a data bus of 32-bit, address bus of 32-bit. 

- Although this is a bit confusing, these different buses are sometimes together called simply "the bus." A user can think of the computer’s “bus” as one unit made up of three parts: data, address, and control, even though the three electrical pathways do not run along each other (and therefore don’t really form a single "unit") within the computer. 
- A PC's CPU will typically contain several buses, often of differing widths, that connect its various subunits. **It is common for modern CPUs to use on-chip buses that are wider than the bus they use to communicate with external devices such as memory** , and the speed difference between on- and off-chip operations must then be bridged by keeping a reservoir of temporary data in a CACHE. **(1)**

<details>
  <summary>Is it the address bus size or the data bus size that determines "8-bit, 16-bit,32-bit, 64-bit" systems?</summary>
  <br>
  Ref: https://superuser.com/questions/446395/is-it-the-address-bus-size-or-the-data-bus-size-that-determines-8-bit-16-bit

  In a simple design, the size of the data bus is the size of the processor registers. This is generally true for the first generation of most designs, so the first 16-bit CPUs had 16-bit buses, 32-bit CPUs had 32-bit data buses, etc.

  However, It is the size of the processor's integer registers that determine the OS type (64 vs 32) and not the data bus. The data bus can differ from the integer registers. Some real world examples where the data bus and integer register widths differ:
  - The original 8088 of the IBM PC is a 16-bit CPU design, but the data bus is 8-bits wide. To move 16-bits into a processor register from RAM required two access cycles.
  - The Original Pentium from 1992 has a 64-bit data bus but is a 32-bit design. The larger data bus allows the CPU to transfer more data in and out with caches but still only access 32-bits at a time internally with its CPU registers.

  Generally the pointer size also follows the register size but the physical address bus width can be bigger or smaller than the register size. Some examples:
  - Most 8-bit CPUs could address at least 64k of memory with a 16-bit address bus.
  - The 8086 was 16-bit but had a 20-bit address bus to allow more addressable RAM.
  - The original AMD Opteron is 64-bit but the physical address bus is 40-bits (internally) to simplify the design of the memory subsystem, since the a full 64-bits is too large to be utilized. Modern 64-bit AMD CPUs are 48-bits.

  **It's best to recognize that the bitness of a CPU is entirely architectural and mostly just from a software perspective. It doesn't have much to do with physical design anymore.**
</details> 

- An 8-bit bus carries data along 8 parallel lines. A 16-bit bus, also called **ISA (Industry Standard Architecture)**, carries data along 16 lines. A 32-bit bus, classified as **EISA (Enhanced Industry Standard Architecture)** or **MCA (Micro Channel Architecture)**, can carry data along 32 lines.
  + 8-bit bus: 8 lines solely for data transfering. 
  + **Separate sets of lines** (buses) designated to be address buses and control buses. 

  Ex: Scenario: A motherboard is advertised to  8-bit 

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
