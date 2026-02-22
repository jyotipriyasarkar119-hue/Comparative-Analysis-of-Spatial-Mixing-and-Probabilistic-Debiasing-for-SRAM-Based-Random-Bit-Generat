
<h1>SRAM Experimental Results</h1>

<h2>Experiment 1: SRAM Random Bit Generation </h2>
<hr>

<h3>Statistical Analysis</h3>

<table>
    <tr>
        <th>Metric</th>
        <th>Value</th>
    </tr>
    <tr>
        <td>Total Bits</td>
        <td>1024</td>
    </tr>
    <tr>
        <td>Ones</td>
        <td>407</td>
    </tr>
    <tr>
        <td>Zeros</td>
        <td>617</td>
    </tr>
    <tr>
        <td>P(1)</td>
        <td>0.397461</td>
    </tr>
    <tr>
        <td>P(0)</td>
        <td>0.602539</td>
    </tr>
    <tr>
        <td>Shannon Entropy</td>
        <td>0.969446</td>
    </tr>
</table>

<hr>

<h3>Interpretation</h3>
<ul>
    <li>The bit distribution shows a bias toward 0.</li>
    <li>Entropy is close to 1, indicating strong randomness.</li>
    <li>SRAM startup behavior demonstrates high statistical unpredictability despite bias.</li>
</ul>

<hr>

<h3>Observations</h3>

<ul>
    <li>Output remains consistent across boots (indicating stable SRAM regions).</li>
    <li>Some spatial bias is visible in memory.</li>
    <li>Suitable for entropy-based applications with statistical post-processing.</li>
</ul>

<hr>

<h1>SRAM XOR Folding Experimental Results</h1>


<hr>

<h2>Experiment 2: XOR Folding (Block Size = 8)</h2>

<table>
<tr>
    <th>Metric</th>
    <th>Value</th>
</tr>
<tr>
    <td>Total Bits</td>
    <td>128</td>
</tr>
<tr>
    <td>Ones</td>
    <td>42</td>
</tr>
<tr>
    <td>Zeros</td>
    <td>86</td>
</tr>
<tr>
    <td>P(1)</td>
    <td>0.328125</td>
</tr>
<tr>
    <td>P(0)</td>
    <td>0.671875</td>
</tr>
<tr class="highlight">
    <td>Shannon Entropy</td>
    <td>0.912999</td>
</tr>
</table>

<hr>

<h2>Experiment 3: XOR Folding (Block Size = 2)</h2>

<table>
<tr>
    <th>Metric</th>
    <th>Value</th>
</tr>
<tr>
    <td>Total Bits</td>
    <td>512</td>
</tr>
<tr>
    <td>Ones</td>
    <td>151</td>
</tr>
<tr>
    <td>Zeros</td>
    <td>361</td>
</tr>
<tr>
    <td>P(1)</td>
    <td>0.294922</td>
</tr>
<tr>
    <td>P(0)</td>
    <td>0.705078</td>
</tr>
<tr class="highlight">
    <td>Shannon Entropy</td>
    <td>0.874995</td>
</tr>
</table>


<hr>

<h2>Experiment 4: Half-Split XOR (Global Mixing)</h2>
<table>
<tr><th>Metric</th><th>Value</th></tr>
<tr><td>Total Bits</td><td>512</td></tr>
<tr><td>Ones</td><td>214</td></tr>
<tr><td>Zeros</td><td>298</td></tr>
<tr><td>P(1)</td><td>0.417969</td></tr>
<tr><td>P(0)</td><td>0.582031</td></tr>
<tr class="best"><td>Shannon Entropy</td><td>0.980496</td></tr>
</table>

<hr>

<h3>Comparative Summary</h3>

<table>
<tr>
    <th>Method</th>
    <th>Total Bits</th>
    <th>P(1)</th>
    <th>Entropy</th>
</tr>
<tr>
    <td>XOR (Block=8)</td>
    <td>128</td>
    <td>0.328125</td>
    <td>0.912999</td>
</tr>
<tr>
    <td>XOR (Block=2)</td>
    <td>512</td>
    <td>0.294922</td>
    <td>0.874995</td>
