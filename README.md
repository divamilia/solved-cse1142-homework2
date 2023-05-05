Download Link: https://assignmentchef.com/product/solved-cse1142-homework2
<br>
In this homework, you are expected to implement a simple smart home system. In a smart home system, there might be several intelligent objects such as smart light, smart plug, smart camera, etc. These devices can be connected to the internet and they can be controlled by households remotely.  Nowadays we can use such devices to improve smart life experience thanks to internet technology and smartphones.

Our simple smart home system has the following OOP class hierarchy:










Please find the class details in below.

<ol>

 <li>Implement an abstract <strong><em>SmartObject</em></strong> class with the following UML diagram.</li>

</ol>

<table width="330">

 <tbody>

  <tr>

   <td width="47"> </td>

   <td width="282"><em>SmartObject </em></td>

  </tr>

  <tr>

   <td width="47">––––</td>

   <td width="282">alias:  String macId: String IP: StringconnectionStatus: boolean</td>

  </tr>

  <tr>

   <td width="47">++++++++</td>

   <td width="282">SmartObject()connect(IP: String):boolean disconnect():boolean SmartObjectToString(): void controlConnection(): boolean<em>testObject(): boolean  shutDownObject (): boolean </em>getter/setter methods for data fields</td>

  </tr>

 </tbody>

</table>







<ul>

 <li><strong><em>SmartObject</em></strong> is an abstract superclass of <strong>SmartLight, SmartPlug</strong> and <strong>SmartCamera</strong></li>

 <li>The <strong>alias</strong> data field represents the name of a smart device. Each device has a unique <strong>macId</strong> to connect to the internet. The <strong>IP</strong> (Internet Protocol) data field is a networking protocol to communicate with other devices. The <strong>connectionStatus</strong> data field represents whether the smart object is connected to the internet or not.</li>

 <li>It has a concrete method <strong>connect</strong> which connects the smart object with the given <strong>IP</strong> It sets the <strong>IP</strong> and <strong>connectionStatus</strong> properties of the smart object and prints a message such as:</li>

</ul>

“SmartCam1 connection established”

<ul>

 <li>It has a concrete method <strong>disconnect</strong> which disconnects the smart object. It sets <strong>IP</strong> and <strong>connectionStatus</strong> properties with appropriate values.</li>

 <li>It has a concrete method of <strong>SmartObjectToString </strong>which prints the details about a smart object as the following:</li>

</ul>

This is SmartCamera device SmartCam1

MacId : AA:BB:CC

IP : 10.0.0.100




<ul>

 <li>It has a concrete method of <strong>controlConnection</strong> which controls the connection of the smart object. If the device is not connected it prints the following message and return false.</li>

</ul>

This device is not connected. SmartCamera -&gt; SmartCam1

<ul>

 <li>It has two abstract methods, <strong><em>testObject</em></strong> and <strong><em>shutdownObject</em>,</strong> with the given signatures above.</li>

 <li>There are setter/getter methods.</li>

</ul>




<ol start="2">

 <li>Implement a <strong><em>LocationControl</em></strong> interface with the following UML diagram.</li>

</ol>




<table width="246">

 <tbody>

  <tr>

   <td width="47"> </td>

   <td width="198">&lt;&lt;interface&gt;&gt;<em>LocationControl </em></td>

  </tr>

  <tr>

   <td width="47"> </td>

   <td width="198"> </td>

  </tr>

  <tr>

   <td width="47">++</td>

   <td width="198"><em>onLeave(): void onCome(): void</em></td>

  </tr>

 </tbody>

</table>




<strong><em>LocationControl</em></strong> interface represents the property of controlling a smart device based on the location of a household.

<ul>

 <li>For example, a household may choose to turn on a device automatically before coming (with <strong>onCome()</strong> method) to the house or turn off a device automatically after leaving the house (with <strong>onLeave()</strong> method).</li>

 <li>The <strong>onLeave()</strong> and <strong>onCome()</strong> abstract methods should be implemented by the classes that implements <strong><em>LocationControl</em></strong></li>

</ul>




<ol start="3">

 <li>Implement a <strong><em>Programmable</em></strong> interface with the following UML diagram.</li>

</ol>




