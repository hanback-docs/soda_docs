<h1> Pop.CAN </h1>
Pop.CAN is easy and fast educational Library for CAN Protocol. It supports can communication and provides motor control and sensor monitoring using CAN communication.
<br>

<!-- # Class & Method Description-->
<hr/>

## <span class="title">Class</span> <span class="title_accent">**Can**</span>    

<blockquote class="desc">Class used whe using CAN interface.</blockquote>

The code to import the Can Class :

``` python
from pop.CAN import Can
```

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">Can()</code> : Can Object<br>

<h5>&emsp;Methods</h5>

&emsp;<code class="code_accent">send(msg_id, buf, is_extended=False)</code> : Sends a message via can communication.<br>   
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`msg_id` : Number of Message ID. <br>
&emsp;&emsp;&emsp;`buf` : It is a message to be transmitted through can communication.  <br>   
&emsp;&emsp;&emsp;`is_extended=False` : Check if the set ID is extended id.  <br>   

&emsp;<code class="code_accent">recv(timeOut=2)</code> : Recv a message via can communication.   <br>   
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`timeOut=2` : Time to wai for message.   <br>   

&emsp;<code class="code_accent">setFilter(can_id, mask)</code> : Set the id filter for incoming messages.   <br>   
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`can_id` : can message id. <br>   
&emsp;&emsp;&emsp;`mask` : can message id. <br>   

---

## <span class="title">Class</span> <span class="title_accent">**OmniWheel**</span>    

<blockquote class="desc">This class controls OmniWheel using Can communication.</blockquote>

The code to import the OmniWheel Class :

``` python
from pop.CAN import OmniWheel
```

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">OmniWheel()</code> : OmniWheel Object<br>

<h5>&emsp;Variables</h5>  
  
&emsp;<code class="code_accent">ULTRASONIC</code> : Constant for reading ultrasonic sensor data.    
&emsp;<code class="code_accent">PSD</code> : Constant for reading PSD sensor data.     
&emsp;<code class="code_accent">ALARM</code> : Constant for reading Obstacle Detect Alarm.     
&emsp;<code class="code_accent">SENSOR_ALL</code> : Constant for reading All sensor data.     

<h5>&emsp;Methods</h5>

&emsp;<code class="code_accent">forward(data)</code> : Method used to move the wheel forward. <br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`data` : List including motor speed, input motor 1,2,3 in sequence, integer between 0 and 100, and if 100, motor operates at 100% speed </br>

&emsp;<code class="code_accent">backward(data)</code> : Method used to move the wheel backward. <br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`data` : List including motor speed, input motor 1,2,3 in sequence, integer between 0 and 100, and if 100, motor operates at 100% speed </br>

&emsp;<code class="code_accent">setObstacleRange(ultra_distance, psd_distance)</code> : Obstacle detection distance setting <br>
&emsp;&emsp; When the two values are the same -> No notification, only detection, motor stops when detected. <br>
&emsp;&emsp; When the two values are not the same -> Only the notification message is delivered between the maximum and minimum values. <br>
&emsp;&emsp; When the two values are not the same -> Motor stop and notification message when it is less than the minimum value. <br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`ultra_distance` : Ultrasonic sensor detection distance. </br>
&emsp;&emsp;&emsp;`psd_distance` : PSD sensor detection distance </br>

&emsp;<code class="code_accent">stop()</code> : Method used to Motor stop 

&emsp;<code class="code_accent">allSensorEnable()</code> : Method used to receive all sensor data from the Omni Wheel </br>

&emsp;<code class="code_accent">ultraEnable(enable=[1,1,1,1,1,1])</code> : Ultrasonic sensor reception status setting. <br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`enable` : List data with ultrasonic sensor activation information, 1 is activated 0 is disabled. </br>

&emsp;<code class="code_accent">psdEnable(enable=[1,1,1])</code> : PSD sensor reception status setting. <br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`enable` : List data with PSD sensor activation information, 1 is activated 0 is disabled </br>

&emsp;<code class="code_accent">getEnable()</code> : Return sensor reception status. </br>

&emsp;<code class="code_accent">sensorDisable()</code> : Disable sensor reception. </br>

&emsp;<code class="code_accent">read(msgType)</code> : Reading messages received on the omni wheel via CAN communication. <br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`msgType` : There are 4 types of data to be passed to msgType. </br>
&emsp;&emsp;&emsp;&emsp;`SENSORALL` : Constant for reading All sensor data. </br>
&emsp;&emsp;&emsp;&emsp;`ULTRASONIC` : Constant for reading ultrasonic sensor data. </br> 
&emsp;&emsp;&emsp;&emsp;`PSD` : Constant for reading PSD sensor data. </br>
&emsp;&emsp;&emsp;&emsp;`ALARM` : Constant for reading Obstacle Detect Alarm. </br>

&emsp;<code class="code_accent">setCallback(func,param=None)</code> : Set up callback function for Obstacle Alarm <br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`func` : Function to use when calling Callback </br>
&emsp;&emsp;&emsp;`param` : Parameters passed to the Callback function , Default None </br>


---

