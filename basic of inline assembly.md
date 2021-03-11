<meta name="ResourceLoaderDynamicStyles" content=""/>
<link rel="stylesheet" href="/w/load.php?lang=ko&amp;modules=site.styles&amp;only=styles&amp;skin=vector"/>
<meta name="generator" content="MediaWiki 1.36.0-wmf.34"/>
<meta name="referrer" content="origin"/>
<meta name="referrer" content="origin-when-crossorigin"/>
<meta name="referrer" content="origin-when-cross-origin"/>
<meta property="og:title" content="x86 어셈블리/x86 아키텍처"/>
<meta property="og:type" content="website"/>
<link rel="alternate" media="only screen and (max-width: 720px)" href="//ko.m.wikibooks.org/wiki/X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98"/>
<link rel="alternate" type="application/x-wiki" title="편집" href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit"/>
<link rel="edit" title="편집" href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit"/>
<link rel="shortcut icon" href="/static/favicon/wikibooks.ico"/>
<link rel="search" type="application/opensearchdescription+xml" href="/w/opensearch_desc.php" title="위키책 (ko)"/>
<link rel="EditURI" type="application/rsd+xml" href="//ko.wikibooks.org/w/api.php?action=rsd"/>
<link rel="license" href="//creativecommons.org/licenses/by-sa/3.0/"/>
<link rel="canonical" href="https://ko.wikibooks.org/wiki/X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98"/>
<link rel="dns-prefetch" href="//login.wikimedia.org"/>
<link rel="dns-prefetch" href="//meta.wikimedia.org" />
</head>
<body class="mediawiki ltr sitedir-ltr mw-hide-empty-elt ns-0 ns-subject mw-editable page-X86_어셈블리_x86_아키텍처 rootpage-X86_어셈블리 skin-vector action-view skin-vector-legacy"><div id="mw-page-base" class="noprint"></div>
<div id="mw-head-base" class="noprint"></div>
<div id="content" class="mw-body" role="main">
	<a id="top"></a>
	<div id="siteNotice" class="mw-body-content"><!-- CentralNotice --></div>
	<div class="mw-indicators mw-body-content">
	</div>
	<h1 id="firstHeading" class="firstHeading" >x86 어셈블리/x86 아키텍처</h1>
	<div id="bodyContent" class="mw-body-content">
		<div id="siteSub" class="noprint">위키책, 위키책</div>
		<div id="contentSub"><span class="subpages">&lt; <a href="/wiki/X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC" title="X86 어셈블리">X86 어셈블리</a></span></div>
		<div id="contentSub2"></div>
		
		<div id="jump-to-nav"></div>
		<a class="mw-jump-link" href="#mw-head">둘러보기로 가기</a>
		<a class="mw-jump-link" href="#searchInput">검색하러 가기</a>
		<div id="mw-content-text" lang="ko" dir="ltr" class="mw-content-ltr"><div class="mw-parser-output"><center><div class="PrettyTextBox noprint" style="width: 90%; float: center; clear: all; padding: 5px; margin: 5px; background-color: #F9F9F9; color: #000000; border: 1px solid #AAAAAA;"><big><b><a href="/wiki/X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC" title="X86 어셈블리">x86 어셈블리</a></b></big>
</div></center>
<div id="toc" class="toc" role="navigation" aria-labelledby="mw-toc-heading"><input type="checkbox" role="button" id="toctogglecheckbox" class="toctogglecheckbox" style="display:none" /><div class="toctitle" lang="ko" dir="ltr"><h2 id="mw-toc-heading">차례</h2><span class="toctogglespan"><label class="toctogglelabel" for="toctogglecheckbox"></label></span></div>
<ul>
<li class="toclevel-1 tocsection-1"><a href="#x86_아키텍쳐"><span class="tocnumber">1</span> <span class="toctext">x86 아키텍쳐</span></a>
<ul>
<li class="toclevel-2 tocsection-2"><a href="#범용_레지스터_(GPR)_-_32비트_지정이름"><span class="tocnumber">1.1</span> <span class="toctext">범용 레지스터 (GPR) - 32비트 지정이름</span></a></li>
<li class="toclevel-2 tocsection-3"><a href="#세그먼트_레지스터"><span class="tocnumber">1.2</span> <span class="toctext">세그먼트 레지스터</span></a></li>
<li class="toclevel-2 tocsection-4"><a href="#EFLAGS_레지스터"><span class="tocnumber">1.3</span> <span class="toctext">EFLAGS 레지스터</span></a></li>
<li class="toclevel-2 tocsection-5"><a href="#명령어_포인터"><span class="tocnumber">1.4</span> <span class="toctext">명령어 포인터</span></a></li>
<li class="toclevel-2 tocsection-6"><a href="#Memory"><span class="tocnumber">1.5</span> <span class="toctext">Memory</span></a></li>
<li class="toclevel-2 tocsection-7"><a href="#Two&#39;s_Complement_Representation"><span class="tocnumber">1.6</span> <span class="toctext">Two's Complement Representation</span></a></li>
<li class="toclevel-2 tocsection-8"><a href="#Addressing_modes"><span class="tocnumber">1.7</span> <span class="toctext">Addressing modes</span></a></li>
<li class="toclevel-2 tocsection-9"><a href="#General-purpose_registers_(64-bit_naming_conventions)"><span class="tocnumber">1.8</span> <span class="toctext">General-purpose registers (64-bit naming conventions)</span></a></li>
</ul>
</li>
<li class="toclevel-1 tocsection-10"><a href="#Stack"><span class="tocnumber">2</span> <span class="toctext">Stack</span></a></li>
<li class="toclevel-1 tocsection-11"><a href="#CPU_Operation_Modes"><span class="tocnumber">3</span> <span class="toctext">CPU Operation Modes</span></a>
<ul>
<li class="toclevel-2 tocsection-12"><a href="#Real_Mode"><span class="tocnumber">3.1</span> <span class="toctext">Real Mode</span></a></li>
<li class="toclevel-2 tocsection-13"><a href="#Protected_Mode"><span class="tocnumber">3.2</span> <span class="toctext">Protected Mode</span></a>
<ul>
<li class="toclevel-3 tocsection-14"><a href="#Flat_Memory_Model"><span class="tocnumber">3.2.1</span> <span class="toctext">Flat Memory Model</span></a></li>
<li class="toclevel-3 tocsection-15"><a href="#Multi-Segmented_Memory_Model"><span class="tocnumber">3.2.2</span> <span class="toctext">Multi-Segmented Memory Model</span></a></li>
</ul>
</li>
</ul>
</li>
</ul>
</div>

