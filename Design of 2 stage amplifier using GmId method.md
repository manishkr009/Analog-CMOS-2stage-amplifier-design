##Why do we need GmID  method in the first place?
According to the specification given for designing the 2 stage amplifier,
If we just follow the [[square law model]] and use hand calculation to set the parameters of our transistors in the design tool like cadence and run our simulation, we are able to see the difference in the results obtained from the simulation with the specifications mentioned for designing the amplifier.

### Now we will go through step by step designing of 2 stage amplifier
- step1- Finding the values from the specifications given to us for our design and also to calculate W/L values of our transistors.
 ![[Op amp specs.jpg]] 
 - This above mentioned is the specifications which we need to keep in mind while designing the amplifier.
- Step 2-  With the next step we will look at the schematic of our 2-stage Operational Amplifier
![[hand calculation circuit.jpg]]

- Here we can see our transistors arrangement and differential input applied to the input of T1 and T1<sup>'</sup> 
- For [[transistors]]details    
### Some explanations for the above architecture 
- why is it called 2 stage amplifier?
--- This amplifier architecture consist of two stages, in first stage its our differential amplifier which has low gain and with the second stage we increases the gain of our amplifier
--- For the negative input our gain will be calculated using -G<sub>m</sub> R<sub>out</sub>  method
so the gain will be (gm1<sup>'</sup> /gm2<sup>'</sup> )* (gm1(rds<sub>2</sub> //rds<sub>1</sub>)* (gm3(rd<sub>3</sub> //rds<sub>4</sub>)) 
and for the positive input the gain can be calculated as (gm1(rds<sub>2</sub> //rds<sub>1</sub>))* (gm3(rd<sub>3</sub> //rds<sub>4</sub>))

Also voltage at N1 and N2 are same if dimensions of left side to right side is same
(W/L)<sub>3</sub> =n(W/L)<sub>2</sub>  and (W/L)<sub>4</sub> = n/2(W/L)<sub>5</sub> 
V<sub>gs3<sup>'</sup></sub> =V<sub>gs2<sup>'</sup></sub>  

So, T2 acts as current mirror for T3

C1 is the sum of total parasitic capacitances at the node N1 and Cm as the [[miller capacitor]]  and C<sub>L</sub> as load capacitor 

I<sub>ref</sub> is the reference current which is considered to be constant and is generated using bandgap reference circuit which we can discuss in next article.

## Now we will start calculating the W and L of our transistors
- To begin with we will have the matlab files which  can be found in my git along with this article, basically its the graph of GmId vs V<sub>gs</sub> , Gmid vs Id values for pMos and Nmos that are there in our design.
- We will be using some of the information that is known it us 
--The calculation of dimensions of transistor in mentioned in the file attached below
[[Dimension calculations.pdf]]

1.To increase the slew rate - more current in M5 so W needs to be increased we increased it to 12.3um keeping the L same.

2.To reduce the offset -input transistors M2 and M3 W and L needs to be increased and we increased by 2.1 times to values W= 21um and L= 4um.

3.To increase the unity gain frequency we increased the W of transistor M7 to 64.9um we will need to increase the value of M8 so that same current flows in the branch we increased it to 180um. But the Phase margin decreased, thus we increased the value of resistor from 1000 ohm to 2000ohm connected with miller capacitor for pole zero compensation.
- Withe above changes we can achieve the below results

1.New value of slew rate is 19.24V/us which is within the specification now.

2.New offset value -3.98mV to 7.487mV to reduce further we increased the W and L of transistor M0 and M1 to 3.375um and 1.5um as even though major offset is due to input transistors some contribution is due to current mirror transistors too.

3.Gain is around 91dB and UGF= 15.7MHz with phase margin around 65.22 which are within the specification.

New Value of our transistor dimensions after running all the simulations.

##Please note the numbering of transistors used in hand calculation and in cadence is different if there is any confusion please click here [[Numbering of transistor]]


|   |   |   |
|---|---|---|
|Transistor number|W (um)|L(um)|
|M0|3.375|1.5|
|M1|3.375|1.5|
|M2|21|4|
|M3|21|4|
|M5|12.3|2|
|M6|7.25|2|
|M7|64.9|1|
|M8|180|2|
![[Pasted image 20241118000918.png]]
--This is how the 2 stage amplifier design will look like in cadence.




-  --
