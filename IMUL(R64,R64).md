<html>
<head>
<title>IMUL (R64, R64)</title>
<link rel="stylesheet" href="https://www.jacklmoore.com/colorbox/example2/colorbox.css"/><script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script><script src="https://cdnjs.cloudflare.com/ajax/libs/jquery.colorbox/1.6.4/jquery.colorbox-min.js"></script><script>$(document).ready(function(){$(".iframe").colorbox({iframe:true, width:"90%", height:"90%", title:function () {return '<a href="' + this.href + '" target="_blank">' + this.href + '</a>'}});});$(document).on("cbox_open",function(){$("body").css({overflow:"hidden"})}).on("cbox_closed",function(){$("body").css({overflow:""})})</script><script src="/m.js"></script>
</head>
<body>
<noscript><p><img src="https://epica.cs.uni-saarland.de/piwik.php?idsite=19&amp;rec=1" style="border:0;" alt="" /></p></noscript>
<h1>IMUL (R64, R64)</h1>
<hr>
<table>
<tr><td>Summary:&nbsp;</td><td>"Signed Multiply"</td></tr>
<tr><td>Reference:&nbsp;</td><td><a class="iframe" href="https://www.felixcloutier.com/x86/IMUL.html">https://www.felixcloutier.com/x86/IMUL.html</a></td></tr>
<tr><td>Extension:&nbsp;</td><td>BASE</td></tr>
<tr><td>Category:&nbsp;</td><td>BINARY</td></tr>
<tr><td>ISA-Set:&nbsp;</td><td>I86</td></tr>
<tr><td>CPL:&nbsp;</td><td>3</td></tr>
<tr><td>iform:&nbsp;</td><td>IMUL_GPRv_GPRv</td></tr>
<tr><td>iclass:&nbsp;</td><td>IMUL</td></tr>
<tr><td>ASM:&nbsp;</td><td>IMUL</td></tr>
</table>
<h2>Operands</h2>
<ul>
<li>Operand 1 (r/w): Register (RAX, RCX, RDX, RBX, RSP, RBP, RSI, RDI, R8, R9, R10, R11, R12, R13, R14, R15)</li>
<li>Operand 2 (r): Register (RAX, RCX, RDX, RBX, RSP, RBP, RSI, RDI, R8, R9, R10, R11, R12, R13, R14, R15)</li>
<li>Operand 3 (w, suppressed): Flags (AF: undef, ZF: undef, OF: w, SF: undef, PF: undef, CF: w)</li>
</ul>
<hr><h2>Available performance data </h2><ul>
<li><a href="#ICL">Ice Lake</a></li>
<li><a href="#CLX">Cascade Lake</a></li>
<li><a href="#CNL">Cannon Lake</a></li>
<li><a href="#SKX">Skylake-X</a></li>
<li><a href="#CFL">Coffee Lake</a></li>
<li><a href="#KBL">Kaby Lake</a></li>
<li><a href="#SKL">Skylake</a></li>
<li><a href="#BDW">Broadwell</a></li>
<li><a href="#HSW">Haswell</a></li>
<li><a href="#IVB">Ivy Bridge</a></li>
<li><a href="#SNB">Sandy Bridge</a></li>
<li><a href="#WSM">Westmere</a></li>
<li><a href="#NHM">Nehalem</a></li>
<li><a href="#WOL">Wolfdale</a></li>
<li><a href="#CON">Conroe</a></li>
<li><a href="#ZEN2">AMD Zen 2</a></li>
<li><a href="#ZEN+">AMD Zen+</a></li>
</ul>
<hr><h2 id="ICL">Ice Lake</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/ICL/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/ICL/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 3</li>
<li>
<a href="../html-lat/ICL/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/ICL/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 3</li>
</ul></li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/ICL/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 1.00</li>
<li><a href="../html-tp/ICL/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 1.00</li>
</ul></li>
<li><a href="../html-tp/ICL/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
<li>Retire slots: 1</li>
<li>Decoded (MITE): 1</li>
<li>Microcode Sequencer (MS): 0</li>
</ul></li>
<li><a href="../html-ports/ICL/IMUL_R64_R64-Measurements.html">Port usage:</a> 1*p1</li>
</ul>
<li><a href="https://software.intel.com/en-us/download/10th-generation-intel-core-processor-instruction-throughput-and-latency-docs" target="_blank">Documentation</a></li>
<ul>
<li>Latency: 3.0</li>
<li>Throughput: 1.0</li>
</ul>
</ul>
<hr><h2 id="CLX">Cascade Lake</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/CLX/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/CLX/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 3</li>
<li>
<a href="../html-lat/CLX/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/CLX/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 3</li>
</ul></li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/CLX/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 1.00</li>
<li><a href="../html-tp/CLX/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 1.00</li>
</ul></li>
<li><a href="../html-tp/CLX/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
<li>Retire slots: 1</li>
<li>Decoded (MITE): 1</li>
<li>Microcode Sequencer (MS): 0</li>
</ul></li>
<li><a href="../html-ports/CLX/IMUL_R64_R64-Measurements.html">Port usage:</a> 1*p1</li>
</ul>
</ul>
<hr><h2 id="CNL">Cannon Lake</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/CNL/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/CNL/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 3</li>
<li>
<a href="../html-lat/CNL/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/CNL/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 3</li>
</ul></li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/CNL/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 1.00</li>
<li><a href="../html-tp/CNL/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 1.00</li>
</ul></li>
<li><a href="../html-tp/CNL/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
<li>Retire slots: 1</li>
<li>Decoded (MITE): 1</li>
<li>Microcode Sequencer (MS): 0</li>
</ul></li>
<li><a href="../html-ports/CNL/IMUL_R64_R64-Measurements.html">Port usage:</a> 1*p1</li>
</ul>
</ul>
<hr><h2 id="SKX">Skylake-X</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/SKX/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/SKX/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 3</li>
<li>
<a href="../html-lat/SKX/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/SKX/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 3</li>
</ul></li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/SKX/IMUL_R64_R64-Measurements.html">Measured:</a> 1.00</li>
</ul></li>
<li><a href="../html-tp/SKX/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
<li>Retire slots: 1</li>
</ul></li>
<li><a href="../html-ports/SKX/IMUL_R64_R64-Measurements.html">Port usage:</a> 1*p1</li>
</ul>
<li>IACA 2.3</li>
<ul>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/SKX/IMUL_R64_R64-IACA2.3.html">IACA:</a> 1.00
</li>
</ul></li>
<li><a href="../html-tp/SKX/IMUL_R64_R64-IACA2.3.html">Number of  &mu;ops:</a> 1</li>
<li><a href="../html-ports/SKX/IMUL_R64_R64-IACA2.3.html">Port usage:</a> 1*p1</li>
</ul>
<li>IACA 3.0</li>
<ul>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/SKX/IMUL_R64_R64-IACA3.0.html">IACA:</a> 0.99
</li>
</ul></li>
<li><a href="../html-tp/SKX/IMUL_R64_R64-IACA3.0.html">Number of  &mu;ops:</a> 1</li>
<li><a href="../html-ports/SKX/IMUL_R64_R64-IACA3.0.html">Port usage:</a> 1*p1</li>
</ul>
</ul>
<hr><h2 id="CFL">Coffee Lake</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/CFL/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/CFL/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 3</li>
<li>
<a href="../html-lat/CFL/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/CFL/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 3</li>
</ul></li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/CFL/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 1.00</li>
<li><a href="../html-tp/CFL/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 1.00</li>
</ul></li>
<li><a href="../html-tp/CFL/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
<li>Retire slots: 1</li>
<li>Decoded (MITE): 1</li>
<li>Microcode Sequencer (MS): 0</li>
</ul></li>
<li><a href="../html-ports/CFL/IMUL_R64_R64-Measurements.html">Port usage:</a> 1*p1</li>
</ul>
</ul>
<hr><h2 id="KBL">Kaby Lake</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/KBL/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/KBL/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 3</li>
<li>
<a href="../html-lat/KBL/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/KBL/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 3</li>
</ul></li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/KBL/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 1.00</li>
<li><a href="../html-tp/KBL/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 1.00</li>
</ul></li>
<li><a href="../html-tp/KBL/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
<li>Retire slots: 1</li>
<li>Decoded (MITE): 1</li>
<li>Microcode Sequencer (MS): 0</li>
</ul></li>
<li><a href="../html-ports/KBL/IMUL_R64_R64-Measurements.html">Port usage:</a> 1*p1</li>
</ul>
</ul>
<hr><h2 id="SKL">Skylake</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/SKL/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/SKL/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 3</li>
<li>
<a href="../html-lat/SKL/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/SKL/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 3</li>
</ul></li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/SKL/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 1.00</li>
<li><a href="../html-tp/SKL/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 1.00</li>
</ul></li>
<li><a href="../html-tp/SKL/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
<li>Retire slots: 1</li>
<li>Decoded (MITE): 1</li>
<li>Microcode Sequencer (MS): 0</li>
</ul></li>
<li><a href="../html-ports/SKL/IMUL_R64_R64-Measurements.html">Port usage:</a> 1*p1</li>
</ul>
<li>IACA 2.3</li>
<ul>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/SKL/IMUL_R64_R64-IACA2.3.html">IACA:</a> 1.00
</li>
</ul></li>
<li><a href="../html-tp/SKL/IMUL_R64_R64-IACA2.3.html">Number of  &mu;ops:</a> 1</li>
<li><a href="../html-ports/SKL/IMUL_R64_R64-IACA2.3.html">Port usage:</a> 1*p1</li>
</ul>
<li>IACA 3.0</li>
<ul>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/SKL/IMUL_R64_R64-IACA3.0.html">IACA:</a> 0.99
</li>
</ul></li>
<li><a href="../html-tp/SKL/IMUL_R64_R64-IACA3.0.html">Number of  &mu;ops:</a> 1</li>
<li><a href="../html-ports/SKL/IMUL_R64_R64-IACA3.0.html">Port usage:</a> 1*p1</li>
</ul>
</ul>
<hr><h2 id="BDW">Broadwell</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/BDW/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/BDW/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 3</li>
<li>
<a href="../html-lat/BDW/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/BDW/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 3</li>
</ul></li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/BDW/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 1.00</li>
<li><a href="../html-tp/BDW/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 1.00</li>
</ul></li>
<li><a href="../html-tp/BDW/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
<li>Retire slots: 1</li>
<li>Decoded (MITE): 1</li>
<li>Microcode Sequencer (MS): 0</li>
</ul></li>
<li><a href="../html-ports/BDW/IMUL_R64_R64-Measurements.html">Port usage:</a> 1*p1</li>
</ul>
<li>IACA 2.2</li>
<ul>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/BDW/IMUL_R64_R64-IACA2.2.html">IACA:</a> 1.00
 (with the -no_interiteration flag: 1.00)
