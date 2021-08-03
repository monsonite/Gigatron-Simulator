# Gigatron-Simulator
Gigatron TTL Computer - simulated in H Neeman's Digital Simulator

This is a simulation of Marcel van Kervinck's Gigatron TTL Computer.

Below is a screenshot of the "Front Panel".  Multiple 7-segment displays allow you to view ROM Address, Instruction, Data, RAM Address, Output Register, Switch Inputs etc. The simulation allows single stepping each instruction at a time.


The design deviates a little from the real Gigatron - registers are 4-bit 74xx173 as they have better arranged pins than the 8-bit 74xx377. Similarly 74xx240, 74xx244 and 74xx273 have been swapped out for more "bus" oriented  '540, '541 and '574.


Whilst a real Gigatron produces a VGA display and audio, the intention of this simulator is to explore the architecture and instruction set of the machine.  It also highlights the effect of the simple pipeline, where one instruction is being executed whilst the next is being fetched.


![image](https://user-images.githubusercontent.com/758847/128010510-6c15c98a-aad1-4ae5-9c60-47e3167304bc.png)

This is a view of the whole Gigatron design - which I have broken down into 6 manageable sections: X & Y RAM addressing registers and RAM, Front Panel and Switches, Program Counter and ROM, Control Unit, ALU-High and ALU Low.

The simlator was running when I grabbed this screenshot - so high and low signals are light and dark green respectively and the data on the hexadecimal displays are updated on each clock cycle.

![image](https://user-images.githubusercontent.com/758847/128020739-3ff8110a-be9c-4248-bf4f-d4743477d6fb.png)