</tr>
<tr class="best">
    <td>Half-Split XOR</td>
    <td>512</td>
    <td>0.417969</td>
    <td>0.980496</td>
</tr>
</table>

<hr>

<h3>Analysis</h3>
<ul>
    <li>Local XOR folding (Block 8 and Block 2) amplified spatial bias in SRAM.</li>
    <li>Reducing block size did not improve entropy.</li>
    <li>Half-Split XOR significantly improved entropy by mixing distant memory regions.</li>
    <li>Spatial correlation is a dominant factor in SRAM startup behavior.</li>
</ul>

<hr>

<h3>Conclusion</h3>
<p>
The Half-Split XOR method demonstrated superior entropy performance compared to local XOR folding techniques.
This indicates strong spatial bias in SRAM startup patterns, and global mixing strategies are more effective
for entropy enhancement in embedded systems.
</p>

<hr>

<h1> SRAM and Von Neumann Debiasing Experimental Results </h1>


<h2>Experiment5: Von Neumann Debiasing </h2>


<h2>Statistical Results</h2>

<table>
<tr>
    <th>Metric</th>
    <th>Value</th>
</tr>
<tr>
    <td>Total Bits</td>
    <td>244</td>
</tr>
<tr>
    <td>Ones</td>
    <td>96</td>
</tr>
<tr>
    <td>Zeros</td>
    <td>148</td>
</tr>
<tr>
    <td>P(1)</td>
    <td>0.393443</td>
</tr>
<tr>
    <td>P(0)</td>
    <td>0.606557</td>
</tr>
<tr class="highlight">
    <td>Shannon Entropy</td>
    <td>0.966985</td>
</tr>
</table>

<hr>

<h2>Interpretation</h2>
<ul>
    <li>The Von Neumann method reduced the total bit count due to pair filtering.</li>
    <li>Probability imbalance remained similar to raw SRAM output.</li>
    <li>Entropy remained high (~0.967) but did not significantly exceed raw entropy.</li>
    <li>This indicates the presence of structural (spatial) bias in SRAM startup.</li>
</ul>

<hr>

<h2>Conclusion</h2>
<p>
The Von Neumann debiasing technique did not significantly improve entropy compared to raw SRAM output.
This suggests that the observed bias is spatially correlated rather than purely probabilistic.
Global mixing methods such as Half-Split XOR demonstrated superior entropy enhancement.
</p>

<hr>

<h1>SRAM + XOR Folding + Von Neumann Debiasing</h1>

<h2> Experiment 6: SRAM + XOR Folding + Von Neumann Debiasing Experiment </h2>
<p><strong>Platform:</strong> Arduino Uno (ATmega328P)</p>

<hr>

<h2>Statistical Results</h2>

<table>
<tr>
    <th>Metric</th>
    <th>Value</th>
</tr>
<tr>
    <td>Total Bits</td>
    <td>25</td>
</tr>
<tr>
    <td>Ones</td>
    <td>11</td>
</tr>
<tr>
    <td>Zeros</td>
    <td>14</td>
</tr>
<tr>
    <td>P(1)</td>
    <td>0.440000</td>
</tr>
<tr>
    <td>P(0)</td>
    <td>0.560000</td>
</tr>
<tr class="highlight">
    <td>Shannon Entropy</td>
    <td>0.989587</td>
</tr>
</table>

<hr>

<h2>Analysis</h2>
<ul>
<li>Entropy reached 0.989587, close to the theoretical maximum of 1.</li>
<li>Probability distribution moved closer to balance compared to raw SRAM.</li>
<li>Significant bit reduction occurred due to Von Neumann filtering.</li>
<li>Only 25 usable bits were produced from 1024 initial raw bits.</li>
</ul>

<hr>


<h2>Conclusion</h2>
<p>
The combined XOR(8) and Von Neumann conditioning pipeline
achieved near-ideal entropy performance. However, the severe
reduction in bit count limits practical throughput. This method
is suitable for high-security low-rate entropy generation but may
not be efficient for high-speed applications.
</p>


