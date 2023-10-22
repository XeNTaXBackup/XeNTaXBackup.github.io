## Post #1
- Username: DrAwesomeXD
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 10, 2017 3:38 am
- Post datetime: 2019-03-29T19:48:55+00:00
- Post Title: Best way to extract multiple animations from Noesis?

I recently made a model and animation importer for a file format in Noesis.
this is related to this topic: [https://forum.xentax.com/viewtopic.php?f=16&t=19538](https://forum.xentax.com/viewtopic.php?f=16&t=19538)
@bigchillghost, thanks for the tip regarding the seams.
Also, your recent bone tutorials were really helpful to me.

So my imported animation data looks like this:
[](https://ibb.co/SPw1Tpr)
[image uploader](https://de.imgbb.com/)

When I export the model as FBX or DAE, the resulting model has all animations concatenated into a single take.
I tried to use -fbxmultitake option in Noesis 4395 and 436 but doesn't seem to do anything. 
What would be the best way to get an fbx or dae file with multiple takes?
There's a lot of files to convert so I don't think I can split them manually without losing my mind lol.
I'm thinking of using blender import scripting or maybe even the fbx sdk as an alternative but if anybody knows a simpler fix without ditching Noesis completely, I'm up for it ^^
## Post #2
- Username: DrAwesomeXD
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 10, 2017 3:38 am
- Post datetime: 2019-04-03T14:53:26+00:00
- Post Title: Best way to extract multiple animations from Noesis?

Nevermind, I figured it out!
The solution is to choose the menu item "File -> Export from Preview" instead of "File -> Export" and then use -fbxmultitake. The export argument will then be used correctly.
I have no idea why that is. Maybe anybdody knows whats up?
Only problem remaining is that batch exporting will not work because you have to preview the file first.