<table width="252">

 <tbody>

  <tr>

   <td width="47"> </td>

   <td width="205">&lt;&lt;interface&gt;&gt;<em>Programmable</em></td>

  </tr>

  <tr>

   <td width="47"> </td>

   <td width="205"> </td>

  </tr>

  <tr>

   <td width="47">+++</td>

   <td width="205"><em>setTimer(seconds: int): void cancelTimer(): void runProgram(): void</em></td>

  </tr>

 </tbody>

</table>




<ul>

 <li><strong><em>Programmable</em></strong> interface represents the property of programming a smart device.</li>

 <li>A household may choose to turn on a device automatically based on setting a timer (with <strong><em>setTimer</em></strong> method). The device should be turned on or turned off after given amount of <strong>seconds</strong></li>

 <li>A household may choose to cancel the timer of a smart device (with <strong><em>cancelTimer</em></strong> method).</li>

 <li>The<strong> <em>runProgram</em></strong> method should check the program time of a smart device when it’s timer is set and it should turn on or turn off the device if the program time matches with the current time.</li>

 <li>The <strong><em>setTimer</em>, <em>cancelTimer</em></strong> and <strong><em>runProgram</em></strong> abstract methods should be implemented by the classes that implements <strong><em>Programmable</em></strong></li>

</ul>




<ol start="4">

 <li>Implement a <strong><em>MotionControl</em></strong> interface with the following UML diagram.</li>

</ol>




<table width="432">

 <tbody>

  <tr>

   <td width="47"> </td>

   <td width="384">           &lt;&lt;interface&gt;&gt;<em>           MotionControl</em></td>

  </tr>

  <tr>

   <td width="47"> </td>

   <td width="384"> </td>

  </tr>

  <tr>

   <td width="47">+</td>

   <td width="384"><em>controlMotion(</em> <em>hasMotion: boolean, isDay: boolean): boolean</em></td>

  </tr>

 </tbody>

</table>







<ul>

 <li><strong><em>MotionControl</em></strong> interface represents the property of motion capturing for a smart device.</li>

 <li>The<strong> <em>controlMotion</em></strong> method takes two <strong>boolean</strong> parameters, in which the first one represents the presence of motion and the second one represents whether it is daytime or night time. It should start recording if there is a captured motion.</li>

</ul>




<strong><em>controlMotion</em></strong> abstract method should be implemented by the classes that implements <strong><em>MotionControl</em></strong> interface.




<ol start="5">

 <li>Implement a <strong>SmartLight</strong> class with the following UML diagram.</li>

</ol>




<table width="546">

 <tbody>

  <tr>

   <td width="47"> </td>

   <td width="498">SmartLight</td>

  </tr>

  <tr>

   <td width="47">–––</td>

   <td width="498">hasLightTurned: boolean programTime: Calendar programAction:  boolean</td>

  </tr>

  <tr>

   <td width="47">+++++++++++</td>

   <td width="498">SmartLight(alias: String, macId: String) turnOnLight(): void turnOffLight(): void testObject(): boolean shutDownObject(): boolean onLeave(): void onCome(): voidsetTimer(seconds: int): void cancelTimer(): void runProgram(): void getter/setter methods</td>

  </tr>

 </tbody>

</table>




<ul>

 <li><strong>SmartLight</strong> is a subclass of <strong>SmartObject </strong>class and it implements <strong><em>LocationControl</em></strong> and <strong><em>Programmable</em></strong></li>

 <li>It has three data fields: <strong>hasLightTurned</strong> takes the value of true if the light is turned on, <strong>programTime</strong> keeps the exact time of automatic activation of the smart device, <strong>programAction</strong> keeps the next action of the smart device (either turn on or turn off).</li>

 <li>The <strong>turnOnLight</strong> method should check the connection of a smart light firstly and it should turn on the light by printing the opening time (i.e. current time). In this method, you should update the <strong>hasLightTurned</strong> property appropriately. If the light is newly turned on, it should print a message as the following:</li>

</ul>

Smart Light – Living Room Light is turned on now (Current time: 10:14:39 )




<ul>

 <li>If the smart light object has been already turned on, then it should print a message as the following:</li>

</ul>

Smart Light – Living Room Light has been already turned on

<ul>

 <li>The <strong>turnOffLight</strong> method should check the connection of a smart light firstly and it should turn off the light by printing the power-off time (i.e. current time). In this method, you should update the <strong>hasLightTurned</strong> property appropriately. If the light is newly turned off, it should print a message as the following:</li>

