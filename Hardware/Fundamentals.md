# Table of Contents
- [Electricity](#electricity)
  + Atoms: Neutrons, Protons, Electrons, Orbital and Bohr Models, isotopes, electrodes (anode and cathode); Electron flow and conventional current.
  + Current / Ampere. Direct Current (DC) and Alternating Current (AC). 
- [Computer Memory Hierarchy](#computer-memory-hierarchy)

# Electricity
## Atoms
Ref: [What is electricity? Electricity Explained - (1)](https://www.youtube.com/watch?v=ru032Mfsfig)
- An atom contains: 
  + Neutrons (No electric charge or neutral charge, half the weight of the atom).
  + Protons (Have a positive charge, half of the weight of the atom).
  + Electrons (Have a negative charge, signficantly lighter than Neutrons and Protons).

- In a **stable, resting, or rather neutral electrical condition**, these charges balance each other out within the atom. This gives the atom a net electric charge of zero. → **Lowest possible energy level (ground state)**. 
  + Ion is a name for an atom which has an unequal amount of electrons and protons. It all depends on how the atom loses or gains more electrons. 
  + Protons > Electrons: Positively charged or positive ion.
  + Protons < Electrons: Negatively charged or negative ion.

![Orbital Model of an Atom](Images/Fundamentals%202%20Orbital%20Model%20of%20an%20Atom.png)

(Ref: [A Better Way To Picture Atoms](https://youtu.be/W2Xb2GFK2yc) - Orbital model as in comparison to the Bohr model (a much simpler representation of an atom, also known as the planetary model))

- Atoms of one element all have the same number of protons, but can have different numbers of neutrons and electrons (Carbon-12, the stable one vs Carbon-14) - they are called **isotopes**. 
- Electron Orbital Shells: 1s<sup>2</sup> 2s<sup>2</sup> 2p<sup>6</sup> (K, L, M, N, O, P, Q shells).
- Atoms with loose (free) electrons on the outermost shell (valence electrons of valence shells) are good **conductors**. Electrons move from atom to atom, even at room temperature (higher temperature causes higher electron movement), the movement of electrons is what creates an electric current.
Ex: 1s<sup>2</sup> 2s<sup>2</sup> 2p<sup>6</sup> 3s<sup>2</sup> 3p<sup>6</sup> 3d<sup>10</sup> **4s<sup>2</sup>**.
- If an atom has a tight grip on the electrons on the outermost shell, they make good **insulators**. (They do not easily give up electrons but can get a local charge when the electrons from a conductor are rubbed off on them)
<br>
[A closed circuit](#)

- **Wire**: Copper coil/core wrapped in rubber (insulating materials) cover.
  + No current applied: Free electrons move about randomly.
  + With current applied: All free electrons will move in the same direction, due the voltage difference from a power source. 
- When electrons move from atom to atom, they displace other electrons already there, which then push other electrons, and so on and so forth.
  + Two electrodes: Anode (negative terminal/source) to Cathode (positive terminal/attractor).
  + Electrons are negatively charged, they flow from the negative terminal to the positive terminal. This is called the **Electron flow**, contrary to the **Conventional current** (Positve end to Negative end), which is the original theory, which is still widely used. 
  + **Charger carrier** is a particle or quasiparticle that is free to move, carrying an electric charge, especially the particles that carry electric charges in electrical conductors. Ex: electrons, ions and holes. 
  + This is why an electrical plug has at least two tongs, one for incoming electrons and the other for outgoing.
- Electrons can't be spent, they do not cease to exist. They are mere carriers of charge and can only be useful on their way to their destination.

**NOTE**: Connecting two poles of a power source directly can be actually very dangerous → Short circuit, because there is nothing between the source and destination of elections, to power, such as a lamp or television. This means that the electron flow will not encounter any resistance. The release of energy, when short circuiting, is therefore instant, often paired with involved wire heating dangerously. 
→ Fuses to cut the current before it becomes too high, preventing damage or worse: Fire

## Current/Ampere
- Current is the flow of electrons, measured in Amperes (Amps), past a single point, in a circuit within a set amount of time.
- 1 ampere is defined as 1 coulomb of charge flowing through a conductor in 1 second. An ampere is a base unit of electric current. (How many electrons flow past a single point every second ?)

1 Amp = 1 Coulomb per second = 6.242 x 10<sup>18</sup> electrons per second

2 Amp = 2 Coulomb per second = 2 x 6.242 x 10<sup>18</sup> electrons per second

→ The higher the amperage, the greater the rate of electron flow (current) through the conductor. 
<br>

- Direct Current (DC): Electrons flow in one direction. An oscilloscope will show DC as a flat line in the positive region.
- Alternating Current (AC): The electricity in your homes provides AC electricity. With alternating current, the electrons flow forwards and backwards continuously, much like the tide of the sea which flows in and out between high tide and low tide. An oscilloscope will show AC as a wave, passing through the positive and negative regions. 

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
    <li><b>The amperage must match or exceed</b> that required by the device. Lower amperage may work but slower charging rate or it doesn't work at all.</li>
    <li>The polarity of the connection must be correct. Ex: In a direct current (DC) circuit, if you connect a battery to an electronic device, you need to ensure that the positive terminal of the battery is connected to the corresponding positive terminal of the device, and likewise for the negative terminals. This ensures the current flow in the intended direction, from negative terminal of the battery through the device and back to the positive terminal of the battery.</li>
  </ul>
  <br>
  <b>AMP is not something that's pushed, it is something that's drawn</b>. The device only use the amperage that it requires.
</details>

## Voltage
[9V and 27V](#)

**Simple analogy**: 
1. Think of a large water tank that puts pressure on the pipes below, thanks to gravity, which creates **positive pressure** (surplus of water). The higher the water level in the tank, the greater the pressure it exerts, similar to how a higher voltage in a bettery results in a stronger push on the electrons flowing through a wire.
2. A syringe: As you pull the plunger back, the **negative pressure** (shortage of water) it creates in the barrel, sucks up whatever liquids is in the bottle (e.g. water). 

With electricity, gravity has little effect, but negative and positive pressures on an electric circuit will cause electrons to flow through it, from one end to the other, **creating an electric current**. 
- A battery is a great way of introducing both negative and positive pressure within an electric circuit (Which is also why they make their appearances in most closed circuit diagrams and illustrations). In general, all batteries have the same principle: They possess two electrodes: Anode (surplus of electrons/ negative terminal/source) and Cathode (shortage of electrons/ positive terminal/ attractor). 
  + When we refer to the surplus of electrons on the anode end, it doesn't necessarily mean that the we negatively charge the anode and keep it that way until its usage.
  + Let's refer to the the first demonstration of a battery by Alessandro Volta ( [How batteries work - Adam Jacobson](https://www.youtube.com/watch?v=9OVtk6G2TnQ) ): A stack of alternating layers of zinc and copper. A piece of Copper on top of a piece of Zinc, separated by papers or clothes soaked in a salt water solution (electrolyte). A chemical reaction is born, which is called **"Oxidation and reduction"**.
  + The zinc oxidizes, which means it loses electrons, and it increases its oxidation state (becoming more positive).  The lost and free electrons are, in turn, gained by the ions in the water in a process called **reduction**, producing hydrogen gas. *The reaction happens in the solution (electrolyte), rather than the supposed 'cathode'*.
 
<br>

- **Voltage is electric potential difference between two points** (Energy difference per coulomb between two points).
- We use a voltmeter to measure the difference in voltage between two points (the probe or test leads with the same color scheme Red(+) - Black(-) of the jumper cables).
  + If we measure two ends of a power source, we will get something like 1.5 V.
  + If we measure the same end, we will get 0V, because there is no difference in electric potential. 

# Computer Memory Hierarchy
![Computer Memory Hierarchy](Images/Misc%201%20Computer%20Memory%20Hierarchy.png)

