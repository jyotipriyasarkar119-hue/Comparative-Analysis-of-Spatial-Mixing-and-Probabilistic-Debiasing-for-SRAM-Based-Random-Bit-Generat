
<h1>SRAM Startup Randomness Analysis</h1>

<h2>1. SRAM Random Bit Generation </h2>
<hr>

<h2>Statistical Analysis</h2>

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

<h2>Interpretation</h2>
<ul>
    <li>The bit distribution shows a bias toward 0.</li>
    <li>Entropy is close to 1, indicating strong randomness.</li>
    <li>SRAM startup behavior demonstrates high statistical unpredictability despite bias.</li>
</ul>

<hr>

<h2>Observations</h2>

<ul>
    <li>Output remains consistent across boots (indicating stable SRAM regions).</li>
    <li>Some spatial bias is visible in memory.</li>
    <li>Suitable for entropy-based applications with statistical post-processing.</li>
</ul>

<hr>