</ul>

Smart Light – Living Room Light is turned off now (Current time: 11:15:45 )




<ul>

 <li>If the smart light object has been already turned off, then it should print a message as the following:</li>

</ul>

Smart Light – Living Room Light has been already turned off

<strong>testObject</strong> method should check the connection of a smart light firstly and it should

test the functionalities of the smart light by invoking <strong>SmartObjectToString</strong>, <strong>turnOnLight</strong>, and <strong>turnOffLight</strong> methods. An example output of the <strong>testObject</strong> method is as the following:

This is SmartLight device Living Room Light

MacId : AA:BB:CC

IP : 10.0.0.100

Smart Light – Living Room Light is turned on now (Current time: 10:14:39 )

Smart Light – Living Room Light is turned off now (Current time: 11:15:45 ) Test completed for SmartLight




o If the smart light object was not connected to the system, then this method should return the value of <strong>false</strong>.




<ul>

 <li>The <strong>shutDownObject</strong> method should check the connection of a smart light firstly. Then, it should turn off the light (if it has been already turned on) after calling</li>

</ul>

<strong>SmartObjectToString</strong> method. If the smart light object was not connected to the system, then this method should return the value of <strong>false</strong>.




<ul>

 <li>The <strong>onLeave</strong> method should check the connection of a smart light firstly and then it should turn off the light. The <strong>onCome</strong> method should check the connection of a smart light firstly, and then it should turn on the light. The example outputs for both methods should be as the following:</li>

</ul>

On Come -&gt; Smart Light – Living Room Light

Smart Light – Living Room Light is turned on now (Current time: 11:15:45 )

On Leave -&gt; Smart Light – Living Room Light

Smart Light – Living Room Light is turned off now (Current time: 11:16:45 )




<ul>

 <li>The <strong>setTimer</strong> method should set the timer of a smart light with the given amount of seconds. Firstly, it should check the connection of a smart light, and then it should set the <strong>programTime</strong> property of the smart light by using the current time. Then, it should add the given amount of seconds to the <strong>programTime</strong> Lastly, it should print the following messages by checking the <strong>hasLightTurned</strong> property:</li>

</ul>

Smart light – Living Room Light will be turned off 5 seconds later! (Current time: 11:15:45 )

<strong> </strong>

<strong><u>OR</u> </strong>Smart light – Living Room Light will be turned on 5 seconds later! (Current time: 11:15:45 )




<ul>

 <li>The <strong>cancelTimer</strong> method should check the connection of a smart light, and then it should cancel the timer of a smart light by assigning the value of <strong>null</strong> to the <strong>programTime</strong> <strong>runProgram</strong> method should check the connection of a smart light firstly. Then, it should either turn on or turn off the light by checking the <strong>programAction</strong> property of the smart light if the <strong>programTime</strong> value equals to the current time.</li>

</ul>

An example flow of <strong>setTimer</strong> and <strong>runProgram</strong> methods are given below:




Smart light – Living Room Light will be turned off 5 seconds later! (Current time: 11:32:14 )

….

RunProgram -&gt; Smart Light – Living Room Light

Smart Light – Living Room Light is turned off now (Current time: 11:32:19 )

<ul>

 <li>You should assign the value <strong>null</strong> to the <strong>programTime</strong> property after printing messages.</li>

 <li>There are setter/getter methods.</li>

</ul>




<ol start="6">

 <li>Implement a <strong>SmartPlug</strong> class with the following UML diagram.</li>

</ol>




<table width="546">

 <tbody>

  <tr>

   <td width="47"> </td>

   <td width="498">SmartPlug</td>

  </tr>

  <tr>

   <td width="47">–––</td>

   <td width="498">status: boolean programTime: Calendar programAction:  boolean</td>

  </tr>

  <tr>

   <td width="47">+++++++++</td>

   <td width="498">SmartPlug(alias: String, macId: String) turnOn(): void turnOff(): void testObject(): boolean shutDownObject(): boolean setTimer(seconds: int): void cancelTimer(): void runProgram(): void getter/setter methods</td>

  </tr>

 </tbody>

</table>