</li>
</ul></li>
<li><a href="../html-tp/BDW/IMUL_R64_R64-IACA2.2.html">Number of  &mu;ops:</a> 1</li>
<li><a href="../html-ports/BDW/IMUL_R64_R64-IACA2.2.html">Port usage:</a> 1*p1</li>
</ul>
<li>IACA 2.3</li>
<ul>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/BDW/IMUL_R64_R64-IACA2.3.html">IACA:</a> 1.00
</li>
</ul></li>
<li><a href="../html-tp/BDW/IMUL_R64_R64-IACA2.3.html">Number of  &mu;ops:</a> 1</li>
<li><a href="../html-ports/BDW/IMUL_R64_R64-IACA2.3.html">Port usage:</a> 1*p1</li>
</ul>
<li>IACA 3.0</li>
<ul>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/BDW/IMUL_R64_R64-IACA3.0.html">IACA:</a> 0.99
</li>
</ul></li>
<li><a href="../html-tp/BDW/IMUL_R64_R64-IACA3.0.html">Number of  &mu;ops:</a> 1</li>
<li><a href="../html-ports/BDW/IMUL_R64_R64-IACA3.0.html">Port usage:</a> 1*p1</li>
</ul>
</ul>
<hr><h2 id="HSW">Haswell</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/HSW/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/HSW/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 3</li>
<li>
<a href="../html-lat/HSW/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/HSW/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 3</li>
</ul></li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/HSW/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 1.00</li>
<li><a href="../html-tp/HSW/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 1.00</li>
</ul></li>
<li><a href="../html-tp/HSW/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
<li>Retire slots: 1</li>
<li>Decoded (MITE): 1</li>
<li>Microcode Sequencer (MS): 0</li>
</ul></li>
<li><a href="../html-ports/HSW/IMUL_R64_R64-Measurements.html">Port usage:</a> 1*p1</li>
</ul>
<li>IACA 2.2</li>
<ul>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/HSW/IMUL_R64_R64-IACA2.2.html">IACA:</a> 1.00
 (with the -no_interiteration flag: 1.00)
