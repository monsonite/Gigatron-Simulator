# Gigatron-Simulator
Gigatron TTL Computer - simulated in H Neeman's Digital Simulator

This is a simulation of Marcel van Kervinck's Gigatron TTL Computer.

The Gigatron is a simple but powerful 8-bit TTL computer built in fewer than 40 ICs.

This simulation allows you to see the various sections of the design work together as you single step through the instructions.

Below is a screenshot of the "Front Panel".  For ease of monitoring the process, multiple 7-segment displays allow you to view ROM Address, Instruction, Data, RAM Address, Output Register, Switch Inputs etc.

A new front panel that allows data entry to the RAM from a hex-heypad is shown further down this ReadMe

The design deviates a little from the real Gigatron - registers are 4-bit 74xx173 as they have a better pin arrangement than the 8-bit 74xx377. 


Similarly 74xx240, 74xx244 and 74xx273 have been swapped out for more "bus" oriented  '540, '541 and '574. Extra chips have been added for sensing zero on the ALU output and providing switch inputs to the processor bus.


Whilst a real Gigatron produces a VGA display and audio, the intention of this simulator is to explore the architecture and instruction set of the machine.  It also highlights the effect of the simple pipeline, where one instruction is being executed whilst the next is being fetched.

## September 2023 Update.

I have removed the parallel ALU, consisting of 8 x 74HC153 multiplexers and 2 x 74HC283 4-bit adders, and replaced it with a bit serial ALU. 

This lowers the chip count and also the instruction rate to approximately 1 million instructions per second from a 10MHz clock.


![image](https://user-images.githubusercontent.com/758847/128181975-99832af3-ba6c-4ea7-afcb-7582785bb38e.png)


This is a view of the whole Gigatron design - which I have broken down into 6 manageable sections: X & Y RAM addressing registers and RAM, Front Panel and Switches, Program Counter and ROM, Control Unit, ALU-High and ALU Low.

The simlator was running when I grabbed this screenshot - so high and low signals are light and dark green respectively and the data on the hexadecimal displays are updated on each clock cycle.

![image](https://user-images.githubusercontent.com/758847/128181804-6539af21-bd16-4298-9402-ba67278c9a3d.png)

Here's a new front panel design concept that uses a hex-keypad to program data into the RAM. 

A diode matrix is used to convert the keypress into a 4-bit binary code.

The last 4 digits from the hex keypad are clocked into the ket-switch register. From here they can either be used to load the program counter or deposited into RAM at the current address.

A further diode matrix is used to decode some simple control functions.

An up-down counter is used for the program counter. This is only because I was considering using it as a stack pointer, which needs to be both incremented and decremented. Without this requirement the program counter can just be a binary counter made from 4 off 74xx163 devices.

If you examine or deposit to memory, the program counter is automatically incremented.

The whole front panel logic consists of just 8 devices.  If you had TIL311 LED displays you could quite readily construct this. 

![image](https://user-images.githubusercontent.com/758847/168101230-76591219-3efa-4d96-af1e-98acab56144b.png) 