<ul>

 <li><strong>SmartPlug</strong> is a subclass of <strong>SmartObject </strong>class and it implements <strong><em>Programmable</em></strong></li>

 <li>It has three data fields: <strong>status</strong> takes the value of true if the plug is turned on, <strong>programTime</strong> keeps the exact time of automatic activation of the smart device, <strong>programAction</strong> keeps the next action of the smart device (either turn on or turn off).</li>

 <li>The <strong>turnOn</strong> method should check the connection of a smart plug firstly and it should turn on it by printing the power on time (i.e. current time). In this method, you should update the <strong>status</strong> property appropriately. If the plug is newly turned on, it should print a message as the following:</li>

</ul>

Smart Plug – Kitchen Plug 1 is turned on now (Current time: 11:32:14 ) o If the smart plug object has been already turned on, then it should print a message as the following:

Smart Plug – Kitchen Plug 1 has been already turned on

<strong>turnOff</strong> method should check the connection of a smart plug firstly and it should turn

off it by printing the power off time (i.e. current time). In this method, you should update the <strong>status</strong> property appropriately. If the plug is newly turned off, it should print a message as the following:

Smart Plug – Kitchen Plug 1 is turned off now (Current time: 11:49:41 )




o If the smart light object has been already turned off, then it should print a message as the following:

Smart Plug – Kitchen Plug 1 has been already turned off




<ul>

 <li>The <strong>testObject</strong> method should check the connection of a smart light firstly and it should test the functionalities of the smart light by invoking <strong>SmartObjectToString</strong>, <strong>turnOn</strong>, and <strong>turnOff</strong> An example output of the <strong>testObject</strong> method is as the following:</li>

</ul>




This is SmartPlug device Kitchen Plug 1

MacId : DD:KK:FF

IP : 10.0.0.102

Smart Plug – Kitchen Plug 1 is turned on now (Current time: 11:49:41 )

Smart Plug – Kitchen Plug 1 is turned off now (Current time: 11:49:41 )

Test completed for SmartPlug o If the smart plug object was not connected to the system, then this method should return the value of <strong>false</strong>.




<ul>

 <li>The <strong>shutDownObject</strong> method should check the connection of a smart light firstly. Then, it should turn off it (if it has been already turned on) after calling <strong>SmartObjectToString</strong> If the smart plug object was not connected to the system, then this method should return the value of <strong>false</strong>.</li>

</ul>




<ul>

 <li>The <strong>setTimer</strong> method should set the timer of a smart plug with the given amount of seconds. Firstly, it should check the connection of a smart plug, and then it should set the <strong>programTime</strong> property of the smart plug by using the current time. Then, it should add the given amount of seconds to the <strong>programTime</strong> Lastly, it should print the following messages by checking the <strong>status</strong> property:</li>

</ul>

Smart plug – Kitchen Plug 1 will be turned on 5 seconds later! (Current time:

11:49:41 )<strong> <u>OR</u></strong>

Smart plug – Kitchen Plug 1 will be turned off 5 seconds later! (Current time:  11:49:41 )

<ul>

 <li>The <strong>cancelTimer</strong> method should check the connection of a smart plug, and then it should cancel the timer of a smart plug by assigning the value of <strong>null</strong> to the <strong>programTime</strong></li>

</ul>




<ul>

 <li>The <strong>runProgram</strong> method should check the connection of a smart plug firstly. Then, it should either turn on or turn off it by checking the <strong>programAction</strong> property of the smart plug if the <strong>programTime</strong> value equals to the current time.</li>

</ul>




An example flow of <strong>setTimer</strong> and <strong>runProgram</strong> methods are given below:




Smart plug – Kitchen Plug 1 will be turned on 5 seconds later! (Current time:     11:49:41 )

….

RunProgram -&gt; Smart Plug – Kitchen Plug 1

Smart Plug – Kitchen Plug 1 is turned on now (Current time: 11:49:46 ) o You should assign the value <strong>null</strong> to the <strong>programTime</strong> property after printing messages.

<ul>

 <li>There are setter/getter methods.</li>

</ul>










<ol start="7">

 <li>Implement a <strong>SmartCamera</strong> class with the following UML diagram.</li>

</ol>




