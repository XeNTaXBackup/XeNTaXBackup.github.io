## Post #1
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-20T02:46:18+00:00
- Post Title: [REL] Natural Selection 2 MeshTool

Not sure what the devs were thinking when they engineered the model format for this game. Their vertex buffer structure is 92 bytes long which could of easily been around 40 if they actually utilized common compression techniques like compressing the UVs into halffloats or store bone indicies as bytes instead of 32bit integers. Anyway I don't think anyone cares thats reading this so I'll stop bitching.


Whats Included?

meshtool.exe
XY_Fix.ms
Mesh2Obj.bat
Mesh2Smd.bat
(bunch of txt files)
Instructions:

I've included some batch files to help ease the use since this is a command line tool it may be difficult for some people that aren't very competent with computers, well actually I have no idea why you would even use this tool if you have no clue on how to use command line applications.

If you want the output to be an obj mesh just drag and drop a .model file onto the Mesh2Obj.bat it should then create an output folder with the resulting mesh. Same applies for the Mesh2Smd.bat just dragdrop onto it.

For more info on the usage of the tool just run the exe and it will give you the usage commands I don't go through it because the Readme.txt has all the info you need.

As for the Maxscript file XY_Fix.ms it can be used with 3DS Max to fix the rotation of the models if you're exporting to SMD since it defaults to the Maya method (Y is Up/Down). Though please note some models may break if bones are not linked properly.

Lastly I'd like to thank [chrrox](http://forum.xentax.com/memberlist.php?mode=viewprofile&u=4722) for his help with this.



Download:
[http://dev.cra0kalo.com/?p=103](http://dev.cra0kalo.com/?p=103)
or here locally


 NS2_Meshtool_v1.zip
(22.02 KiB) Downloaded 56 times
## Post #2
- Username: kmthrong
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Oct 22, 2014 9:19 pm
- Post datetime: 2014-10-22T13:27:15+00:00
- Post Title: [REL] Natural Selection 2 MeshTool

Good but how can I extract the 3d models. I meant where are there(In which .dat or .fat file)??with which formats?
## Post #3
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2014-12-07T14:14:21+00:00
- Post Title: [REL] Natural Selection 2 MeshTool

Well I tried your tool and at first i was exited, only to find that the UV maps are destroyed. The models are exported and they look ok, but the UV map coordinates are missing. Maybe it's due to an update of the game? (I tried to open the marine models - female and male models, all of them have the same problem)
## Post #4
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-12-07T14:32:44+00:00
- Post Title: [REL] Natural Selection 2 MeshTool

> Reply from napoleon321
>
> Well I tried your tool and at first i was exited, only to find that the UV maps are destroyed. The models are exported and they look ok, but the UV map coordinates are missing. Maybe it's due to an update of the game? (I tried to open the marine models - female and male models, all of them have the same problem)
could be an update to the game because the UVs and all were working perfectly fine when I did it. Attach some samples or pm me them ill have a look.
