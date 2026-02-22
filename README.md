<h1> Comparative Analysis of Spatial Mixing and Probabilistic Debiasing for SRAM-Based Random Bit Generation </h1>

<h2>Introduction</h2>
<p>
  Random number generation is a critical component in secure communication, cryptographic systems, authentication protocols, and embedded security applications. Hardware-based entropy sources are often preferred over purely algorithmic pseudo-random generators because they derive randomness from physical device behavior.

This project investigates SRAM startup behavior as a hardware entropy source on the ATmega328P microcontroller. When a microcontroller powers up, SRAM cells initialize into semi-random states due to manufacturing variations and physical noise. These startup patterns can be analyzed and conditioned to generate random bits.

The study systematically evaluates different entropy conditioning techniques to determine their effectiveness in improving randomness quality.
</p>

<h2>Objective</h2>
<p>
  The objective of this project is to:
</br>
-Extract raw SRAM startup data after power cycling.
</br>
-Analyze statistical randomness using bit frequency and Shannon entropy.
</br>
-Investigate spatial bias in memory.
</br>
-Compare entropy conditioning techniques:
</br>
-Local XOR Folding
</br>
-Global Half-Split XOR
</br>
-Von Neumann Debiasing
</br>
-Combined conditioning methods
</br>
-Evaluate entropy vs throughput tradeoffs.
</br>
-Identify the most effective conditioning strategy for embedded applications.
</p>

<h2>Concept</h2>
<p>
  SRAM startup values are not purely random. They exhibit:
</br>
-Spatial correlation</br>
-Structural bias</br>
-Dominant zero regions</br>
-Stable memory cells</br>
</br>
The project studies how different conditioning techniques affect:

Entropy = −P(1)log2​P(1)−P(0)log2​P(0)
</br>	
</br>​
The goal is to increase entropy while maintaining usable bit rate.

