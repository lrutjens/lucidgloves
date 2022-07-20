## Printing Overview
This is a guide for 3D printing parts for the LucidGloves prototype 4 and 4.1. 
These instructions should apply to almost any FDM printer.  

Before printing, take a moment to look at the different potentiometers and mounting systems supported.

![Green Pots vs WL Pots](https://cdn.discordapp.com/attachments/785135646082990120/875850313578459176/unknown.png)  
Both green potentiometers and WL potentiometers are supported. Since they are different sizes, different Tensioner and PotHolder parts are needed.

The mounting system used is also a factor in what PotHolder is used. There are two options for mounting:  
* Rigid Mount, which adds a new 3d printed, slide mounting system **(Recommended)**
* Legacy Mounting, which uses elastic bands like prototype 3 

![Rigid Mount](https://cdn.discordapp.com/attachments/785135646082990120/875859787257102417/unknown.png)
![Elastic Mounts](https://cdn.discordapp.com/attachments/785135646082990120/875864994686844998/unknown.png)

## Printed Parts List
STL files for 3D printing are located in the [hardware folder](https://github.com/LucidVR/lucidgloves/tree/main/hardware). 

The printed parts required **for each hand** are:
1. HapticSpool (5x)
2. SpoolCover (5x)
3. Tensioner (5x)
	- For either WL or green potentiometers
4. PotHolder (5x)
	- For either WL or green potentiometers
	- For either elastic or rigid mount
5. GuideNode (2+ per finger, 1+ for thumb)
	- Can be substituted with GuideRings (Will need to be resized)
6. Quest2_MountSlider OR Vive3.0_MountSlider (1x)
	- Only needed for rigid mounting
7. RigidMount (1x)
	- Left or Right hand
	- Only needed for rigid mounting
8. EndCap (5x)
	- Resize each EndCap to fit each finger

Disclaimer: You WILL need to print multiple sizes of the EndCap to fit the size of your fingers. Resize these in your slicer. Alternatively, you could print them in TPU for more flexible sizing. I recommend resizing the EndCaps non-uniformly to squish them down to fit the oval shape of your fingers, this way they don't rotate around.

![Different sized end caps](https://cdn.discordapp.com/attachments/822593475396632587/823344405712601149/unknown.png)

## Printing Tips
Recommended printer settings:
* Nozzle diameter: 0.4
* Infill: 10-20%, you can go higher if your layer adhesion needs it
* Layer height: 0.2mm
* No supports 
  * Parts are designed to not need supports
  * Brims are acceptable
* Shell thickness: 0.8mm (2 outlines)
* Retraction settings: May differ between printers, 5mm on Ender 3 is fine

All parts for prototype 4 are designed to be printed flat. Print them in the following orientations for the best finish:  

![Recommended orientations](https://cdn.discordapp.com/attachments/785135646082990120/875867269270495252/unknown.png)  

If your bed is big and level enough, you may be able to print all the parts at once, but feel free to print them individually as well, you may get higher yield printing individually.  
![All parts at once](https://cdn.discordapp.com/attachments/785135646082990120/875878026062204928/unknown.png)
