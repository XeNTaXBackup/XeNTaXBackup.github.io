## Post #1
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-01-22T23:54:56+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Character Models

Hey guys,
I've been digging alot through Backyard Wrestlings (Ps2) files recently and wanted to share what I discovered so far.

First of all I gotta thank albinoleopard for creating all those BMS scripts including 3 for Backyard Wrestling([https://zenhax.com/viewtopic.php?t=8](https://zenhax.com/viewtopic.php?t=8)). I used these scripts to extract models and textures from the game. Sadly the scripts are just numbered and you will end up with a couple thousand files. I tried to contact albinoleopard about this via email but he never replied. So here is what I got:



Archive:
The main file on the disc amongst the .pss and movie files is the GAMEDATA.WAD (670.220 KB). It contains all of the games assets like textures models and sounds. Using albinoleopards Bms script "BackyardWrestlingDTTAHwad.bms" I was able to extract a total of 1076 files. 867 being listed as Type: Data and 209 as Type: MESH-Data.



Textures:

The textures are extracted by using the BMS script "BackyardWrestlingDTTAwadTexture.bms" on the GAMEDATA.WAD file. You will end up with 1009 .TXD files. Meaning they can be converted with other programs. Here is an example:





Sounds:

The sound files were the toughest ones to obtain. I tried cubeplayer, raw import in audacity and MFAudio. I finally managed to get all the level based and character sounds by using the directory scan function in psound. Well that was my latest archievment.



3D-Models:

This is where I'm lost. I used albinoleopards third script "BackyardWrestlingMeshto3dsUVbeta.bms" to convert all the .mesh files into 3ds files with uv-cords (excluding character models). The 3ds extraction results in even more files. I found out that Backyard Wrestling stores all 3D models used for a level in group-files (the .mesh files).
Via alot of importing and deleting nameless (just numbered) files in blender I found out that the following files contain all 3D models used for the levels listed next to them:

FILE NAME_______________FILE SIZE_______________LEVEL
96.mesh_________________2.189 KB________________Backyard
107.mesh________________3.462 KB________________Truck Stop
118.mesh________________3.524 KB________________Mansion
129.mesh________________2.741 KB________________Gentlemans Club
140.mesh________________2.756 KB________________Mall
151.mesh________________2.944 KB________________Slaughter House
161.mesh________________2.662 KB________________TV Studio
171.mesh________________2.563 KB________________TV Studio 2
181.mesh________________3.522 KB________________Mansion 2

Kind of funny that there is two versions of each the Mansion and the TV Studio with different file sizes.
However, like I metioned the script doesn't work on the characters. albinoleopard statet that on his side though, but since he never replied, I couldn't ask him why. I still managed to come a little closer to my goal (ripping the characters). By opening random .mesh files with a hex editor I stumbled across a file containing this text:

```
abdomen.........................¸’»µOŒ.ÄsåÃA.......€...€¼.......¸...........chest.n.........................ÞJÇµ£·%ÄsåÃA£¸²½...€...€¼...................l_clavicle......................Ø.Ž@0®<Ä›ê.B£¸²½...€...€¼.......P...........neck.vicle......................‚·.¶{.DÄ‹].B³¸²½...€...€¼.......œ...........head.vicle...................... H*¶ãDRÄðm7A³¸²½...€...€¼.......è...........head_end.e......................~ÕÇµìhjÄ‰.½@³¸²½...€...€¼.......4...........r_clavicle......................Ø.ŽÀ0®<Ä.ê.B£¸²½...€...€¼.......€...........r_shoulder......................<2ÀÂFŠ<Äû].BÖ¸²½...€...€¼.......Ì...........r_bicep.er......................iã"Ãæˆ<Ä.m.BÖ¸²½...€...€¼...................r_forearm.......................A.lÃ?.<Ä Ï.B.¹²½...€...€¼.......d...........r_wrist.m........................õ.ÃOž<Ä±..B.¹²½...€...€¼.......°...........r_hand..m........................¹±Ãt.<Ä±÷.B.¹²½...€...€¼.......ü...........r_metacarpal03......
```

That shows the bone structure and sub models in the .mesh files. Now we now that the characters are build this way:

______________head______________
____________head_end____________
______________neck______________
___r_clavicle__________l_clavicle___
__r_shoulder__________l_shoulder__
_____r_bicep___chest___l_bicep_____
_r_forearm___abdomen___l_forearm_
_____r_wrist___pelvis___l_wrist_____
_____r_hand___________l_hand_____
r_metacarpal__________l_metacarpal
__r_proximal__________l_proximal__
____r_middle__________l_middle____
_________________________________
_________r_thigh__l_thigh__________
__________r_calf__l_calf___________
__________r_foot__l_foot___________
__________r_toe__l_toe____________
______r_toe_end__l_toe_end________

And that adds up to a total of 34 sub meshes in the character .mesh files (if there isn't anything else inside).
Listening to the audio files shows a pattern. Every DATA file containing the audio got a character .mesh-file a number below (e.g.: 221 = MDogg20 audio so 220=MDogg20 character).
Here is a list of the characters I could identify via listening to their vocal recordings:

FILE NAME_______________FILE SIZE_______________CHARACTER
220.mesh_________________218 KB_________________MDogg20
229.mesh_________________232 KB_________________Tylene Buck
238.mesh_________________223 KB_________________Josh Prohibition
247.mesh_________________249 KB_________________Karnage
256.mesh_________________222 KB_________________Gupta
265.mesh_________________205 KB_________________Masked Mike
274.mesh_________________223 KB_________________Violent J
283.mesh_________________227 KB_________________Shaggy 2 Dope
292.mesh_________________225 KB_________________Sabu
301.mesh_________________232 KB_________________Atrocity XXX
310.mesh_________________227 KB_________________Mad Man Pondo
319.mesh_________________227 KB_________________Comissioner
328.mesh_________________221 KB_________________Kitana
337.mesh_________________224 KB_________________Evil Dead
346.mesh_________________231 KB_________________Masked Horndog
355.mesh_________________233 KB_________________El Drunko
364.mesh_________________212 KB_________________Sally
373.mesh_________________213 KB_________________Jezebel
382.mesh_________________245 KB_________________Jamie Madrox
391.mesh_________________237 KB_________________Monoxide
400.mesh_________________209 KB_________________Tom Dub
409.mesh_________________230 KB_________________Rude Boy
418.mesh_________________235 KB_________________Ross Lover
427.mesh_________________217 KB_________________Dameon Redd
436.mesh_________________261 KB_________________Da Bone Doctor
445.mesh_________________242 KB_________________El Chicharron
454.mesh_________________249 KB_________________Sonny D. Chopper
463.mesh_________________232 KB_________________Rosie
472.mesh_________________241 KB_________________Adrianne Pain
481.mesh_________________226 KB_________________Hernia

That makes a total of 30 characters which matches the number of playable characters in the game. noticed a pattern? There is always 9 DATA files inbetween the character .mesh files (one of them being the sound file for each one). There is still some level specific characters that are not included in this structer that i listed (their sounds are within the DATA files for each level).
Here I'm stuck....only other thing to mention is that the executable on the ps2 disc got file paths noted in it. So there might be a way to open the GAMEDATA.WAD with a game extractor using a custom script. Thats beyond my possibilities, though. I gave it a shot with model researcher but i couldn't get a point cloud. Playing around with the padding never got me into the pattern in which the vertecie cords are stored. Or maybe I was wrong.....can't tell.
Thank you for listening, if you are still reading. I hope some of you appreciate the results and the work i put into this and maybe know a way on how I get my hands on them character models.
The BMS spripts by albinoleopard are attached at the end (since his site is down).
As a little bonus: here is a render i did with Twiztid via ninja ripper (you can see that there is issues with the uvs and I had to correct alot to make em look like this), the games main theme ripped ([https://www.youtube.com/watch?v=RFp-Qmc ... qbk0h00410](https://www.youtube.com/watch?v=RFp-QmcUmoE&lc=z22xcdwzhzbhszupn04t1aokgon1qqcsofu3tptgkwpqbk0h00410)) and a screenshot of the square faced t-posed models i found on a website (uploader is not contactable either).


(Sorry but the site I got it from is down)
[BYW_BMS-Scripts.zip](https://xentaxbackup.github.io/file/15545_BYW_BMS-Scripts.zip)
## Post #2
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-01-26T18:16:34+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Character Models

*bump*
91 People saw this post now and i'm not sure if people are either not interested or can't help out with advanced 3d ripping skills. Or maybe i didn't make it clear enough in this topic 
So i kindly want to ask if there is anybody here who can help me getting my hands on the character models in order to provide them to anybody who is interested 
Greetings from Bavaria, germany

EDIT:
Here is the .mesh file of monoxide! .....totally forgot to upload a sample file ^^
Please have a look at it.
[Monoxide(BYW).zip](https://xentaxbackup.github.io/file/15591_Monoxide(BYW).zip)
## Post #3
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-02-05T17:56:19+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Character Models

Is nobody able to help me out on this?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-05T19:12:43+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Character Models

> Reply from Henchman800
>
> Is nobody able to help me out on this?dunno.
PS2 formats are annoying in most cases so, 'yes', most 3D format analysers ignore them.

Did you search for PS2 solutions in the forum that might shed a light on your problem?
here for example: [viewtopic.php?f=16&t=18905&hilit=ps2](http://forum.xentax.com/viewtopic.php?f=16&t=18905&hilit=ps2)
## Post #5
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-02-06T13:01:32+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Character Models

Thanks for the advice!
I tired a couple things already, though. Didn't have luck with creating a bms script and i cant get that poitcloud in model researcher. this is why i was hoping for somebody to help me with that last piece in the line. I don't see where the vertex cords start and end in the uploaded example file :-/


EDIT:

But I see that monoxides character model has been downloaded 5 times 
hopefully you guys can manage to extract some 3d data.
## Post #6
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2019-03-09T15:40:20+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Character Models

Blend file to import mesh files with uvs ,bones and weights.

[http://www.mediafire.com/file/q3416gvoa ... 3-09%5D.7z](http://www.mediafire.com/file/q3416gvoa5lhiss/Blender249%5BBackyardWrestling%5D%5BPS2%5D%5Bmesh%5D%5B2019-03-09%5D.7z)

You need:
[http://download.blender.org/release/Ble ... indows.exe](http://download.blender.org/release/Blender2.49b/blender-2.49b-windows.exe)
and
[https://www.python.org/ftp/python/2.6.6 ... -2.6.6.msi](https://www.python.org/ftp/python/2.6.6/python-2.6.6.msi)

Unpack archive, doubleclick on file "Blender249.blend" , press alt+p in Blender Text Window and import .mesh.

Meshes are split by the same texture (uv mapping).
## Post #7
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-03-12T20:18:07+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Character Models

Jesus Christ on a motorbike!
Holy f****n cow thank you so much for doing this Szkaradek123!!! You really gained some good karma here 

Never worked with blender 2.49 before, i Joined with 2.79. 
Can you help me out here?
Monoxides pivot point doesnt match the rig. Is there further steps to do in order to do the right parenting with the rig?
Thx again man!
## Post #8
- Username: Curtain
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Apr 18, 2017 2:13 am
- Post datetime: 2019-11-23T22:45:32+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Character Models

> Reply from Szkaradek123 ↑Sat Mar 09, 2019 11:40 pm at Sat Mar 09, 2019 11:40 pm
>
> 
Blend file to import mesh files with uvs ,bones and weights.

http://www.mediafire.com/file/q3416gvoa ... 3-09%5D.7z

You need:
http://download.blender.org/release/Ble ... indows.exe
and
https://www.python.org/ftp/python/2.6.6 ... -2.6.6.msi

Unpack archive, doubleclick on file "Blender249.blend" , press alt+p in Blender Text Window and import .mesh.

Meshes are split by the same texture (uv mapping).

Any plans to update this add-on for Blender 2.8X? 
I was helping someone who has been trying to import models from [X-Men: Next Dimension](https://forum.xentax.com/viewtopic.php?f=16&t=21310), but he said the following:

> Reply from huitbgoiouythy
>
> but the script to import mesh is not working 100% sadly and does not open every mesh, when I export to obj there is also problem with normal, many thx to Szkaradek123 for the script
## Post #9
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-11-24T14:35:09+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Character Models

This dude did some magic right there!
I could only Management to do it with the old blender Version...
It would need somebody skilled to Transformer this into a noesis script for instance :-/
## Post #10
- Username: Jamaicano
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Dec 06, 2015 11:52 pm
- Post datetime: 2020-04-06T20:31:32+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Character Models

This world is small ... Albinoleopard is called Michael Peter, he made these BYW scripts in 2013/2014 for me. I had the idea of ​​making a project with the game models and I contacted him to make these scripts I donated 15U $ for his great work. I am happy to see that 7 years later someone is using this to rip the models of this great backyard game. long live Juggalos
## Post #11
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-06T22:49:42+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Character Models

> Reply from Jamaicano ↑Tue Apr 07, 2020 4:31 am at Tue Apr 07, 2020 4:31 am
>
> 
long live Juggalos

Whoop Whoop!
## Post #12
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-07T09:30:59+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Character Models

Shakotay2 is also helping me with level files!
[viewtopic.php?f=16&t=21510&hilit=Backya ... g&start=15](https://forum.xentax.com/viewtopic.php?f=16&t=21510&hilit=Backyard+wrestling&start=15)
## Post #13
- Username: Jamaicano
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Dec 06, 2015 11:52 pm
- Post datetime: 2020-09-27T13:55:54+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Character Models

What is the Mesh file off Josh Asbill?
## Post #14
- Username: Jamaicano
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Dec 06, 2015 11:52 pm
- Post datetime: 2020-09-27T20:30:22+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Character Models

I find.

857.mesh_________________215 KB_________________Josh Asbill
## Post #15
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-09-28T10:26:42+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Character Models

Just wanted to Text you that haha
## Post #16
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2021-09-09T11:24:53+00:00
- Post Title: Re: Backyard Wrestling - Don't Try This At Home Character Models

Could it be that the extracted .mesh files are just plugin generated .3ds files??

[http://paulbourke.net/dataformats/3ds/](http://paulbourke.net/dataformats/3ds/)

Im too much of a noob when it comes to coding to confirm this :-/
## Post #17
- Username: dusttosut
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 21, 2021 1:01 am
- Post datetime: 2021-11-20T17:03:20+00:00
- Post Title: Re: Backyard Wrestling - Don't Try This At Home Character Models

can anyone give me the mesh of tylene buck
## Post #18
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2021-11-21T08:44:37+00:00
- Post Title: Re: Backyard Wrestling - Don't Try This At Home Character Models

> Reply from dusttosut ↑Sun Nov 21, 2021 1:03 am at Sun Nov 21, 2021 1:03 am
>
> 
can anyone give me the mesh of tylene buck
--> [https://p3dm.ru/files/characters/human/ ... -buck.html](https://p3dm.ru/files/characters/human/18575-tylene-buck.html)
## Post #19
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-04-04T08:14:05+00:00
- Post Title: Re: Backyard Wrestling - Don't Try This At Home Character Models

> Reply from Szkaradek123 ↑Sat Mar 09, 2019 11:40 pm at Sat Mar 09, 2019 11:40 pm
>
> 
Blend file to import mesh files with uvs ,bones and weights.

http://www.mediafire.com/file/q3416gvoa ... 3-09%5D.7z

You need:
http://download.blender.org/release/Ble ... indows.exe
and
https://www.python.org/ftp/python/2.6.6 ... -2.6.6.msi

Unpack archive, doubleclick on file "Blender249.blend" , press alt+p in Blender Text Window and import .mesh.

Meshes are split by the same texture (uv mapping).

finally was able to upload every wrestler!
im having trouble though with this .mesh file....its got character structure inside aswell....and your plugin is giving one root bone and this error message in the console:

```
Checking for installed Python... got it!
Traceback (most recent call last):
  File "starter.py", line 137, in Parser
    if sys.ext=='mesh':sys.parseFile(meshParser,'rb',log=0)
  File "C:\Users\---\Desktop\Blender249[BackyardWrestling][PS2][mesh][2019-03-09]\newGameLib\myLibraries\binaresLib.py", line 960, in parseFile
    function(self.input,g)
  File "starter.py", line 29, in meshParser
    skeleton.draw()
  File "C:\Users\---\Desktop\Blender249[BackyardWrestling][PS2][mesh][2019-03-09]\newGameLib\myLibraries\skeletonLib.py", line 133, in draw
    self.create_bone_connection()
  File "C:\Users\---\Desktop\Blender249[BackyardWrestling][PS2][mesh][2019-03-09]\newGameLib\myLibraries\skeletonLib.py", line 230, in create_bone_connection
    parentName=self.boneList[parentID].name
IndexError: list index out of range
```

Here is the file in question:


 4862.zip
character mesh not working (66.66 KiB) Downloaded 13 times



could you please have a look at this?
thank you so much!
