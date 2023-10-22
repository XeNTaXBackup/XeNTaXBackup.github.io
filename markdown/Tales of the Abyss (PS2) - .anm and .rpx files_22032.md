## Post #1
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2020-04-19T01:54:27+00:00
- Post Title: Tales of the Abyss (PS2) - .anm and .rpx files

Tried to convert the rpx file with RPXto3DS.bms (not made by me!!) and it gave me a error.

```
Error: No such file or directory

Last script line before the error or that produced the error:
  1   open FDDE 3DS 1
```


I tried versions 0.10.1 and 0.7.7 of quickbms and they gave me the same error. So that either probably worked with a version of quickbms that was older than 0.7.7 or a file that works with that .bms file.

Here is a zip file containing the files from the game and the bms file that I used with the .rpx file.

[https://anonymousfiles.io/0jplRIcI/](https://anonymousfiles.io/0jplRIcI/)

I also included HyoutaTools in it, so here is the tutorial.

Launch HyoutaToolsGui.exe, click on the one that says "Tales Abyss FPS3 Extract", get the path of one .NPC or .PKF file and put it into the arguments, click on the run button, and it will extract the files into the folder with a similar name to the file. 

There are texture files in the .rpx files, but I am not sure how to get them right now.

There is also the .anm files, which that relates to the animation used in the game, but we need to get the bones of the .rpx model files first before that.

EDIT: 

Thanks to shakotay2, now we figured out why that error happens.

you just basically execute this: quickbms -w RPXto3DS.bms 0000.rpx

and then it will tell you that the file named "0000.3DS" doesn't exist, type in "y", and it will create a new one.

I hope that someone makes a adaptation of RPXto3DS.bms as a model import plugin for the 3d model editing software that supports plugins (like 3ds max or blender) which makes it quicker to rip the model inside the .rpx files.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-19T11:40:48+00:00
- Post Title: Tales of the Abyss (PS2) - .anm and .rpx files

> Reply from andree ↑Sun Apr 19, 2020 9:54 am at Sun Apr 19, 2020 9:54 am
>
> 
Tried to convert the rpx file with RPXto3DS.bms (not made by me!!) and it gave me a error.made by whom, then?
Didn't provide the author instructions how to use the script?  
.



Tea00.png (32.11 KiB) Viewed 96 times
## Post #3
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2020-04-19T12:34:30+00:00
- Post Title: Tales of the Abyss (PS2) - .anm and .rpx files

> Reply from shakotay2 ↑Sun Apr 19, 2020 7:40 pm at Sun Apr 19, 2020 7:40 pm
>
> 
andree wrote: ↑Sun Apr 19, 2020 9:54 am
Tried to convert the rpx file with RPXto3DS.bms (not made by me!!) and it gave me a error.made by whom, then?
Didn't provide the author instructions how to use the script?

It was made by albinoleopard from ps23dformat.wikispaces.com (a old site that was archived few years ago) and the instructions in the Tales of the Abyss page on the old site said this:

```
Any tool that can extract files from ISO.
https://github.com/AdmiralCurtiss/HyoutaTools
https://github.com/aap/rwtools
https://github.com/mchubby/RE-games-attic/blob/master/sega-nextech/cvm_tool%20%5Broxfan%5D/cvm_tool_02.zip?raw=true
http://aluigi.altervista.org/quickbms.htm
RPXto3DS.bms
RPXto3DS.bms

and of course, you need the Tales of the Abyss ISO.

First, extract TO7NPC.CVM from the ISO of the game using your favorite ISO tool.

Once you have done that, use cvm_tool to convert the CVM to ISO.
Then, use your ISO tool to extract whatever NPC you want to convert.

Use HyoutaTools's TotAfps3e function to extract the .NPC files.

You should get a .rpx file.

Use the RPXto3DS.bms script to convert .rpx files into .3DS files with the UV coords.

You will get a .3DS file in the same directory.

Now, to get the textures, use txdex (from rwtools) to get .tga files from the .rpx.

Then once imported in blender, to get the textures to display properly:
Select all the UV's then use the button in the uv menu that says Mirror "Flip on Y axis"

Then import the tga image(s).
The model will now appear to have holes to fix this:
Select the object, then change the mode into edit mode.
Now go to the Mesh menu, and the sub menu Normals, and press "Recalculate Outside".
Now go to the Mesh menu again, and the sub menu Normals, and press "Recalculate Outside".
Then when still in edit mode, go to the bottom of the screen and underneath the words on the panel
that says "Mesh Tools"
press "Rem Double"
Then again go to the Mesh menu, and the sub menu Normals, and press "Recalculate Outside".

Your model should looked textured such as this one:
beast0UV.jpg


The model above is found in DOG00.NPC

This format uses the Renderware SDK.

RPX file extension (RenderWare stream) format:


```


BTW how did you figured out a way to get the model? Did you got a version of quickbms that works with it or you made a program/plugin that rips the model all by itself by using the BMS script as the base for it?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-19T13:20:37+00:00
- Post Title: Tales of the Abyss (PS2) - .anm and .rpx files

> Reply from andree ↑Sun Apr 19, 2020 8:34 pm at Sun Apr 19, 2020 8:34 pm
>
> BTW how did you figured out a way to get the model?I had a look at said bms script, its handling of "FILE 1" didn't make sense to me. There's a problem with the "write access" to that file. The quickbms.txt (manual) led me further.

Guess the script author used a batch file containing this line (or similar):
quickbms -w RPXto3DS.bms 0000.rpx

Still didn't work.
So I created an empty 0000.3Ds file manually which did the trick. "0000" is mandatory, same "name" as the rpx file.

edit: well, the last step is superfluous. The script asks whether to create the 3DS file from scratch, so the only missing info in this process was the -w parameter.
