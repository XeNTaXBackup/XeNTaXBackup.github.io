## Post #1
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-04-09T02:48:41+00:00
- Post Title: Halo 5: Guardians Waypoint Models (.js & .json)

So a lot of people have been working with models ripped from 343i's Waypoint site through the site's armor customization feature. Someone I was in contact with had given me a TXT file that listed all the URL addresses of the models and textures, which I was able to get the textures directly and am working on upscaling them. The issue is that some armors are missing from download links I've seen of other people's Waypoint rips, and I would like to try to get them. My ther goal is to make sure that the highest poly models are being used rather than lower poly ones.

The issue is that, while able to download the files, they are all stored in .js format. After some research, I've come across a program known as ThreeJS which allows users to convert typical 3D files into JS or JSON files. I tried importing these models directly into ThreeJS' editor feature, but it would not open them up. The editor would not display dialog, unlike if I tried to import a non-compatible file type. I tried suing both the .js and .json extension, but to no avail.

Currently, the master TXT file lists all the armors in low, medium, and high poly forms.
Here are links to the files (which open as raw text in your browser):
[Low Poly](https://content.halocdn.com/media/Default/games/halo-5-guardians/spartan-render/09-03-15/body/a010/a010_body_low-cce3179185d942ddad619ab82b35e801.js)
[Medium Poly](https://content.halocdn.com/media/Default/games/halo-5-guardians/spartan-render/09-03-15/body/a010/a010_body_high-a4618ad2208b4f3086c13e176404e435.js)
[High Poly](https://content.halocdn.com/media/Default/games/halo-5-guardians/spartan-render/09-03-15/body/a010/a010_body_high-a4618ad2208b4f3086c13e176404e435.js)

Interestingly, the Medium and High poly models are the same file size, but some other models have different size for each polygon count.

Also, interestingly, the TXT includes animation files (also in .js), and I'll link to them here.
[Default Animation](http://w.halocdn.com/Areas/Games/Scripts/Halo-5/spartandefaultanimation.min.js)
[Chest Animation](http://w.halocdn.com/Areas/Games/Scripts/Halo-5/spartanchestanimation.min.js)
[Helmet Animation](http://w.halocdn.com/Areas/Games/Scripts/Halo-5/spartanhelmetanimation.min.js)
[Idle Animation](http://w.halocdn.com/Areas/Games/Scripts/Halo-5/spartanidleanimation.min.js)
[Idle Animation 2](http://w.halocdn.com/Areas/Games/Scripts/Halo-5/spartanidleanimation2.min.js)

Any insight on this would be greatly appreciated!
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-04-09T14:14:49+00:00
- Post Title: Halo 5: Guardians Waypoint Models (.js & .json)

agreed, the editor doesn't seem to import. i tried removing the materials but the console reports "p is undefined" which tells me something is broken in code.

also - your medium and high links are identical (so the same size anyway)

what are you trying to do with the files? convert them to another format?
## Post #3
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-04-12T05:39:33+00:00
- Post Title: Halo 5: Guardians Waypoint Models (.js & .json)

The goal is to convert them to more known formats like OBJ or FBX, so at least other people can have the highest quality meshes to work with.

And yeah, I for the example I uploaded the Medium and High models are the same size, but there are a couple of other models in the list that have differing sizes for their Medium and High meshes.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-12T10:10:33+00:00
- Post Title: Halo 5: Guardians Waypoint Models (.js & .json)

> Reply from HunterAP
>
> The goal is to convert them to more known formats like OBJ or FBX"faces":[42,0,1,2,0,0,2,1,0,1,2,42,4,2,3,0,4,1,3,3,2,4,42,...

reminds me of a thread in this forum. This is like [42] a,b,c [m] a,b,c, a,b,c
where [42] says: triangles ([43]: quads) and [m] should be the material number

For the hi poly a010 body js I didn't get decent faces - tried tristrips, at no avail.

From the lo poly body I managed to extract a submesh which is not too spoiled. 



a010body-low.jpg (47.82 KiB) Viewed 568 times
## Post #5
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-04-17T07:45:17+00:00
- Post Title: Halo 5: Guardians Waypoint Models (.js & .json)

Instead of uploading samples for you to try out, [here is the download link](https://www.dropbox.com/s/ltm8uop1c3ru4o9/customization.txt?dl=1) for the txt file that contains links to all the models.

You can simply search ".js" and it will point you to the download links for meshes.

Thank you for looking into this!
## Post #6
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-04-24T09:57:21+00:00
- Post Title: Halo 5: Guardians Waypoint Models (.js & .json)

Hi
Here is blend file for import models from js files.
It requires to install Blender version 249b (32 bit) and Python 2.6.6.(32 bit).
Doubleclick file "Blender249.blend" and in Text Window press alt+p to run script.
Select file with *.js and press import.
Script import geometry, uv and weights for vertex.
To get animations need file with bones.
[Blender249[Halo5][js][2016-04-24].zip](https://xentaxbackup.github.io/file/10824_Blender249[Halo5][js][2016-04-24].zip)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-24T10:23:47+00:00
- Post Title: Halo 5: Guardians Waypoint Models (.js & .json)

Hi Mariusz,
great work as always!  

With Windows 7, 64 bit there might occur such error, though:
Traceback (most recent call last):
  File "starter.py", line 133, in Parser
  File "starter.py", line 22, in jsonParser
NameError: global name 'Yson' is not defined

(This may only happen if you extract blender2.49 from a zip without installer so maybe .blend files are not registered in your system.)
I solved this by copying  the newGameLib folder into the Blender 2.49b directory (where the blender.exe resides).
(Dunno whether there's a better solution.)



a010_body_high-js.jpg (64.52 KiB) Viewed 494 times
## Post #8
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-24T13:12:09+00:00
- Post Title: Halo 5: Guardians Waypoint Models (.js & .json)

Wow Mariusz, this is great, I love Halo series! Thanks a lot for this, I was thinking to look what's going on with model format here, you saved my day
## Post #9
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-04-28T03:50:03+00:00
- Post Title: Halo 5: Guardians Waypoint Models (.js & .json)

It works beautifully, but I can't seem to export the file in any format besides a .blend. Can anyone help me out with this?
## Post #10
- Username: Luche
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 19, 2017 5:18 pm
- Post datetime: 2017-10-19T09:58:06+00:00
- Post Title: Halo 5: Guardians Waypoint Models (.js & .json)

This looks like just the sort of thing I needed!

My buddy is a big Halo player and has his custom armour on Waypoint and he wondered if I could 3D print his armour as a cosplay.

I said I'd look into if the model parts were rippable and it seems you guys have blazed the trail for me.

So do I just need Blender and Python installed for the files Szkaradek123 uploaded and then find the armour he uses and export to my other 3d modelling programs or is there more to it than that?

Pretty sure I can export from Blender into something that 3DSMax can access and then refine the base model to make it printable.
