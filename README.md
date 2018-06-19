# da340a
Indoor positioning using ultrasound combined with TDOA 
Our aim was to design a cost-effective prototype for indoor positioning. The software solution is elegant in its simplicity. The system
uses four transmitters, that each burst an ultrasound signal. By estimating the time differences of arrival of all the beacon signals a
3D-position is calculated using an advanced mathematical algorithm. The overall position accuracy was less than 10 cm in a 4x2 m area. The
hardware is scarce as compared to many protoypes one finds in academic reasearch papers: we use ARM Cortex M3 processor (SAM3X8E on
Arduino Due) capable of fast and complicated computations, a miniscule MEMS microphone with a wide frequency range, a comparator to
trigger on the amplitude of an input signal and a Bluetooth-modul to transfer the (x,y,z)-position to an external unit for display. The
software solution is straightforward: once the amplitude of an input signal exceeds the voltage threshold level put in the comparator its
arrival time is recorded using a 42 MHz Timer Counter. The signals are sent one at a time with 30 ms between every 200 ms, based on the
TDMA-principle. An advantage with this is that enough time is given to avoid echoes. Once all four signals have been detected the TDOA
values derived and subsequently a position is calculated which gets shipped out via Bluetooth. As mentioned earlier, the position accuracy
was below 10 cm. Considering that the positioning technique was purely based on multilateration this is a very good result. Many systems
that use TDOA include some other form of positioning such as trilateration with TOA (Time of Arrival) which requires additional hardware,
such as radio modules. This gives room for more complex mathematical algorithms that also have an intrinsic error-handling approach to
them, which our algorithm lacks. 
