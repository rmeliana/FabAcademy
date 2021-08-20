# 4. Computer Controlled Cutting

## Assignment

* Group assignment:

    * characterize your lasercutter's focus, power, speed, rate, kerf, and joint clearance;
    * document your work (individually or in group).


*   Individual assignments

    * Design, lasercut, and document a parametric press-fit construction kit, which can be assembled in multiple ways. Account for the lasercutter kerf;
    * cut something on the vinylcutter.

## Group assignment
**All of the test files were created using Autodesk Fusion 360 by the lab technician Leonardo Nazário. And then, we made the conversion for `.dxf` files.**

### Material
For the tests, the MDF (Medium-density fibreboard) with a thickness of 3 mm was used.

![](imgs/laser_focus_1.jpg){.center style="height:250px"}

### Sofware
The laser cutter model is [Duplotech 1080](https://www.insper.edu.br/fab-lab/equipamentos/) and its software is called [RDWorks (RDCAM)](http://www.duploj.com.br/suporte). It can support `.dxf` and .`bitmap` files. Here is its interface.

![](imgs/RDWorks.jpg){.center style="height:400px"}

### Focus
The laser cutter has a manual focus. According to the manufacturer's instructions, the distance between the material surface and the laser nozzle must be 6 mm. Therefore, we placed a 6 mm thick piece of acrylic on the MDF sheet and let the laser nozzle touches it (the two screws highlighted in the picture below can be handled to allow the cannon to be free/fixed).

![](imgs/laser_focus_2.jpg){.center style="height:300px"}

### Setting test (power, speed, rate)
To get a better sense of what the best parameters are for cutting and engraving we developed two tests, one of power(%) vs speed(mm/s) for testing cutting parameters and another one with interval(mm) vs power(%) using a fixed speed of 350mm/s to test engraving parameters. We set different parameters up divided by colors.

You can download the setting test file [here](4downloads/Setting_test.dxf).

![](imgs/setting_test_1.jpg){.center style="height:400px"}

![](imgs/setting_test_2.jpg){.center}

![](imgs/setting_test_3.gif){.center}

|The results after cutting and engraving in 3mm MDF|
|:------------------------------------------------:|
|![](imgs/setting_test_5.jpg){.center}|

### Kerf Test
In this file were drawn some 15 mm diameter circles. Each color was set up with a different power (%). And the first row was cut with a speed of 5 mm/s and the second 15 mm/s.

You can download the kerf test file [here](4downloads/Kerf_test.dxf).

![](imgs/kerf_test_1.jpg){.center style="height:400px"}

![](imgs/kerf_test_2.jpg){.center style="height:400px"}

There isn’t that much of a difference changing the parameters. The calculated kerf is around ***0.225mm*** and ***0.275mm***.
![](imgs/kerf_test_3.jpg){.center}


### Joint clearance test
Setting value: power 70%, speed 15mm/s.
You can download the joint clearance test file [here](4downloads/Join test.dxf).

![](imgs/joint_clearance_1.jpg){.center style="height:400px"}

![](imgs/joint_clearance_2.jpg){.center style="height:400px"}

![](imgs/joint_clearance_3.gif){.center style="height:400px"}

![](imgs/joint_clearance_4.jpg){.center style="height:400px"}

The gap which had the best fit was 2.75mm (kerf around 0,25mm).

![](imgs/joint_clearance_5.jpg){.center style="height:400px"}

## Individal assignment

### Parametric press-fit construction kit

### Laser cutting machine parameters

<style>
td, th {
  border: 1px solid #dddddd;
  text-align: center;
}
</style>
