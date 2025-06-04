# this is the journal from when i built the 3d printer

# part one, this is all going to go extactly as planned

its not

my first challenge in build the 3d printer was making the holes in the 2020 extrusion that joins it to the the 2040 extusion

# the hotbed voltage pannic
i had a little mishap with ordering my heat bed , ali express decided to refund me on the heat bed i ordered, which was nice, but left me without a heatbed
so in a an effort to try and get my printer working i got a hot bed of ebay, but i didnt realise it was 12v

however
if you do the maths
and work out 
if you run a 12v bed at 24v it doesnt draw double the power, it draws 4x the power

120w @ 12v  means i=10a
v/i=r, 12v/10a=1.2 ohms=r

so at 24v
i=v/r, i=24/1.2=20a
p=iv, so 24*20=p=480w
which is a BIGGGG issue
i dont want to light more printer electronics on fire in my room (different story)

so in theory a duty cycle of 0.25 would work, but out of fear of magic smoke, i ran it at a 0.2 duty cycle

Note from future william: 
this didnt result and any magic smoke **yet** , so i think it worked well enough. not that i would recommend you do this yourself

# the slip ring challenges
WOOO challenge number something
the wires on my slip ring feel REALLYYY thin
i allready knew that out of the wires i had in the slipring
i was going to run:
4 in paralel for V+
4 in paralel for V-
2 in a pair for the bed thermistor

but 4 wires felt REALLYYY thin for what would be 3-4a
which was another reason that i lowered the duty cycle below the theoretical 0.25
so i carefully checked the wires temperatures both with my hand and with a thermistor in klipper, and a bit of kapton tape
in the end, it ended up being _fine_ 

# the bearing challenges

One of the main things that made my project particularly difficult was the fact that i designed my own bearing for the bed
with the idea being that i could use two, and stack them with a gap to try and improve Z stability

the bearings i made deffinetly worked however they had a few issues but i will talk about them as a whole next

i hadnt fully planned on how i would assemble, however the approach of getting the balls into each and then joining the two halves together deffinetly worked quite well

![image](https://github.com/user-attachments/assets/da2307f3-03ef-43af-af21-284ea2f064f7)
that image shows a crossection of the bearing assembbly, quite alot of stuff going on in there which did make me worried
however it went together REALLY well

for a few bolts 
![image](https://github.com/user-attachments/assets/25e9f66e-71d2-479f-88cb-52b091a5909a)
i found that i needed to use a ball end hex driver because a normal driver wouldnt be able to access them
and those were the bits i joined last

now time for the issues i encountered with the bearings:

i intially printed it fully out of PLA, including the following parts
![image](https://github.com/user-attachments/assets/034a157d-8d18-40f2-af7a-ddec901393d8)
the issue of this was that PLA has a habbit of creeping, where it slowly deforms over time if there is a load on it
and with the weight of the 3d printer, it was effectively canatalevered off the main extrusion
causing the PLA to creep
and the bottom of the bearing which take the load, to sag below the top part, which is purely there for alignment
my solution to this was to pre load the bearing, putting a force on it to hold the bearings into the channels they are supposed to travel in

![image](https://github.com/user-attachments/assets/bf500512-cb36-4dc7-aec4-7eac2d94f255)
which lead to these being designed
where you can tighten the screw to add more tension and hold it together more or less
however there should be some sort of spring ect to account for it slowly creeping or needing more
the little pre tensioner things should be attached afterwards

i also supported the bearing from both sides so it wasnt cantalevered





# things i would change if i did it again
- print parts in ABS from the start
- put a bit more thought into some of the non critical parts in cad
- ELECTRONICS BOX
  - the electronics really needed to be less of a birds nest
  - it was functional, nothing went wrong, but it could have been safer if it was less open
- 24v bed, dont do what i did with the duty cycle
- get a slip ring that is rated for higher than what you need, instead of running a bunch of the wires in paralel
- think about canatalevers more, 3d printed parts arent as stiff as metal
