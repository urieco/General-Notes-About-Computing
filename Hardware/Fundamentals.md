# Table of Contents
- [Electricity](#electricity)
  + Atoms: Neutrons, Protons, Electrons, Orbital and Bohr Models, isotopes.
  + Current / Ampere
- [Computer Memory Hierarchy](#computer-memory-hierarchy)

# Electricity
## Atoms
Ref: [What is electricity? Electricity Explained - (1)](https://www.youtube.com/watch?v=ru032Mfsfig)
- An atom contains: 
  + Neutrons (No electric charge or neutral charge, half the weight of the atom).
  + Protons (Have a positive charge, half of the weight of the atom).
  + Electrons (Have a negative charge, signficantly lighter than Neutrons and Protons).

- In a **stable, resting, or rather neutral electrical condition**, these charges balance each other out within the atom. This gives the atom a net electric charge of zero. → **Lowest possible energy level (ground state)**. 
  + Protons > Electrons: Positively charged.
  + Protons < Electrons: Negatively charged. 
  + It all depends on how the atom loses or gains more electrons. 

![Orbital Model of an Atom](Images/Fundamentals%202%20Orbital%20Model%20of%20an%20Atom.png)

(Ref: [A Better Way To Picture Atoms](https://youtu.be/W2Xb2GFK2yc) - Orbital model as in comparison to the Bohr model (a much simpler representation of an atom, also known as the planetary model))

- Atoms of one element all have the same number of protons, but can have different numbers of neutrons and electrons (Carbon-12, the stable one vs Carbon-14) - they are called **isotopes**. 
- Electron Orbital Shells: 1s2 2s2 2p6 (K, L, M, N, O, P, Q shells).
- Atoms with loose (free) electrons on the outermost shell (valence electrons of valence shells) are good **conductors**. Electrons move from atom to atom, even at room temperature (higher temperature causes higher electron movement), the movement of electrons is what creates an electric current.
Ex: 1s2 2s2 2p6 3s2 3p6 3d10 **4s2**.
- If an atom has a tight grip on the electrons on the outermost shell, they make good **insulators**. (They do not easily give up electrons but can get a local charge when the electrons from a conductor are rubbed off on them)
<br>

- **Wire**: Copper coil/core wrapped in rubber (insulating materials) cover.
  + No current applied: Free electrons move about randomly.
  + With current applied: All free electrons will move in the same direction. 
- When electrons move from atom to atom, they displace other electrons already there, which then push other electrons, and so on and so forth.
  + Anode (negative terminal/source) to Cathode (positive terminal/attractor).
  + Electrons are negatively charged, they flow from the negative terminal to the positive terminal. 
  + This is why an electrical plug has at least two tongs, one for incoming electrons and the other for outgoing.
- Electrons can't be spent, they do not cease to exist. They are mere carriers of charge and can only be useful on their way to their destination.

**NOTE**: Connecting two poles of a power source directly can be actually very dangerous → Short circuit, because there is nothing between the source and destination of elections, to power, such as a lamp or television. This means that the electron flow will not encounter any resistance. The release of energy, when short circuiting, is therefore instant, often paired with involved wire heating dangerously. 
→ Fuses to cut the current before it becomes too high, preventing damage or worse: Fire

## Current/Ampere
- Current is the flow of electrons, measured in Amperes (Amps), past a single point, in a circuit within a set amount of time.
- 1 ampere is defined as 1 coulomb of charge flowing through a conductor in 1 second. An ampere is a base unit of electric current. (How many electrons flow past a single point every second ?)

1 Amp = 1 Coulomb per second = 6.242 x 10^18 electrons per second

2 Amp = 2 Coulomb per second = 2 x 6.242 x 10^18 electrons per second

→ The higher the amperage, the greater the rate of electron flow (current) through the conductor. 

<details>
  <summary>Can I use a charger with the same voltage but different Amperage Rating?</summary>
  <br>
  Scenario: Base: 2V, 1.5A 
  <br>
  Replacement: 2V, 2A (or even 100A)
  <br>
  Conditions: 
  <ul>
    <li><b>The voltage must match</b>. Some devices can be designed to handle higher voltages, but it's better to get the same voltage. (If you're off by a little bit, it may be fine but if you're off by more than a little bit, it may damage the device). <b>Check if the input voltage is a range (100 - 200V) to make sure.</b></li>
    <li><b>The amperage must match or exceed</b> that required by the device. Lower amperage may work but slower or doesn't work at all.</li>
    <li>The polarity of the connection must be correct. Ex: In a direct current (DC) circuit, if you connect a battery to an electronic device, you need to ensure that the positive terminal of the battery is connected to the corresponding positive terminal of the device, and likewise for the negative terminals. This ensures the current flow in the intended direction, from negative terminal of the battery through the device and back to the positive terminal of the battery.</li>
  </ul>
  <br>
  AMP is not something that's pushed, it is something that's drawn. The device only use the amperage that it requires.
</details>

# Computer Memory Hierarchy
![Computer Memory Hierarchy](Images/Misc%201%20Computer%20Memory%20Hierarchy.png)