<table width="590">

 <tbody>

  <tr>

   <td width="51"> </td>

   <td width="539">SmartCamera</td>

  </tr>

  <tr>

   <td width="51">–––</td>

   <td width="539">status: boolean batteryLife: int nightVision:  boolean</td>

  </tr>

  <tr>

   <td width="51">+++++++++</td>

   <td width="539">SmartCamera(alias: String, macId: String, nightVision: boolean, batteryLife: int) recordOn(isDay: boolean): voidrecordOff(): void testObject(): boolean shutDownObject(): BooleancontrolMotion(hasMotion: Boolean, isDay:boolean): boolean compareTo(smartCamera: SmartCamera): int toString(): String getter/setter methods</td>

  </tr>

 </tbody>

</table>




<ul>

 <li><strong>SmartCamera</strong> is a subclass of <strong>SmartObject </strong>class and it implements <strong><em>MotionControl</em></strong> and <strong><em>Comparable</em></strong></li>

 <li>It has three data fields: <strong>status</strong> takes the value of true if the camera is recording, <strong>batteryLife</strong> represents the battery life of the camera, <strong>nightVision</strong> represents the night vision feature of the camera.</li>

 <li>The <strong>recordOn</strong> method should check the followings firstly: the connection of a smart camera, the <strong>isDay</strong> value and the <strong>nightVision</strong> feature of the smart camera. Based on these controls it should start recording. In this method, you should update the <strong>status</strong> property appropriately. If the camera is newly turned on, it should print a message as the following:</li>

</ul>

Smart Camera – Garden Cam is turned on now o If the smart camera object has been already turned on, then it should print a message as the following:

Smart Camera – Garden Cam has been already turned on




<ul>

 <li>If the time of the day is night time (i.e., <strong>isDay</strong> is false) and there is no night vision feature of the camera (i.e., <strong>nightVision </strong>is false), then it should display the following message:</li>

</ul>

Sorry! Smart Camera – Garden Cam does not have night vision feature.

<ul>

 <li>The <strong>recordOff</strong> method should check the connection of a smart camera firstly and it should stop recording. In this method, you should update the <strong>status</strong> property appropriately. If the camera is newly turned off, it should print a message as the following:</li>

</ul>

Smart Camera – Child Room Cam is turned off now




<ul>

 <li>If the smart camera object has been already turned off, then it should print a message as the following:</li>

</ul>

Smart Camera – Child Room Cam has been already turned off




<ul>

 <li>The <strong>testObject</strong> method should check the connection of a smart camera firstly and it should test the functionalities of the smart camera by invoking <strong>SmartObjectToString</strong>, <strong>recordOn(true) </strong>(i.e daytime), and <strong>turnOff</strong> methods firstly. Then, it should invoke <strong>recordOn(false) </strong>(i.e night time), and <strong>turnOff</strong> An example output of the <strong>testObject</strong> method is as the following:</li>

</ul>




This is SmartCamera device Child Room Cam

MacId : JJ:KK:LL

IP : 10.0.0.107

Test is starting for SmartCamera day time

Smart Camera – Child Room Cam is turned on now

Smart Camera – Child Room Cam is turned off now

Test is starting for SmartCamera night time

Sorry! Smart Camera – Child Room Cam does not have night vision feature.

Smart Camera – Child Room Cam has been already turned off

Test completed for SmartCamera Test completed for SmartCamera

o If the smart camera object was not connected to the system, then this method should return the value of <strong>false</strong>.




<ul>

 <li>The <strong>shutDownObject</strong> method should check the connection of a smart camera firstly. Then, it should turn off it (if it has been already turned on) after calling</li>

</ul>

<strong>SmartObjectToString</strong> method. If the smart camera object was not connected to the system, then this method should return the value of <strong>false</strong>.




<ul>

 <li>The <strong>controlMotion</strong> method should check the <strong>hasMotion</strong> parameter, and it should print “Motion not detected!” if it is false; “Motion detected!” otherwise. Then, it should check <strong>isDay</strong> parameter, if it is true (i.e., daytime) it should start recording. If it is false, it should check the <strong>nightVision</strong> property of the camera firstly, and then it should start recording or not.</li>

</ul>




<ul>

 <li>The <strong>compareTo</strong> method should check the <strong>batteryLife </strong>of the smart camera with the given parameter <strong>smartCamera</strong>. If the battery life of the smart camera is greater than the</li>

</ul>

battery life of the <strong>smartCamera</strong> parameter, it should return the value of 1. If they are equal, return the value of 0. If it is smaller, then return the value of -1.