</li>
</ul></li>
<li><a href="../html-tp/HSW/IMUL_R64_R64-IACA2.2.html">Number of  &mu;ops:</a> 1</li>
<li><a href="../html-ports/HSW/IMUL_R64_R64-IACA2.2.html">Port usage:</a> 1*p1</li>
</ul>
<li>IACA 2.3</li>
<ul>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/HSW/IMUL_R64_R64-IACA2.3.html">IACA:</a> 1.00
</li>
</ul></li>
<li><a href="../html-tp/HSW/IMUL_R64_R64-IACA2.3.html">Number of  &mu;ops:</a> 1</li>
<li><a href="../html-ports/HSW/IMUL_R64_R64-IACA2.3.html">Port usage:</a> 1*p1</li>
</ul>
<li>IACA 3.0</li>
<ul>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/HSW/IMUL_R64_R64-IACA3.0.html">IACA:</a> 0.99
</li>
</ul></li>
<li><a href="../html-tp/HSW/IMUL_R64_R64-IACA3.0.html">Number of  &mu;ops:</a> 1</li>
<li><a href="../html-ports/HSW/IMUL_R64_R64-IACA3.0.html">Port usage:</a> 1*p1</li>
</ul>
</ul>
<hr><h2 id="IVB">Ivy Bridge</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/IVB/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/IVB/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 3</li>
<li>
<a href="../html-lat/IVB/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/IVB/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 3</li>
</ul></li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/IVB/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 1.00</li>
<li><a href="../html-tp/IVB/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 1.00</li>
</ul></li>
<li><a href="../html-tp/IVB/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
<li>Retire slots: 1</li>
<li>Decoded (MITE): 1</li>
<li>Microcode Sequencer (MS): 0</li>
</ul></li>
<li><a href="../html-ports/IVB/IMUL_R64_R64-Measurements.html">Port usage:</a> 1*p1</li>
</ul>
</ul>
<hr><h2 id="SNB">Sandy Bridge</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/SNB/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/SNB/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 3</li>
<li>
<a href="../html-lat/SNB/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/SNB/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 3</li>
</ul></li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/SNB/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 1.00</li>
<li><a href="../html-tp/SNB/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 1.00</li>
</ul></li>
<li><a href="../html-tp/SNB/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
<li>Retire slots: 1</li>
<li>Decoded (MITE): 1</li>
<li>Microcode Sequencer (MS): 0</li>
</ul></li>
<li><a href="../html-ports/SNB/IMUL_R64_R64-Measurements.html">Port usage:</a> 1*p1</li>
</ul>
</ul>
<hr><h2 id="WSM">Westmere</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/WSM/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/WSM/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 3</li>
<li>
<a href="../html-lat/WSM/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/WSM/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 3</li>
</ul></li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/WSM/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 1.00</li>
<li><a href="../html-tp/WSM/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 1.00</li>
</ul></li>
<li><a href="../html-tp/WSM/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
<li>Retire slots: 1</li>
<li>Microcode Sequencer (MS): 0</li>
</ul></li>
<li><a href="../html-ports/WSM/IMUL_R64_R64-Measurements.html">Port usage:</a> 1*p1</li>
</ul>
<li>IACA 2.1</li>
<ul>
<li><a href="../html-lat/WSM/IMUL_R64_R64-IACA2.1.html">Latency:</a> 3</li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/WSM/IMUL_R64_R64-IACA2.1.html">IACA:</a> 1.33
 (with the -no_interiteration flag: 1.00)