<h2><span id="x86_.EC.95.84.ED.82.A4.ED.85.8D.EC.B3.90"></span><span class="mw-headline" id="x86_아키텍쳐">x86 아키텍쳐</span><span class="mw-editsection"><span class="mw-editsection-bracket">[</span><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;section=1" title="부분 편집: x86 아키텍쳐">+/-</a><span class="mw-editsection-bracket">]</span></span></h2>
<p>x86 아키텍쳐는 8개의 범용 레지스터(GPR; General-Purpose Register), 6개의 세그먼트 레지스터, 1개의 플래그 레지스터, 마지막으로 명령어 포인터를 갖는다. 64비트 x86에는 더 많은 레지스터가 있다.
</p>
<h3><span id=".EB.B2.94.EC.9A.A9_.EB.A0.88.EC.A7.80.EC.8A.A4.ED.84.B0_.28GPR.29_-_32.EB.B9.84.ED.8A.B8_.EC.A7.80.EC.A0.95.EC.9D.B4.EB.A6.84"></span><span class="mw-headline" id="범용_레지스터_(GPR)_-_32비트_지정이름">범용 레지스터 (GPR) - 32비트 지정이름</span><span class="mw-editsection"><span class="mw-editsection-bracket">[</span><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;section=2" title="부분 편집: 범용 레지스터 (GPR) - 32비트 지정이름">+/-</a><span class="mw-editsection-bracket">]</span></span></h3>
<p>8개의 범용 레지스터는 다음과 같다:
</p>
<ol><li>AX (Accumulator register). 산술 연산에 사용.</li>
<li>CX (Counter register). 시프트/회전 연산과 루프에서 사용.</li>
<li>DX (Data register). 산술 연산과 I/O 명령에서 사용.</li>
<li>BX (Base register). 데이터의 주소를 가리키는 포인터로 사용. (세그멘티드 모드에서는 세그멘트 레지스터 DS로 존재)</li>
<li>SP (Stack Pointer register). 스택의 최상단을 가리키는 포인터로 사용.</li>
<li>BP (Stack Base Pointer register). 스택의 베이스를 가리키는 포인터로 사용.</li>
<li>SI (Source Index register). 스트림 명령에서 소스를 가리키는 포인터로 사용.</li>
<li>DI (Destination Index register). 스트림 명령에서 도착점을 가리키는 포인터로 사용.</li></ol>
<p>위의 나열 순서는 다음에 더욱 자세히 다루게 될 스택 삽입 명령에서 사용되는 순서이다.
</p><p>모든 레지스터는 16비트와 32비트 모드에서 모두 접근 가능하다. 16비트 모드에서 레지스터는 위의 리스트에 있는 두 글자의 약자로 통칭된다. 32비트 모드에서는 16비트의 두 자 앞에 'E'(<i>extended</i>)를 붙여 표시한다. 예를 들어, 'EAX'는 32비트 값을 갖는 어큐뮬레이터 레지스터이다.
</p><p>비슷하게, 64비트 버전에서는 'E' 대신 'R'을 사용한다. 즉, 'EAX'의 64비트 버전은 'RAX'가 된다.
</p><p>처음 네 개의 16비트 레지스터 (AX, CX, DX, BX)는 두 개의 8비트 레지스터로 각각 접근할 수 있다. LSB, 또는 낮은 반은 'X' 대신 'L'을 써서 접근할 수 있으며, MSB, 또는 높은 반은 'H'를 써서 접근할 수 있다. 예를 들어, CL은 카운터 레지스터의 LSB이다.
</p><p>전체적으로 우리는 어큐뮬레이터, 카운터, 데이터, 베이스 레지스터에 5가지 방법으로 접근할 수 있다. (64비트, 32비트, 16비트, 8비트 LSB, 8비트 MSB) 나머지 네 레지스터는 3가지 방법으로 접근 가능하다. (64비트, 32비트, 16비트) 요약하면 다음과 같다: 
</p>
<table class="wikitable">

<tbody><tr>
<th>Register
</th>
<th style="width: 10%;" colspan="8">Accumulator
</th>
<th style="width: 10%;" colspan="8">Counter
</th>
<th style="width: 10%;" colspan="8">Data
</th>
<th style="width: 10%;" colspan="8">Base
</th>
<th style="width: 10%;" colspan="8">Stack Pointer
</th>
<th style="width: 10%;" colspan="8">Stack Base Pointer
</th>
<th style="width: 10%;" colspan="8">Source
</th>
<th style="width: 10%;" colspan="8">Destination
</th></tr>
<tr style="text-align: center;">
<th scope="row">64-bit
</th>
<td style="width: 10%;" colspan="8">RAX
</td>
<td style="width: 10%;" colspan="8">RCX
</td>
<td style="width: 10%;" colspan="8">RDX
</td>
<td style="width: 10%;" colspan="8">RBX
</td>
<td style="width: 10%;" colspan="8">RSP
</td>
<td style="width: 10%;" colspan="8">RBP
</td>
<td style="width: 10%;" colspan="8">RSI
</td>
<td style="width: 10%;" colspan="8">RDI
</td></tr>
<tr style="text-align: center;">
<th scope="row">32-bit
</th>
<td style="width: 5%;" colspan="4">
</td>
<td style="width: 5%;" colspan="4">EAX
</td>
<td style="width: 5%;" colspan="4">
</td>
<td style="width: 5%;" colspan="4">ECX
</td>
<td style="width: 5%;" colspan="4">
</td>
<td style="width: 5%;" colspan="4">EDX
</td>
<td style="width: 5%;" colspan="4">
</td>
<td style="width: 5%;" colspan="4">EBX
</td>
<td style="width: 5%;" colspan="4">
</td>
<td style="width: 5%;" colspan="4">ESP
</td>
<td style="width: 5%;" colspan="4">
</td>
<td style="width: 5%;" colspan="4">EBP
</td>
<td style="width: 5%;" colspan="4">
</td>
<td style="width: 5%;" colspan="4">ESI
</td>
<td style="width: 5%;" colspan="4">
</td>
<td style="width: 5%;" colspan="4">EDI
</td></tr>
<tr style="text-align: center;">
<th scope="row">16-bit
</th>
<td colspan="6">
</td>
<td colspan="2">AX
</td>
<td colspan="6">
</td>
<td colspan="2">CX
</td>
<td colspan="6">
</td>
<td colspan="2">DX
</td>
<td colspan="6">
</td>
<td colspan="2">BX
</td>
<td colspan="6">
</td>
<td colspan="2">SP
</td>
<td colspan="6">
</td>
<td colspan="2">BP
</td>
<td colspan="6">
</td>
<td colspan="2">SI
</td>
<td colspan="6">
</td>
<td colspan="2">DI
</td></tr>
<tr style="text-align: center;">
<th scope="row">8-bit
</th>
<td colspan="6">
</td>
<td>AH
</td>
<td>AL
</td>
<td colspan="6">
</td>
<td>CH
</td>
<td>CL
</td>
<td colspan="6">
</td>
<td>DH
</td>
<td>DL
</td>
<td colspan="6">
</td>
<td>BH
</td>
<td>BL
</td>
<td style="width: 10%;" colspan="8">
</td>
<td style="width: 10%;" colspan="8">
</td>
<td style="width: 10%;" colspan="8">
</td>
<td style="width: 10%;" colspan="8">
</td></tr></tbody></table>
<h3><span id=".EC.84.B8.EA.B7.B8.EB.A8.BC.ED.8A.B8_.EB.A0.88.EC.A7.80.EC.8A.A4.ED.84.B0"></span><span class="mw-headline" id="세그먼트_레지스터">세그먼트 레지스터</span><span class="mw-editsection"><span class="mw-editsection-bracket">[</span><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;section=3" title="부분 편집: 세그먼트 레지스터">+/-</a><span class="mw-editsection-bracket">]</span></span></h3>
<p>6개의 세그먼트 레지스터들은 다음과 같다:
</p>
<ul><li>Stack Segment (SS). 스택을 가리킨다.</li>
<li>Code Segment (CS). 코드를 가리킨다.</li>
<li>Data Segment (DS). 데이터를 가리킨다.</li>
<li>Extra Segment (ES). 추가적인 데이터를 가리킨다 ('Extra'의 첫 글자 'E').</li>
<li>F Segment (FS). 많은 추가적인 데이터를 가리킨다 ('E' 다음은 'F').</li>
<li>G Segment (GS). 더 많은 추가적인 데이터를 가리킨다 ('F' 다음은 'G').</li></ul>
<p>많은 최신 운영체제에서 대부분의 애플리케이션들은 (FreeBSD, Linux 또는 Microsoft Windows와 같이) 거의 모든 세그먼트 레지스터가 동일한 위치를 가리키는 메모리 모델을 사용하는 대신, 페이징을 사용하여 세그먼트 레지스터의 사용을 비활성화 한다. 하지만 일반적으로 FS와 GS는 이 규칙에서 예외이며, 대신 스레드 특정 데이터를 가리키는데 사용된다.
</p>
<h3><span id="EFLAGS_.EB.A0.88.EC.A7.80.EC.8A.A4.ED.84.B0"></span><span class="mw-headline" id="EFLAGS_레지스터">EFLAGS 레지스터</span><span class="mw-editsection"><span class="mw-editsection-bracket">[</span><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;section=4" title="부분 편집: EFLAGS 레지스터">+/-</a><span class="mw-editsection-bracket">]</span></span></h3>
<p>EFLAGS 는 프로세서의 작동 결과와 상태를 저장하기 위해 부울 값들의 모음으로 사용되는 32비트 레지스터이다.
</p><p>비트들의 이름은 다음과 같다:
</p>
<table width="100%" style="text-align: center;">
<tbody><tr>
<td>31</td>
<td>30</td>
<td>29</td>
<td>28</td>
<td>27</td>
<td>26</td>
<td>25</td>
<td>24</td>
<td>23</td>
<td>22</td>
<td>21</td>
<td>20</td>
<td>19</td>
<td>18</td>
<td>17</td>
<td>16
</td></tr>
<tr style="background-color: blue; color: white;">
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>ID</td>
<td>VIP</td>
<td>VIF</td>
<td>AC</td>
<td>VM</td>
<td>RF
</td></tr>
<tr>
<th colspan="16" height="5">
</th></tr>
<tr>
<th colspan="16" style="background-color: black;">
</th></tr>
<tr>
<td>15</td>
<td>14</td>
<td>13</td>
<td>12</td>
<td>11</td>
<td>10</td>
<td>9</td>
<td>8</td>
<td>7</td>
<td>6</td>
<td>5</td>
<td>4</td>
<td>3</td>
<td>2</td>
<td>1</td>
<td>0
</td></tr>
<tr style="background-color: #777777; color: white;">
<td>0</td>
<td>NT
</td>
<th colspan="2">IOPL
</th>
<td>OF</td>
<td>DF</td>
<td>IF</td>
<td>TF</td>
<td>SF</td>
<td>ZF</td>
<td>0</td>
<td>AF</td>
<td>0</td>
<td>PF</td>
<td>1</td>
<td>CF
</td></tr></tbody></table>
<p>비트의 이름이 0 과 1 인 것은 예약된 비트들로써 수정될 수 없다.
</p>
<table>
<tbody><tr>
<th style="text-align: left;" colspan="2">The different use of these flags are:
</th></tr>
<tr>
<td style="text-align: right; vertical-align: top">0.</td>
<td>CF&#160;: Carry Flag. Set if the last arithmetic operation carried (addition) or borrowed (subtraction) a bit beyond the size of the register.  This is then checked when the operation is followed with an add-with-carry or subtract-with-borrow to deal with values too large for just one register to contain.
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">2.</td>
<td>PF&#160;: Parity Flag. Set if the number of set bits in the least significant byte is a multiple of 2.
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">4.</td>
<td>AF&#160;: Adjust Flag. Carry of Binary Code Decimal (BCD) numbers arithmetic operations.
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">6.</td>
<td>ZF&#160;: Zero Flag. Set if the result of an operation is Zero (0).
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">7.</td>
<td>SF&#160;: Sign Flag. Set if the result of an operation is negative.
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">8.</td>
<td>TF&#160;: Trap Flag. Set if step by step debugging.
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">9.</td>
<td>IF&#160;: Interruption Flag. Set if interrupts are enabled.
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">10.</td>
<td>DF&#160;: Direction Flag. Stream direction. If set, string operations will decrement their pointer rather than incrementing it, reading memory backwards.
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">11.</td>
<td>OF&#160;: Overflow Flag. Set if signed arithmetic operations result in a value too large for the register to contain.
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">12-13.</td>
<td>IOPL&#160;: I/O Privilege Level field (2 bits). I/O Privilege Level of the current process.
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">14.</td>
<td>NT&#160;: Nested Task flag. Controls chaining of interrupts. Set if the current process is linked to the next process.
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">16.</td>
<td>RF&#160;: Resume Flag. Response to debug exceptions.
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">17.</td>
<td>VM&#160;: Virtual-8086 Mode. Set if in 8086 compatibility mode.
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">18.</td>
<td>AC&#160;: Alignment Check. Set if alignment checking of memory references is done.
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">19.</td>
<td>VIF&#160;: Virtual Interrupt Flag. Virtual image of IF.
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">20.</td>
<td>VIP&#160;: Virtual Interrupt Pending flag. Set if an interrupt is pending.
</td></tr>
<tr>
<td style="text-align: right; vertical-align: top">21.</td>
<td>ID&#160;: Identification Flag. Support for CPUID instruction if can be set.
</td></tr></tbody></table>
<h3><span id=".EB.AA.85.EB.A0.B9.EC.96.B4_.ED.8F.AC.EC.9D.B8.ED.84.B0"></span><span class="mw-headline" id="명령어_포인터">명령어 포인터</span><span class="mw-editsection"><span class="mw-editsection-bracket">[</span><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;section=5" title="부분 편집: 명령어 포인터">+/-</a><span class="mw-editsection-bracket">]</span></span></h3>
<p>분기가 수행되지 않은 경우, EIP 레지스터는 <b>다음</b> 에 실행되어야 할 명령어의 주소를 가지고 있다.
</p><p>EIP는 오직 <code>call</code> 명령어를 사용해 스택을 통해서만 읽을 수 있다.
</p>
<h3><span class="mw-headline" id="Memory">Memory</span><span class="mw-editsection"><span class="mw-editsection-bracket">[</span><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;section=6" title="부분 편집: Memory">+/-</a><span class="mw-editsection-bracket">]</span></span></h3>
<p>The x86 architecture is <a href="https://en.wikipedia.org/wiki/Little_endian" class="extiw" title="wikipedia:Little endian">little-endian</a>, meaning that multi-byte values are written least significant byte first. (This refers only to the ordering of the bytes, not to the bits.)
</p><p>So the 32 bit value B3B2B1B0<sub>16</sub> on an x86 would be represented in memory as:
</p>
<table border="1">
<caption><b>Little endian representation</b>
</caption>
<tbody><tr>
<td><code>B0</code>
</td>
<td><code>B1</code>
</td>
<td><code>B2</code>
</td>
<td><code>B3</code>
</td></tr></tbody></table>
<p>For example, the 32 bits double word 0x1BA583D4 (the <b>0x</b> denotes hexadecimal) would be written in memory as:
</p>
<table border="1">
<caption><b>Little endian example</b>
</caption>
<tbody><tr>
<td><code>D4</code>
</td>
<td><code>83</code>
</td>
<td><code>A5</code>
</td>
<td><code>1B</code>
</td></tr></tbody></table>
<p>This will be seen as <code>0xD4 0x83 0xA5 0x1B</code> when doing a memory dump.
</p>
<h3><span id="Two.27s_Complement_Representation"></span><span class="mw-headline" id="Two's_Complement_Representation">Two's Complement Representation</span><span class="mw-editsection"><span class="mw-editsection-bracket">[</span><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;section=7" title="부분 편집: Two&#039;s Complement Representation">+/-</a><span class="mw-editsection-bracket">]</span></span></h3>
<p>Two's complement is the standard way of representing negative integers in binary.  The sign is changed by inverting all of the bits and adding one.
</p>
<table border="1">
<caption><b>Two's complement example</b>
</caption>
<tbody><tr>
<td><i>Start</i>:
</td>
<td><code>0001</code>
</td></tr>
<tr>
<td><i>Invert</i>:
</td>
<td><code>1110</code>
</td></tr>
<tr>
<td><i>Add One</i>:
</td>
<td><code>1111</code>
</td></tr></tbody></table>
<p>0001 represents decimal 1
</p><p>1111 represents decimal -1
</p>
<h3><span class="mw-headline" id="Addressing_modes">Addressing modes</span><span class="mw-editsection"><span class="mw-editsection-bracket">[</span><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;section=8" title="부분 편집: Addressing modes">+/-</a><span class="mw-editsection-bracket">]</span></span></h3>
<p>The addressing mode indicates the manner in which the operand is presented.
</p>
<dl><dt>Register Addressing</dt>
<dd>(operand address R is in the address field)</dd></dl>
<div class="mw-highlight mw-highlight-lang-asm mw-content-ltr" dir="ltr"><pre><span></span><span class="nf">mov</span> <span class="no">ax</span><span class="p">,</span> <span class="no">bx</span>  <span class="c1">; moves contents of register bx into ax</span>
</pre></div>
<dl><dt>Immediate</dt>
<dd>(actual value is in the field)</dd></dl>
<div class="mw-highlight mw-highlight-lang-asm mw-content-ltr" dir="ltr"><pre><span></span><span class="nf">mov</span> <span class="no">ax</span><span class="p">,</span> <span class="mi">1</span>   <span class="c1">; moves value of 1 into register ax</span>
</pre></div>
<p>or
</p>
<div class="mw-highlight mw-highlight-lang-asm mw-content-ltr" dir="ltr"><pre><span></span><span class="nf">mov</span> <span class="no">ax</span><span class="p">,</span> <span class="mi">010</span><span class="no">Ch</span> <span class="c1">; moves value of 0x010C into register ax</span>
</pre></div>
<dl><dt>Direct memory addressing</dt>
<dd>(operand address is in the address field)</dd></dl>
<div class="mw-highlight mw-highlight-lang-asm mw-content-ltr" dir="ltr"><pre><span></span><span class="na">.data</span>
<span class="nf">my_var</span> <span class="no">dw</span> <span class="mi">0</span><span class="no">abcdh</span> <span class="c1">; my_var = 0xabcd</span>
<span class="na">.code</span>
<span class="nf">mov</span> <span class="no">ax</span><span class="p">,</span> <span class="p">[</span><span class="no">my_var</span><span class="p">]</span> <span class="c1">; copy my_var content in ax (ax=0xabcd)</span>
</pre></div>
<dl><dt>Direct offset addressing</dt>
<dd>(uses arithmetics to modify address)</dd></dl>
<div class="mw-highlight mw-highlight-lang-asm mw-content-ltr" dir="ltr"><pre><span></span><span class="nf">byte_tbl</span> <span class="no">db</span> <span class="mi">12</span><span class="p">,</span><span class="mi">15</span><span class="p">,</span><span class="mi">16</span><span class="p">,</span><span class="mi">22</span><span class="p">,.....</span> <span class="c1">; Table of bytes</span>
<span class="nf">mov</span> <span class="no">al</span><span class="p">,[</span><span class="no">byte_tbl</span><span class="err">+</span><span class="mi">2</span><span class="p">]</span>
<span class="nf">mov</span> <span class="no">al</span><span class="p">,</span><span class="no">byte_tbl</span><span class="p">[</span><span class="mi">2</span><span class="p">]</span> <span class="c1">; same as the former</span>
</pre></div>
<dl><dt>Register Indirect</dt>
<dd>(field points to a register that contains the operand address)</dd></dl>
<div class="mw-highlight mw-highlight-lang-asm mw-content-ltr" dir="ltr"><pre><span></span><span class="nf">mov</span> <span class="no">ax</span><span class="p">,[</span><span class="no">di</span><span class="p">]</span>
</pre></div>
<dl><dd>The registers used for indirect addressing are BX, BP, SI, DI</dd></dl>
<dl><dt>Base-index</dt>
<dd></dd></dl>
<div class="mw-highlight mw-highlight-lang-asm mw-content-ltr" dir="ltr"><pre><span></span><span class="nf">mov</span> <span class="no">ax</span><span class="p">,[</span><span class="no">bx</span> <span class="err">+</span> <span class="no">di</span><span class="p">]</span>
</pre></div>
<dl><dd>For example, if we are talking about an array, BX contains the address of the beginning of the array, and DI contains the index into the array.</dd></dl>
<dl><dt>Base-index with displacement</dt>
<dd></dd></dl>
<div class="mw-highlight mw-highlight-lang-asm mw-content-ltr" dir="ltr"><pre><span></span><span class="nf">mov</span> <span class="no">ax</span><span class="p">,[</span><span class="no">bx</span> <span class="err">+</span> <span class="no">di</span> <span class="err">+</span> <span class="mi">10</span><span class="p">]</span>
</pre></div>
<h3><span id="General-purpose_registers_.2864-bit_naming_conventions.29"></span><span class="mw-headline" id="General-purpose_registers_(64-bit_naming_conventions)">General-purpose registers (64-bit naming conventions)</span><span class="mw-editsection"><span class="mw-editsection-bracket">[</span><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;section=9" title="부분 편집: General-purpose registers (64-bit naming conventions)">+/-</a><span class="mw-editsection-bracket">]</span></span></h3>
<p><a href="/w/index.php?title=%ED%8B%80:Main&amp;action=edit&amp;redlink=1" class="new" title="틀:Main (아직 수록되지 않은 문서 제목)">틀:Main</a>
64-bit x86 adds 8 more general-purpose registers, named R8, R9, R10 and so on up to R15. It also introduces a new naming convention that must be used for these new registers and can also be used for the old ones (except that AH, CH, DH and BH have no equivalents). In the new convention:
</p>
<ul><li>R0 is RAX.</li>
<li>R1 is RCX.</li>
<li>R2 is RDX.</li>
<li>R3 is RBX.</li>
<li>R4 is RSP.</li>
<li>R5 is RBP.</li>
<li>R6 is RSI.</li>
<li>R7 is RDI.</li>
<li>R8,R9,R10,R11,R12,R13,R14,R15 are the new registers and have no other names.</li>
<li>R0D~R15D are the lowermost 32 bits of each register. For example, R0D is EAX.</li>
<li>R0W~R15W are the lowermost 16 bits of each register. For example, R0W is AX.</li>
<li>R0L~R15L are the lowermost 8 bits of each register. For example, R0L is AL.</li></ul>
<p><a href="/w/index.php?title=%ED%8B%80:Main&amp;action=edit&amp;redlink=1" class="new" title="틀:Main (아직 수록되지 않은 문서 제목)">틀:Main</a>
As well, 64-bit x86 includes SSE2, so each 64-bit x86 CPU has at least 8 registers (named XMM0~XMM7) that are 128 bits wide, but only accessible through <a href="/w/index.php?title=X86_Assembly/SSE&amp;action=edit&amp;redlink=1" class="new" title="X86 Assembly/SSE (아직 수록되지 않은 문서 제목)">SSE instructions</a>. They cannot be used for quadruple-precision (128-bit) floating-point arithmetic, but they can each hold 2 double-precision or 4 single-precision floating-point values for a SIMD parallel instruction. They can also be operated on as 128-bit integers or vectors of shorter integers. If the processor supports AVX, as newer Intel and AMD desktop CPUs do, then each of these registers is actually the lower half of a 256-bit register (named YMM0~YMM7), the whole of which can be accessed with AVX instructions for further parallelization.
</p>
<h2><span class="mw-headline" id="Stack">Stack</span><span class="mw-editsection"><span class="mw-editsection-bracket">[</span><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;section=10" title="부분 편집: Stack">+/-</a><span class="mw-editsection-bracket">]</span></span></h2>
<p>The stack is a Last In First Out (LIFO) data structure; data is pushed onto it and popped off of it in the reverse order. 
</p>
<div class="mw-highlight mw-highlight-lang-asm mw-content-ltr" dir="ltr"><pre><span></span> <span class="nf">mov</span> <span class="no">ax</span><span class="p">,</span> <span class="mi">006</span><span class="no">Ah</span>
 <span class="nf">mov</span> <span class="no">bx</span><span class="p">,</span> <span class="no">F79Ah</span>
 <span class="nf">mov</span> <span class="no">cx</span><span class="p">,</span> <span class="mi">1124</span><span class="no">h</span>
 <span class="nf">push</span> <span class="no">ax</span>
</pre></div>  
<p>You push the value in AX onto the top of the stack, which now holds the value $006A.
</p>
<div class="mw-highlight mw-highlight-lang-asm mw-content-ltr" dir="ltr"><pre><span></span><span class="nf">push</span> <span class="no">bx</span>
</pre></div>
<p>You do the same thing to the value in BX; the stack now has $006A and $F79A.
</p>
<div class="mw-highlight mw-highlight-lang-asm mw-content-ltr" dir="ltr"><pre><span></span><span class="nf">push</span> <span class="no">cx</span>
</pre></div>
<p>Now the stack has $006A, $F79A, and $1124.
</p>
<div class="mw-highlight mw-highlight-lang-asm mw-content-ltr" dir="ltr"><pre><span></span><span class="nf">call</span> <span class="no">do_stuff</span>
</pre></div>
<p>Do some stuff. The function is not forced to save the registers it uses, hence us saving them.
</p>
<div class="mw-highlight mw-highlight-lang-asm mw-content-ltr" dir="ltr"><pre><span></span><span class="nf">pop</span> <span class="no">cx</span>
</pre></div>
<p>Pop the last element pushed onto the stack into CX, $1124; the stack now has $006A and $F79A.
</p>
<div class="mw-highlight mw-highlight-lang-asm mw-content-ltr" dir="ltr"><pre><span></span><span class="nf">pop</span> <span class="no">bx</span>
</pre></div>
<p>Pop the last element pushed onto the stack into BX, $F79A; the stack now has just $006A.
</p>
<div class="mw-highlight mw-highlight-lang-asm mw-content-ltr" dir="ltr"><pre><span></span><span class="nf">pop</span> <span class="no">ax</span>
</pre></div>
<p>Pop the last element pushed onto the stack into AX, $006A; the stack is empty.
</p><p>The Stack is usually used to pass arguments to functions or procedures and also to keep track of control flow when the <code>call</code> instruction is used. The other common use of the Stack is temporarily saving registers.
</p>
<h2><span class="mw-headline" id="CPU_Operation_Modes">CPU Operation Modes</span><span class="mw-editsection"><span class="mw-editsection-bracket">[</span><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;section=11" title="부분 편집: CPU Operation Modes">+/-</a><span class="mw-editsection-bracket">]</span></span></h2>
<h3><span class="mw-headline" id="Real_Mode">Real Mode</span><span class="mw-editsection"><span class="mw-editsection-bracket">[</span><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;section=12" title="부분 편집: Real Mode">+/-</a><span class="mw-editsection-bracket">]</span></span></h3>
<p>Real Mode is a holdover from the original Intel 8086. You generally won't need to know anything about it (unless you are programming for a DOS-based system or, more likely, writing a boot loader that is directly called by the BIOS).
</p><p>The Intel 8086 accessed memory using 20-bit addresses. But, as the processor itself was 16-bit, Intel invented an addressing scheme that provided a way of mapping a 20-bit addressing space into 16-bit words. Today's x86 processors start in the so-called Real Mode, which is an operating mode that mimics the behavior of the 8086, with some very tiny differences, for backwards compatibility.
</p><p>In Real Mode, a segment and an offset register are used together to yield a final memory address. The value in the segment register is multiplied by 16 (shifted 4 bits to the left) and the offset is added to the result. This provides a usable address space of 1 MB. However, a quirk in the addressing scheme allows access past the 1 MB limit if a segment address of 0xFFFF (the highest possible) is used; on the 8086 and 8088, all accesses to this area wrapped around to the low end of memory, but on the 80286 and later, up to 65520 bytes past the 1 MB mark can be addressed this way if the A20 address line is enabled. <i>See: <a href="/w/index.php?title=X86_Assembly/16_32_and_64_Bits&amp;action=edit&amp;redlink=1" class="new" title="X86 Assembly/16 32 and 64 Bits (아직 수록되지 않은 문서 제목)">The A20 Gate Saga</a></i>.
</p><p>One benefit shared by Real Mode segmentation and by <a href="#Multi-Segmented_Memory_Model">Protected Mode Multi-Segment Memory Model</a> is that all addresses must be given relative to another address (this is, the segment base address). A program can have its own address space and completely ignore the segment registers, and thus no pointers have to be relocated to run the program. Programs can perform <i>near</i> calls and jumps within the same segment, and data is always relative to segment base addresses (which in the Real Mode addressing scheme are computed from the values loaded in the Segment Registers).
</p><p>This is what the DOS *.COM format does; the contents of the file are loaded into memory and blindly run. However, due to the fact that Real Mode segments are always 64&#160;KB long, COM files could not be larger than that (in fact, they had to fit into 65280 bytes, since DOS used the first 256 of a segment for housekeeping data); for many years this wasn't a problem.
</p>
<h3><span class="mw-headline" id="Protected_Mode">Protected Mode</span><span class="mw-editsection"><span class="mw-editsection-bracket">[</span><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;section=13" title="부분 편집: Protected Mode">+/-</a><span class="mw-editsection-bracket">]</span></span></h3>
<h4><span class="mw-headline" id="Flat_Memory_Model">Flat Memory Model</span><span class="mw-editsection"><span class="mw-editsection-bracket">[</span><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;section=14" title="부분 편집: Flat Memory Model">+/-</a><span class="mw-editsection-bracket">]</span></span></h4>
<p>If programming in a modern operating system (such as Linux, Windows), you are basically programming in flat 32-bit mode. Any register can be used in addressing, and it is generally more efficient to use a full 32-bit register instead of a 16-bit register part. Additionally, segment registers are generally unused in flat mode, and it is generally a bad idea to touch them.
</p>
<h4><span class="mw-headline" id="Multi-Segmented_Memory_Model">Multi-Segmented Memory Model</span><span class="mw-editsection"><span class="mw-editsection-bracket">[</span><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;section=15" title="부분 편집: Multi-Segmented Memory Model">+/-</a><span class="mw-editsection-bracket">]</span></span></h4>
<p>Using a 32-bit register to address memory the program can access (almost) all of the memory in a modern computer. For earlier processors (with only 16-bit registers) the segmented memory model was used. The 'CS', 'DS', and 'ES' registers are used to point to the different <i>chunks</i> of memory. For a small program (small model) the CS=DS=ES. For larger memory models, these 'segments' can point to different locations.
</p>
<!-- 
NewPP limit report
Parsed by mw1371
Cached time: 20210223021730
Cache expiry: 2592000
Dynamic content: false
Complications: []
CPU time usage: 0.080 seconds
Real time usage: 1.076 seconds
Preprocessor visited node count: 144/1000000
Post‐expand include size: 332/2097152 bytes
Template argument size: 0/2097152 bytes
Highest expansion depth: 5/40
Expensive parser function count: 0/500
Unstrip recursion depth: 0/20
Unstrip post‐expand size: 5287/5000000 bytes
Number of Wikibase entities loaded: 0/400
-->
<!--
Transclusion expansion time report (%,ms,calls,template)
100.00%  407.394      1 -total
  8.05%   32.814      1 틀:소문자
  5.80%   23.617      1 틀:X86_어셈블리
  0.25%    1.013      2 틀:Main
-->

<!-- Saved in parser cache with key kowikibooks:pcache:idhash:8696-0!canonical and timestamp 20210223021729 and revision id 40535. Serialized with JSON.
 -->
</div><noscript><img src="//ko.wikibooks.org/wiki/Special:CentralAutoLogin/start?type=1x1" alt="" title="" width="1" height="1" style="border: none; position: absolute;" /></noscript>
<div class="printfooter">원본 주소 "<a dir="ltr" href="https://ko.wikibooks.org/w/index.php?title=X86_어셈블리/x86_아키텍처&amp;oldid=40535">https://ko.wikibooks.org/w/index.php?title=X86_어셈블리/x86_아키텍처&amp;oldid=40535</a>"</div></div>
		<div id="catlinks" class="catlinks" data-mw="interface"><div id="mw-normal-catlinks" class="mw-normal-catlinks"><a href="/wiki/%ED%8A%B9%EC%88%98:%EB%B6%84%EB%A5%98" title="특수:분류">카테고리</a>: <ul><li><a href="/w/index.php?title=%EB%B6%84%EB%A5%98:%EA%B5%AC%EC%8B%9D_source_%ED%83%9C%EA%B7%B8%EB%A5%BC_%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94_%EB%AC%B8%EC%84%9C&amp;action=edit&amp;redlink=1" class="new" title="분류:구식 source 태그를 사용하는 문서 (아직 수록되지 않은 문서 제목)">구식 source 태그를 사용하는 문서</a></li><li><a href="/wiki/%EB%B6%84%EB%A5%98:X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC" title="분류:X86 어셈블리">X86 어셈블리</a></li></ul></div></div>
	</div>
</div>

<div id="mw-navigation">
	<h2>둘러보기 메뉴</h2>
	<div id="mw-head">
		<!-- Please do not use role attribute as CSS selector, it is deprecated. -->
<nav id="p-personal" class="mw-portlet mw-portlet-personal vector-menu" aria-labelledby="p-personal-label" role="navigation" 
	 >
	<h3 id="p-personal-label" class="vector-menu-heading">
		<span>개인 도구</span>
	</h3>
	<div class="vector-menu-content">
		<ul class="vector-menu-content-list"><li id="pt-anonuserpage">로그인하지 않음</li><li id="pt-anontalk"><a href="/wiki/%ED%8A%B9%EC%88%98:%EB%82%B4%EC%82%AC%EC%9A%A9%EC%9E%90%ED%86%A0%EB%A1%A0" title="IP 참여자의 토론 문서 [n]" accesskey="n">이 아이피 참여자에 대한 토론</a></li><li id="pt-anoncontribs"><a href="/wiki/%ED%8A%B9%EC%88%98:%EB%82%B4%EA%B8%B0%EC%97%AC" title="이 IP 주소의 편집 목록 [y]" accesskey="y">기여</a></li><li id="pt-createaccount"><a href="/w/index.php?title=%ED%8A%B9%EC%88%98:%EA%B3%84%EC%A0%95%EB%A7%8C%EB%93%A4%EA%B8%B0&amp;returnto=X86+%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC%2Fx86+%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98" title="계정을 만들고 로그인하는 것이 좋습니다; 하지만, 필수는 아닙니다">계정 만들기</a></li><li id="pt-login"><a href="/w/index.php?title=%ED%8A%B9%EC%88%98:%EB%A1%9C%EA%B7%B8%EC%9D%B8&amp;returnto=X86+%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC%2Fx86+%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98" title="로그인하실 것을 권장합니다. [o]" accesskey="o">로그인</a></li></ul>
		
	</div>
</nav>

		<div id="left-navigation">
			<!-- Please do not use role attribute as CSS selector, it is deprecated. -->
<nav id="p-namespaces" class="mw-portlet mw-portlet-namespaces vector-menu vector-menu-tabs" aria-labelledby="p-namespaces-label" role="navigation" 
	 >
	<h3 id="p-namespaces-label" class="vector-menu-heading">
		<span>이름공간</span>
	</h3>
	<div class="vector-menu-content">
		<ul class="vector-menu-content-list"><li id="ca-nstab-main" class="selected"><a href="/wiki/X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98" title="내용 읽어 보기 [c]" accesskey="c">문서</a></li><li id="ca-talk" class="new"><a href="/w/index.php?title=%ED%86%A0%EB%A1%A0:X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit&amp;redlink=1" rel="discussion" title="토론 페이지 읽어 보기 (아직 수록되지 않은 문서 제목) [t]" accesskey="t">토론</a></li></ul>
		
	</div>
</nav>

			<!-- Please do not use role attribute as CSS selector, it is deprecated. -->
<nav id="p-variants" class="mw-portlet mw-portlet-variants emptyPortlet vector-menu vector-menu-dropdown" aria-labelledby="p-variants-label" role="navigation" 
	 >
	<input type="checkbox" class="vector-menu-checkbox" aria-labelledby="p-variants-label" />
	<h3 id="p-variants-label" class="vector-menu-heading">
		<span>변수</span>
	</h3>
	<div class="vector-menu-content">
		<ul class="vector-menu-content-list"></ul>
		
	</div>
</nav>

		</div>
		<div id="right-navigation">
			<!-- Please do not use role attribute as CSS selector, it is deprecated. -->
<nav id="p-views" class="mw-portlet mw-portlet-views vector-menu vector-menu-tabs" aria-labelledby="p-views-label" role="navigation" 
	 >
	<h3 id="p-views-label" class="vector-menu-heading">
		<span>보기</span>
	</h3>
	<div class="vector-menu-content">
		<ul class="vector-menu-content-list"><li id="ca-view" class="selected"><a href="/wiki/X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98">읽기</a></li><li id="ca-edit"><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=edit" title="이 문서 편집하기 [e]" accesskey="e">편집</a></li><li id="ca-history"><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=history" title="문서의 과거 판 [h]" accesskey="h">역사 보기</a></li></ul>
		
	</div>
</nav>

			<!-- Please do not use role attribute as CSS selector, it is deprecated. -->
<nav id="p-cactions" class="mw-portlet mw-portlet-cactions emptyPortlet vector-menu vector-menu-dropdown" aria-labelledby="p-cactions-label" role="navigation" 
	 >
	<input type="checkbox" class="vector-menu-checkbox" aria-labelledby="p-cactions-label" />
	<h3 id="p-cactions-label" class="vector-menu-heading">
		<span>더 보기</span>
	</h3>
	<div class="vector-menu-content">
		<ul class="vector-menu-content-list"></ul>
		
	</div>
</nav>

			<div id="p-search" role="search" >
	<h3 >
		<label for="searchInput">찾아보기</label>
	</h3>
	<form action="/w/index.php" id="searchform">
		<div id="simpleSearch" data-search-loc="header-navigation">
			<input type="search" name="search" placeholder="위키책 검색" autocapitalize="sentences" title="찾기 위키책 [f]" accesskey="f" id="searchInput"/>
			<input type="hidden" name="title" value="특수:검색"/>
			<input type="submit" name="fulltext" value="검색" title="이 낱말이 담긴 페이지 찾기" id="mw-searchButton" class="searchButton mw-fallbackSearchButton"/>
			<input type="submit" name="go" value="문서" title="꼭 이 낱말이 담긴 페이지로 가기" id="searchButton" class="searchButton"/>
		</div>
	</form>
</div>

		</div>
	</div>
	
<div id="mw-panel">
	<div id="p-logo" role="banner">
		<a class="mw-wiki-logo" href="/wiki/%EC%9C%84%ED%82%A4%EC%B1%85:%EB%8C%80%EB%AC%B8"
			title="대문으로 가기"></a>
	</div>
	<!-- Please do not use role attribute as CSS selector, it is deprecated. -->
<nav id="p-navigation" class="mw-portlet mw-portlet-navigation vector-menu vector-menu-portal portal" aria-labelledby="p-navigation-label" role="navigation" 
	 >
	<h3 id="p-navigation-label" class="vector-menu-heading">
		<span>둘러보기</span>
	</h3>
	<div class="vector-menu-content">
		<ul class="vector-menu-content-list"><li id="n-mainpage-description"><a href="/wiki/%EC%9C%84%ED%82%A4%EC%B1%85:%EB%8C%80%EB%AC%B8" title="대문으로 가기 [z]" accesskey="z">대문</a></li><li id="n-recentchanges"><a href="/wiki/%ED%8A%B9%EC%88%98:%EC%B5%9C%EA%B7%BC%EB%B0%94%EB%80%9C" title="최근에 바뀐 일들 [r]" accesskey="r">최근 바뀜</a></li><li id="n-randompage"><a href="/wiki/%ED%8A%B9%EC%88%98:%EC%9E%84%EC%9D%98%EB%AC%B8%EC%84%9C" title="임의 문서를 찾아봅니다... [x]" accesskey="x">임의의 문서로</a></li><li id="n-logpage"><a href="/wiki/%ED%8A%B9%EC%88%98:%EA%B8%B0%EB%A1%9D">기록 일지</a></li></ul>
		
	</div>
</nav>

	<!-- Please do not use role attribute as CSS selector, it is deprecated. -->
<nav id="p-portal" class="mw-portlet mw-portlet-portal vector-menu vector-menu-portal portal" aria-labelledby="p-portal-label" role="navigation" 
	 >
	<h3 id="p-portal-label" class="vector-menu-heading">
		<span>편집실</span>
	</h3>
	<div class="vector-menu-content">
		<ul class="vector-menu-content-list"><li id="n-help"><a href="/wiki/%EC%9C%84%ED%82%A4%EC%B1%85:%EB%8F%84%EC%9B%80%EB%A7%90" title="도움말">도움말</a></li><li id="n-portal"><a href="/wiki/%EC%9C%84%ED%82%A4%EC%B1%85:%ED%8E%B8%EC%A7%91%EC%8B%A4" title="위키책 편집부 안내">편집실</a></li><li id="n-booksort"><a href="/wiki/%EC%9C%84%ED%82%A4%EC%B1%85:%EC%A3%BC%EC%A0%9C%EB%B3%84_%EC%9C%84%ED%82%A4%EC%B1%85">주제별 위키책</a></li><li id="n-currentevents"><a href="/wiki/%EC%9C%84%ED%82%A4%EC%B1%85:%EC%9E%90%EC%9C%A0%EA%B2%8C%EC%8B%9C%ED%8C%90" title="위키책 자유 게시판">자유게시판</a></li><li id="n-sitesupport"><a href="//donate.wikimedia.org/wiki/Special:FundraiserRedirector?utm_source=donate&amp;utm_medium=sidebar&amp;utm_campaign=C13_ko.wikibooks.org&amp;uselang=ko" title="위키미디어 재단에 기부 안내">기부 안내</a></li></ul>
		
	</div>
</nav>
<!-- Please do not use role attribute as CSS selector, it is deprecated. -->
<nav id="p-tb" class="mw-portlet mw-portlet-tb vector-menu vector-menu-portal portal" aria-labelledby="p-tb-label" role="navigation" 
	 >
	<h3 id="p-tb-label" class="vector-menu-heading">
		<span>도구</span>
	</h3>
	<div class="vector-menu-content">
		<ul class="vector-menu-content-list"><li id="t-whatlinkshere"><a href="/wiki/%ED%8A%B9%EC%88%98:%EA%B0%80%EB%A6%AC%ED%82%A4%EB%8A%94%EB%AC%B8%EC%84%9C/X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98" title="링크된 문서들 [j]" accesskey="j">링크된 문서</a></li><li id="t-recentchangeslinked"><a href="/wiki/%ED%8A%B9%EC%88%98:%EB%A7%81%ED%81%AC%EC%B5%9C%EA%B7%BC%EB%B0%94%EB%80%9C/X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98" rel="nofollow" title="링크된 문서들의 바뀐 일들 [k]" accesskey="k">가리키는 글의 최근 바뀜</a></li><li id="t-upload"><a href="//commons.wikimedia.org/wiki/Special:UploadWizard?uselang=ko" title="이미지 및 미디어 파일 올리기 [u]" accesskey="u">파일 올리기</a></li><li id="t-specialpages"><a href="/wiki/%ED%8A%B9%EC%88%98:%ED%8A%B9%EC%88%98%EB%AC%B8%EC%84%9C" title="특별 페이지들 [q]" accesskey="q">특수 문서 목록</a></li><li id="t-permalink"><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;oldid=40535" title="문서의 현재 버전에 걸린 고유 링크">앞뒤 버전</a></li><li id="t-info"><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=info" title="이 문서에 대한 자세한 정보">문서 정보</a></li><li id="t-cite"><a href="/w/index.php?title=%ED%8A%B9%EC%88%98:%EC%9D%B4%EB%AC%B8%EC%84%9C%EC%9D%B8%EC%9A%A9&amp;page=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC%2Fx86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;id=40535&amp;wpFormIdentifier=titleform" title="이 문서를 인용하는 방법에 대한 정보">이 문서 인용하기</a></li></ul>
		
	</div>
</nav>
<!-- Please do not use role attribute as CSS selector, it is deprecated. -->
<nav id="p-coll-print_export" class="mw-portlet mw-portlet-coll-print_export vector-menu vector-menu-portal portal" aria-labelledby="p-coll-print_export-label" role="navigation" 
	 >
	<h3 id="p-coll-print_export-label" class="vector-menu-heading">
		<span>인쇄/내보내기</span>
	</h3>
	<div class="vector-menu-content">
		<ul class="vector-menu-content-list"><li id="coll-create_a_book"><a href="/w/index.php?title=%ED%8A%B9%EC%88%98:%EC%B1%85&amp;bookcmd=book_creator&amp;referer=X86+%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC%2Fx86+%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98">책 만들기</a></li><li id="coll-download-as-rl"><a href="/w/index.php?title=%ED%8A%B9%EC%88%98:DownloadAsPdf&amp;page=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC%2Fx86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;action=show-download-screen">PDF 다운로드</a></li><li id="t-print"><a href="/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;printable=yes" title="이 문서의 인쇄용 판 [p]" accesskey="p">인쇄용 판</a></li></ul>
		
	</div>
</nav>

	<!-- Please do not use role attribute as CSS selector, it is deprecated. -->
<nav id="p-lang" class="mw-portlet mw-portlet-lang vector-menu vector-menu-portal portal" aria-labelledby="p-lang-label" role="navigation" 
	 >
	<h3 id="p-lang-label" class="vector-menu-heading">
		<span>다른 언어</span>
	</h3>
	<div class="vector-menu-content">
		<ul class="vector-menu-content-list"></ul>
		<div class="after-portlet after-portlet-lang"><span class="uls-after-portlet-link"></span><span class="wb-langlinks-add wb-langlinks-link"><a href="https://www.wikidata.org/wiki/Special:NewItem?site=kowikibooks&amp;page=X86+%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC%2Fx86+%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98" title="언어 간 링크 추가" class="wbc-editpage">링크 추가</a></span></div>
	</div>
</nav>

</div>

</div>
<footer id="footer" class="mw-footer" role="contentinfo" >
	<ul id="footer-info" >
	<li id="footer-info-lastmod"> 이 문서는 2020년 7월 27일 (월) 19:58에 마지막으로 편집되었습니다.</li>
	<li id="footer-info-copyright">내용은 <a href="https://creativecommons.org/licenses/by-sa/3.0/deed.ko">크리에이티브 커먼즈 저작자표시-동일조건변경허락 라이선스</a>에 따라 사용할 수 있으며 추가적인 조건이 적용될 수 있습니다.
자세한 내용은 <a href="https://foundation.wikimedia.org/wiki/Terms_of_Use/ko">이용 약관</a>을 참조하십시오.</li>
</ul>

	<ul id="footer-places" >
	<li id="footer-places-privacy"><a href="https://foundation.wikimedia.org/wiki/Privacy_policy" class="extiw" title="wmf:Privacy policy">정보 보호 사항</a></li>
	<li id="footer-places-about"><a href="/wiki/%EC%9C%84%ED%82%A4%EC%B1%85:%EC%86%8C%EA%B0%9C" title="위키책:소개">위키책 소개</a></li>
	<li id="footer-places-disclaimer"><a href="/wiki/%EC%9C%84%ED%82%A4%EC%B1%85:%EC%9D%BC%EB%B0%98_%EC%9C%A0%EC%9D%98%EC%82%AC%ED%95%AD" title="위키책:일반 유의사항">유의사항</a></li>
	<li id="footer-places-mobileview"><a href="//ko.m.wikibooks.org/w/index.php?title=X86_%EC%96%B4%EC%85%88%EB%B8%94%EB%A6%AC/x86_%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98&amp;mobileaction=toggle_view_mobile" class="noprint stopMobileRedirectToggle">모바일 보기</a></li>
	<li id="footer-places-developers"><a href="https://www.mediawiki.org/wiki/Special:MyLanguage/How_to_contribute">개발자</a></li>
	<li id="footer-places-statslink"><a href="https://stats.wikimedia.org/#/ko.wikibooks.org">통계</a></li>
	<li id="footer-places-cookiestatement"><a href="https://foundation.wikimedia.org/wiki/Cookie_statement">쿠키 정책</a></li>
</ul>

	<ul id="footer-icons" class="noprint">
	<li id="footer-copyrightico"><a href="https://wikimediafoundation.org/"><img src="/static/images/footer/wikimedia-button.png" srcset="/static/images/footer/wikimedia-button-1.5x.png 1.5x, /static/images/footer/wikimedia-button-2x.png 2x" width="88" height="31" alt="Wikimedia Foundation" loading="lazy" /></a></li>
	<li id="footer-poweredbyico"><a href="https://www.mediawiki.org/"><img src="/static/images/footer/poweredby_mediawiki_88x31.png" alt="Powered by MediaWiki" srcset="/static/images/footer/poweredby_mediawiki_132x47.png 1.5x, /static/images/footer/poweredby_mediawiki_176x62.png 2x" width="88" height="31" loading="lazy"/></a></li>
</ul>

	<div style="clear: both;"></div>
</footer>


<script>(RLQ=window.RLQ||[]).push(function(){mw.config.set({"wgPageParseReport":{"limitreport":{"cputime":"0.080","walltime":"1.076","ppvisitednodes":{"value":144,"limit":1000000},"postexpandincludesize":{"value":332,"limit":2097152},"templateargumentsize":{"value":0,"limit":2097152},"expansiondepth":{"value":5,"limit":40},"expensivefunctioncount":{"value":0,"limit":500},"unstrip-depth":{"value":0,"limit":20},"unstrip-size":{"value":5287,"limit":5000000},"entityaccesscount":{"value":0,"limit":400},"timingprofile":["100.00%  407.394      1 -total","  8.05%   32.814      1 틀:소문자","  5.80%   23.617      1 틀:X86_어셈블리","  0.25%    1.013      2 틀:Main"]},"cachereport":{"origin":"mw1371","timestamp":"20210223021730","ttl":2592000,"transientcontent":false}}});mw.config.set({"wgBackendResponseTime":159,"wgHostname":"mw1321"});});</script>
</body></html>
