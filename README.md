<h1> Experimental-Analysis-of-SRAM-Startup-Randomness-Using-Statistical-Post-Processing-Techniques </h1>
<p> 
  To experimentally analyze the statistical randomness properties of SRAM startup data on the ATmega328P microcontroller and evaluate the effectiveness of XOR folding   and Von Neumann correction in improving bit frequency balance and Shannon entropy.
</p>
<h3> 
  This project investigates the randomness characteristics of SRAM startup behavior in the ATmega328P microcontroller by extracting raw memory states immediately    after power-on and analyzing their statistical properties. The generated bit stream is evaluated using bit frequency measurement and Shannon entropy calculation to quantify randomness quality. To improve statistical balance and reduce bias, two post-processing techniques—XOR folding and Von Neumann correction—are independently implemented and analyzed. A full integrated version combining both techniques is also evaluated. Comparative analysis is performed across four configurations: raw SRAM output, XOR-only processing, Von Neumann-only correction, and combined processing. The results quantify improvements in entropy, bit probability balance, and effective bit rate, thereby providing a systematic evaluation of hardware-based random bit generation and lightweight entropy enhancement techniques on an embedded microcontroller platform.
</h3>
