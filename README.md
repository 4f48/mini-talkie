# mini-talkie

A little 868 MHz walkie-talkie with LoRa radio for long ranges with built-in battery and USB-C charging.

![3D render of the complete project with all parts, including the antenna.](/images/assembly.png)

### Features:
- 100% off-grid. Works anywhere!
- Long range: multiple kilometers in ideal conditions
- Long battery life: 1200 mAh lithium-polymer battery
- Convenient USB-C charging
- Swappable antenna: use any 868 MHz antenna you want
- Multiple modes: push-to-talk, voice activation
- Small size: fits in your pockets

### Usage:
1. Turn it on using the switch on the left.
2. Start talking! Use the push-to-talk button, or switch to voice activation and talk hands free.
3. Battery low? Plug it in to your regular phone charger.

## Why?
All the walkie-talkies I tried before have too short range, have too many fancy features I would never use, or are very expensive. This walkie-talkie is unique in the way that it uses LoRa radio, making it operate through exceptional ranges. It's also dead simple: no screen, no dials. It doesn't have many extra features, but the ones it has just work. It is also not very expensive to build. It's great for hiking so nobody gets lost, or multiple-car road trips to keep in contact with the other cars without phone calls.

## Assembly
You can actually build a mini-talkie for yourself. All you need is the PCB, SMD components, a speaker, an antenna and internal antenna cable. Below is a rough guide to making one.

### 1. PCB and components

![3D render of a green circuit board needed for assembly.](/images/bare_pcb.png)

The printed circuit board has to be manufactured somewhere. I recommend [Aisler](https://aisler.net) or [JLCPCB](https://jlcpcb.com), but any similar services work. You can find the source files for the PCB in [/pcb](/mini-talkie/src/branch/main/pcb). Make sure to order the PCBA (assembly) service if you are not comfortable soldering smaller sized components.

You also need some other components ordered. Check out the [Bill of Materials](/mini-talkie/src/branch/main/bom.csv) which includes links to help you order them easily.

### 2. Printed parts

![The 3D printed parts needed for assembly seen alongside each other in a 3D render.](/images/3d_models.png)

mini-talkie's enclosure is made from 2 parts. These have to be made on a 3D printer. If you don't have access to a 3D priner, explore services like [JLC3DP](https://jlc3dp.com) that print and ship the parts to you.

You can find the source files and exported models in STL and STEP formats in [/3d](/mini-talkie/src/branch/main/3d).

### 3. Soldering

![The same printed circuit board as before, but with components such as resistors and capacitors soldered on the surface.](/images/assembled_pcb.png)

A fine-tipped soldering iron and some flux is needed for this part. Refer to the PCB source files in [/pcb](/mini-talkie/src/branch/main/pcb) as a reference for placing the correct parts.

Skip this step if you ordered your PCBs assembled (PCBA).

In addition, you need to remove the included connectors from the speaker and battery and solder on the 2-pin JST PH connectors you ordered instead. You need to do this even if you ordered a PCBA.

### 4. Programming

You need a Raspberry Pi Zero (2) or a separate debugger. Connect it to the SWD port on the circuit board and load the firmware from [/firmware](/mini-talkie/src/branch/main/firmware).

> TODO: Complete this part with instructions once the code is actually done.

### 5. Assembly
1. Insert 3 threaded inserts in the correct holes on the bottom enclosure. Appropriate tools are needed for this step.
2. Install the antenna cable using the included washers and nut.
3. Peel the protective layer off the adhesive on the speaker and stick it on the top enclosure, behind the speaker grille, but in a way that it won't obstruct the microphone.
4. Drop the battery into the compartment under where the PCB goes and plug it into the board.
5. Place the board on the bottom enclosure so that the battery connector is facing down.
6. Plug in the speaker to the board, and put the top enclosure on the bottom, then screw all the M2.5 screws into the top enclosure. Those 3 screws hold everything together, so make sure they are secure.
7. Compete the build by installing your SMA antenna on the top.
