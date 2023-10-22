## Post #1
- Username: hoopera
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 20, 2016 12:18 am
- Post datetime: 2022-02-22T22:31:32+00:00
- Post Title: Extracting 3D Map Models from SSX 3

Lately I've been on a mission to extract the 3D Environments from SSX 3. It's proving to be more difficult than I first anticipated, so I come to you all for some assistance! I've been trying my best to find the best way to get the model from the game, and there's only 2 methods I can think of: Extracting the model directly from the game files, or ripping them with an injector program (Nina Ripper, 3DRipperX). This is how far I've gotten with each one:

Extract from game files:

First is getting the game files themselves. SSX 3, and like many other EA sports games, uses .big files for their data storage. This is the game's file structure:

 You can use the program FinalBIG to view and extract all the .big files directly from the game: [https://www.moddb.com/downloads/final-big-editor/](https://www.moddb.com/downloads/final-big-editor/) 

After this, we now need to find where the map files are stored. I found this thread on Xentax to help: [viewtopic.php?f=16&t=21408&hilit=ssx](https://forum.xentax.com/viewtopic.php?f=16&t=21408&hilit=ssx)

TL;DR - Character models are stored in data > char > mdlngc.big as [character]_[part].mnf. Naturally you'd think that game developers would also have their map models as the same file right? If only it were that simple. 

As Henchman800 pointed out on that post:

> Reply from Henchman800 ↑Wed Jan 22, 2020 3:56 am at Wed Jan 22, 2020 3:56 am
>
> 
Yo guys, check this out:
a pre-alpha of ssx 3 has been discovered. Strangely EA used the .mpf format for their models in this one....at least thats what i think/see.....
Usually a .mpf goes with a .mus. the mus-file contains the actual audio and the mpf-file comes with info and offsets to start the song on certrain timecodes. In this particular case it seems to contain 3d info:
Code: Select allTopBoltD_H
 HeadBoltA_H HandsA_NIS DummyA_NIS TopBoltD_M
 HeadBoltA_M TopBoltD_L
 HeadBoltA_L TopBoltD_Shdw BottomA_Shdw BootsA_Shdw
 HeadA_Shdw HandsA_Shdw HeadBoltA_Shdw HeadBoltD_H
 HeadBoltD2_H
 HeadBoltD_M
 HeadBoltD2_M
 HeadBoltD_L
 HeadBoltD2_L
 HeadBoltD_Shdw
 HeadBoltD2_Shdw
 SplitHair_H HeadBoltB4_H SplitHair_M HeadBoltB4_M SplitHair_L HeadBoltB4_L SplitHair_Shdw HeadBoltB4_Shdw
ë mY1YßÆ¦ PTQt
 mY1Y!9¦ PTQD
 mY1Y 3ZuD
 ?lowerspine ?middlespine ?upperspine
 ?clavicleleft ?bicepleft
 ?biceptwistleft
 ?forearmleft ?clavicleright ?bicepright
 ?biceptwistright ?forearmright
 ?handright
 ?thighleft ?thighright ?shinright ?footright
Á p$gAh6tAy)E
‘Á V=~Ah6tAy)E
 xR6AÈÂ 3B8G
 sec_hoodie
 aXA7V‚Àð F3B7F]A
Ù m,Ad}u@gG'BÙ m,Ad}u@gG'BX‡ GAqt
Ù m,Ad}u@gG'BÙ m,Ad}u@gG'BÙ m,Ad}u@gG'B
 aXA7V‚Àð F3BX‡ GAqt
 ?lowerspine ?middlespine ?upperspine
 ?clavicleleft ?bicepleft
 ?biceptwistleft
 ?forearmleft ?clavicleright ?bicepright
 ?biceptwistright ?forearmright
 ?handright
 ?thighleft ?thighright ?shinright ?footright
 sec_hoodie
