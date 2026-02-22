<h1>SRAM Startup Randomness Experimental Study</h1>
<p><strong>Platform:</strong> Arduino Uno (ATmega328P)</p>

<hr>

<h2>Objective</h2>
<p>
To evaluate SRAM startup randomness and analyze the effectiveness of 
different entropy conditioning techniques including XOR folding and 
Von Neumann debiasing.
</p>

<hr>

<h2>Experimental Results Summary</h2>

<table>
<tr>
<th>Method</th>
<th>Total Bits</th>
<th>P(1)</th>
<th>Entropy</th>
<th>Observation</th>
</tr>

<tr>
<td>Raw SRAM</td>
<td>1024</td>
<td>0.397</td>
<td>0.969</td>
<td>High entropy, noticeable zero bias</td>
</tr>

<tr>
<td>XOR (Block=8)</td>
<td>128</td>
<td>0.328</td>
<td>0.913</td>
<td>Bias amplified, entropy reduced</td>
</tr>

<tr>
<td>XOR (Block=2)</td>
<td>512</td>
<td>0.295</td>
<td>0.875</td>
<td>Stronger bias, lower entropy</td>
</tr>

<tr>
<td>Half-Split XOR</td>
<td>512</td>
<td>0.418</td>
<td>0.980</td>
<td>Spatial bias reduced, strong entropy</td>
</tr>

<tr>
<td>Von Neumann Only</td>
<td>244</td>
<td>0.393</td>
<td>0.967</td>
<td>Probability bias reduced slightly</td>
</tr>

<tr>
<td>XOR(8) + Von Neumann</td>
<td>25</td>
<td>0.440</td>
<td>0.989</td>
<td>Highest entropy, extremely low bit rate</td>
</tr>

<tr>
<td>XOR(2) + Von Neumann</td>
<td>69</td>
<td>0.406</td>
<td>0.974</td>
<td>Improved entropy, moderate bit rate</td>
</tr>

<tr class="best">
<td>Half-Split XOR + Von Neumann</td>
<td>112</td>
<td>0.384</td>
<td>0.961</td>
<td>Over-conditioning reduced entropy</td>
</tr>

</table>

<hr>

<h2>Graphs</h2>


<hr>


<h2>Key Findings</h2>
<ul>
<li>SRAM startup exhibits strong spatial correlation and zero bias.</li>
<li>Local XOR folding (Block=2 and Block=8) amplifies structural bias.</li>
<li>Half-Split XOR significantly improves entropy by mixing distant memory regions.</li>
<li>Von Neumann correction improves probability balance but does not remove spatial bias.</li>
<li>Aggressive conditioning increases entropy but drastically reduces usable bit rate.</li>
<li>Over-conditioning can reduce statistical reliability due to small sample size.</li>
</ul>

<hr>

<h2>Entropy vs Bit-Rate Tradeoff</h2>
<p>
The experiment demonstrates a clear tradeoff between entropy quality 
and throughput. While XOR(8) + Von Neumann achieved near-ideal entropy,
it produced very few usable bits. Half-Split XOR provided the best 
balance between entropy improvement and usable bit rate.
</p>

<hr>

<h2>Conclusion</h2>
<p>
This study demonstrates that SRAM startup randomness on the ATmega328P
is dominated by spatial correlation rather than pure probabilistic bias.
Global mixing techniques such as Half-Split XOR are more effective than 
local folding methods. Entropy conditioning must balance randomness 
quality and throughput for practical embedded applications.
</p>

