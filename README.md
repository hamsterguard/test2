Welcome to the test2 wiki!

[Raspberry Pi][1]
[1] : https://www.amazon.com

Or leave it empty and use the [link text itself].
[link text itself]: http://www.reddit.com

[[#displayed text|#1-raspberry-pi-amazon]]

# **The Door Unlocker Project**

## The Sequence of Operation
<div>
<img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="350" width="250" align="right">
<br>	The Door unlocker is setup so that when a person taps an access card on the RFID reader, the mechanism will unlock the door and allow the person to enter.<br><br>
	To prevent unauthorized personnel from entering, after leaving the door unlocked for 5 seconds, the mechanism will once again trigger, lock the door, and light up the blue LED to indicate that the RFID reader is ready to detect access cards. <br><br><br> <br><br><br><br>
</div>


## Materials
<div>
	Pretty much all of the components used here were items purchased from Amazon, and scavenged from the delivery boxes. The only things I did not buy on amazon were the wood to build the stand, the nuts and bolts to fasten them, and the single coat hanger, and some of the tools for wood working. <br><br><br>
</div>

<div>
<img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="230">
<img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="230">
<img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="230">

<img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="230">
<img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="230">
<img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="230">

<img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="230">
<img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="230">
<img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="230">
</div>

***

## The Build Components

### 1. [Raspberry Pi](http://amzn.to/2pZSVVA)

.inactiveLink {
   pointer-events: none;
   cursor: default;
}

<div>
  <img src="https://github.com/hamsterguard/test/blob/master/image/Rasp-1.jpg" width="340" title=“RedOutdoorweater” alt=“Our red outdoor sweaters are on sale now!” class="inactiveLink">
  <img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="340">
</div>

<div>
	This is the main component of the project, and the first item to setup in this build. A basic Raspberry Pi installation is required. You can follow the link below for suggestions on how to set it up, or alternatively, you can purchase a SD Card with the Pixel OS pre-installed [Amazon].<br>
	If your Raspberry Pi does not come with a wireless adaptor module, you can buy an external wireless adaptor here [Amazon] and set it up by following the instructions here [Link].``<br>
	Ensure that your Raspberry Pi is functional before moving on as we will use the raspberry pi to test the next components. For this example, after completing the Raspberry Pi installation setup, we will be accessing the Pi via ssh, and therefore will not need the keyboard, mouse, or monitor.(See instructions for accessing your Raspberry Pi through ssh [Link]). 
	For portability and testing, we used an USB battery charger to power the Raspberry Pi [ Amazon]. If this build is expected to be left on for most of the day, we recommend powering the Pi will a wall charger [amazon] or a high capacity battery charger around 100 000mah [Amazon]
	Your Raspberry Pi will look like this, and the notice the empty GPIO pins [Pic] [Pic]
</div>


### 2. LED [Amazon]

<div>
  <img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="340">
  <img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="340">
</div>

<div>
	The LED will be used here as an indicator to let you know when the RFID reader is active and ready to read. See this tutorial on testing the LED on the Raspberry Pi [Link]. Connect the LED and a 110ohm resistor [Link] [amazon], in shown the arrangement below [Pic]. 
</div>

### 3. RFID Reader [Amazon]

<div>
  <img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="340">
  <img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="340">
</div>

<div>
	The RFID Reader [Amazon] will be there to detect access cards or fobs and trigger the mechanism. See the instructions to use the RFID Reader [Link]. 
	You will need to also enter into the terminal the following:
		$ sudoasd asd
		$ sudo asd asd
	Connect the RFID Reader to the Raspberry Pi in the arrangement shown [Pic]
</div>

### 4. Servo Motor [Amazon]

<div>
  <img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="340">
  <img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="340">
</div>

<div>
	The two servo motors are here to move the unlocker arm and the lock gripper. See this tutorial as an example of how to use your servo motor [Link]. For this example build, we will be using pigpiod to manage the two servo motors. Install instructions pigpiod [Link].
	Connect the motors with the additional battery pack to the Raspberry Pi. The battery pack is to provide power to the servo motor so that the servo motors don't impose too large a drain on the Pi. They are somewhat optional, but I bought mine here [Amazon][Amazon].
	For flexibility of testing and ease of labelling, I added extra wires [Amazon] to extend the reach of the servo, but this is optional. IF you do choose to buy additional cables, you can link up all of the Ground GPIO pins to provide a central point to access. Your arrangement will look like this [Pic] 
</div>

### 5. Stand and Gripper

<div>
  <img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="340">
  <img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="340">
</div>

<div>
	The structure of the stand is the most difficult to describe, because it is modelled according to the shape of the door I was testing on.
	It primarily comprises of 3 portions, the backboard, the offsetter, the hinge, the swivel arm, the gripper. The backboard is made of cardboard, 2 layers, behind it, command adhesives were applied to stick it to the door. 
The offsetter are pieces of wood that raise the servo motor and hinge off away from the backboard to match the protruding depth of the deadbolt handle. My set was put assembled from leftover wood and cardboard with measurements that sport very amenable and high tolerances.
	The top servo motor pivots the arm over a regular 2" door hinge [Amazon]. The bolts, screws, and other fasteners were bought from a dollar-store. They are not expected to carry much weight unless you place additions to the arm. Zipties [Amazon] were also used to fasten the servo motors to the wooden pieces.
	The twisting gripper was fashioned from about 3 small layers of foamboard [Amazon], held in place with a cardboard and secured to the servo arm with screws.

</div>

### 6. Python Script

<div>
  <img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="340">
  <img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="180" width="340">
</div>

<div>
	Add the following files.
</div>









| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| ![alt text][logo2]     | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

[logo2]: https://github.com/hamsterguard/test/blob/master/untitled23.gif "Logo Title Text 2"



# test
<h1>Responsive Flexbox table with Fallbackfghfhhhhhhhhhhhhhhhhhhhhhhggg:
</h1>

And also text here


<div>
<img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" height="350" width="250" align="right">
<br>
	The Door unlocker is setup so that when a person taps an access card on the RFID reader, the mechanism will unlock the door and allow the person to enter.<br><br>
	To prevent unauthorized personnel from entering, after leaving the door unlocked for 5 seconds, the mechanism will once again trigger, lock the door, and light up the blue LED to indicate that the RFID reader is ready to detect access cards. <br><br><br> <br><br><br>
</div>

<div style="text-align:center;border:1px solid red">
<img src="https://github.com/hamsterguard/test/blob/master/untitled23.gif" width="300" align="right">
<br>
This is some text in a div element! is some text in a div element! is some text in a div element! is some text in a div element! is some text in a div element! is some text in a div element! is some text in a div element!  <br>                <br><br><br><br>                                                       
</div>


***


<div style="text-align:center;border:1px solid red">
This is some text in a div element! is some text in a div element! is some text in a div element! is some text in a div element! is some text in a div element! is some text in a div element! is some text in a div element!

</div>

### Inline-style: 
![alt text2](https://github.com/hamsterguard/test/blob/master/test.gif)

Inline-style: 
![alt text3](https://github.com/hamsterguard/test/blob/master/blog-1.png "Logo Title Text 1" )

Reference-style: 
![alt text4][logo11]

[logo11]: https://github.com/hamsterguard/test/blob/master/Carton-v1-tint.png "Logo Title Text 2"

As Kanye West said:
> We're living the future so
> the present is our past.
- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)
- [x] this is a complete item
- [ ] this is an incomplete item