À rTEB 5Ahm
 ?lowerspine ?middlespine ?upperspine
 ?clavicleleft ?bicepleft
 ?biceptwistleft
 ?forearmleft ?clavicleright ?bicepright
 ?biceptwistright ?forearmright
 ?handright
 ?thighleft ?thighright ?shinright ?footright
 sec_hoodie
 ?lowerspine ?middlespine ?upperspine
 ?clavicleleft ?bicepleft
 ?biceptwistleft
 ?forearmleft ?clavicleright ?bicepright
 ?biceptwistright ?forearmright
 ?handright
 ?thighleft ?thighright ?shinright ?footright
 sec_hoodie

So hopefully this info and the file itself help to get to its innerts and understand how EA is working their 2003 era models.
Heres a download to nates .mpf file:
rocco.zip

I'll be looking into some need for speed stuff....maybe they use the same model containers and nfs extractors work on ssx aswell?
anybody got info or experience with that?

If you've played SSX 3, this makes total sense! SSX 3 likes to make it's music be in-time with the gameplay. As in, you make a huge jump, the music's vocals stop and a low-pass filter is heard, but as soon as you land, it comes back in full force. With the gameplay changing the music, you'd have to setup your worlds this way. But, we could still possibly find some models with this. We'll need to know how the game references the maps, and what according to the code, each region is referred to. Thankfully, someone's already done that for us! [http://www.merqurycity.com/ssx_forum/vi ... S2#p333003](http://www.merqurycity.com/ssx_forum/viewtopic.php?f=8&t=12138&p=333003&hilit=MDLPS2#p333003)

On that page (Posting it here for possible archival/posterity reasons) they've found that the maps are referenced as such:

```
EBC3_E = between the end of The Throne to Black Station

Black Station = E

E_ERA5 = Area the leads to Gravitude after Black Station
E_EBA3 = Leads to Much 2 Much
E_ESS3 = Leads to Kick Doubt
E_EHP3 = Area that leads to Perpendiculous

EBA3 = Much-2-Much
ESS3 = Kick Doubt
EHP3 = Perpendiculous
ERA5 = Gravitude

ERA5_C = End of Gravitude to Yellow Station

C = Yellow Station

C_CRA3 = Section that Leads to Ruthless Ridge
C_CHP2 = Leads to Schizophrenia
C_CBA2 = Section leading towards Launch Time

CHP2 = Schizophrenia
CBA2 = Launch Time
CRA3 = Ruthess Ridge

CRA3_D = Between Ruthless Ridge end and Red Station

DBC2 = Ruthless

DBC2_D = End of Ruthless to Red Station

D = Red Station

D_DRA4 = Section that leads to Intimidator
D_DSS2 = Leads to Style Mile

DSS2 = Style Mile
DRA4 = Intimidator

DRA4_A = End of Intimidator to Green Station

ABC1 = Happiness

ABC1_A = End of Happiness to Green Station

A = Green Station

A_ARA1 = Leads to Snow Jam
A_ASS1 = Section leading to R&B
A_ABA1 = Leads to Crow's Nest

ABA1 = Crow's Nest
ASS1 = R&B
ARA1 = Snow Jam

ARA1_B = End of Snow Jam to Blue Station

B = Blue Station

B_BRA2 = Section leading to Metro City
B_BHP1 = Section leading to The Junction


BHP1 = The Junction
BRA2 = Metro City
```


However, searching through the .big files so far isn't giving me any indication that these are stored in there somewhere. I'm not really finding any .mpf files that are referenced above. However, I can confirm that's how the game references them, because of these files!



These come from data > worlds > bam.big. If I look in bam.gdb with HexEdit (With the data aligned at 88 columns):



They're all there! So somehow, bam.gdb is referencing all of the levels. I assume that this is a pointer file to somewhere else, but alas this is where my knowledge of data extraction ends. I tried to use this to get some kind of model with 3D Model Researcher, but it's only given me a garbled mess of faces and random vertices.

I tried another step to maybe help locate the exact file, but this also leads me into the next section.

Ripping the models:

This method produced the fastest results, but very very dirty and would take a ton of cleanup work to get going. Plus, it'd probably produce a lot of issues with the model itself given that these ripping programs aren't usually the best at setting normals correctly, nor getting super correct UVs (Though it's surprised me in the past with how accurate it is). 

The easiest way to do this is to your respective ripping program (I use Ninja Ripper), and open the game with an emulator. Since I'm using the gamecube version of the game, I used Dolphin! [https://dolphin-emu.org/](https://dolphin-emu.org/)

The process here would be pretty simple: You load into the game where you want to be, and press whatever button to rip the models, throw them in a 3D program like Blender, and get to work putting it together! But, there's a severe issue with this.

CULLING

Culling, the devil of any game...tinkerer? I don't know what I am, just a guy who likes to mess with games honestly. If you're unfamiliar, culling is how modern systems handle rendering geometry that isn't visible to the in-game camera, or rather, how they don't handle it. Culling removes any geometry that is not in view of the camera, and this is why your games look so good and run so well! Every video game in the 3D era uses culling, but when we're trying to extract exact 3D models from a game, it becomes a nightmare.

With culling, we'd have to make sure we get every single angle of the map completely visible, and rip the model multiple times. This adds sooooo much time and tediousness to this process, not to mention that the models aren't always the same orientation due to the in-game camera moving.

Luckily, we have some tools to help with this! First, is Dolphin has built-in freelook camera function that allows you to completely control the direction the camera is facing. This works pretty well with SSX 3 as well, but keep in mind that the camera's translation (position in a 3D space) is locked to the character, but it can be offset and rotated any direction. It lets us do this:



Nice! Closer, but that damn culling...I wish we could get rid of that...

Ah ha! Of course, we have a tool for that too! Please take a look at this, Dolphin VR: [https://github.com/CarlKenner/dolphin](https://github.com/CarlKenner/dolphin)

Dolphin VR? Why are you linking this? Good question, Me! While Dolphin VR is awesome for playing gamecube/Wii games in full VR (Your mileage may vary there), it also has a few added debugging features that aren't in regular Dolphin, specifically it's debug mode, and a brute forcer.

See, the devs of Dolphin VR ran into the same issues with culling as we do. When you look around with a VR headset in Dolphin, the view is changing, but the in-game camera's operations aren't, at least according to the game they aren't. So, the developer introduced a brute forcer into the program. What this brute forcer does, is it loads a specific save state and references a 'symbol map' that's saved from the debugger. It loads this save state over and over again, and goes through the different hex values that the game's scene is using, and sets their value to either 0 or 1. It's a really dirty way, but often times this is able to find a way to turn off the culling operation within the game entirely! So instead of getting this:



We get this!



Pretty sweet! This is finished up with setting the changed code as an AR (Action Replay) code so that the game can reference it each time. And, there's an entire subreddit dedicated to these codes: [https://www.reddit.com/r/DolphinVRcullin/](https://www.reddit.com/r/DolphinVRcullin/)

AND, someone has posted culling codes for SSX 3! [https://www.reddit.com/r/DolphinVRculli ... cssx_3usa/](https://www.reddit.com/r/DolphinVRcullin/comments/8dkdtk/gcssx_3usa/) Unfortunately, these don't seem to work for me. I'm not sure if that's because they were done with an older version of Dolphin VR and/or game, but we have a method of taking the culling away for our ripping!

For an in-depth guide on how to do this, you can either reference this page, or check out the code block below: (Again, posting as text for posterity sake): [https://forums.oculusvr.com/t5/Games-an ... rue#M34587](https://forums.oculusvr.com/t5/Games-and-Apps/Dolphin-Emulator-CV1-compatibility/m-p/401451/highlight/true#M34587)

```
1. OPEN DolphinVR and RUN the game you want to Cull. (Run it with no HMD's running, so DolphinVR runs in 2D mode), Also go to your Documents > Dolphin Emulator > Screenshots folder (or wherever your default screenshots folder is) and DELETE everything you have in there to make things a little simpler later, keep this screenshots folder open.

2. Make sure you have FreeLook enabled and once you get to a point in the game where you are in control (Like a hub world) Hold down the Left and Right mouse buttons over the game window and DRAG your mouse to ROTATE the camera around behind you or to a point where the screen has been culled to black or when you can only see a very small amount of scenery. (You may need to go as far as completely moving the camera to a new position).

3. PAUSE the game, go to the Main Dolphin Window and go to Tools > Debugger, rearrange your windows so you can see everything clearly.

4. (OPTIONAL: I do it anyway because it might make a difference I don't know...) Go to Symbols > Clear Symbols, Click "Yes" on the dialog box, then go to Symbols > Generate Symbol Map.

5. Symbols > Save Symbol Map As... And take note of the game code as this will be the name of the folder generated in the screenshots folder, Click "Save", making sure it is saved in the "Maps" Directory (Alternatively you could just click Symbols > Save Symbol Map, and it will just save without the pop-up "Save As" box)

6. IMPORTANT: BEFORE DOING ANYTHING ELSE!
Hit SHIFT-F1 to Save State in Slot 1 (OR go to Emulation > Save State > Slot 1) , this will be called by the Bruteforcer as a reference to be used with the .map file, it is VERY IMPORTANT that you DO NOT UNPAUSE THE GAME between saving the .map file and saving to Save Slot 1

7. Hit the STOP button on the emulator and EXIT DolphinVR, Create a shortcut to DolphinVR somewhere, preferably on the Desktop if you haven't got one there already, Right-Click on the Shortcut > Properties, then add the line...
-bruteforce 0 
OR
-bruteforce 1 

...to the end of the "Target:" textbox as shown below. Click Apply and then RUN DolphinVR

(I try to Bruteforce 0 first, then if i don't get any results Ill change it to 1 and do another run of bruteforcing)

8. If everything goes well, DolphinVR should open and start running through the Bruteforcing process automatically, your screen should look similar to what is shown below. Notice that the Screenshots folder now has a file called position.txt and a folder in it.

9. Inside the newly created folder there should be an ever increasing number of screenshots plus an .xml file or two, Right Click anywhere in the folder and Arrange Icons By > Size, making sure that the bigger screenshots are at the top.

As the bruteforcing process is happening you may encounter errors like the one above, this is normal and happens every so often, DolphinVR will almost always crash... but don't worry! the position.txt file saves the number of screenshots it has already saved and continues from where it left off.

If for any reason you want the bruteforcer to start again, delete the position.txt file, more advanced users may want to jump ahead to a certain place in the bruteforcing timeline, you can edit the position file to start from the 2000th screenshot for example.

10. and....WAIT....HOLY SHIT!

While creating this tutorial, I didn't expect to actually find a culling code! WOOOO BONUS! Normally you could expect to be waiting maybe HOURS for a screenshot to pop up that removes culling successfully... just letting you know! :tongue:

So now that we have our screenshot...what the hell do we do with it? Well it is quite simple really, you use this code as a template...

04yyyyyy    6000000x (where x = -bruteforce x, command line)
04yyyyy(y+4)4E800020
Where the y's are is the code that was in the name of the screenshot, the second line you need to add 4 in hexadecimal, FOR EXAMPLE: if the top one is 0400000F then the bottom needs to be 04000013, and so on...

Once you code is added... run the game and see how it goes... and for me... it didnt actually go that well... turns out this code is a dud! I'll just have to keep looking!
```


The next hurdle, or brick wall more like it, is render distance. Dolphin can only show so much of the game depending on how the game was coded, so once we're out of that view range, the models seem to disappear. This could possibly be changed with it's own AR code, but if it exists I haven't been able to find it. I've ran both the 0 and 1 bruteforcer for a while and haven't gotten the results I'm looking for, but I'll keep trying!

I also tried a somewhat hybrid of these two methods as well, which is using Dolphin's built in debugging to try and find where the map models are located. There were a few tools needed for this, Dolphin's built in cheat creator, and it's FIFO recorder/player/analyzer.

The cheat creator works much like the brute forcer, it's just far more manual. You give it a memory address range to search, and a value to look for in those addresses, and change the value from 1 to 0 (or 0 to 1) and see what happens. People often use this for infinite money/health/ammo cheats, but it can use any memory address, so there's nothing stopping it from changing anything else. I tried for a bit to play around with the values from the aforementioned culling code for SSX 3, but I wasn't able to get it to work. 

Now, the FIFO tool is much much different. For those who are unsure of what FIFO is:

FIFO stands for 'First In First Out'. Put very simply, it's a buffer in the gamecube's RAM that let the CPU and GPU talk to each other, and what allowed the CPU to send commands to the GPU to render your game! (For an in-depth explanation on the Gamecube's architecture, check this: [https://www.copetti.org/writings/consoles/gamecube/](https://www.copetti.org/writings/consoles/gamecube/))

So, Dolphin has a built in tool to analyze this memory buffer, and output exactly what it's doing for each frame that's rendered. You tell it how many frames to record, click record, save the file, then load it up in the analyzer. I did so for a scene (The one I showed above actually) and this was my output: 



I had it analyze 15 frames, but we only really needed one. There was a total of 773 object rendered in the scene, and it has an output for both all of those objects, and some EFB Copies. With the FIFO tool, we can also have it loop a single frame, and then remove/readd the objects in the scene, either one by one or for an entire range. This is how we can find what object is what, and I did just that! For frame 1, this was the list of objects in the scene:

```

0 - 14 - Rider Shadow
14 - Skybox
15-31 - Environment Map
32-256 - Map/World Object
257 - 275 - Rider
276 - 290 - Rocks
291-296 - Rails
297 - 320 - Trees (Probably Low LOD)
321 - 324/470/473/475 - Barriers
325 - 370/405 - 425/450 - 466 - Track Objects (Crowd, stands, etc)
371 - pebbles/snow clumps
372 - 396 - Tree Details (Probably Low LOD)
397 - 404 - Powerups
426 - 449 - More Trees (Probably High LOD)
467 - 469/474 - Money
471 - 472 - Waterfalls
476 - 480 - Smoke/Clouds
481 - 482 - Lights
483 - 767 - Snowflakes
768 - 769 - Rider Trails
770 - 772 - Powerup Lights
```


And, when going to the analyzer to reference Object 32:



Hello vertex and texture mapping information!! To me this seems like a really awesome place to try and fine the specific vertex data for each object/scene to then get them from the game's hex files, but unfortunately, there's no information here on what file they are getting these from.

SO DANG CLOSE! I feel like I'm this close to getting these stinking models, but there's always just one little thing that's stopping me. It's probably just my lack of knowledge of hexadecimal, but I don't know.

This is as far as I've gotten sadly. I've pieced together all of this information over the past 2 days, and I feel like I've gotten a lot farther than most, but I need that last bit of help to get me to the goal, so I'm here!

If anyone can help me get a little farther in any of this, I think that's what would allow us to really crack open these models and get them in the hands of the players. Not that they were meant for that, but hey, the game's almost 20 years old now lol. Thanks for your time!
## Post #2
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-02-23T08:52:38+00:00
- Post Title: Extracting 3D Map Models from SSX 3

Oh my god man!
Thats some sweet sweet Progress!!
Theres .mnf .mpf and .mxf ...depending on GameCube, ps2 or Xbox.

But man!
I Always wanted to do what you Just did Here!!!
The ssx Community would Love that!

Thanks for your Work in this!
## Post #3
- Username: modeco80
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 15, 2020 11:04 am
- Post datetime: 2022-02-23T08:58:55+00:00
- Post Title: Extracting 3D Map Models from SSX 3

BAM.[x]DB is loaded by the game to provide essential track information (where in the stream to seek, track begin chunks, yada...)

BAM.[x]SB is the actual data that you should shift your attention to, and is essentially formatted like this (loosely following the actual BX code style, at least typenames):

```
	uint32_t Magic; // 'CBXS' for a typical file chunk, 'CEND' for the last/ending file chunk
	uint32_t NextOff; // size in bytes to next tBxStreamingFileHeader
};

// After this, aligned RefPack (EAC LZSS) compressed data follows

```


To make things even "better" (worse), once you decompress all of the files from the stream data, you get a bunch of "interleave" files
which conform to another data format. Which is:

```
	// Retail PS2:
	// 2 - world models (not beziers)
	// 3 - unknown
	// 9 - "Shape" (texture)
	// 10 - Lightmap (32bpp)
	// 20 - Audio bank (presumably used to stream in course specific sfx)
	uint8_t type;
	uint24_t size; // could also be "next offset". Note that uint24_t is not a real C type, and this is probably a bitfield?
	
	uint32_t RID; // resource ID? unknown what this actually means, but the acronym comes up in code
};
// file data until next tBxInterleaveFileHeader proceeds...

```


I've already written a tool to extract this data (and subsequently uninterleave the decompressed interleave files), but I've only verified its output on PS2 (and I really need to clean it up at some point): [https://github.com/SSXModding/makecbxs](https://github.com/SSXModding/makecbxs)

Also - just to address it, models using `.m[x]f` (or, .mpf on PS2) as an extension is very unrelated to the PathFinder/SNDPATH_/PATH_ mapfile format, and more a unfortunate collision of extension. Data between the two are completely different.
## Post #4
- Username: hoopera
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 20, 2016 12:18 am
- Post datetime: 2022-02-23T14:54:22+00:00
- Post Title: Extracting 3D Map Models from SSX 3

> Reply from modeco80 ↑Wed Feb 23, 2022 4:58 pm at Wed Feb 23, 2022 4:58 pm
>
> 
BAM.[x]DB is loaded by the game to provide essential track information (where in the stream to seek, track begin chunks, yada...)

BAM.[x]SB is the actual data that you should shift your attention to, and is essentially formatted like this (loosely following the actual BX code style, at least typenames):
Code: Select allstruct tBxStreamingFileHeader {
	uint32_t Magic; // 'CBXS' for a typical file chunk, 'CEND' for the last/ending file chunk
	uint32_t NextOff; // size in bytes to next tBxStreamingFileHeader
};

// After this, aligned RefPack (EAC LZSS) compressed data follows


To make things even "better" (worse), once you decompress all of the files from the stream data, you get a bunch of "interleave" files
which conform to another data format. Which is:
Code: Select allstruct tBxInterleaveFileHeader {
	// Retail PS2:
	// 2 - world models (not beziers)
	// 3 - unknown
	// 9 - "Shape" (texture)
	// 10 - Lightmap (32bpp)
	// 20 - Audio bank (presumably used to stream in course specific sfx)
	uint8_t type;
	uint24_t size; // could also be "next offset". Note that uint24_t is not a real C type, and this is probably a bitfield?
	
	uint32_t RID; // resource ID? unknown what this actually means, but the acronym comes up in code
};
// file data until next tBxInterleaveFileHeader proceeds...


I've already written a tool to extract this data (and subsequently uninterleave the decompressed interleave files), but I've only verified its output on PS2 (and I really need to clean it up at some point): https://github.com/SSXModding/makecbxs

Also - just to address it, models using `.m[x]f` (or, .mpf on PS2) as an extension is very unrelated to the PathFinder/SNDPATH_/PATH_ mapfile format, and more a unfortunate collision of extension. Data between the two are completely different.

Oooo nice! That certainly did something! So if what I think is happening is right, these .bin files that are created from it are essentially the different tracks stitched together? Is there any way to read these files or export them to a model besides hex2obj/3d Model Reasearcher? If not, did you happen to know where I could start with finding the vertex and face data?
## Post #5
- Username: hoopera
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 20, 2016 12:18 am
- Post datetime: 2022-02-23T15:35:51+00:00
- Post Title: Extracting 3D Map Models from SSX 3

> Reply from Henchman800 ↑Wed Feb 23, 2022 4:52 pm at Wed Feb 23, 2022 4:52 pm
>
> 
Oh my god man!
Thats some sweet sweet Progress!!
Theres .mnf .mpf and .mxf ...depending on GameCube, ps2 or Xbox.

But man!
I Always wanted to do what you Just did Here!!!
The ssx Community would Love that!

Thanks for your Work in this!

Don't thank me lol, I'm just piecing info together that everyone else already found out
## Post #6
- Username: modeco80
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 15, 2020 11:04 am
- Post datetime: 2022-02-23T21:19:00+00:00
- Post Title: Extracting 3D Map Models from SSX 3

> Reply from hoopera ↑Wed Feb 23, 2022 10:54 pm at Wed Feb 23, 2022 10:54 pm
>
> 
Oooo nice! That certainly did something! So if what I think is happening is right, these .bin files that are created from it are essentially the different tracks stitched together? Is there any way to read these files or export them to a model besides hex2obj/3d Model Reasearcher? If not, did you happen to know where I could start with finding the vertex and face data?

Each bin file seems to be

- one interleave file for some piece (or all?) textures/lightmaps
- one interleave file for some piece of track data (models, beziers, Luno script bytecode, audio bank, so on, so forth..)

This data layout seems to be intentional, as they only need to upload (or keep in memory) textures once, whereas for track data they have to load piece by piece.
## Post #7
- Username: hoopera
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 20, 2016 12:18 am
- Post datetime: 2022-02-25T18:04:33+00:00
- Post Title: Extracting 3D Map Models from SSX 3

> Reply from modeco80 ↑Thu Feb 24, 2022 5:19 am at Thu Feb 24, 2022 5:19 am
>
> 
hoopera wrote: ↑Wed Feb 23, 2022 10:54 pm
Oooo nice! That certainly did something! So if what I think is happening is right, these .bin files that are created from it are essentially the different tracks stitched together? Is there any way to read these files or export them to a model besides hex2obj/3d Model Reasearcher? If not, did you happen to know where I could start with finding the vertex and face data?


Each bin file seems to be

- one interleave file for some piece (or all?) textures/lightmaps
- one interleave file for some piece of track data (models, beziers, Luno script bytecode, audio bank, so on, so forth..)

This data layout seems to be intentional, as they only need to upload (or keep in memory) textures once, whereas for track data they have to load piece by piece.

Interesting! I do know that SSX 3 pieces together a track in realtime by streaming different sections of it together, and upon looking at these in HexEdit I can definitely see some good info!

For others viewing the thread, I discussed this a bit more on the SSX community discord, and Modeco80 here was more than helpful! Upon sending me that program of theirs, I was able to extract the bam.xsd to a folder (Yeah .XSD. Though, this tool will work for the .SSB and .GSB versions, which are from the PS2 and Gamecube respectively) and got all of these files and folders!



Going into any of the uninterleaved folders shows this:



According to Modeco80 and Kris2ffer, these different numbered files correspond to different aspects of the track.

```
_3 = Bezier Patch data (SSX 3 uses Bezier Patches to give it's snow a very smooth appearance with very little performance/memory impact. Read more: https://www.gamedeveloper.com/programming/dynamic-level-of-detail-terrain-rendering-with-b-zier-patches)
_9 = Textures
_10 = Lightmaps
_14 = Collision model
_20 = Most likely music, or data that affects how the music plays. Unsure of what it is exactly.
```


Upon opening the 256_2.bin file for example and aligning the data to 32 columns, this is what I can see in HexEdit:




Now I don't know about you, but looking at these and referencing shakotay2 in his post here: [viewtopic.php?t=10894](https://forum.xentax.com/viewtopic.php?t=10894)

This looks like vertex and face data! So that's really promising! But there's a bit of an issue. While we should be able to get just the track model somehow, getting the smooth snowy surface is a whole, entirely different bag.

Remember that bezier patch data I referenced above? Well, that's how the game pieces together the track to keep it all smooth, and getting something like a 3D model from that seems to be...very difficult considering how NURBS are interpreted. If that's possible to get from files like this, I have no idea how or where to even start.

But, the snow isn't all that big of a deal to me, really. I kinda just wanted to the track model and the different props and such in the world to mess around with them in 3D programs like Blender or put them in different game engines, or make something cool in like VRChat. At this point though, I'm kinda stuck unfortunately! If anyone's got ideas for where to go, please do let us know!!
## Post #8
- Username: ssxmapper
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 24, 2022 8:12 pm
- Post datetime: 2022-10-24T12:15:45+00:00
- Post Title: Extracting 3D Map Models from SSX 3

Hi,

I have just figured out how to extract the curved surfaces from the SSX and SSX Tricky maps, so that information may help you with SSX 3. See:
[https://youtu.be/d3-8wFibjC4](https://youtu.be/d3-8wFibjC4)
[https://github.com/SsxMapper/SSXandTrickyMapExtractor](https://github.com/SsxMapper/SSXandTrickyMapExtractor)

Possibly SSX 3 uses the same format.
