## 12/17/2025 - I started my project by breadbording a distortion circuit  

_Time spent: 4.0h_  

‎ 
‎	My name is Henrique, and I’m from São Paulo, Brazil. Currently, I’m in the eleventh grade of high 
school and building my first guitar pedal during vacation. Today, on December seventeenth, I started my 
project by defining the type of guitar pedal I want to build and organizing my thoughts about possible 
topologies.
‎ 
	This device is going to be an aluminum box with two jacks for audio input and output, a dc power 
input, and a battery clip. On the top, there will be a footswitch for turning the pedal on and off, along 
with some knobs for tweaking the sound. My objective is to design a high-gain signal-modeling circuit 
that shapes the guitar tone in an aggressive, harmonically rich, and musical way.    My name is Henrique, 
and I’m from São Paulo, Brazil. Currently, I’m in the eleventh grade of high school and building my first 
guitar pedal during vacation. Today, on December seventeenth, I started my project by defining the type 
of guitar pedal I want to build and organizing my thoughts about possible topologies.
‎ 
	I breadboarded some ideas I had in mind for the circuit to clarify my objectives for the project. I 
set up my audio interface and computer as an oscilloscope and graphic equalizer, grabbed my guitar and 
components, and started brainstorming. I finished the day using an lm308 op amp in a non-inverting 
configuration feeding an asymmetric hard-clipping stage with a red led and a 1n4148 diode. I didn’t do 
much tweaking and didn’t add any input or output buffers, but I really liked the harmonic complexity I 
got from the asymmetric clipping.
‎ 
	By noon, I started taking notes about which topology to go for. I haven’t done too much research 
yet, because I’ve been studying how transistors clip sound, something I’ll probably need to understand, 
but I did establish some directions. My conclusion is that I want something as reactive as a Fuzz Face, 
but more modern, with fewer overtones,  however, not as modern as a Big Muff, which is basically an 
overdrive that sounds like a fuzz and is full of low-pass filtering. I need something bright, with a lot 
of character, but still modern - something in between fuzz and overdrive.


   
![WhatsApp Image 2025-12-17 at 21.17.32](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjU4NDMsInB1ciI6ImJsb2JfaWQifX0=--3572fe40fa53341f490b4a73679fffb6b6998052/WhatsApp%20Image%202025-12-17%20at%2021.17.32.jpeg)  

## 12/18/2025 - I decided the effect type: a mix of fuzz and distortion  

_Time spent: 4.0h_  

‎ 
	Today, December eighteenth, I've done some research on what topology I'd build my circuit into, and when going through my thoughts on pedals I liked, I was certain that a fuzz face would do the job. I went online to find a nice schematic of a fuzz pedal that could be the base, and the chosen one was the _Sili-Face_, a fuzz face interpretation in NPN silicon transistors by [home-wrecker.com](url). It will be basically the bones of my project.
‎ 
	During most part of the evening I occupied myself with building it. After concluding the _Sili-Face_ circuit on my breadboard I went straight to modding. I started by switching the transistor pair from two 230hFE 2n5088 to the combination of a 230hFE 2n5088 and a 320hFE 2n4401; this took the gain proportion closer to the original fuzz face standard. After this, I put two diodes - a led clipping the negative portion of the wave and a 1n60 clipping the positive - hard clipping after the cap at the end of the gain stage. This made the fuzz even fuzzier by squaring the tops of the wave, giving more harmonic content to the pedal. At last but not at least, I needed to fix the noise hiss and squeak, that as i found out, was caused by Barkhausen oscillation and to fix that I replaced the 100pF from Q1 to Q2 collectors because it was not effective, and instead placed between base and collector a 100pF cap at Q1 and a 1n8 cap at Q2. 
‎ 
	The next steps will be to place post gain filtering, because I'm looking for a brighter sound, a output buffer, and add a third gain stage somewhere in the circuit for control, since I didn't liked how the classical fuzz pot placement from the fuzz face sounded like when not maxed out.

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjYzNDksInB1ciI6ImJsb2JfaWQifX0=--f48038fbe737427846178315ae7ce5e66b632cb7/image.png)  

## 12/21/2025 - Circuit upgraded: buffers, gain control, and a schematic  

_Time spent: 8.0h_  

 

For the past two days I've been working on some big changes to the project. First, I added input and output buffers and level controls. The biggest issue was to do so without compromising the interaction between the guitar volume knob and the circuit and the noise oscillation inherent from the fuzz face topology. Secondly, I added a kind of turbo switch to the pedal; It connects an asymetric hard clipping stage to the circuit by pulling a lever. At last but not least, I went to kicad and put all the work I had on the breadboard into a schematic, where it is easier to understand the circuit and diagnose potential issues.
 
The next steps are designing a tone control, possibly rearrange the output buffer for such application and drafting the pcb in kicad.
 
Edit: I also added the kicad project to a github repository and added to the blueprint page.
	
![122025revA-1](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6Mjc0NTAsInB1ciI6ImJsb2JfaWQifX0=--1592f07be28801e9d7933a6c599ebcde426ef694/122025revA-1.png)  

## 12/27/2025 - Tone knob, schematic finished, footprints, and BOM  

_Time spent: 8.0h_  

 
 
For the last few days I was working in settling on a final version of this pedal. Since this topology is very versatile i had trouble in getting things right. I ended up switching the first op amp type from non-inverting to inverting, placing the gain control in the feedback loop, switching the fuzz face feedback resistor for two diodes in antiparalell, removed completely the distortion section, and even adding an agressive rc high pass filter at 720Hz at the end of the signal chain. Now the circuit has three knobs - gain, tone, and level - and is on a schematic in the github page.
 
 
Today, I revised the schematic, added footprints(some of them have no 3D model but i hope that's fine), got the circuit to pass the ERC, and created the BOM. The next steps will be to draw the pcb and to submit the project to review.
 
![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MzAzNzEsInB1ciI6ImJsb2JfaWQifX0=--313fbad592280716780811cd71dfb3c8198fdfb5/image.png)


![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MzAzMjgsInB1ciI6ImJsb2JfaWQifX0=--92bb4b73eb6530e3c16a1885dd9b3d07d198cbef/image.png)

![WhatsApp Image 2025-12-27 at 00.16.44](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MzAzNjksInB1ciI6ImJsb2JfaWQifX0=--3a988a2277f9d4ed29ce4e22f9c3ae2de60cf241/WhatsApp%20Image%202025-12-27%20at%2000.16.44.jpeg)

  

## 12/29/2025 - Today I routed the pcb  

_Time spent: 4.0h_  

 
Today I finished the pcb of my project! I went on kicad, placed and connected all of the components from the schematic. I even added a few testing points. Now I'll submit design review so I can get some funding for buying the metal case, pcb, and pcb mount potentiometers, which are all expensive or hard to buy in São Paulo, Brazil, where I live.
 
![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MzIyMjcsInB1ciI6ImJsb2JfaWQifX0=--c24c00ddd431f0ef602fa29b1e30a47778a372e2/image.png)
![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MzIyMjYsInB1ciI6ImJsb2JfaWQifX0=--7c5fef3e3d4f50abdbb891f0ef3df57cf31b743e/image.png)
![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MzIyMjQsInB1ciI6ImJsb2JfaWQifX0=--28d04e754bfd8452231a5bed593a2aa54a2583ec/image.png)
![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MzIyMjUsInB1ciI6ImJsb2JfaWQifX0=--b26f71f29b4a28884142fb95aff627b94a4736c2/image.png)


  

