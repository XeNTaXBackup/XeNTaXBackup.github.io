## Post #1
- Username: hoopera
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 20, 2016 12:18 am
- Post datetime: 2016-10-19T16:44:02+00:00
- Post Title: How to extract Dark Souls 1 map models

Hey everyone! So for a really long time I wanted to figure out how to extract the map models from Dark Souls 1 for use in other applications. It took a lot of digging but from piecing together information from this ([https://facepunch.com/showthread.php?t=1262653](https://facepunch.com/showthread.php?t=1262653)) post i was able to figure it out.

Let's start with the prerequisites:
1. A way to view the Dark Souls maps outside of the game. For that, we'll use DSMODT: http://www.nexusmods.com/darksouls/mods/983/?
2. A way to rip the models from DSMODT to a somewhat usable file. For that, we'll use Ninja Ripper: http://gamebanana.com/tools/5638
3. A way to view and extract the ripped files. For that, you will need both Noesis: http://richwhitehouse.com/index.php?con ... sv4202.zip and the ninjaripper script for it: http://www.mediafire.com/download/gr30v ... per_rip.py
4. A 3D Editing program of your choice. Blender will work.

Once you have ALL of that, we can begin.

Take these steps to extract the maps:
1. Open up Ninja Ripper.
2. Click the button next to the .exe box for the target application.
3. Locate wherever you extracted DSMODT and add DSMODT's .exe.
4. Make sure the injection method is set to "Intruder Inject" and click run.
5. Point DSMODT to where you have Dark Souls installed.
6. Let it load, then choose whatever map you want to extract.
7. Once the map has loaded, click the little blue button on the left and change the preferred camera mode to FPS
8. Use the mouse and WASD keys to zoom out to where the whole map is visible.
9. Press F12 to extract both the model and the textures all at once. Depending on the map and your computer this can take some time.
10. Now, navigate to wherever you have DSMODT installed and look for the folder named "_NinjaRipper"
11. From here, go to the folder that's in there that should coincide with the date/time you extracted the model.
12. In here, you should see a whole bunch of files named "Mesh_xxx.rip" and "Tex_xxx_x.dds". These are the extracted files from ninja ripper of the map.
13. Now, load up Noesis, and navigate to the folder you just found.
14. At the top, click tools, then batch process.
15. From here click "Folder batch" and select the folder with all the .rip files.
16. Make sure the input is rip, but you can set the output to whatever you like (I keep it at obj just to be safe.)
17. Click Export. Congrats! You now have a dark souls map in a readable, editable 3D format!
18. Open the newly exported models in whatever 3D program you wish, and apply the corresponding texture to that model. 

At this point you should be about done. To get the models looking correct you'll need to do some manual editing, but hopefully I saved quite a few people some headaches by lining this out as best I could. Have fun guys!
## Post #2
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-10-21T16:21:14+00:00
- Post Title: How to extract Dark Souls 1 map models

Good idea, but I think we already have direct extraction methods for the maps that do not require ninjaripper, and direct extraction is always preferable.
## Post #3
- Username: hoopera
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 20, 2016 12:18 am
- Post datetime: 2017-03-27T18:32:32+00:00
- Post Title: How to extract Dark Souls 1 map models

> Reply from Portugalotaku
>
> Good idea, but I think we already have direct extraction methods for the maps that do not require ninjaripper, and direct extraction is always preferable.

Wait seriously? Can you point me in the right direction? I'm always looking for easier methods.
