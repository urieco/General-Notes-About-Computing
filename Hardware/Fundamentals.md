# Table of Contents
- [Electricity](#electricity)
  + Atoms: Neutrons, Protons, Electrons, Orbital and Bohr Models, isotopes, electrodes (anode and cathode); Electron flow and conventional current.
  + Current / Ampere. Direct Current (DC) and Alternating Current (AC).
  + Voltage:
    + Open Circuit Voltage.
    + Undervoltage and Overvoltage.
  + Resistance.
  + The relationship of Ampere, Voltage and Resistance.
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
3. The pressure difference between the inside and outside of the cabin is analogous to the voltage, or electric potential difference, in an electrical circuit. When you open a small crack in an airplane window, you create a sudden pressure difference between the inside and outside of the cabin. This pressure difference causes air to rush from higher-pressure area (inside the cabin) to the lower-pressure area (outside the cabin) through the crack. The rapid movement of air represents a flow of energy, as the air carries kinetic engery in the form of its motion.
- Similarly, in an electrical circuit, **a voltage difference creates an electric field that drives the flow of electric charge (current)** from a higher potential to a lower potential. This flow of charge represents a flow of energy, as electrical energy is transferred from one point in the circuit to another.
- Consequencely, after a period of time, the pressure in the cabin equalizes with the pressure outside the cabin, the suction effect diminishes, and air flow through the crack subsides. Eventually, the pressure inside the cabin stabilizes, and the concentration of air inside the cabin becomes similar to that outside at that altitude. Similarly, in an electrical circuit, when the power source runs out of electricity (batteries use up all their stored chemical energy or we pull the plug out of the socket), the potential difference diminishes, the current flow decreases until it reaches equilibrium. At this point, the flow of electrical energy stabilizes, and the system reaches a steady state.

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
  + If we measure the voltage with the voltmeter, at the end of a battery capacity for example, we will see a decline until the number reaches 0.
- Certain devices are designed to operate within a specific voltage range. If the voltage supplied by the battery does not meet the requirements of the device, it may not function properly or may not operate at all.
<br>

### Open Circuit Voltage
Ref: [learningaboutelectronics.com](http://www.learningaboutelectronics.com/Articles/What-is-open-circuit-voltage.php)

Open circuit voltage (or potential) is voltage which is not connected to any load in a circuit. Because it doesn't drop any voltage across a load, as what would happen when it is connected to a load, a voltage source's open circuit voltage represents its full voltage value, since the voltage doesn't share any of its voltage with a load.

[Open circuit voltage and closed circuit voltage](#)

- The battery to the left is unconnected to any load. Assuming that this 1.5-volt battery is new and has full operational life of 1.5 volts, it will measure the full 1.5 volts across it when we take a voltmeter and place the meter's probes across its terminals. 
- The battery to the right, now, is connected to a load. Again, assuming that this battery has full life of 1.5 volts, it will only retain 0.17V of the 1.5V. The remaining voltage will be dropped across the 8Ω resistor. This is calculated by using Ohm's law, I=V/R. Since there is 9Ω in the circuit and the voltage source is 1.5V, the current going through the circuit is I= 1.5V/9Ω= 0.17A. We now use a revised version of ohm's law, V=IR, to calculate the voltages across the battery and the resistor. Since the battery has an internal resistance of 1Ω, it drops V= 0.17A * 1Ω= 0.17V. The resistor has a voltage drop of V= 0.17A * 8Ω= 1.36V.

**Open circuit voltage is real voltage**: There is a misconception many times that because a voltage source isn't connected to a circuit or load, the voltage doesn't really exist or its power doesn't go into effect until it is connected to a closed circuit path. However, this is erroneous.

A voltage source does not need to be connected to anything for voltage to exist. Voltage unconnected is real voltage. Even if a voltage source is unconnected and not attached to any load, the potential power still exists. A prime example of this is the voltage which comes out of a wall outlet. The standard value for the US is 120VAC. Even when nothing is plugged into the wall outlet, the potential across the power terminal's power supply and ground of the outlet will still measure 120VAC with nothing connected. The hazard of getting shocked from a wall outlet is still there. 

**While current can only exist when a circuit is closed, voltage always has potential**.

### Undervoltage and Overvoltage
Ref: [mes.com](https://www.mes.com.sg/2019/09/19/overvoltage-undervoltage-all-you-need-to-know/)
- Undervoltage happens when the average voltage of equipment falls below the rated voltage amount. Frequent undervoltage can result in a degradation in equipment performance and reliability. The winding suffers a substaintial amount of wear and tear in the winding and reduces the lifespan of the equipment. Insufficient voltage means that the equipment has to draw extra current in order to meet the power requirements. As a result of being unable to fulfil these needs – the equipment is not able to perform as how it normally does.
- Overvoltage happens when the average voltage is equivalent to higher output or efficiency. To be more precise, its when a supply voltage of 10 percent and above the rated motor voltage occurs, as seen from the listed standards. When overvoltage first occurs, it will usually impact the sensitive system components – motherboards and circuit boards. All these tiny electronic circuits are unable to cope with any extra voltage and current peaks. Additionally, it also leads to overheating due to the conversion of extra heat instead of operational output like torque. All these heat will continue accelerating and eventually cause the deterioration of bearing and insulation systems.

## Resistance
In a series circuit, where components are connected end-to-end, the Total Resistance is simply the sum of the resistances of each component:

R<sub>Total</sub> = R<sub>1</sub> + R<sub>2</sub> + R<sub>3</sub> + ...

In a parallel circuit, where components are connected across common points, the total resistance is more complex to calculate and involves the reciprocal of the sum of the reciprocals of each resistance:

1/R<sub>Total</sub> = 1/R<sub>1</sub> + 1/R<sub>2</sub> + 1/R<sub>3</sub> + ...

## The relationship of Ampere, Voltage and Resistance
- To measure how much current flows, we use **ampere**.
- To measure how strong current flows, we use **voltage**. 
- Voltage can exist without a current.
- If there is a non-zero voltage (V) applied across

**Ohm's Law**:

```V = I * R```

Whereas:
- V: Voltage (volt/V)
- I: Current (Ampere/A)
- R: Resistance (Ohm/Ω)

Ex: In a circuit, with a battery and a resistor. The battery can produce 10V. We want to have half an Amp flow through our circuit. We will need ```R = V / I = 10V / 0.5A = 20 (Ω)``` resistor. 

Some key points:
- It applies to **direct current** (DC) circuits, where the current flows in one constant direction.
- In **alternating current** (AC) circuits, the voltage and current constantly reverse direction, but Ohm's Law still applies to the instantaneous values at any given moment.
- Resistance is a property of the material the conductor is made of and its physical dimensions (length, thickness). 

# Computer Memory Hierarchy
![Computer Memory Hierarchy](Images/Misc%201%20Computer%20Memory%20Hierarchy.png)