</li>
</ul></li>
<li><a href="../html-tp/WSM/IMUL_R64_R64-IACA2.1.html">Number of  &mu;ops:</a> 1</li>
<li><a href="../html-ports/WSM/IMUL_R64_R64-IACA2.1.html">Port usage:</a> 1*p1</li>
</ul>
<li>IACA 2.2</li>
<ul>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/WSM/IMUL_R64_R64-IACA2.2.html">IACA:</a> 1.33
 (with the -no_interiteration flag: 1.00)
</li>
</ul></li>
<li><a href="../html-tp/WSM/IMUL_R64_R64-IACA2.2.html">Number of  &mu;ops:</a> 1</li>
<li><a href="../html-ports/WSM/IMUL_R64_R64-IACA2.2.html">Port usage:</a> 1*p1</li>
</ul>
</ul>
<hr><h2 id="NHM">Nehalem</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/NHM/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/NHM/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 3</li>
<li>
<a href="../html-lat/NHM/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/NHM/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 3</li>
</ul></li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/NHM/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 1.00</li>
<li><a href="../html-tp/NHM/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 1.00</li>
</ul></li>
<li><a href="../html-tp/NHM/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
<li>Retire slots: 1</li>
<li>Microcode Sequencer (MS): 0</li>
</ul></li>
<li><a href="../html-ports/NHM/IMUL_R64_R64-Measurements.html">Port usage:</a> 1*p1</li>
</ul>
<li>IACA 2.1</li>
<ul>
<li><a href="../html-lat/NHM/IMUL_R64_R64-IACA2.1.html">Latency:</a> 3</li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/NHM/IMUL_R64_R64-IACA2.1.html">IACA:</a> 1.33
 (with the -no_interiteration flag: 1.00)
