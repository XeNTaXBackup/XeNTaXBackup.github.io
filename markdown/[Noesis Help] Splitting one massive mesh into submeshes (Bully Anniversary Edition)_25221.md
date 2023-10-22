## Post #1
- Username: Edness
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 11, 2018 7:26 pm
- Post datetime: 2022-04-04T17:25:55+00:00
- Post Title: [Noesis Help] Splitting one massive mesh into submeshes (Bully: Anniversary Edition)

Hey there, I'm writing a Noesis texture + model plugin for Bully: Anniversary Edition, and I've encountered into a problem - most of the models in this game are one single massive mesh, and at the footer of each of those meshes is a list of where to divide the faces (e.g. from 0 apply to 2052 faces, from 2052 apply to 36 etc.) I also checked with Model Researcher to also make sure this is the case.


[Here are 4 examples](https://cdn.discordapp.com/attachments/340499300754915329/960587954470932490/BullyAE.7z), 3 of which are one massive mesh like this, and one (ext_outsidepatio.msh) being a rare one that is split into 4 meshes so it previews in Noesis more normally (but some of those are still split in submeshes) + all of the additional .mtl and .tex files that the script already parses and loads which those particular .msh files expect to find.

And attached is the script as I've written it so far, where my very jank and failed attempt to divide into submeshes can be seen commended out at Line 390.  As it is now, it just applies the last texture it read for each mesh because of the lack of dividing into submeshes.
[fmt_BullyAE.7z](https://xentaxbackup.github.io/file/22060_fmt_BullyAE.7z)
## Post #2
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-04T19:20:51+00:00
- Post Title: [Noesis Help] Splitting one massive mesh into submeshes (Bully: Anniversary Edition)

1. 357Kb is not a "massive mesh" - complex true, but not massive. Those "submeshes" of yours are the smoothing groups I believe
2. Splitting by texture usage is not the rght way - what if one of those separated meshies is using more than 1 texture? You will end up with hundreds of small fragments.
3. There is two possible way to do this:
    a. Grab 3DS Max and do it by hand.
    b. Go through all vertices and regroup them.
## Post #3
- Username: Edness
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 11, 2018 7:26 pm
- Post datetime: 2022-04-05T11:04:29+00:00
- Post Title: [Noesis Help] Splitting one massive mesh into submeshes (Bully: Anniversary Edition)

> Reply from VendorX ↑Tue Apr 05, 2022 3:20 am at Tue Apr 05, 2022 3:20 am
>
> 
Those "submeshes" of yours are the smoothing groups I believe
2. Splitting by texture usage is not the rght way - what if one of those separated meshies is using more than 1 texture? You will end up with hundreds of small fragments.
No, the amount of groups in the many meshes I tested matches the amount of materials in the header, as well as their indexes with how it's meant to look in-game.  Meshes with only one material also only have one of those groups in the footer that span all of the faces, and render properly in Noesis too.  Otherwise, how else would the game determine where to apply separate textures asides just plain UVs?  The script parses just about all of the information there is, other than some bone and anim stuff in the header I've yet to tackle.

> Reply from VendorX ↑Tue Apr 05, 2022 3:20 am at Tue Apr 05, 2022 3:20 am
>
> 
    b. Go through all vertices and regroup them.
That is what I was trying to do in that commented out spaghetti code, but alas I was unsuccessful.  I do have a few more ideas on how to potentially do it, but due to college resuming I'll no longer be home for most workdays so I won't get to try said idea until Friday evening or Saturday, which is why I posted it here to see if anyone else has ideas while I'm away.

Edit: Seems like this may have been solved by Joschka/Dimy on Discord.
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2022-04-05T12:03:33+00:00
- Post Title: [Noesis Help] Splitting one massive mesh into submeshes (Bully: Anniversary Edition)

This is the basics of how I would approach it - my simple script attached.

It's just for example purposes, so I made a lot of assumptions just for time.  It doesn't read the material data/texture info, but it shows how I would read the mesh/submesh data and apply the materials to it so that each submesh is separate and has its own texture.

It should work on the "mountains" file, so you can see what it does.


 bully.zip
(1.08 KiB) Downloaded 19 times
## Post #5
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-04-05T12:14:29+00:00
- Post Title: [Noesis Help] Splitting one massive mesh into submeshes (Bully: Anniversary Edition)

I'm going to post the script I did too, sent it to Edness already. It should do what was expected, I simply moved a few lines of the original script to makeit work.


 fmt_BullyAE.zip
(4.41 KiB) Downloaded 17 times
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2022-04-05T14:43:25+00:00
- Post Title: [Noesis Help] Splitting one massive mesh into submeshes (Bully: Anniversary Edition)

> Reply from Joschka ↑Tue Apr 05, 2022 8:14 pm at Tue Apr 05, 2022 8:14 pm
>
> 
I'm going to post the script I did too, sent it to Edness already. It should do what was expected, I simply moved a few lines of the original script to makeit work.
fmt_BullyAE.zip

I just saw the edit after I'd posted mine lol.  That's why I didn't go full on with doing everything
## Post #7
- Username: Edness
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 11, 2018 7:26 pm
- Post datetime: 2022-04-08T16:32:49+00:00
- Post Title: [Noesis Help] Splitting one massive mesh into submeshes (Bully: Anniversary Edition)

Now looking at Joschka's script closer when I'm home, I can clearly see where I made the one mistake that prevented the whole thing from working  I was multiplying the submesh faces amount by two originally which, well, means Noesis is expecting twice as many and failing!  Fixed up a few other things here and there, and while there's still plenty of stuff to do, the script is now also publicly available. [https://github.com/EdnessP/scripts/blob ... BullyAE.py](https://github.com/EdnessP/scripts/blob/main/bully/fmt_BullyAE.py)
