Keyword:
- PCI, PCIe, AGP, ISA
- BUS, Serial / Parallel BUS, Multiplexer

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
