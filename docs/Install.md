<h1> Soda OS Download and Installation </h1>

<h2> Soda OS Donwload </h2>
To install and use Soda OS for the first time or to restore it to its initial state, you need to download the image.

The download path is as follows.
[Download Page](https://github.com/hanback-docs/Soda)

![os](./picture/soda_page.png)

Here, programs such as compression programs and SD Formatter are bundled for user convenience and provided under the name of "host tools".

The list of programs included in "host tools" is as follows.

<h4> HostTools </h4>
&emsp;<code class="code_accent">Bonjour Browser</code> : Discover devices on the network<br>
&emsp;<code class="code_accent">D2CodingFonts</code> : Free coding-only fonts<br>
&emsp;<code class="code_accent">iPuTTY</code> : Virtual Terminal<br>
&emsp;<code class="code_accent">VcXsrv</code> : X Server for Windows<br>
&emsp;<code class="code_accent">NoMachine</code> : Remote Desktop<br>
&emsp;<code class="code_accent">Win32DiskImager</code> : Image Writer<br>
&emsp;<code class="code_accent">WinSCP</code> : Remote Explorer<br>

<h2> SD Card Formatting </h2>

This is performed when Soda OS cannot be installed by Win32DiskImager due to a logical error in the SD memory. If there is no problem, this operation is skipped.

Users who need it download SDFormatter from the following path and install it.
[SDFormatter](https://www.sdcard.org/downloads/formatter/eula_windows/index.html)

Connect the prepared SD memory to an SD reader, plug it into a PC, and run SD Card Formatter to recognize the SD memory as a drive letter (eg D). Select this and press the Format button to format it again.

![format](./picture/format.png)


<!-- # Class & Method Description-->
<hr/>

## <span class="title">Class</span> <span class="title_accent">**Out**</span>    

<blockquote class="desc"> Output device is controlled by GPIO</blockquote>

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">Out(n)</code> : Out Object<br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`n` : GPIO number connected to the Output Device

<h5>&emsp;Methods</h5>

&emsp;<code class="code_accent">on()</code> : Set GPIO connected to Output Device to HIGH  
&emsp;<code class="code_accent">off()</code> : Set GPIO connected to Output Device to LOW   

<h5>&emsp;Example</h5>
<details>
	<summary>simple example</summary>
		
~~~python   
	from pop import Out
	import time 

	output = Out(1)
	output.on()
	time.sleep(1)
	output.off()	
~~~
	
</details>

---
