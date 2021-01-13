<h1> Pop </h1>
The code to import the whole of Pop Library : 

```python
from pop import *
```
<br>

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

## <span class="title">Class</span> <span class="title_accent">**Led**</span>    
<blockquote class="desc">LEDs are controlled by GPIO</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Led(n)</code> : Led Object inheriting from [Out Class](pop.md#class-out)<br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`n` : GPIO number connected to the LED   

<h5>&emsp;Methods</h5>

&emsp;Refer to [Out Class](pop.md#class-out) for inherited and used methods.

<h5>&emsp;Example</h5>

<details>
	<summary>simple example 1</summary>

~~~python
	from pop import Led
	import time 

	led = Led(1)
	o.on()
	time.sleep(1)
	o.off()
~~~

</details>

<details>
	<summary>simple example 2</summary>

~~~python
	from pop import Led
	import time 

	leds = [Led(23), Led(24), Led(25), Led(27)]    

	for i in range(20):
	    for led in leds:
		led.on()
		time.sleep(0.1)

	    for led in leds:
		led.off()
		time.sleep(0.1)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**Leds**</span>    
<blockquote class="desc">LEDs are controlled by GPIO</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Leds(n)</code> : Leds object inheriting from [Led Class](pop.md#class-led)<br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`n` : List number defined in board and connected to the LED  

<h5>&emsp;Methods</h5>   

&emsp;<code class="code_accent">allOn()</code> : Set all GPIO connected to Output Device to HIGH    
&emsp;<code class="code_accent">allOff()</code> : Set all GPIO connected to Output Device to LOW    

&emsp;Refer to [Out Class](pop.md#class-out) or [Led Class](pop.md#class-led) for inherited and used methods.

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Leds
	import time 

	leds = Leds()
	leds.allOn()
	time.sleep(1)
	leds.allOff()
~~~

</details>


---

## <span class="title">Class</span> <span class="title_accent">**Fan**</span>    
<blockquote class="desc">Fan is controlled by GPIO</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Fan(n)</code> : Fan object inheriting from [Out Class](pop.md#class-out)<br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`n` : GPIO number connected to the Fan   

<h5>&emsp;Methods</h5>

&emsp;Refer to [Out Class](pop.md#class-out) for inherited and used methods.

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Fan
	import time 

	dcfan = Fan(17)
	dcfan.on()
	time.sleep(2)
	dcfan.off()
~~~

</details>


---

## <span class="title">Class</span> <span class="title_accent">**Input**</span>    
<blockquote class="desc">Read the Input Device through GPIO</blockquote>    

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">Input(n,activeHigh=Ture)</code> : Input Object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : GPIO number connected to the Input Device    
&emsp;&emsp;&emsp;`activeHigh` : Used to check if the Input Device is HIGH when pressed , Default `True`    

<h5>&emsp;Definitions</h5>

&emsp;<code class="code_accent">FALLING</code> : Detect Falling Edge    
&emsp;<code class="code_accent">RISING</code> : Detect Rising Edge    
&emsp;<code class="code_accent">BOTH</code> : Detect Both Side    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">read()</code> : Read the Input Device status    
&emsp;<code class="code_accent">setCallback(func,param=None,type=BOTH)</code> : Set Callback function when detecting Edge<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`func` : Function to use when calling Callback    
&emsp;&emsp;&emsp;`param` : Parameters passed to the Callback function , Default None    
&emsp;&emsp;&emsp;`type` : Call condition of Callback function , Default BOTH  

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Input

	input = Input(22)
	data = input.read()
	print(ret)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**Switch**</span>    
<blockquote class="desc">Read the switch status through GPIO</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Switch(n)</code> : Switch object inheriting from [Input Class](pop.md#class-input)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : GPIO number connected to the switch    

<h5>&emsp;Methods</h5>

&emsp;Refer to [Input Class](pop.md#class-input) for inherited and used methods.

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Switch

	sw = Switch(22)
	data = sw.read()
	print(data)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**Switches**</span>    
<blockquote class="desc">Read the switch status through GPIO</blockquote>    

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">Switches(n)</code> : Switch object inheriting from [Input Class](pop.md#class-input)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : List number defined in the board and connected to the Switch    

<h5>&emsp;Methods</h5>

&emsp;Refer to [Input Class](pop.md#class-input) or [Switch Class](pop.md#class-switch) for inherited and used methods.

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Switches
	switch = Switches()

	data = switch[0].read()

	print(data)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**Pir**</span>    
<blockquote class="desc">Pir</blockquote>

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">Pir(n)</code> : Pir object inheriting from [Input Class](pop.md#class-input)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : GPIO number connected to the Pir 

<h5>&emsp;Methods</h5>

&emsp;Refer to [Input Class](pop.md#class-input) for inherited and used methods.

<h5>&emsp;Example</h5>

<details>
	<summary>simple example 1</summary>

~~~python
	from pop import Pir
	pir = Pir(22)

	data = pir.read()

	print(data)
~~~

</details>

<details>
	<summary>simple example 2</summary>

~~~python
	from pop import Pir
	import time

	pir = Pir(22)

	def onPir(param):
	    ret = pir.read()
	    if (ret == True):
		print("detect...")
		time.sleep(2)
	    else:
		time.sleep(0.1)

	pir.setCallback(onPir)
	input("Press <Enter> Key...\n")
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**SpiAdc**</span>    
<blockquote class="desc"> Control the adc chip through SPI interface</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">SpiAdc(channel, device=0, bus=0, speed=1000000)</code> : SpiAdc object <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)  
			
<h5>&emsp;Definitions</h5>  

&emsp;<code class="code_accent">TYPE_AVERAGE</code> : Average data based on sampling count    
&emsp;<code class="code_accent">TYPE_NORMAL</code> : Unaveraged raw data    
&emsp;<code class="code_accent">MODE_FULL</code> : Always call Callback function    
&emsp;<code class="code_accent">MODE_INCLUSIVE</code> : If data is in arange(max, min), call Callback function    
&emsp;<code class="code_accent">MODE_EXCLUSIVE</code> : If data is over arange, call Callback function    

<h5>&emsp;Methods</h5>   

&emsp;<code class="code_accent">getSample()</code> : Get sampling count    
&emsp;<code class="code_accent">read()</code> : Read data from device (Raw Type)    
&emsp;<code class="code_accent">readAverage()</code> : Read average data from device    
&emsp;<code class="code_accent">run()</code> : Read data and call Callback function according to mode  
&emsp;<code class="code_accent">setChipSelect(cs)</code> : Set the SPI chip select PIN<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`cs` : Chip select GPIO for SPI Interface

&emsp;<code class="code_accent">setSample(sample)</code> : Set sampling count<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`sample` : Sampling count


&emsp;<code class="code_accent">readVolt(ref=3.3,max=3020.0)</code> : Read data from device (Voltage Type)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`ref` : Reference voltage    
&emsp;&emsp;&emsp;`max` : Maximum value of raw data


&emsp;<code class="code_accent">readVoltAverage(ref=3.3,max=3020.0)</code> : Read data from device (Voltage Type)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`ref` : Reference voltage    
&emsp;&emsp;&emsp;`max` : Maximum value of raw data

&emsp;<code class="code_accent">setCallback(func,param=None,type=TYPE_AVERAGE,mode=MODE_FULL,min=0,max=ADC_MAX)</code> <br>&emsp;: Set up callback function for automatic data read<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`func` : Function to use when calling Callback    
&emsp;&emsp;&emsp;`param` : Parameters passed to the Callback function , Default None    
&emsp;&emsp;&emsp;`type` : Data read type , Default TYPE_AVERAGE    
&emsp;&emsp;&emsp;`mode` : Select mode , Default MODE_FULL    
&emsp;&emsp;&emsp;`min` : Analog data minimum , Default 0    
&emsp;&emsp;&emsp;`max` : Analog data maximum , Default 4095 (MCP3208 12bit ADC Chip)

<h5>&emsp;Example</h5>

<details>
	<summary>simple example 1</summary>

~~~python
	from pop import SpiAdc
	import time

	adc = SpiAdc(7)

	for i in range(20):
	    val = adc.read()
	    print("%d"%(val))
	    time.sleep(0.1)
~~~

</details>

<details>
	<summary>simple example 2</summary>

~~~python
	from pop import SpiAdc
	import time

	adc = SpiAdc(7)

	for i in range(20):
	    val = adc.readVolt()
	    print("volt = %.2f"%(val))
	    time.sleep(0.1)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**Psd**</span>    
<blockquote class="desc"> Measure the distance with PSD sensor</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Psd(channel=-1, device=0, bus=0, speed=1000000)</code> : PSD object inheriting from [SpiAdc Class](pop.md#class-spiadc)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">calcDist(val,calibration=1.1)</code> : Calculate distance value from raw data    <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : ADC Raw Data    
&emsp;&emsp;&emsp;`calibration` : Calibration Value, Default 1.1    

&emsp;Refer to [SpiAdc Class](pop.md#class-spiadc) for inherited and used methods.
		
<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Psd
	import time 
	
	psd = Psd(1)
	for i in range(20):
		val = psd.readAverage()
		cm = psd.calcDist(val)
		print(cm)
		time.sleep(0.5)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**Cds**</span>  
<blockquote class="desc"> Measure the Light with Cds sensor</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Cds(channel=-1, device=0, bus=0, speed=1000000)</code> : Cds object inheriting from [SpiAdc Class](pop.md#class-spiadc)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)    
			
<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">readAverage()</code> : Read lux data from device and calibration function  
&emsp;<code class="code_accent">setCalibrationPseudoLx(func)</code> : Set calibration function<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`func` : Calibration function

&emsp;Refer to [SpiAdc Class](pop.md#class-spiadc) for inherited and used methods.

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Cds
	import time 
	
	cds = Cds(2)
	
	for i in range(20):
		val = cds.readAverage()
		print(val)
		time.sleep(0.5)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**Gas**</span>    
<blockquote class="desc">Measure the Gas value with Gas sensor</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Gas(channel=-1, device=0, bus=0, speed=1000000)</code> : Gas object inheriting from [SpiAdc Class](pop.md#class-spiadc)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)       
			
<h5>&emsp;Methods</h5>

&emsp;<code class="code_accent">calibration(rl=4.7, clean=1)</code> : return calibration value for r0<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`rl` : register(k ohm) in circuit. default 4.7(k ohm)   
&emsp;&emsp;&emsp;`clean` : value for calibration in clean air    

&emsp;<code class="code_accent">setPropanCurve(x, y, inclination)</code> : set PropanCurve<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : any x-axis at PropanCurve in datasheet    
&emsp;&emsp;&emsp;`y` : any y-axis at PropanCurve in datasheet    
&emsp;&emsp;&emsp;`inclination` : inclination at PropanCurve in datasheet   

&emsp;<code class="code_accent">setMethanCurve(x, y, inclination)</code> : set MethanCurve<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : any x-axis at MethanCurve in datasheet    
&emsp;&emsp;&emsp;`y` : any y-axis at MethanCurve in datasheet    
&emsp;&emsp;&emsp;`inclination` : inclination at MethanCurve in datasheet    

&emsp;<code class="code_accent">setEthanolCurve(x, y, inclination)</code> : set EthanolCurve<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : any x-axis at EthanolCurve in datasheet    
&emsp;&emsp;&emsp;`y` : any y-axis at EthanolCurve in datasheet    
&emsp;&emsp;&emsp;`inclination` : inclination at EthanolCurve in datashee    

&emsp;<code class="code_accent">calcPropan(val)</code> : return Propan Gas value as ppm<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : raw ADC value    

&emsp;<code class="code_accent">calcMethan(val)</code> : return Methan Gas value as ppm<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : raw ADC value    

&emsp;<code class="code_accent">calcEthanol(val)</code> : return Ethanol Gas value as ppm<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : raw ADC value    

&emsp;<code class="code_accent">resistanceCalculation(val, rl=4.7)</code> : return resistance of gas sensor<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : raw ADC value    
&emsp;&emsp;&emsp;`rl` : register(k ohm) in circuit. default 4.7(k ohm) 

&emsp;Refer to [SpiAdc Class](pop.md#class-spiadc) for inherited and used methods.

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Gas 
	import time 

	gas = Gas(6)

	for i in range(20):
	    val = gas.readAverage()
	    print("val = %d, methan = %d"%(val,gas.calcMethan(val)))
	    time.sleep(0.1)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**Temperature**</span>    
<blockquote class="desc">Temperature object inheriting from SpiAdc Class</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Temperature(channel, device=0, bus=0, speed=1000000)</code> : Temperature object inheriting from [SpiAdc Class](pop.md#class-spiadc)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)   
			
<h5>&emsp;Methods</h5>

&emsp;<code class="code_accent">calcTempC(val, cal=1309)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : ...    
&emsp;&emsp;&emsp;`cal` : ...    

&emsp;Refer to [SpiAdc Class](pop.md#class-spiadc) for inherited and used methods.

---

## <span class="title">Class</span> <span class="title_accent">**Sound**</span>    
<blockquote class="desc"> Measure the Ambient sound with Sound sensor</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Sound(channel=-1, device=0, bus=0, speed=1000000)</code> : Sound object inheriting from [SpiAdc Class](pop.md#class-spiadc)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)    

<h5>&emsp;Methods</h5>

&emsp;Refer to [SpiAdc Class](pop.md#class-spiadc) for inherited and used methods.
		
<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Sound
	import time 
	
	sound = Sound(3)

	for i in range(20):
	    val = sound.read()
	    print(val)
	    time.sleep(0.2)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**Vr**</span>    
<blockquote class="desc"> Measure the Voltage with variable resistor</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Vr(channel=-1, device=0, bus=0, speed=1000000)</code> : Vr object inheriting from [SpiAdc Class](pop.md#class-spiadc)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)    

<h5>&emsp;Methods</h5>

&emsp;Refer to [SpiAdc Class](pop.md#class-spiadc) for inherited and used methods.
		
<details>
	<summary>simple example1</summary>
		
~~~python   
	from pop import Vr
	import time

	vr = Vr(5)
	
	for i in range(20):
		val = vr.read()
		print(val)
		time.sleep(0.2)
~~~
	
</details>
	
---

## <span class="title">Class</span> <span class="title_accent">**Potentiometer**</span>    
<blockquote class="desc"> Measure the Voltage with variable resistor</blockquote>    

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">Potentiometer(channel=-1, device=0, bus=0, speed=1000000)</code> <br>&emsp;: Potentiometer object inheriting from [SpiAdc Class](pop.md#class-spiadc)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)    

<h5>&emsp;Methods</h5>   
  
&emsp;<code class="code_accent">readAverage()</code> : Return level from range table   
&emsp;<code class="code_accent">getRangeTable()</code> : Return range table  
&emsp;<code class="code_accent">setRangeTable(table)</code> : Set potentiometer range table<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`table` : Table with 10 elements    
&emsp;&emsp;&emsp;&emsp;ex) [48, 300, 700, 1090, 1540, 1945, 2320, 2715, 2980, 3040]    

&emsp;Refer to [SpiAdc Class](pop.md#class-spiadc) for inherited and used methods.

<details>
	<summary>simple example1</summary>
		
~~~python   
	from pop import Potentiometer
	import time

	poten = Potentiometer(5)
	
	for i in range(20):
		val = poten.read()
		print(val)
		time.sleep(0.2)
~~~
	
</details>

---

## <span class="title">Class</span> <span class="title_accent">**PiezoBuzzer**</span>    
<blockquote class="desc">PiezoBuzzer is controlled by Software PWM</blockquote>  

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">PiezoBuzzer(n)</code> : PiezoBuzzer object inheriting from PopThread<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : A GPIO number connected to the PiezoBuzzer defined in board, or it can be manually set    

<h5>&emsp;Methods</h5>   

&emsp;<code class="code_accent">isPlay()</code> : Return play status  
&emsp;<code class="code_accent">getTempo()</code> : Get tempo value  
&emsp;<code class="code_accent">setTempo(n)</code> : Set tempo value<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : Value to be set to tempo

&emsp;<code class="code_accent">tone(scale,pitch,duration)</code> : Play a note on piezo buzzer during duration value    <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`scale` : Scale value to play on piezo buzzer (int type)    
&emsp;&emsp;&emsp;`pitch` : Pitch value to play on piezo buzzer. 'Do' is 1, 'Do♯' is 2, 'Re' is 3 and 'Si' is 12    
&emsp;&emsp;&emsp;`duration` : Tone is playing during duration value

&emsp;<code class="code_accent">rest(duration)</code> : Stop to play piezo buzzer    <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`duration` : The duration of the stopping

&emsp;<code class="code_accent">play(sheet)</code> : Play music by sheet<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`sheet` : list [[scale],[pitch],[duration]]

<h5>&emsp;Example</h5>

<details>
	<summary>simple example 1</summary>

~~~python
	from pop import PiezoBuzzer
	p = PiezoBuzzer(12)

	p.tone(4, 8, 4)
~~~

</details>	

<details>
	<summary>simple example 2</summary>

~~~python
	from pop import PiezoBuzzer
	p = PiezoBuzzer(12)

	p.setTempo(120)

	butterfly_scale = [4,4,4, 4,4,4, 4,4,4,4, 4,4,4,  4,4,4,4, 4,4,4, 4,4,4,4, 4,4,4]
	butterfly_pitch = [8,5,5, 6,3,3, 1,3,5,6, 8,8,8,  8,5,5,5, 6,3,3, 1,5,8,8, 5,5,5]
	butterfly_duration = [8,8,4,   8,8,4, 8,8,8,8, 8,8,4,  8,8,8,8, 8,8,4, 8,8,8,8, 8,8,4]
	sheet_butterfly = [butterfly_scale, butterfly_pitch, butterfly_duration]

	p.play(sheet_butterfly)
~~~

</details>	

---

## <span class="title">Class</span> <span class="title_accent">**I2c**</span>    
<blockquote class="desc">Class used when using I2C interface</blockquote>

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">I2c(addr, bus=1)</code> : I2c object <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`addr` : I2c Address    
&emsp;&emsp;&emsp;`bus` : I2c Interface bus. Default is 1    
			
<h5>&emsp;Methods</h5>   

&emsp;<code class="code_accent">read()</code> : Read 1byte data.

&emsp;<code class="code_accent">readByte(reg)</code> : Read 1byte data from register of chip connected through I2C.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`reg` : Register Address. Please refer to the datasheet of the I2C chip.    

&emsp;<code class="code_accent">readWord(reg)</code> : Read 1word data from register of chip connected through I2C.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`reg` : Register Address. Please refer to the datasheet of the I2C chip.    

&emsp;<code class="code_accent">readBlock(reg, length)</code> : Read block data from register of chip connected through I2C.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`reg` : Register Address. Please refer to the datasheet of the I2C chip.    
&emsp;&emsp;&emsp;`length` : Length of block to read. In case of length is 4, 4-byte data is read.     

&emsp;<code class="code_accent">write(data)</code> : Write 1byte data<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`data` : Data to write to the chip.    

&emsp;<code class="code_accent">writeByte(reg, data)</code> : Write 1byte data from the chip register connected through I2C.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`reg` : Register Address. Please refer to the datasheet of the I2C chip.  
&emsp;&emsp;&emsp;`data` : Data to write to the chip.    

&emsp;<code class="code_accent">writeWord(reg, data)</code> : Write 1word data from the chip register connected through I2C.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`reg` : Register Address. Please refer to the datasheet of the I2C chip.  
&emsp;&emsp;&emsp;`data` : Data to write to the chip.    

&emsp;<code class="code_accent">writeBlock(reg, data)</code> : Write block data from the chip register connected through I2C.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`reg` : Register Address. Please refer to the datasheet of the I2C chip.  
&emsp;&emsp;&emsp;`data` : Data to write to the chip.    

---

## <span class="title">Class</span> <span class="title_accent">**TempHumi**</span>    
<blockquote class="desc">Temperature & Humidity Sensor using I2C Interface</blockquote>

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">TempHumi(addr=0x77, debug=False)</code> : TempHumi Object <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`addr` : I2c Address. default 0x77     
&emsp;&emsp;&emsp;`debug` : Debug Mode. default False   

<h5>&emsp;Methods</h5>   

&emsp;<code class="code_accent">readTemp()</code> : Return calculated and calibrated celsius(°C) temperature. (float type)  
&emsp;<code class="code_accent">readHumi()</code> : Return calculated and calibrated humidity. (float type)  

&emsp;Refer to [I2c Class](pop.md#class-i2c) for inherited and used methods.

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import TempHumi
	import time

	th = TempHumi()

	for i in range(20):
	    temp = th.getTemperature()
	    humi = th.getHumidity()
	    print(temp, humi)
	    time.sleep(0.5)
~~~

</details>	

---

## <span class="title">Class</span> <span class="title_accent">**Oled**</span>    
<blockquote class="desc">Oled is controlled by I2C Interface</blockquote>    

<h5>&emsp;Initialization</h5>  

&emsp;<code class="code_accent">Oled( addr=OLED_ADDR, type=OLED_NONE_TYPE, automode=True)</code> <br>&emsp;: Oled object inheriting from [I2C Class](pop.md#class-i2c) (I2c Slave Address -> 0x3c). This method calls init(), clearDisplay()    <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`addr` : OLED I2C ADDR.default 0x3c    
&emsp;&emsp;&emsp;`type` : OLED Type. difined board config    
&emsp;&emsp;&emsp;`automode` : select automode. default `True`    

&emsp;**Definitions**    
&emsp;<code class="code_accent">OLED_SSD1306_I2C_128x32</code> : OLED device type number, if model name is 'SSD1306', select this type    
&emsp;<code class="code_accent">OLED_SH1106_I2C_128x64</code> : OLED device type number, if model name is 'SSH1106', select this type    
&emsp;<code class="code_accent">BLACK</code> : In OLED, you can use only 2 colors, One of them is black, Numeric value is 0   
&emsp;<code class="code_accent">WHITE</code> : Another of them is white, Numeric value is 1    

<h5>&emsp;Methods</h5>

&emsp;<code class="code_accent">width()</code> : Retun widht of OLED    
&emsp;<code class="code_accent">height()</code> : Return height of OLED   
&emsp;<code class="code_accent">display()</code> : Display buffer data on OLED    
&emsp;<code class="code_accent">clearDisplay()</code> : Clear the data on OLED    
&emsp;<code class="code_accent">init(type=OLED_SH1106_I2C_128x64)</code> <br>&emsp;: Initialize OLED and set width/height of OLED, This method calls setTextSize(), setTextColor(), clearDisplay()    <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`type` : Select OLED type

&emsp;<code class="code_accent">print(string)</code> : Print a string on OLED, Replace '\n' to New-Line    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`string`: The string to print on OLED

&emsp;<code class="code_accent">drawCircle(x0, y0, r, color)</code> : Draw a circle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x0` : Start point of x-axis    
&emsp;&emsp;&emsp;`y0` : Start point of y-axis    
&emsp;&emsp;&emsp;`r` : Radious of the circle    
&emsp;&emsp;&emsp;`color` : The color of a circle. BLACK(0) or WHITE(1)    

&emsp;<code class="code_accent">fillCircle(x0, y0, r, color)</code> : Draw a filled circle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x0` : Start point of x-axis    
&emsp;&emsp;&emsp;`y0` : Start point of y-axis    
&emsp;&emsp;&emsp;`r` : Radious of the circle    
&emsp;&emsp;&emsp;`color` : The color of a circle. BLACK(0) or WHITE(1)   

&emsp;<code class="code_accent">drawLine(x0, y0, x1, y1, color)</code> : Draw a line on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x0` : Start point of x-axis    
&emsp;&emsp;&emsp;`y0` : Start point of y-axis    
&emsp;&emsp;&emsp;`x1` : End point of x-axis    
&emsp;&emsp;&emsp;`y1` : End point of y-axis    
&emsp;&emsp;&emsp;`color` : The color of a line. BLACK(0) or WHITE(1)    

&emsp;<code class="code_accent">drawRect(x, y, w, h, color)</code> : Draw a rectangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Width of the rectangle    
&emsp;&emsp;&emsp;`h` : Height of the rectangle    
&emsp;&emsp;&emsp;`color` : The color of a rectangle. BLACK(0) or WHITE(1)   

&emsp;<code class="code_accent">fillRect(x, y, w, h, color)</code> : Draw a filled rectangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Width of the rectangle    
&emsp;&emsp;&emsp;`h` : Height of the rectangle    
&emsp;&emsp;&emsp;`color` : The color of a rectangle. BLACK(0) or WHITE(1)    

&emsp;<code class="code_accent">drawVerticalBargraph(x, y, w, h, color, percent)</code> : Draw a graph on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Width of the graph    
&emsp;&emsp;&emsp;`h` : Full height of the graph    
&emsp;&emsp;&emsp;`color` : The color of the graph. BLACK(0) or WHITE(1)    
&emsp;&emsp;&emsp;`percent` : The percentage of a graph. The direction of graph is always up-side    

&emsp;<code class="code_accent">drawHorizontalBargraph(x, y, w, h, color, percent)</code> : Draw a graph on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Full width of the graph    
&emsp;&emsp;&emsp;`h` : Height of the graph    
&emsp;&emsp;&emsp;`color` : The color of the graph. BLACK(0) or WHITE(1)    
&emsp;&emsp;&emsp;`percent` : The percentage of a graph. The direction of graph is always right-side    

&emsp;<code class="code_accent">drawRoundRect(x, y, w, h, r, color)</code> : Draw a rounded rectangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Width of the rounded rectangle    
&emsp;&emsp;&emsp;`h` : Height of the rounded rectangle    
&emsp;&emsp;&emsp;`r` : Curvature of edge of the rounded rectangle    
&emsp;&emsp;&emsp;`color` : The color of a graph. BLACK(0) or WHITE(1)   

&emsp;<code class="code_accent">fillRoundRect(x, y, w, h, r, color)</code> : Draw a rounded and filled rectangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Width of the rounded rectangle    
&emsp;&emsp;&emsp;`h` : Height of the rounded rectangle    
&emsp;&emsp;&emsp;`r` : Curvature of edge of the rounded rectangle    
&emsp;&emsp;&emsp;`color` : The color of a graph BLACK(0) or WHITE(1)   

&emsp;<code class="code_accent">drawTriangle(x0, y0, x1, y1, x2, y2, color)</code> : Draw a triangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x0` : The first point of x-axis    
&emsp;&emsp;&emsp;`y0` : The first point of y-axis    
&emsp;&emsp;&emsp;`x1` : The second point of x-axis    
&emsp;&emsp;&emsp;`y1` : The second point of y-axis    
&emsp;&emsp;&emsp;`x2` : The third point of x-axis    
&emsp;&emsp;&emsp;`y2` : The third point of y-axis    
&emsp;&emsp;&emsp;`color` : The color of a triangle. BLACK(0) or WHITE(1)    

&emsp;<code class="code_accent">fillTriangle(x0, y0, x1, y1, x2, y2, color)</code> : Draw a filled triangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x0` : The first point of x-axis    
&emsp;&emsp;&emsp;`y0` : The first point of y-axis    
&emsp;&emsp;&emsp;`x1` : The second point of x-axis    
&emsp;&emsp;&emsp;`y1` : The second point of y-axis    
&emsp;&emsp;&emsp;`x2` : The third point of x-axis    
&emsp;&emsp;&emsp;`y2` : The third point of y-axis    
&emsp;&emsp;&emsp;`color` : The color of a triangle. BLACK(0) or WHITE(1)
   
&emsp;<code class="code_accent">drawChar(x, y, c, color, bg, size)</code> : Draw a character on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of x-axis    
&emsp;&emsp;&emsp;`c` : A character to be drawn    
&emsp;&emsp;&emsp;`color` : The color of a character. BLACK(0) or WHITE(1)    
&emsp;&emsp;&emsp;`bg` : The background of a character. Background size is 6 * 8 * textsize    
&emsp;&emsp;&emsp;`size` : Pixel size of charactor strock. Default is 1   

&emsp;<code class="code_accent">drawBitmap(x, y, bitmap, w, h, color)</code> : Draw a bitmap data on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`bitmap` : A two dimensional array which consist of 0 and 1, 0 is black and 1 is white    
&emsp;&emsp;&emsp;`w` : Width of bitmap data    
&emsp;&emsp;&emsp;`h` : Height of bitmap data    
&emsp;&emsp;&emsp;`color` : The color of a character. BLACK(0) or WHITE(1)   

&emsp;<code class="code_accent">setCursor(x, y)</code> : Set the cursor on OLED, This value is used in write()    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : x-axis point of cursor    
&emsp;&emsp;&emsp;`y` : y-axis point of cursor 

&emsp;<code class="code_accent">setTextSize(s)</code> : Set text size, This value is used in write()    
&emsp;&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`s` : Pixel size of charactor strock. Default is 1 

&emsp;<code class="code_accent">setTextColor(c)</code> : Set text color, This value is used in write()    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`c` : Text color value. BLACK(0) or WHITE(1)   

&emsp;<code class="code_accent">setTextColorWithBg(c, b)</code> : Set text color and background color, This value is used in write()    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`c` : Text color value. BLACK(0) or WHITE(1)    
&emsp;&emsp;&emsp;`b` : Background color value. BLACK(0) or WHITE(1) 

&emsp;<code class="code_accent">drawPixel(x, y, color)</code> : Draw a dot on OLED    
&emsp;&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : The point of a dot    
&emsp;&emsp;&emsp;`y` : The point of a dot    
&emsp;&emsp;&emsp;`color` : The color of a dot    

&emsp;<code class="code_accent">setBrightness(Brightness)</code> : Set brightness of OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`Brightness` : Brightness value to be set   

&emsp;<code class="code_accent">invertDisplay(i)</code> : Change display mode    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`i` : If i is `True`, dispaly mode is Inverse mode but if i is False, display mode is Normal mode. In Inverse mode, 0 is white and 1 is black    

&emsp;<code class="code_accent">istartscrollright(start, stop)</code> <br>&emsp;: Scroll the screen in the row-right direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`start` : Start point of scrolling    
&emsp;&emsp;&emsp;`stop` : Stop point of scrolling   

&emsp;<code class="code_accent">startscrollleft(start, stop)</code> <br>&emsp;: Scroll the screen in the row-left direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`start` : Start point of scrolling    
&emsp;&emsp;&emsp;`stop` : Stop point of scrolling  

&emsp;<code class="code_accent">startscrolldiagright(start, stop)</code> <br>&emsp;: Scroll the screen in the column-right direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`start` : Start point of scrolling    
&emsp;&emsp;&emsp;`stop` : Stop point of scrolling  

&emsp;<code class="code_accent">startscrolldiagleft(start, stop)</code> <br>&emsp;: Scroll the screen in the column-left direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`start` : Start point of scrolling    
&emsp;&emsp;&emsp;`stop` : Stop point of scrolling  

&emsp;<code class="code_accent">stopscroll()</code> : Stop scrolling the screen    

&emsp;<code class="code_accent">write(c)</code> : Write the character at location of cursor on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`c` : The character to be written   

&emsp;<code class="code_accent">setAutomode(automode)</code> : set automode    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`automode` : `True` or `False`    

&emsp;Refer to [I2c Class](pop.md#class-i2c) for inherited and used methods.

<h5>&emsp;Example</h5>

<details>
	<summary>simple example 1</summary>

~~~python
	from pop import Oled

	display = Oled()

	display.print("Hello World")
~~~

</details>	

<details>
	<summary>simple example 2</summary>

~~~python
	from pop import Oled
	import time 

	display = Oled(automode=False)

	display.drawCircle(60,30,10,display.WHITE)
	display.display()
	time.sleep(1)
	display.fillCircle(60,30,10,display.WHITE)
	display.display()
~~~

</details>	

<hr/>

## <span class="title">Class</span> <span class="title_accent">**Gesture**</span>    
<blockquote class="desc">Apds9960 Controlled via I2C Interface</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Gesture(addr=APDS9960_ADDR)</code> : Gesture object inheriting from [I2C Class](pop.md#class-i2c) (I2c Slave Address -> 0x39)    
	
<h5>&emsp;Methods</h5>   

&emsp;<code class="code_accent">isAvailable()</code> : Return whether Gesture sensor is available(1), Wait until Gesture is detected    
&emsp;<code class="code_accent">read()</code> : Return number as Gesture status  
&emsp;&emsp;**Return**    
&emsp;&emsp;&emsp;`0` : "None" , `1` : "Left", `2` : "Right", `3` : "Up", `4` : "Down", `5`: "Near", `6` : "Far"    

&emsp;<code class="code_accent">readStr()</code> : Return String as Gesture status    
&emsp;&emsp;**Return**  
&emsp;&emsp;&emsp;"None" , "Left", "Right", "Up", "Down", "Near", "Far"    
		
&emsp;Refer to [I2c Class](pop.md#class-i2c) for inherited and used methods.		
		
<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Gesture
	import time 
	gesture = Gesture()

	for i in range(0,1000):
	    if gesture.isAvailable():   
		motion = gesture.readStr() 
		print(motion) 
	    time.sleep(0.1)
~~~

</details>

<h5>&emsp;Inner Class</h5>  

&emsp;**Light**    
&emsp;&emsp;**Initialization**<br>
&emsp;&emsp;`Light()` : Light object  <br><br>
&emsp;&emsp;**Methods**<br>
&emsp;&emsp;`read()` : Return light value    

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Gesture
	import time 
	
	gesture = Gesture()
	light = Gesture.Light()

	for i in range(0,10):
	    val = light.read()
	    print(val)
	    time.sleep(0.2)
~~~

</details>
<br>

&emsp;**Color**    
&emsp;&emsp;**Initialization**<br>
&emsp;&emsp;`Color()` : Color object  <br><br>
&emsp;&emsp;**Methods**<br>
&emsp;&emsp;`readRed()` : Return Red value    
&emsp;&emsp;`readGreen()` : Return Green value    
&emsp;&emsp;`readBlue()` : Return Blue value

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Gesture
	import time 
	
	gesture = Gesture()
	C = Gesture.Color()

	for i in range(0,10):
	    print(C.readRed(), C.readGreen(), C.readBlue())
	    time.sleep(0.2)
~~~

</details>
<br>

&emsp;**Proximity**  
&emsp;&emsp;**Initialization**<br>
&emsp;&emsp;`Proximity()` : Proximity object  <br><br>
&emsp;&emsp;**Methods**<br>
&emsp;&emsp;`read()` : Return Proximity value    

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Gesture
	import time 
	
	gesture = Gesture()
	p = Gesture.Proximity()

	for i in range(0,10):
	    val = p.read()
	    print(val)
	    time.sleep(0.2)
~~~

</details>
	
<hr/>

## <span class="title">Class</span> <span class="title_accent">**PixelDisplay**</span>    
<blockquote class="desc">Pixel Display is controlled by Hardware PWM</blockquote>  
  
<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">PixelDisplay(width=8, height=8, gpio=-1, type=GRB, dma=10, automode=True, debug=False)</code> <br>&emsp;: PixelDisplay object    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`width` : Number of pixel width    
&emsp;&emsp;&emsp;`height` : Number of pixel height    
&emsp;&emsp;&emsp;`automode` : Automode setting. `True` or `False`    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">display()</code> : Send command from buffer when Automode is `False`, this is not executed and the command is automaically sent when Automode is `True`     
&emsp;<code class="code_accent">getRGBType()</code>: Get the RGB Type    
&emsp;<code class="code_accent">RGBtoHEX(color_arr)</code> : Convert the RGB list data to HEX  
&emsp;<code class="code_accent">clear()</code> : Clear Pixel Display  
&emsp;<code class="code_accent">rainbow()</code> : Display rainbow color on Pixel Display  
&emsp;<code class="code_accent">fill(color_arr)</code> : Fill Pixel Display with one color    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`color_arr` : A color to be filled. Type is list of [R, G, B]  
   
&emsp;<code class="code_accent">setColor(x, y, color_arr)</code> : Set Pixel Display color_arr on x,y    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : x-axis    
&emsp;&emsp;&emsp;`y` : y-axis    
&emsp;&emsp;&emsp;`color_arr` : A color to be set. Type is list of [R, G, B] or HEX (0xRRGGBB)    

&emsp;<code class="code_accent">getColor(x, y)</code> : Return color on x,y as INT type    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : x-axis    
&emsp;&emsp;&emsp;`y` : y-axis 

&emsp;<code class="code_accent">setAutomode(automode)</code> : Set automode. Default `True`. If `False` set, display() should be used    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`automode` : `True` or `False`    
   
&emsp;<code class="code_accent">setBrightness(brightness)</code> : Set Brightness    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`brightness` : Brightness (0~255)    
  
&emsp;<code class="code_accent">setColorInvert(invert)</code> : Invert the color. Default `False`    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`invert`  
&emsp;&emsp;&emsp;&emsp;`True` : input (255,0,0) -> (0,255,255)    
&emsp;&emsp;&emsp;&emsp;`False` : input (255,0,0) -> (255,0,0)    

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import PixelDisplay
	import time 
	
	display = PixelDisplay()

	display.setColor(0, 0, [5, 0, 0])
	time.sleep(1)
	display.fill([5, 0, 0])
	time.sleep(1)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**TextLcd**</span>    
<blockquote class="desc">TextLcd</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">TextLcd()</code> <br>&emsp;: TextLcd object 

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">clear()</code> : Clear Textlcd. It makes Textlcd empty.  
&emsp;<code class="code_accent">returnHome()</code> : Move cursor to (0, 0).  
&emsp;<code class="code_accent">displayOn()</code> : Turn on the display. The display is turned on at first.  
&emsp;<code class="code_accent">displayOff()</code> : Turn off the display. The display is not working.  
&emsp;<code class="code_accent">displayShiftR()</code> : Shift the display to right.  
&emsp;<code class="code_accent">displayShiftL()</code> : Shift the display to left.  
&emsp;<code class="code_accent">cursorShiftR()</code> : Shift cursor to right.  
&emsp;<code class="code_accent">cursorShiftL()</code> : Shift cursor to left.  
&emsp;<code class="code_accent">entryModeSet()</code> : ...  
&emsp;<code class="code_accent">cursorOff()</code> : Turn off cursor.  
&emsp;<code class="code_accent">cursorOn(blinking)</code> : Turn on cursor.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`blinking` : If True, cursor is blinking. Else False, cursor is always on.    

&emsp;<code class="code_accent">command(command)</code> : Send the command to TextLcd<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`command` : Command that to be sent to Textlcd.    

&emsp;<code class="code_accent">setCursor(x, y)</code> : Move cursor to (x, y). Unit is 1 block.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : x axis of cursor. (0 ~ Width)    
&emsp;&emsp;&emsp;`y` : y axis of cursor. (0 ~ Height)    

&emsp;<code class="code_accent">data(data)</code> : Print 1byte data on the TextLcd. Data is written on the Textlcd.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`data` : Data to be sent to the Textlcd.    

&emsp;<code class="code_accent">print(string)</code> : Print string data on the Textlcd.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`string` : String data to be sent to the Textlcd.    

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Textlcd 
	import time

	lcd = Textlcd()

	str = "Hello Pop Library"
	time.sleep(1)
	lcd.print(str)
	time.sleep(1)
	lcd.clear() 
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**Mpu6050**</span>    
<blockquote class="desc">Mpu6050</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">Mpu6050(addr)</code> <br>&emsp;: Mpu6050 object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`addr` : I2c slave address. default 0x68    

&emsp;**Variables**    
&emsp;<code class="code_accent">accelRawX</code> : Raw accel data of X axis.    
&emsp;<code class="code_accent">accelRawY</code> : Raw accel data of Y axis.    
&emsp;<code class="code_accent">accelRawZ</code> : Raw accel data of Z axis.    
&emsp;<code class="code_accent">accelScaledX</code> : Scaled accel data of X axis.    
&emsp;<code class="code_accent">accelScaledY</code> : Scaled accel data of Y axis.    
&emsp;<code class="code_accent">accelScaledZ</code> : Scaled accel data of Z axis.    
&emsp;<code class="code_accent">gyroRawX</code> : Raw gyro data of X axis.    
&emsp;<code class="code_accent">gyroRawY</code> : Raw gyro data of Y axis.    
&emsp;<code class="code_accent">gyroRawZ</code> : Raw gyro data of Z axis.    
&emsp;<code class="code_accent">gyroScaledX</code> : Scaled gyro data of X axis.    
&emsp;<code class="code_accent">gyroScaledY</code> : Scaled gyro data of Y axis.    
&emsp;<code class="code_accent">gyroScaledZ</code> : Scaled gyro data of Z axis.    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">readAccel()</code> : Update accel variables.  
&emsp;<code class="code_accent">readGyro()</code> : Update gyro variables.  

<details>
	<summary>simple example</summary>

~~~python
	from pop import Mpu6050
	import time
	mpu6050 = Mpu6050()

	for i in range(30):
		gyro = mpu6050.readGyro()
		accel = mpu6050.readAccel()

		print("Gyro - X:%d, Y:%d, Z:%d"%(gyro[0], gyro[1], gyro[2]))
		print("Accel - X:%d, Y:%d, Z:%d"%(accel[0], accel[1], accel[2]))
	    time.sleep(0.5)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**Touch**</span>    
<blockquote class="desc">Touch</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">Touch(addr)</code> <br>&emsp;: Touch object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`addr` : I2c slave address. default 0x5a    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">reset()</code> : Software reset for Touch Sensor.   

&emsp;<code class="code_accent">readAll()</code> : Read all channels included in Touch at once. 

&emsp;<code class="code_accent">readChannel(ch)</code> : Read one channel of Touch.  
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`ch` : channel value. (0 ~ 11)    

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Touch 
	import time 

	touch = Touch()

	for i in range(100):
	    ret = touch.readAll()
	    for i in range(12):
		if ret[i] == True:
		    print('ch %d pushed!\n'%i)

		time.sleep(0.05)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**Dust**</span>    
<blockquote class="desc">Dust</blockquote> 

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">Dust(addr)</code> <br>&emsp;: Dust object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`addr` : I2c slave address. default 0x28

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">reset()</code> : Software reset for Dust Sensor.     

&emsp;<code class="code_accent">read()</code> : Read all sensor data that can be read by the dust sensor.  

&emsp;**Variables**    
&emsp;<code class="code_accent">pm_1p0_grimm</code> : Fine dust data read pm1.0 by grimm.    
&emsp;<code class="code_accent">pm_2p5_grimm</code> : Fine dust data read pm2.5 by grimm.   
&emsp;<code class="code_accent">pm_10_grimm</code> : Fine dust data read pm10 by grimm.   
&emsp;<code class="code_accent">pm_1p0_tsi</code> : Fine dust data read pm1.0 by tsi.    
&emsp;<code class="code_accent">pm_2p5_tsi</code> : Fine dust data read pm2.5 by tsi.   
&emsp;<code class="code_accent">pm_10_tsi</code> : Fine dust data read pm10 by tsi.   

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import Dust
	import time 

	dust = Dust()
	while True:
	    dust.read()
	    print("PM 1.0 GRIM  : %u ㎍/㎥"%dust.pm_1p0_grimm)
	    print("PM 2.5 GRIM  : %u ㎍/㎥"%dust.pm_2p5_grimm)
	    print("PM 10  GRIM  : %u ㎍/㎥"%dust.pm_10_grimm)
	    time.sleep(0.5)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**PwmController**</span>    
<blockquote class="desc">PwmController</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">PwmController(addr)</code> <br>&emsp;: PwmController object <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`addr` : I2c slave address. default 0x5e   

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">init()</code> : initialize PwmController.<br>

&emsp;<code class="code_accent">setChannel(channel)</code> : Set the PWM Channel for control<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : channel value. (0 ~ 15)    

&emsp;<code class="code_accent">setDuty(percent)</code> : Specifies the duty cycle of pwm.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`percent` : Specifies the duty ratio as a percentage. (0 ~ 100)    

&emsp;<code class="code_accent">setFreq(freq)</code> : Specifies the pwm frequency.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`freq` : Frequency. ex) 50 -> 50Hz     

&emsp;<code class="code_accent">setInvertPulse()</code> : Invert the output PWM signal.  

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import PwmController
	import time

	pwm = PwmController()
	pwm.init()
	pwm.setChannel(0)
	pwm.setFreq(50)
	for i in range(10):
	    pwm.setDuty(i*10)
	    time.sleep(0.5)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**RGBLed**</span>    
<blockquote class="desc">RGBLed</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">RGBLed(*ns)</code> <br>&emsp;: RGBLed object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`*ns` : ...    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">on(color)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`color` : ...    

&emsp;<code class="code_accent">off(color)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`color` : ...    

&emsp;<code class="code_accent">set(*colors)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`*colors` : ...    

---

## <span class="title">Class</span> <span class="title_accent">**ShiftRegister**</span>    
<blockquote class="desc">ShiftRegister</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">ShiftRegister([n0,n1,n2])</code> <br>&emsp;: ShiftRegister object <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`[n0,n1,n2]` : List of GPIO numbers connected to Shift Register. n0-Data / n1-Clock / n2-Latch    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">shiftout(val)</code> : Write data to Shift Rgister<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : 8-bit data to be transferred to Shift Register    

&emsp;<code class="code_accent">fnd(val)</code> : Write data to Shift Rgister for control FND<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : number to be show on FND. range from '0' to '9'    

<h5>&emsp;Example</h5>

<details>
	<summary>simple example</summary>

~~~python
	from pop import ShiftRegister
	import time 

	gpio = [16,5,6]
	s = ShiftRegister(gpio)

	s.shiftout(0xff)
	time.sleep(1)
	s.shiftout(0x00)
	time.sleep(1)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**StepMotor**</span>    
<blockquote class="desc">StepMotor</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">StepMotor(*ns)</code> <br>&emsp;: StepMotor object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`*ns` : ...    

<h5>&emsp;Definitions</h5>

&emsp;<code class="code_accent">SPEED_1</code> : ...    
&emsp;<code class="code_accent">SPEED_2</code> : ...    
&emsp;<code class="code_accent">SPEED_3</code> : ...    
&emsp;<code class="code_accent">ONE_PHASE_FULLSTEP</code> : ...    
&emsp;<code class="code_accent">TWO_PHASE_FULLSTEP</code> : ...    
&emsp;<code class="code_accent">HALFSTEP</code> : ...    
&emsp;<code class="code_accent">SPEED_SEQ</code> : ...    
&emsp;<code class="code_accent">ONE_PHASE_FULLSTEP_SEQ</code> : ...    
&emsp;<code class="code_accent">TWO_PHASE_FULLSTEP_SEQ</code> : ...    
&emsp;<code class="code_accent">HALFSTEP_SEQ</code> : ...    


<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">forward()</code> : ...  
&emsp;<code class="code_accent">backward()</code> : ...  
&emsp;<code class="code_accent">stop()</code> : ...  
&emsp;<code class="code_accent">setMode(mode)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`mode` : ...    

---

## <span class="title">Class</span> <span class="title_accent">**Audio**</span>    
<blockquote class="desc">Audio</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">Audio(blocking=True, cont=False)</code> <br>&emsp;: Audio object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`blocking` : If Ture, working in blocking mode. Else non-blocking mode. Default is True.    
&emsp;&emsp;&emsp;`cont` : If True, repeat playing file. Else play one time. This is working in only non-blocking mode. Default is False.    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">stop()</code> : Stop playing if in non-blocking mode. This method is used in subclass like 'AudioPlay'.    
&emsp;<code class="code_accent">close()</code> : Clear audio resources explicitly. This method is used in subclass like 'AudioPlay'.    

---

## <span class="title">Class</span> <span class="title_accent">**AudioPlay**</span>    
<blockquote class="desc">AudioPlay</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">AudioPlay(file, blocking=True, cont=False)</code> <br>&emsp;: AudioPlay object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`file` : Name of WAV file to play.    
&emsp;&emsp;&emsp;`blocking` : If Ture, working in blocking mode. Else non-blocking mode. Default is True.    
&emsp;&emsp;&emsp;`cont` : If True, repeat playing file. Else play one time. This is working in only non-blocking mode. Default is False.    


<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">run()</code> : Start playing the file.    
&emsp;<code class="code_accent">isPlay()</code> : Return playing status. True means playing now, False means stopped.    

<details>
	<summary>simple example</summary>

~~~python
	from pop import AudioPlay
	import time 

	with AudioPlay("/usr/share/sounds/alsa/Side_Left.wav", False, True) as play:   
	    play.run()
	    print("Start Play...")
	    for _ in range(12):  
	        time.sleep(1)

	    play.stop()
	    print("Stop play...")
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**AudioPlayList**</span>    
<blockquote class="desc">AudioPlayList</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">AudioPlayList(files, blocking=True, cont=False)</code> <br>&emsp;: AudioPlayList object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`files` : Names of WAV file to play. (list type)    
&emsp;&emsp;&emsp;`blocking` : If Ture, working in blocking mode. Else non-blocking mode. Default is True.    
&emsp;&emsp;&emsp;`cont` : If True, repeat playing file. Else play one time. This is working in only non-blocking mode. Default is False.    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">isPlay()</code> : Return playing status. True means playing now, False means stopped.    
&emsp;<code class="code_accent">run(pos=0)</code> : Start playing the file.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`pos` : Index of WAV file in playing list. Default is 0.    

<details>
	<summary>simple example</summary>

~~~python
	from pop import AudioPlayList
	import time 

	playlist = ["/usr/share/sounds/alsa/Front_Center.wav", "/usr/share/sounds/alsa/Side_Left.wav", "/usr/share/sounds/alsa/Side_Right.wav"]

	with AudioPlayList(playlist) as play:
	    print("Start PlayList...") 
	    play.run()
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**AudioRecord**</span>    
<blockquote class="desc">AudioRecord</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">AudioRecord(file, sFormat=8, sChannel=1, sRate=48000, sFramePerBuffer=1024)</code> <br>&emsp;: AudioRecord object. Only non-blocking mode is supported.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`file` : Name of WAV file to save.    
&emsp;&emsp;&emsp;`sFormat` : Sampling type. 8 is paInt16, 2 is paInt32, 1 is pa Float32. Default is 8. (int type)    
&emsp;&emsp;&emsp;`sChannel` : Number of channel. Default is 1.    
&emsp;&emsp;&emsp;`sRate` : Sampling rate(Hz). Default is 48000.    
&emsp;&emsp;&emsp;`sFramePerBuffer` : Frame per buffer. Default 1024.    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">run()</code> : Start recording.   

<details>
	<summary>simple example</summary>

~~~python
	from pop import AudioRecord
	import time 

	with AudioRecord("my_record.wav") as record:
	    record.run()
	    print("Start Recording...") 
	
	    for _ in range(5):
	        time.sleep(1)
	
	    record.stop()
	    print("Stop Recording...") 
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**Tone**</span>    
<blockquote class="desc">Tone</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">Tone(tempo=100, volume=.5, rate=48000, channels=1)</code> <br>&emsp;: Tone object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`tempo` : Tempo of melody. Default is 100.    
&emsp;&emsp;&emsp;`volume` : Volume of meldy. Default is 0.5. (0 ~ 1)    
&emsp;&emsp;&emsp;`rate` : Sampling rate(Hz). Default is 48000.    
&emsp;&emsp;&emsp;`channels` : Number of channels. Default is 1.    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">close()</code> : Clear audio resources explicitly.   
&emsp;<code class="code_accent">setTempo(tempo)</code> : Set the tempo of melody.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`tempo` : Value of tempo.    

&emsp;<code class="code_accent">rest(duration)</code> : Intervals of silence.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`duration` : Duration of silence. (4, 2, 1, 1/2, 1/4, ...)    

&emsp;<code class="code_accent">play(octave, pitch, duration)</code> : Play the melody.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`octave` : Octave of melody. (1 ~ 8)    
&emsp;&emsp;&emsp;`pitch` : Pitch of melody. ("DO", "DO#", "RE", "RE#", "MI", "FA", "SOL", "SOL#", "RA", "RA#", "SI")    
&emsp;&emsp;&emsp;`duration` : Duration of melody.    

<details>
	<summary>simple example1</summary>

~~~python
	from pop import Tone
	import time 

	with Tone() as tone:
		for n in [1, 3, 5, 7, 8, 10, 12]:
			tone.play(3, n, 4)
~~~

</details>

<details>
	<summary>simple example2</summary>

~~~python
	from pop import Tone

	schoolBell1 = ((4, "SOL", 1/4), (4, "SOL", 1/4), (4, "RA", 1/4), (4, "RA", 1/4), (4, "SOL", 1/4), (4, "SOL", 1/4), (4, "MI", 1/2), (4, "SOL", 1/4), (4, "SOL", 1/4), (4, "MI", 1/4), (4, "MI", 1/4), (4, "RE", 1/2 + 1/4))
	schoolBell2 = (*schoolBell1[:7], (4, "SOL", 1/4), (4, "MI", 1/4), (4, "RE", 1/4), (4, "MI", 1/4), (4, "DO", 1/2 + 1/4))

	with Tone() as tone:
	    tone.setTempo(200)

	    for n in schoolBell1:
	        tone.play(*n)
	    tone.rest(1/4)

	    for n in schoolBell2:
	        tone.play(*n)
	    tone.rest(1/4)
~~~

</details>

---

## <span class="title">Class</span> <span class="title_accent">**SoundMeter**</span>    
<blockquote class="desc">SoundMeter</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">SoundMeter(sampleFormat=pyaudio.paInt16, channelNums=1, framesPerBuffer=1024, sampleRate=48000)</code> <br>&emsp;: SoundMeter object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`sampleFormat` : Sampling type. Default is pyaudio.paInt16.    
&emsp;&emsp;&emsp;`channelNums` : Number of channel. Default is 1.    
&emsp;&emsp;&emsp;`framesPerBuffer` : Frame per buffer. Default 1024.    
&emsp;&emsp;&emsp;`sampleRate` : Sampling rate(Hz). Default is 48000.    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">stop()</code> : Stop measurement and clear audio resources explicitly.    
&emsp;<code class="code_accent">setCallback(func, *args)</code> : Set user callback method and start measurement.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`func` : User callback method.    
&emsp;&emsp;&emsp;`*args` : Argument to be conveyed to user callback method. (skippable)    

<details>
	<summary>simple example</summary>

~~~python
	import time
	from pop import SoundMeter
	
	sm = SoundMeter()
	
	def onSoundMeter(rms, inData):
	    if(rms>600):
	        print(rms)
	
	sm.setCallback(onSoundMeter)
	
	input("input something")
	
	sm.stop()
~~~

</details>
