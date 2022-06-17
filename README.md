# Buck_IRS25411
High Voltage Buck featuring IRS25411 LED driver.

The IRS25411 is a hysteretic Buck driver for LED applications.
Hysteretic means that there is no fixed frequency but it switches with over and undershooting the threshold level of the feedback pin with the current ripple.
Due to the feedback voltage of 0.5V it is not worth driving more than 1A of current. The needed current sensing resistor results to R = 0.5V / 1A = 0.5Ohms. The power losses are Pls = 0.5V * 1A = 0.5W. This is already to much for a standard 1206 resistor. Using multiple resistors in parallel it might work.

In this design the current sensing resistor moved directly behind the inductor and a op-amp is driving a pnp transistor to provide an appropriate voltage to the feedback pin. Thus, a constant current is maintained.
Additionally, an other part of the circuitry around the TS431 is regulating the voltage.

In parallel operation both CC and CV regulators are active. When the maximum current is flowing the voltage drops and the buck is working in CC mode.
When the maximum current is not flowing the voltage is clipped at the voltage set and the buck is working in CV mode.

The schematic offers the opportunity to assemble the pcb in three ways:
1. Infineon typical application with low side shunt
2. High current CC mode with the op-amp
3. CV mode with TS431
4. Combined high current CC and CV mode

Schematics:
1. Infineon typical application with low side shunt
![Buck_Schematic_default](https://github.com/pellematrose/Buck_IRS25411/blob/main/assembly_normal.png)

2. High current CC mode with the op-amp
![Buck_Schematic_cc](https://github.com/pellematrose/Buck_IRS25411/blob/main/assembly_cc.png)

3. CV mode with TS431
![Buck_Schematic_cc](https://github.com/pellematrose/Buck_IRS25411/blob/main/assembly_cv.png)

4. Combined high current CC and CV mode
![Buck_Schematic_cc](https://github.com/pellematrose/Buck_IRS25411/blob/main/assembly_cv_cc.png)

To make it easy to adjust some component values the excel file may help you understand how the values are calculated.
The buck is tested in Combined mode with the values in the excel file.

I got the main inspiration from various application notes about the buck converter.  
[TI CC CV converter](https://www.ti.com/lit/an/snva829/snva829.pdf)  
[Electronics Stackexchange](https://electronics.stackexchange.com/questions/458384/cc-cv-buck-controller)  
[Buck converter design](https://www.mouser.de/pdfdocs/BuckConverterDesignNote.pdf)

Furthermore, here some links to usefull sites about mosfet losses:  
[Infineon MOSFET Losses Appnote](https://community.infineon.com/gfawx74859/attachments/gfawx74859/MOSFET/285/4/MOSFET%20Power%20Losses%20Calculation%20Using%20the%20Data-Sheet%20Parameters.pdf)  
[Youtube with Dr. K](https://www.youtube.com/watch?v=RViwOc4g-gw)</p>

