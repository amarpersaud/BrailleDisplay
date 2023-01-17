# Version A
Version A consisted of an solenoid powered device with a physical latching mechanism, rather than the magnetic mechanism of MOLBED. 
Due to its low actuation force, complexity, and issues with actuation errors due to physical loading while actuating, it is no longer a consideration. 
Version A.1 and A.2 are two designs that are similar with slightly different operation. A.1 was the main design considered.

# Version A.1
Version A.1 is shown below: 
<p align="center">
<img src="https://github.com/amarpersaud/BrailleDisplay/raw/main/Hardware/CAD%20Model/Version%20A/Image/A.1%20-%20Side%20view.png"/>
<img src="https://github.com/amarpersaud/BrailleDisplay/raw/main/Hardware/CAD%20Model/Version%20A/Image/A.1%20-%20Solenoid%20Cutaway.png"/>
</p>

The left wall is excluded for a better view of the internals, however it is identical to the right wall.

In the cutaway, the sections are labelled as follows:
- Blue - Plastic dot cap which the user physically interracts with
- Green - Iron or steel ferromagnetic rods
- Pink - Neodymium magnet
- Aqua - Plastic spool for holding the magnet wire which forms the solenoid
- Orange - Solenoid or electromagnet coil

The slot on the right wall allows for a sliding grid to be employed. When a dot is depressed, the bars of the grid go over the lip on the dot's cap. When a dot is extended, the bar passes below the lip and holds the dot up. This forms a physical latching mechanism. On the bottom, the horizontal electromagnet allows actuation of the grid via a lever linkage. Below the two electromagnets are two PCB layers with clearance for components. A ferromagnetic rod is used in the electromagnet to increase its strength, and in the solenoid to increase the permeability.

Issues with this design include low area on the circuit boards, a large space taken up by the electromagnets, high part count and complexity, susceptibility to wear and damage, a requirement for close tolerances, and the possibility for actuation failure.

# Version A.2
Version A.2 is shown below: 
<p align="center">
<img src="https://github.com/amarpersaud/BrailleDisplay/raw/main/Hardware/CAD%20Model/Version%20A/Image/A.2%20-%20Electromagnet%20Cutaway.png"/>
</p>

Version A.2 is design which takes a slightly different approach and was abandoned as well.

In the cutaway, the sections are labelled as follows:
- Yellow - Plastic dot cap which the user physically interracts with
- Horizontal Green Washer - Felt or soft material lower actuation noise
- Vertical Green Rod - Iron or steel ferromagnetic rods
- Pink - Neodymium magnet
- Aqua - Plastic for casing
- Blue - Plastic or PCB 
- Orange - Solenoid or electromagnet coil

This design has many drawbacks, including having a high retraction force but a much smaller actuation force, and relying on the physical actuation gives higher complexity.