<ul>

 <li>The <strong>toString</strong> method should return a representative string for the smart camera as the following:</li>

</ul>

SmartCamera -&gt; Child Room Cam’s battery life is 30 status is recording




<ul>

 <li>There are setter/getter methods.</li>

</ul>







<ol start="8">

 <li>Implement a <strong>SmartHome</strong> class with the following UML diagram.</li>

</ol>




<table width="590">

 <tbody>

  <tr>

   <td width="51"> </td>

   <td width="539">SmartHome</td>

  </tr>

  <tr>

   <td width="51">–</td>

   <td width="539">smartObjectList:  ArrayList&lt;SmartObject&gt;</td>

  </tr>

  <tr>

   <td width="51">++++++++++</td>

   <td width="539">SmartHome()addSmartObject(smartObject: SmartObject): boolean  removeSmartObject(smartObject: SmartObject): boolean controlLocation(onCome: boolean): voidcontrolMotion(hasMotion: boolean, isDay: boolean): void controlProgrammable(): void  controlTimer(seconds: int): void controlTimerRandomly(): void  sortCameras(): void getter/setter methods</td>

  </tr>

 </tbody>

</table>







<ul>

 <li><strong>SmartHome</strong> represents a smart house containing several smart objects (smartObjects are kept in <strong>smartObjectList</strong>).</li>

 <li>The <strong>addSmartObject</strong> method adds the given <strong>smartObject</strong> to the</li>

</ul>

Firstly, it invokes <strong>connect</strong> method of the <strong>smartObject</strong> by sending it’s <strong>IP</strong> value.

o The IP value is set as “10.0.0.x”, where x represents the index of the smart object in the <strong>smartObjectList </strong>starting from 100. For example, if it is the first smart object added to the list, the IP value should be “10.0.0.100”. If it is the second smart object added to the list, the IP value should be “10.0.0.101”, etc. o Then, it should invoke the <strong>testObject</strong> method for the given <strong>smartObject</strong> o An example output of <strong>addSmartObject</strong> method is as the following:







—————————————————————————

—————————————————————————

Adding new SmartObject

—————————————————————————

Living Room Light connection established

Test is starting for SmartLight

This is SmartLight device Living Room Light

MacId : AA:BB:CC

IP : 10.0.0.100

Smart Light – Living Room Light is turned on now (Current time: 12:25:36 )

Smart Light – Living Room Light is turned off now (Current time: 12:25:36 ) Test completed for SmartLight







<ul>

 <li>The <strong>removeSmartObject</strong> method removes the given <strong>smartObject</strong> from the</li>

</ul>




<ul>

 <li>The <strong>controlLocation</strong> method should traverse the <strong>smartObjectList</strong> and if it finds an object implementing <strong><em>LocationControl</em></strong> interface, then, it should invoke either <strong>onCome</strong> or <strong>onLeave</strong> method of it by checking the <strong>onCome </strong>boolean parameter. If <strong>onCome</strong> boolean parameter is true, then it should invoke <strong>onCome</strong> method, and <strong>onLeave</strong> method otherwise.</li>

</ul>




An example output of this method is given below:

—————————————————————————

—————————————————————————

LocationControl : OnCome

—————————————————————————

On Come -&gt; Smart Light – Living Room Light

Smart Light – Living Room Light is turned on now (Current time: 12:25:36 )

On Come -&gt; Smart Light – Kitchen Light

Smart Light – Kitchen Light is turned on now (Current time: 12:25:36 )




<ul>

 <li>The <strong>controlMotion</strong> method should traverse the <strong>smartObjectList</strong> and if it finds an object implementing <strong><em>MotionControl</em></strong> interface, then, it should invoke <strong>controlMotion</strong> method of it by sending <strong>hasMotion</strong> and <strong>isDay</strong> boolean parameters.</li>

</ul>




An example output of this method is given below:

—————————————————————————

—————————————————————————

MotionControl : HasMotion, isDay

—————————————————————————

Motion detected!

Smart Camera – Garden Cam is turned on now

Motion detected!

Smart Camera – Child Room Cam is turned on now  Motion detected!

Smart Camera – Gate Cam is turned on now




 The <strong>controlProgrammable</strong> method should traverse the <strong>smartObjectList</strong> and if it finds an object implementing <strong><em>Programmable</em></strong>  interface, then, it should invoke <strong>runProgram</strong> method of it.




