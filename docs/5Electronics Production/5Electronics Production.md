# 5. Electronics Production


## Group assignment

* Characterize the design rules for your PCB production process: document feeds, speeds, plunge rate, depth of cut (traces and outline) and tooling.
* document your work (in a group or individually).

## Design rules for PCB production

### Minimum trace width

The minimum trace width that we were able to produce using both the Roland MDX-540 and Rolland MDX-40A was **0,6mm/23mils** due to two factors:

 - Unevenness of phenolic based PCB's
 - Difficulty of finding micro end-mills at the Brazilian market

![Image Explaning the tapper mill problem](imgs/taperProblem.svg){.center style="height:400px"}

As it's difficult to find micro end-mill to do the engraving part of the boards we end up using tapered mills instead, which causes some problems as the deeper you go into the material, thicker the mill gets.

#### File to test

Similar to the file [linetest](5downloads/linetest.png) given by Neil for the students of class 2021, we made a simple PCB using the software Autodesk Eagle. The goal here was to test the performance of Roland MDX-540 milling different trackes width (range between 0.001 and 1.0 mm).

![Eagle layout](imgs/Board_layout.png){.center style="height:450px"}

To generate the gcode with its commands and parameters the software [FlatCAM](http://flatcam.org/download) was used. In it, we can adjust depth cut, multi-depth, feed rate, spindle speed...

![Interface FlatCAM](imgs/FlatCAM.png){.center style="height:450px"}

For more details about how to prepare files and mill a PCB using the machine Roland MDX-40 see the Individual Assignment.

#### Milling

Using a tapered end-mill of Ø 0,1mm and depth cut of -0,11mm, we had the result below. We can note that was removed much more material than necessary due to the format of the mill.

<center>
![Tapered mill](imgs/tapered mill.jpg){style="height:200px"}
<figcaption><b>Tapered end mill</b></figcaption>
</center>

![PCB trackes width](imgs/PCB_trackes.jpg){style="height:200px"}

#### Files

* [Eagle](5downloads/Traces_Eagle.7z) files;
* [FlatCAM](5downloads/Track width.FlatPrj) files;
* [Gcodes](5downloads/Gcode.7z) files.

### Minimum isolation

The minimum isolation hits on the same barrier as the trace width. If we use too much isolation the tapered end-mill starts milling away the other traces during isolation milling.

### Feeds & Speeds

| Operation | Tool        | Cut Z(mm) | Multi-Depth(mm) | Travel Z(mm) | Feed Rate X-Y(mm/s) | Feed Rate Z(mm/s) | Spindle Speed(RPM) |
|:----------|:-----------:|----------:|----------------:|-------------:|--------------------:|------------------:|-------------------:|
| Drill     | 0.5mm-1.2mm |     -1.65 |            0.55 |           15 |                 450 |               650 |              12000 |
| Engrave   | 0,1mm" 30º    |     -0.11 |            0.06 |              |                 450 |               650 |              12000 |
| Profile   | 1/8"        |     -1.65 |            0.55 |           15 |                 450 |               650 |               8000 |


## Individual assignment

* Make an in-circuit programmer by milling and stuffing the PCB, test it, then optionally try other PCB fabrication process.
