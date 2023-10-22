## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-28T15:56:04+00:00
- Post Title: Uncharted: Nathan Drake Collection Exporter (PS4)

Hey,

I made a program to view/export models from the Uncharted trilogy on ps4. The main focus was to get the characters to load, but it seems to work fine with other stuff too : animals, props, maps etc.

So the program looks like this


Main Form
- Select the pak file that has the meshes.
- For the skeleton you might need to specify a separate pak file. UC1 seems to have meshes and the skeleton in a single pak file. For UC2/UC3 you will probably need to select "-base" paks as separate skeleton files.
- Select "No skinning" if you don't want the skeleton to be loaded. Meshes will also be non-skinned. This is mostly necessary for loading map files.
- Click "Load".

3D Preview
- You can see the meshes and the skeleton contained in the pak files here.
- Skeleton will appear mirrored in the preview, it will be normal when you export the model.
- Preview controls:

Right-click and move mouse : Orbit around model
Ctrl + Mouse Wheel Scroll : Zoom
Mouse Wheel Click and move mouse : Pan

Exporting
- Click the "Export" button to export the model 
- Non-skinned meshes will be exported as obj.
- Skinned meshes and the skeleton will be exported as iqe.
- How to load iqe:  [viewtopic.php?p=138153#p138153](http://forum.xentax.com/viewtopic.php?p=138153#p138153)

Textures 
- Use this to export the textures : [viewtopic.php?p=138150#p138150](http://forum.xentax.com/viewtopic.php?p=138150#p138150)

Download:  [http://www.mediafire.com/file/4elmplnmu ... porter.rar](http://www.mediafire.com/file/4elmplnmupzl0tw/NDCExporter.rar)

Some examples :

Elena's winter model from UC2


Part of Yemen map from UC3


Note:  Use "No skinning" for maps. Also most of the times the objects will be placed at the origin, on top of each other. So it won't look like a complete map. You can export the map to see the individual meshes, but you will need to position them manually.

Thanks to
- volfin for providing all necessary resources
- daemon1 for his video tutorials
## Post #2
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2018-02-28T23:14:00+00:00
- Post Title: Uncharted: Nathan Drake Collection Exporter (PS4)

Wow, even maps?!
I'll have to test this. Thanks! 


Edit: I think you created the The Last of Us PS4 exporter too.
Is there any chance it could support loading the maps?
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-01T01:12:34+00:00
- Post Title: Uncharted: Nathan Drake Collection Exporter (PS4)

> Reply from lolwatt
>
> 
Edit: I think you created the The Last of Us PS4 exporter too.
Is there any chance it could support loading the maps?

I am planning to update the TLOU exporter in couple of days. Working on the uncharted files, I noticed that the tool can be improved. It should support the map files properly after the changes.
## Post #4
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2018-03-01T03:04:23+00:00
- Post Title: Uncharted: Nathan Drake Collection Exporter (PS4)

Am I understanding correctly, its possible to export the meshes in their correct positions, eventhough in the viewer they'll all be set to 0? but upon export they'll be in the same order as in the game.

How does this work for meshes that're duplicated many times? Such as a barrel or wood planks etc?
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-01T07:57:31+00:00
- Post Title: Uncharted: Nathan Drake Collection Exporter (PS4)

> Reply from lionheartuk
>
> Am I understanding correctly, its possible to export the meshes in their correct positions, eventhough in the viewer they'll all be set to 0? but upon export they'll be in the same order as in the game.
Unfortunately no, maybe I formulated it wrong in my post. All of the meshes are placed at the origin. Position where the meshes appear is purely based on vertex positions. Actor meshes have global vertex positions, so when the they are loaded everything will appear in the right place. Still all of of the mesh nodes are placed at 0.

That is not the case for map meshes.  The meshes need to be transformed in order to appear in their correct positions, but I haven't really looked into that. There might be a part in the file that contains all the transformations. I can take a look when I have the time.
## Post #6
- Username: Skryle
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 09, 2018 5:06 pm
- Post datetime: 2018-04-05T21:22:02+00:00
- Post Title: Uncharted: Nathan Drake Collection Exporter (PS4)

Software supports TLOU ?
## Post #7
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-05T22:10:52+00:00
- Post Title: Uncharted: Nathan Drake Collection Exporter (PS4)

> Reply from Skryle
>
> Software supports TLOU ?
[viewtopic.php?t=15816](http://forum.xentax.com/viewtopic.php?t=15816)

This should work fine with the characters/animals/objects. I have a new version ready that can load the maps, will release it in couple of days.
## Post #8
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-04-07T19:07:44+00:00
- Post Title: Uncharted: Nathan Drake Collection Exporter (PS4)

Hi i just wonder why the models look like this in Blender when the texture's are applied?
Does anyone else have this issue?

Oh and it happens on the Last Of Us models too
[Diversuit.JPG](https://xentaxbackup.github.io/file/14175_Diversuit.JPG)
## Post #9
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2018-04-10T14:54:00+00:00
- Post Title: Uncharted: Nathan Drake Collection Exporter (PS4)

Ok, so this looks awesome, I admit, and I'd VERY much like to try this... but, how exactly does one GET the Nathan Drake Collection onto one's computer? I've looked for torrents and such to download the files, but there aren't any. And yes, I do own the game, but I don't have a blu ray player for my computer, so.... not sure what to do.
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-10T18:27:43+00:00
- Post Title: Uncharted: Nathan Drake Collection Exporter (PS4)

> Reply from kingfisher13
>
> how exactly does one GET the Nathan Drake Collection onto one's computer?
Check psxhax forums. You can find decrypted game back ups there.
## Post #11
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-04-10T21:13:52+00:00
- Post Title: Uncharted: Nathan Drake Collection Exporter (PS4)

If anyone is having the same issue as i did
All you have to do is convert the DDS to TGA then everything looks fine
## Post #12
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2018-04-11T16:36:34+00:00
- Post Title: Uncharted: Nathan Drake Collection Exporter (PS4)

Ok, so I found a hacked copy of the game, but its in a friggin PKG file, and the only tool I've found to extract these files doesn't work, because the only tutorial I found on how to use it, is wrong. I get a syntax error when I follow it exactly
## Post #13
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-11T17:06:22+00:00
- Post Title: Uncharted: Nathan Drake Collection Exporter (PS4)

> Reply from kingfisher13
>
> Ok, so I found a hacked copy of the game, but its in a friggin PKG file
Use the Fake PKG Generator. Passcode should be all 0s.
## Post #14
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2018-04-11T17:36:36+00:00
- Post Title: Uncharted: Nathan Drake Collection Exporter (PS4)

I downloaded the fake PKG generator, it makes no sense, and has no instructions... there aren't even any tutorials online...

I almost got a virus in the process of downloading the d*mn thing too, the file host its uploaded to is REALLY shady.
## Post #15
- Username: Neo241
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 08, 2020 3:06 pm
- Post datetime: 2020-12-18T08:40:34+00:00
- Post Title: Uncharted: Nathan Drake Collection Exporter (PS4)

Can this be updated to support Textures on Maps as well?

Would love that
Thank you!!!
## Post #16
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-18T10:22:07+00:00
- Post Title: Re: Uncharted: Nathan Drake Collection Exporter (PS4)

> Reply from Neo241 ↑Fri Dec 18, 2020 4:40 pm at Fri Dec 18, 2020 4:40 pm
>
> 
Can this be updated to support Textures on Maps as well?
It can. I am planning to revisit this some time, but can't promise anything atm.