</li>
</ul></li>
<li><a href="../html-tp/NHM/IMUL_R64_R64-IACA2.1.html">Number of  &mu;ops:</a> 1</li>
<li><a href="../html-ports/NHM/IMUL_R64_R64-IACA2.1.html">Port usage:</a> 1*p1</li>
</ul>
<li>IACA 2.2</li>
<ul>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/NHM/IMUL_R64_R64-IACA2.2.html">IACA:</a> 1.33
 (with the -no_interiteration flag: 1.00)
</li>
</ul></li>
<li><a href="../html-tp/NHM/IMUL_R64_R64-IACA2.2.html">Number of  &mu;ops:</a> 1</li>
<li><a href="../html-ports/NHM/IMUL_R64_R64-IACA2.2.html">Port usage:</a> 1*p1</li>
</ul>
</ul>
<hr><h2 id="WOL">Wolfdale</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/WOL/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 5</li>
<li>
<a href="../html-lat/WOL/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 7</li>
<li>
<a href="../html-lat/WOL/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 7</li>
<li>
<a href="../html-lat/WOL/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 7</li>
</ul></li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/WOL/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 2.00</li>
<li><a href="../html-tp/WOL/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 2.00</li>
</ul></li>
<li><a href="../html-tp/WOL/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
</ul></li>
<li><a href="../html-ports/WOL/IMUL_R64_R64-Measurements.html">Port usage:</a> 1*p0</li>
</ul>
</ul>
<hr><h2 id="CON">Conroe</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/CON/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 5</li>
<li>
<a href="../html-lat/CON/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 7</li>
<li>
<a href="../html-lat/CON/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 7</li>
<li>
<a href="../html-lat/CON/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 7</li>
</ul></li>
<li>Throughput<ul>
<li>Computed from the port usage: 1.00</li>
<li><a href="../html-tp/CON/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 2.00</li>
<li><a href="../html-tp/CON/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 2.00</li>
</ul></li>
<li><a href="../html-tp/CON/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
</ul></li>
<li><a href="../html-ports/CON/IMUL_R64_R64-Measurements.html">Port usage:</a> 1*p0</li>
</ul>
</ul>
<hr><h2 id="ZEN2">AMD Zen 2</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/ZEN2/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/ZEN2/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 3</li>
<li>
<a href="../html-lat/ZEN2/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/ZEN2/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 3</li>
</ul></li>
<li>Throughput<ul>
<li><a href="../html-tp/ZEN2/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 1.00</li>
<li><a href="../html-tp/ZEN2/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 1.00</li>
</ul></li>
<li><a href="../html-tp/ZEN2/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
</ul></li>
</ul>
<li><a href="https://developer.amd.com/wp-content/resources/56305.zip" target="_blank">Documentation</a></li>
<ul>
<li>Latency: 3,4</li>
<li>Throughput: 1.00</li>
<li>Number of  &mu;ops: 1-2</li>
<li>Port usage: ALU1</li>
</ul>
</ul>
<hr><h2 id="ZEN+">AMD Zen+</h2>
<ul>
<li>Measurements</li>
<ul>
<li>Latencies<ul>
<li>
<a href="../html-lat/ZEN+/IMUL_R64_R64-Measurements.html#lat1->1">Latency operand 1 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/ZEN+/IMUL_R64_R64-Measurements.html#lat1->3">Latency operand 1 &rarr; 3:</a>
 3</li>
<li>
<a href="../html-lat/ZEN+/IMUL_R64_R64-Measurements.html#lat2->1">Latency operand 2 &rarr; 1:</a>
 3</li>
<li>
<a href="../html-lat/ZEN+/IMUL_R64_R64-Measurements.html#lat2->3">Latency operand 2 &rarr; 3:</a>
 3</li>
</ul></li>
<li>Throughput<ul>
<li><a href="../html-tp/ZEN+/IMUL_R64_R64-Measurements.html">Measured (loop):</a> 1.00</li>
<li><a href="../html-tp/ZEN+/IMUL_R64_R64-Measurements.html">Measured (unrolled):</a> 1.00</li>
</ul></li>
<li><a href="../html-tp/ZEN+/IMUL_R64_R64-Measurements.html">Number of &mu;ops</a><ul>
<li>Executed: 1</li>
</ul></li>
</ul>
<li><a href="https://developer.amd.com/wordpress/media/2013/12/55723_3_00.ZIP" target="_blank">Documentation</a></li>
<ul>
<li>Latency: 3,4</li>
<li>Throughput: 1.00</li>
<li>Number of  &mu;ops: 1-2</li>
<li>Port usage: MUL</li>
</ul>
</ul></body>
</html>
