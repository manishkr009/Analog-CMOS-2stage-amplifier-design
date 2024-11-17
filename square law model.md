##To understand square law model we need to understand the working of a metal oxide semiconductor transistor 
MOS transistor is a 4 terminal device consisting of 
- drain
- source
- gate
- bulk
and MOS is of two types depending upon the type of channel i.e. 
- Nmos
- Pmos
For easy understanding we will consider Nmos transistor.
When an input is applied to the gate terminal it causes the electrons from the substrate to accumulate between source and drain terminal making a channel.
At this point our transistor is considered to be on if the gate voltage exceeds [[threshold voltage]].
For the transistor to start conducting the current we will be applying the drain voltage and now our transistor can be driven in two regions
- Linear region 
- Saturation region

##Linear region
The region in which the drain current increases linearly with the drain-source voltage for different gate source voltage.

There are two types of fields that exist
- Vertical electrical field is when voltage is applied to the gate terminal and it is greater then threshold voltage, the vertical field as E <sub>GC</sub> (x) due to V<sub>GC</sub> (x) determines the charge Q<sub>C</sub> (x) as the capacitance is formed between the gate and channel due to the insulated oxide layer separating the channel with the gate. This infinitesimal small plate capacitor of length delta x with the width W, for which  V<sub>GC</sub> (x) is considered constant 
	---$\Delta$Q<sub>C</sub> =-W$\Delta$xC<sub>ox</sub> [V<sub>GC</sub> (x) - V<sub>T</sub> -V<sub>CS</sub> ]

![[Vertical field.jpg]] 


- Lateral field E <sub>CS</sub> (x) due to V<sub>CS</sub>(x) causes drift current I<sub>D</sub> i.e. electrons move with drift velocity and now putting the equation of drift velocity in the above equation and integrating the above equation for conditions:

	--- limits for  I<sub>D</sub> are 0 to L and for V<sub>CS</sub> from 0 to V<sub>DS</sub>
	we can get the equation for drain current for linear region and i.e.
	I<sub>D</sub>=u<sub>n</sub> C<sub>ox</sub> W/L[V<sub>GS</sub> (x) - V<sub>T</sub> -V<sub>DS</sub>/2 ]V<sub>DS</sub> 
	Similarly for Saturation region the equation will be where V<sub>DS</sub> =V<sub>GS</sub> (x) - V<sub>T</sub> 
	I<sub>D</sub>=u<sub>n</sub> C<sub>ox</sub> W/2L[V<sub>GS</sub> (x) - V<sub>T</sub> ]<sup>2</sup> 

![[Lateral field.jpg]]


#Limitations of Square law model 

--- Square law model was developed for long -channel transistors i.e. L> 1um with the V<sub>GS</sub> larger than a well defined threshold voltage V<sub>T</sub> i.e. the transistors are biased in strong inversion.

--- When V<sub>GSeff</sub> is 0 i.e. for V<sub>GS</sub> -V<sub>T</sub> is 0 according to square law model the I<sub>D</sub> should be 0 and the gm/I<sub>D</sub>  will be infinity but according to the simulation result that is not the case. For  V<sub>GSeff</sub> <0 the simulation results shows there is a definite value for the gm/I<sub>D</sub> .

--- So square law model fails in the case of weak and moderate inversion region and is valid only for long channel transistor with L >1um and as the L increases the square law model becomes more accurate in accordance with the simulation results.

#Different regions of operation  [[strong inversion]] [[weak and moderate inversion]]  and [[sub-threshold region]] 

