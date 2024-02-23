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
  - Video adapters
  - Network interface card
  - Sound card
  - I/O Shield


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

![]
![]
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
![]

## Video adapters
- Some also have built-in video adapters. Old: DVI, VGA; New: HDMI, DisplayPort. 

## Network interface card
![Network socket]

## Sound card
Integrated sound card: 
- Lime Green (Line-out): primary output for audio playback (speakers, headphones).
- Pink (Mic-in): Low currents, mic-level. Example: Microphone. 
- Light blue (Line-in): Strong currents, line-level. Example: Piano. Both pink and blue are audio inputs, but they are indicative of the voltage level of the audio signal.
- Orange (CS-Out/Center/Subwoofer): When you have a dedicated subwoofer or a center. Front speakers or a soundbar.
- Black (RS-Out): Rear speakers. 
- White (SS-Out): Side speakers.

## I/O Shield
![]
- Protects against electromagnetic interference (EMI) between your motherboard and the components you are connecting to the IO panel (USB, HDMI, ethernet, etc).
- Acts as another physical barrier on the back of the case (against dust and potentially insects).
- Comes with the motherboard.
- Installed before the motherboard.
- Replacement --> Call the supplier. 