An example output of this method is given below:

—————————————————————————

—————————————————————————

Programmable : runProgram

————————————————————————— runProgram -&gt; Smart Light – Living Room Light

Smart Light – Living Room Light is turned off now (Current time: 12:42:36 ) runProgram -&gt; Smart Plug – Living Room Plug 1

Smart Plug – Living Room Plug 1 is turned on now (Current time: 12:42:36 ) runProgram -&gt; Smart Plug – Living Room Plug 2

Smart Plug – Living Room Plug 2 is turned on now (Current time: 12:42:36 )







 The <strong>controlTimer</strong> method should traverse the <strong>smartObjectList</strong> and it should search for a smart object implementing <strong><em>Programmable</em></strong>  interface. In case of finding such an object, it should invoke <strong>setTimer</strong> method of it if the given seconds value is greater than 0, and it should invoke <strong>cancelTimer</strong> method if the given seconds value is equal to 0.




An example output of this method is given below:

—————————————————————————

—————————————————————————

Programmable : Timer = 10 seconds

————————————————————————— Smart light – Living Room Light will be turned off  10 seconds later! (Current time: 12:44:24 )

Smart light – Kitchen Light will be turned off  10 seconds later! (Current time:

12:44:24 )

Smart plug – Kitchen Plug 1 will be turned on 10 seconds later! (Current time:

12:44:24 )

Smart plug – Kitchen Plug 2 will be turned on 10 seconds later! (Current time:

12:44:24 )

Smart plug – Living Room Plug 1 will be turned on 10 seconds later! (Current time: 12:44:24 )

Smart plug – Living Room Plug 2  will be turned on 10 seconds later! (Current  time: 12:44:24 )




 The <strong>controlTimerRandomly</strong> method should traverse the <strong>smartObjectList</strong> and it should search for a smart object implementing <strong><em>Programmable</em></strong>  interface. In case of finding such an object, it should invoke <strong>setTimer</strong> method of it with the value of 5 or 10 seconds randomly. If the random number is 0, then it should invoke <strong>cancelTimer</strong> method. (Here, the random number should be 0, 5, or 10).




An example output of this method is given below:

—————————————————————————

—————————————————————————

Programmable : Timer = 0, 5 or 10 seconds randomly

————————————————————————— Smart light – Living Room Light will be turned off  10 seconds later! (Current time: 12:44:24 )

Smart light – Kitchen Light will be turned off  10 seconds later! (Current time:

12:44:24 )

Smart plug – Kitchen Plug 1 will be turned on 10 seconds later! (Current time:

12:44:24 )

Smart plug – Kitchen Plug 2 will be turned on 5 seconds later! (Current time:

12:44:24 )

Smart plug – Living Room Plug 1 will be turned on 5 seconds later! (Current time: 12:44:24 )

Smart plug – Living Room Plug 2  will be turned on 10 seconds later! (Current time: 12:44:24 )




 The <strong>sortCameras</strong> method should traverse the <strong>smartObjectList</strong> and it should search for  smart cameras implementing <strong><em>Comparable</em></strong> interface. Then, it should invoke <strong>Arrays.sort </strong>method to sort smart cameras based on the battery life.




An example output of this method is given below:

—————————————————————————

—————————————————————————

Sort Smart Cameras

—————————————————————————

SmartCamera -&gt; Child Room Cam’s battery life is 30 status is recording

SmartCamera -&gt; Gate Cam’s battery life is 50 status is recording

SmartCamera -&gt; Garden Cam’s battery life is 60 status is recording







<ol start="9">

 <li>Use the given <strong>Test</strong> class for your program. Please analyze the Test class carefully by reading the comments. The test class creates a <strong>SmartHome</strong> instance and adds several smart objects into it. It invokes most of the methods in the <strong>SmartHome</strong> class. There is a special method of <strong>sleepSystem</strong> which sleeps the system for 5 seconds. This method is used for checking <strong>setTimer</strong> and <strong>runProgram</strong> methods of the smart objects implementing <strong><em>Programmable</em></strong> interface. An example console output of the test program is given in “consoleOutput.txt” (You are not required to do File I/O, the output is given in a file due to long output size).</li>

</ol>


