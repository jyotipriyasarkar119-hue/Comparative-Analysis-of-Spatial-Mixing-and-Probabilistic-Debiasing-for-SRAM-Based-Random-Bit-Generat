<h1> Experimental-Analysis-of-SRAM-Startup-Randomness-Using-Statistical-Post-Processing-Techniques </h1>
<p> 
  To experimentally analyze the statistical randomness properties of SRAM startup data on the ATmega328P microcontroller and evaluate the effectiveness of XOR folding   and Von Neumann correction in improving bit frequency balance and Shannon entropy.
</p>
<h3>Description</h3>
  <p></p>
  This project investigates the randomness characteristics of SRAM startup behavior in the ATmega328P microcontroller by extracting raw memory states immediately    after power-on and analyzing their statistical properties. The generated bit stream is evaluated using bit frequency measurement and Shannon entropy calculation to quantify randomness quality. To improve statistical balance and reduce bias, two post-processing techniques—XOR folding and Von Neumann correction—are independently implemented and analyzed. A full integrated version combining both techniques is also evaluated. Comparative analysis is performed across four configurations: raw SRAM output, XOR-only processing, Von Neumann-only correction, and combined processing. The results quantify improvements in entropy, bit probability balance, and effective bit rate, thereby providing a systematic evaluation of hardware-based random bit generation and lightweight entropy enhancement techniques on an embedded microcontroller platform.
</p>

<h4>The randomness quality is evaluated using: </h4>

- Bit Frequency Measurement
- Shannon Entropy Calculation
- XOR Folding 
- Von Neumann Correction 
- Combined Post-Processing

<h3>Hardware Platform</h3>

- Arduino Uno (ATmega328P)

<h3> Experimental Method </h3>

1. Power cycle the board completely.
2. Read 128 bytes of uninitialized SRAM.
3. Convert bytes into bit stream (1024 bits).
4. Measure:
   - Number of 0s and 1s
   - Probability P(1) and P(0)
   - Shannon Entropy

<h3>Entropy Formula</h3>

<h4>H = -P(1)log2(P(1)) - P(0)log2(P(0))</h4>

Maximum entropy = 1 (ideal random)


