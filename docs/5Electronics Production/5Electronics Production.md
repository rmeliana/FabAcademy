# 5. Electronics Production


## Group assignment

* Characterize the design rules for your PCB production process: document feeds, speeds, plunge rate, depth of cut (traces and outline) and tooling.
* document your work (in a group or individually).

## Design rules for PCB production

### Minimum trace width

The minimum trace width that we were able to produce using both the Roland MDX-540 and Rolland MDX-40A was **0,12mm/4,72mils** due to two factors:

 - Unevenness of phenolic based PCB's
 - Difficulty of finding micro end-mills at the Brazilian market

![Image Explaning the tapper mill problem](imgs/taperProblem.svg){.center style="height:400px"}

As it's difficult to find micro end-mill to do the engraving part of the boards we end up using tapered mills instead, which causes some problems as the deeper you go into the material, thicker the mill gets.

#### File to test

Similar to the file [linetest](5downloads/linetest.png) given by Neil for the students of class 2021, we made a simple PCB using the software Autodesk Eagle. The goal here was to test the performance of Roland MDX-540 milling different traces width (range between 0.001 and 1.0 mm).

![Eagle layout](imgs/Board_layout.png){.center style="height:450px"}

To generate the gcode with its commands and parameters the software [FlatCAM](http://flatcam.org/download) was used. In it, we can adjust depth cut, multi-depth, feed rate, spindle speed...

![Interface FlatCAM](imgs/FlatCAM.png){.center style="height:450px"}

!!! Important "For more details about how to prepare files and to mill a PCB using the machine Roland MDX-540 see the [Individual Assignment](https://rmeliana.github.io/FabAcademy/5Electronics%20Production/5Electronics%20Production/#individual-assignment)."


#### Milling

Using a tapered end-mill of Ø 0,1mm (and 20°) and depth cut of -0,14mm (the default depth of -0,11mm was not enough, so we added more 0,03mm to this parameter), we had the result below. We can note that was removed much more material than necessary due to the format of the mill.

<center>
![Tapered mill](imgs/tapered mill.jpg){style="height:200px"}
<figcaption><b>Tapered end mill</b></figcaption>
</center>

<center>
![PCB traces width](imgs/PCB_traces1.jpeg){style="height:250px"} &nbsp;
![PCB traces width](imgs/PCB_traces2.jpeg){style="height:250px"}
<figcaption><b>PCB milled</b></figcaption>
</center>

Using the equipment called stereoscope microscope Stemi 508 and the software AxioVision, we were able to measure the real width of the traces. Just taking a snapshot with super zoom and using the dimension command.

<style>
td, th {
  border: 1px solid #dddddd;
  text-align: center;
}
</style>

<html>
  <head>
    <link rel="stylesheet" href="stylesheets/gallery.theme.css">
    <link rel="stylesheet" href="stylesheets/gallery.min.css">
  </head>

  <body>
    <div class="gallery items-4">
      <div id="item-1" class="control-operator"></div>
      <div id="item-2" class="control-operator"></div>
      <div id="item-3" class="control-operator"></div>
      <div id="item-4" class="control-operator"></div>

      <figure class="item">
        <center>
        <h1><img src="https://github.com/rmeliana/FabAcademy/blob/master/docs/5Electronics%20Production/imgs/microscope.jpeg?raw=true" width="300" /></h1>
        <figcaption>Stereoscope microscope Stemi 508</figcaption>
        </center>
      </figure>

      <figure class="item">
        <center>
        <h1><img src="https://github.com/rmeliana/FabAcademy/blob/master/docs/5Electronics%20Production/imgs/zoom%20microscope.jpeg?raw=true" width="300" /></h1>
        <figcaption>Stereoscope zoom</figcaption>
        </center>
      </figure>

      <figure class="item">
        <center>
        <h1><img src="https://github.com/rmeliana/FabAcademy/blob/master/docs/5Electronics%20Production/imgs/snapshot.jpeg?raw=true" width="300" /></h1>
        <figcaption>Snapshot of the trace</figcaption>
        </center>
      </figure>

      <figure class="item">
        <center>
        <h1><img src="https://github.com/rmeliana/FabAcademy/blob/master/docs/5Electronics%20Production/imgs/dimension.jpeg?raw=true" width="500"/></h1>
        <figcaption>Measurement</figcaption>
        </center>
      </figure>


      <div class="controls">
        <a href="#item-1" class="control-button">.</a>
        <a href="#item-2" class="control-button">.</a>
        <a href="#item-3" class="control-button">.</a>
        <a href="#item-4" class="control-button">.</a>
      </div>
    </div>
  </body>
</html>


Here is a table with the virtual widths of the traces (Eagle parameters) and the real ones (milled by a tapered end-mill).

<center>

| Virtual | Real |
|:-------:|:----:|
| 1,0mm   |0,82mm|
| 0,9mm   |0,72mm|
| 0,8mm   |0,62mm|
| 0,7mm   |0,52mm|
| 0,6mm   |0,42mm|
| 0,5mm   |0,32mm|
| 0,4mm   |0,22mm|
| 0,3mm   |0,12mm|

</center>

Therefore, the minimum trace width that we were able to produce using the Roland MDX-540, depth cut of -0,14mm, is **0,12mm/4,72mils**, when we use a virtual trace with 0,3mm.

#### Files

* [Eagle](5downloads/Traces_Eagle.7z) files;
* [FlatCAM](5downloads/Traces_FlatCAM.FlatPrj) files;
* [Gcodes](5downloads/Traces_Gcode.7z) files.

### Minimum isolation

The minimum isolation hits on the same barrier as the trace width. If we get a cut depth deeper the tapered end-mill tool starts milling away the other traces during isolation milling.

In the file below there are some traces near each other. We milled three PCBs with the same layout, but changing the depth cut.

![PCB isolation width](imgs/PCB_isolation.jpg){.center style="height:450px"}

#### Files
* [Eagle](5downloads/Isolation_Eagle.7z) files;
* [FlatCAM](5downloads/Isolation_FlatCAM.FlatPrj) files;
* [Gcodes](5downloads/Isolation_Gcode.7z) files.

### Feeds & Speeds

Here is the parameters that we used to mill our boards:

| Operation | Tool        | Cut Z(mm) | Multi-Depth(mm) | Travel Z(mm) | Feed Rate X-Y(mm/s) | Feed Rate Z(mm/s) | Spindle Speed(RPM) |
|:----------|:-----------:|----------:|----------------:|-------------:|--------------------:|------------------:|-------------------:|
| Drill     | 0.5mm-1.2mm |     -1.65 |            0.55 |           15 |                 450 |               650 |              12000 |
| Engrave   | 0,1mm" 30º    |     -0.11 |            0.06 |              |                 450 |               650 |              12000 |
| Profile   | 1/8"        |     -1.65 |            0.55 |           15 |                 450 |               650 |               8000 |


## Individual assignment

* Make an in-circuit programmer by milling and stuffing the PCB, test it, then optionally try other PCB fabrication process.

###Printed Circuit Board (PCB)

For this task, I decided to reproduce a PCB that I've already made, but I didn't register the process. This board is part of a project called Giraffe Lamp. How you can see below, it's the ears of giraffe. And it'll be responsible to control the RGB leds (lamp's bulbs).

![](imgs/Giraffe Lamp.png){.center style="height:350px"}

###ATmega328P Microcontroller
Here in the lab, we usually use the Arduino Uno board to test prototypes. Due it, the heart of my board will be the same microcontroller [ATmega328P](https://ww1.microchip.com/downloads/en/DeviceDoc/Atmel-7810-Automotive-Microcontrollers-ATmega328P_Datasheet.pdf), but in a SMD package. One more chance to try my soldering skills!

<center>
![](imgs/atmega328p.jpg){.center style="height:280px"}    <figcaption><b>ATmega328P AU</b></figcaption>
</center>

###Bootloader and FTDI
Microcontrollers aren't sold ready to receive a programming. For this, it's necessary to 
