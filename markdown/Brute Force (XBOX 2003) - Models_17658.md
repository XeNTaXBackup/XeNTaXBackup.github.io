## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-02-04T12:41:20+00:00
- Post Title: Brute Force (XBOX 2003) - Models

Hello yet again, everyone

After some more digging, I came upon what seems to be the model format for the game, however I have no idea where to even start. It seems to be a library of models used within the level. The format is .ivd as I can see.
I've uploaded some samples: [here](https://mega.nz/file/dY4GkA4D#11l2ZByE4DOXaK4WGZhY0_QrI0-oOveaT1yh_VhC25U).
[Here is the full directory for whoever is interested.](https://mega.nz/file/dY4GkA4D#11l2ZByE4DOXaK4WGZhY0_QrI0-oOveaT1yh_VhC25U)
Thank you for your attention and I'm looking forward to porting these models to source!
## Post #2
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-02-07T10:21:59+00:00
- Post Title: Brute Force (XBOX 2003) - Models

*bump*
## Post #3
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-02-01T01:49:41+00:00
- Post Title: Brute Force (XBOX 2003) - Models

Alright, I did some more digging into the filetypes. I am restless over these assets for this game is a childhood classic of mine and I'd love to witness these models and animations close up.

[Textures ](https://forum.xentax.com/viewtopic.php?t=17657) and [ Sounds ](https://forum.xentax.com/viewtopic.php?t=16969) have been solved for the most part in the threads linked. 


The models and animations are found inside various different containers/archives:



BF_Folder_Contents.png (33.54 KiB) Viewed 324 times


For models: .ivd, .ipn (their names must be referenced inside of the .xmb file with the same name)
For animations: .chnl, .xmb (for animation names)

Thank you so much for your time and I apologize for the annoyance, I just really wish to get these some day~
Have a good one!   

Here is the link to the samples uploaded: [https://mega.nz/file/8AZATR6R#fnLxzEC8A ... 8G-Jt-8my0](https://mega.nz/file/8AZATR6R#fnLxzEC8AFgXb0HPBQaQeV0LPzSX38wTJ8G-Jt-8my0)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-01T16:46:36+00:00
- Post Title: Brute Force (XBOX 2003) - Models

objects-e01-ivdfst-SM.png (68.73 KiB) Viewed 314 times


(Some fiddling required to get the rest of the vertices.)
FVFsize toggles between 24 and 32 for example.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-01T18:44:23+00:00
- Post Title: Brute Force (XBOX 2003) - Models

You can try out dozens of face index blocks - fail so far:
.



0xDDE8C.png (62.63 KiB) Viewed 307 times
## Post #6
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-02-01T19:21:35+00:00
- Post Title: Brute Force (XBOX 2003) - Models

Woah, those are some funky looking models. Is there any script I can use to import them? They seem to have their own proprietary and unique format.. I suck at Hex2Obj and I don't want to lose their rigging data either.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-01T19:30:39+00:00
- Post Title: Brute Force (XBOX 2003) - Models

> Reply from Pepsee ↑Tue Feb 02, 2021 3:21 am at Tue Feb 02, 2021 3:21 am
>
> 
Woah, those are some funky looking models. Is there any script I can use to import them?You don't think I'd struggle around with hex2obj if I had access to scripts, do you?  

> I suck at Hex2Obj and I don't want to lose their rigging data either.I know. But atm there's no way around.
.



map&giant.png (108.51 KiB) Viewed 301 times
## Post #8
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-02-01T22:36:06+00:00
- Post Title: Brute Force (XBOX 2003) - Models

The index to the files is stored inside the .xmb files (which weren't in the uploaded data), and then it all becomes a bit clearer.

So in objects-e01.xmb, for example, at offset 0xbfb you've got 0x290 for the faces and 0x26 vertices at 0xb8acc.  Seems like each entry is 0x39 bytes.

Parts of these xmb files are obfuscated, so not sure how to parse them to get to the file table, but it might help.
## Post #9
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-02-02T01:11:51+00:00
- Post Title: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Tue Feb 02, 2021 3:30 am at Tue Feb 02, 2021 3:30 am
>
> 
Pepsee wrote: ↑Tue Feb 02, 2021 3:21 am
Woah, those are some funky looking models. Is there any script I can use to import them?You don't think I'd struggle around with hex2obj if I had access to scripts, do you?  
I suck at Hex2Obj and I don't want to lose their rigging data either.I know. But atm there's no way around.
.
map&amp;giant.png

Yeah you're right, you wouldn't bother with Hex2Obj and sadly there's no alternative yet.  

> Reply from DKDave ↑Tue Feb 02, 2021 6:36 am at Tue Feb 02, 2021 6:36 am
>
> 
The index to the files is stored inside the .xmb files (which weren't in the uploaded data), and then it all becomes a bit clearer.

So in objects-e01.xmb, for example, at offset 0xbfb you've got 0x290 for the faces and 0x26 vertices at 0xb8acc.  Seems like each entry is 0x39 bytes.

Parts of these xmb files are obfuscated, so not sure how to parse them to get to the file table, but it might help.

Those xmb archives might be the best source of information atm, to be honest. Wish this was a more well-known and used format.
## Post #10
- Username: Knightly Doggo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 06, 2021 1:14 pm
- Post datetime: 2021-07-13T10:42:08+00:00
- Post Title: Brute Force (XBOX 2003) - Models

Any recent progress been made on this? I would also like to get the models as well.
## Post #11
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-07-13T14:21:06+00:00
- Post Title: Brute Force (XBOX 2003) - Models

> Reply from Knightly Doggo ↑Tue Jul 13, 2021 6:42 pm at Tue Jul 13, 2021 6:42 pm
>
> 
Any recent progress been made on this? I would also like to get the models as well.

Sadly, no. I managed to emulate the game but I can't ninjarip from XEMU and I'd most likely not get the models in a T-pose anyways.. 
I have reuploaded the files here for people's convenience since the old link was dead.
[https://mega.nz/file/oQpwmCbA#ta5OAK_jW ... 75My5z1R9E](https://mega.nz/file/oQpwmCbA#ta5OAK_jW0PIVGSeQ1YsMOQLxOAwvler175My5z1R9E)

EDIT: More links in the main post for whoever is curious

Really hoping we'll be able to rip these files sometime in the future!!
## Post #12
- Username: eeveemaster
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 15, 2021 8:57 pm
- Post datetime: 2021-07-15T13:03:00+00:00
- Post Title: Brute Force (XBOX 2003) - Models

Omg, I thought nobody else knew about Brute Force! I recently got reminded of it due to youtube recommendations! I really hope we get to have access to the models it had! they were so cool! Maybe even the guns as well!
## Post #13
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-07-16T08:27:19+00:00
- Post Title: Brute Force (XBOX 2003) - Models

I've managed to find some screenshots on a very old personal website owned by technical artist Shea McCombs. It showcases the UI, some weapons models and map previews apparently done in maya.


[Here's the website, besides screenshots there's not much else..](http://upvector.com/?section=Graphics&subsection=Games)
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-16T12:15:46+00:00
- Post Title: Brute Force (XBOX 2003) - Models

I don't have objects-e01.xmb and I wouldn't download 435 MB just to have a look at this one file.
## Post #15
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-07-16T13:49:30+00:00
- Post Title: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Fri Jul 16, 2021 8:15 pm at Fri Jul 16, 2021 8:15 pm
>
> 
I don't have objects-e01.xmb and I wouldn't download 435 MB just to have a look at this one file.

Here you go, hope this helps!
[objects-e01.xmb.zip](https://xentaxbackup.github.io/file/20459_objects-e01.xmb.zip)
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-16T16:38:00+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

well, on a quick check (following DKDave) this (start of face indices, v cnt, v addr):
 0. 0x290 , 38 verts at 0xb8acc
 1. 0x310 , 64 verts at 0xb8e5c
 2. 0x3E0 , 64 verts at 0xb945c
 3. 0x4B0 , 64 verts at 0xb9a5c
 4. 0x580 , 108 verts at 0xba05c

So, that's not overwhelming (from the vertex counts).   More research to be done. (My motivation? You know...  )

Guess a search for 7250E71F for example (because of varying block size) could give more addresses/counts.

(Params to be used with the .ivd file, btw.)
.



objects-e01_ivd-sub_mesh_5.png (71.89 KiB) Viewed 198 times
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-16T21:30:27+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Picked up params of some bigger meshes (sub_mesh_no, hex_start address of FIs, dec_vertexCount, vertexStart):

```

 37. 46844, 2192 at 0x11c40c, correction start of FIs: 0x46850

 38. 9150, 424 at 0x12918c
 39. 9650, 632 at 0x12b94c
 42. 491d8, 872 at 0x15388c

 45. e3d0, 720 at 0x168f6c

 47. fa70, 564 at 0x17602c

 62. 15c20, 480 at 0x1ab32c

 109. 527ec, 678 at 0x25ec44

 112. 25240, 406 at 0x273d94

 125. 27bc0, 682 at 0x29050c

 160. 393b0, 415 at 0x3532ac

 164. 39e30, 444 at 0x357a64

 168. 3aab0, 746 at 0x35ceac
 169. 3b400, 518 at 0x36149c
```

Rest not worth to mention.

Start address of face indices had to be corrected for some unk reason (usually start with 0000 0100 0200; maybe not always).
Also you'll need to trick around with the counts sometimes. FVFsize= 24 (or try 32)
Face_index_count: trial & error  

Guess, I'm done with this format. Well, here's a Make_H2O tool:

> Reply from shakotay2 ↑Tue Sep 21, 2021 11:14 pm at Tue Sep 21, 2021 11:14 pm
>
> 
.



objects-e01_ivd-selection.png (105.96 KiB) Viewed 195 times
## Post #18
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-07-18T17:12:41+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

I really hope someone releases a script to extract these models and textures (maybe even anims), I'm willing to pay for their troubles if needed, I've been wanting these assets for a very long time..
## Post #19
- Username: Ivan04
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 31, 2019 4:05 am
- Post datetime: 2021-07-20T00:09:10+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

This was one of my childhood games, I'm really interested on extracting models from it too, hopefully someone's up to the task.
## Post #20
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-10T05:20:53+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

With RenderDoc Fbx Exporter and Xemu used together properly with multiple frame capturing (at least 3 or 4) using the "trigger capture" button, you can get some models from any emulated Xbox game in a 3D screenshot format with some time. It's not that great because there is no way to export the models ripped through the emulator/renderdoc with their correct UV Mapping or skeleton rig at all. It is the only tool like Ninjaripper that actually works on Xemu. You could still use these ripped models for modifcation though, and with some effort I believe then they can be made better. I'll link this piece of brutus that was ripped here for usage. It is a raw model and has been rescaled and stretched to appear more accurate, though it is not perfect whatsoever. I've managed to get flints legs, tex's body, and quite a few textures from the game using the program. It reveals all textures shown in the frame you capture, ready for converting to png/jpg as well.
[tryitBrutus.rar](https://xentaxbackup.github.io/file/20764_tryitBrutus.rar)
## Post #21
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-10T05:21:40+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Image preview of the Brutus file
[nothingood.jpg](https://xentaxbackup.github.io/file/20765_nothingood.jpg)
## Post #22
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-12T21:48:23+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

I have linked here the full 3D Model of the shotgun directly from the game, using RenderDoc.
I've accurately stretched and resized the shotgun model as close as I could. The UV Map is completely wrong, but that's it.
[ShotgunfrombruteForce.rar](https://xentaxbackup.github.io/file/20782_ShotgunfrombruteForce.rar)
## Post #23
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-12T21:49:55+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

The 3D model of the shotgun with a ripped Brutus piece, which I did not include in the .rar file because it wasn't ripped in the t-pose for some reason. But in RenderDoc the character model pieces do have a t-pose when you preview them.
[takeshotgun.png](https://xentaxbackup.github.io/file/20783_takeshotgun.png)
## Post #24
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-09-16T10:48:11+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from manbig343 ↑Mon Sep 13, 2021 5:49 am at Mon Sep 13, 2021 5:49 am
>
> 
The 3D model of the shotgun with a ripped Brutus piece, which I did not include in the .rar file because it wasn't ripped in the t-pose for some reason. But in RenderDoc the character model pieces do have a t-pose when you preview them.

Thank you so much!! I'll be looking further into this. Sadly, the lack of UV's or textures makes this really troublesome..
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-16T11:40:57+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

uvs of static models in ivd files are easy to optain:
.



objects_e01-ivd.png (90.95 KiB) Viewed 128 times
## Post #26
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-16T18:43:47+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

If the UV map is able to be somehow made to work onto the shotgun model I got, then here is the texture. I don't fully have a grasp on how all of the technical model things like that are done. Can hex2obj extract the model files as an OBJ file? because I didn't see an option. It's either Renderdoc fbx exporter or that program (if it even lets you do that) for the time being.
[SHOTGUN.jpg](https://xentaxbackup.github.io/file/20799_SHOTGUN.jpg)
## Post #27
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-16T18:50:41+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Here is what Shea Mccombs, the person who worked on the game that had their website up with those model screenshots - had to say when I asked if the models still existed somewhere in a format that was useable or if a script existed to work with them.
This might be helpful to know.
[Bruteforcedev.png](https://xentaxbackup.github.io/file/20802_Bruteforcedev.png)
## Post #28
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-16T22:53:49+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from manbig343 ↑Fri Sep 17, 2021 2:43 am at Fri Sep 17, 2021 2:43 am
>
> 
If the UV map is able to be somehow made to work onto the shotgun model I got, then here is the texture.Usually I don't care for weapons.
But well, to help you step in into the format: I'd need the info in which ivd file that gun is to be found?

> Can hex2obj extract the model files as an OBJ file? because I didn't see an option.Use File\SaveAs mesh
(suiting params required, of course, addresses and counts for vertices and face indices, FVFsize)

btw, I noticed a difference between the count of objects (derived from the count of signature findings in an xbm file) and the (bigger) count of sub meshes (derived from 000001000200 findings in the belonging ivd file).

(Maybe it's just that objects may have several sub meshes each but someone should have a look on this.)
Or it's this problem?

> Reply from DKDave ↑Tue Feb 02, 2021 6:36 am at Tue Feb 02, 2021 6:36 am
>
> Parts of these xmb files are obfuscated, so not sure how to parse them to get to the file table, but it might help.
Minor problem is some superfluous faces/solved:
.



e01_ivd.png (93.21 KiB) Viewed 80 times



----------------------------------

> Reply from manbig343 ↑Fri Sep 17, 2021 2:50 am at Fri Sep 17, 2021 2:50 am
>
> 
Here is what Shea Mccombs, the person who worked on the game that had their website up with those model screenshots - had to sayStill active? Funny!
## Post #29
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-17T01:13:21+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

As I mentioned previously, I'm simply cheating my way into getting these models out of the game by using renderdoc fbx exporter, while emulating the game and just ripping the models through the program. 
The shotgun model itself I know for a fact is loaded in the second level of the game, since Brutus uses it. I'll link the ivd for the second level's 2nd chapter for you to see if you can find it there. I had taken the shotgun model by using renderdoc fbx. Same way like I took half of Brutus' model. 
What's weird is in renderdoc it shows the character/model perfectly normal. But when you export it, the exported FBX model is a flat mirrored 2D mesh. Which is strange, I wonder if there was a fix made that someone has but never released.

The shotgun should be in this file.

[https://drive.google.com/file/d/17Vk9A5 ... sp=sharing](https://drive.google.com/file/d/17Vk9A5LVhrgTPm6ZOL8A-gGa4ZgrqdE5/view?usp=sharing)
[rdoc.png](https://xentaxbackup.github.io/file/20805_rdoc.png)
## Post #30
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-09-17T12:40:19+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from manbig343 ↑Fri Sep 17, 2021 2:50 am at Fri Sep 17, 2021 2:50 am
>
> 
Here is what Shea Mccombs, the person who worked on the game that had their website up with those model screenshots - had to say when I asked if the models still existed somewhere in a format that was useable or if a script existed to work with them.
This might be helpful to know.

It's really nice that the devs are finding out about the fact that it has a fanbase that although probably not that large as others, is still alive and kicking.

Looking forward to how this develops!
## Post #31
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-17T16:16:38+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

@manbig343: thanks! But there's too many objects to find what you want so I just chose this one:
.



m01_b_0x1b0c54.png (68.76 KiB) Viewed 106 times

 


----------------------------------------
For the object im my previous post the params from the xbm file are very clear:
...
 167. 3a860, 168 at 0x35beec
 168. 3aab0, 746 at 0x35ceac  <<<<<
 169. 3b400, 518 at 0x36149c

You just need to trick around with the face indices count.

Which you can get from a 000001000200 search in the ivd file:
ivd, search for face indices blocks:
...
658. 3a860 296 -> vCnt: 167
659. 3aab0 1192 -> vCnt: 745   <<<<<
660. 3b400 1000 -> vCnt: 517
661. 3bbd0 120 -> vCnt: 73
662. 3bcc0 136 -> vCnt: 70
...

(This couldn't be found automatically because the vertex count was 1 to small, sadly.)
## Post #32
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-17T18:05:59+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Okay, that's one of the other weapons in the game. I believe I actually have the texture for that weapon saved.

Last night I went in deep on trying to see if I could simply use renderdoc's EXPORT as CSV function as a way to get these character models from the game with much trial and error, and finding scripts that would allow me to import them into Blender as a 3d object. What happened was this -

I essentially got the entire models of Tex and Brutus in their original T-Pose/A-Pose doing this.

This is probably not the most optimized way to try and get these models but I did figure this out. Each model you see in the screenshots has separate parts to it. The body, head, legs, and armor on the characters are all separate. I hope that somewhat helps at all knowing that.

Now for some reason Tex's legs imported perfectly into blender through the .csv file I was able to make. I don't know why. Every other .csv model in the importer script once put in blender or anything else, probably due to the .csv importing script I used is missing many triangles.

If somewhere there exists a script to import .csv data into some program like blender or 3dsmax with these .csv exports having all of their faces intact instead of them being missing, or perhaps some sort of fix to the script I used which I could link if anyone wanted to see it, the models can then just be rigged afterward and can be used like that. But again this is most likely not that good of an idea.

The picture you see of Brutus to the right is from the Ultimate Halo Companion DVD which shows the exact same T-Pose!
[CSVblenderimport.png](https://xentaxbackup.github.io/file/20817_CSVblenderimport.png)
## Post #33
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-17T18:51:49+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from manbig343 ↑Sat Sep 18, 2021 2:05 am at Sat Sep 18, 2021 2:05 am
>
> I essentially got the entire models of Tex and Brutus in their original T-Pose/A-Pose doing this.

This is probably not the most optimized way to try and get these models but I did figure this out.Yeah, cool! There's many ways to Rome - what counts is that you reach it (without feeling sad or so  ).
.



m01_b-2293ac.png (91.43 KiB) Viewed 101 times
## Post #34
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-17T19:11:42+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

rest of the beast (hands not tri stripped for some unknown reason):
.



Brutus.png (145.28 KiB) Viewed 100 times
## Post #35
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-17T22:47:07+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Wait, how did you just get that complete model of brutus? Using hex2obj? Did you somehow use the numbers in my screenshot from the thing I sent in anyway for that?
Also can you link an .obj or fbx file for him? I'd like to try and get it rigged, and since those UV maps are correct I'm assuming I'll be able to use the brutus textures I got from the game, which I'll send here. 

This winrar file contains all 3 of Brutus needed textures for his model they may need to be rotated.
I don't think the skeletons from the game are able to be imported whatsoever.
[s2.png.rar](https://xentaxbackup.github.io/file/20822_s2.png.rar)
## Post #36
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-17T22:48:54+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

That model in your screenshot actually might be a feral colonist or one of the outcasts, looking closer.
## Post #37
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-18T10:39:58+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from manbig343 ↑Sat Sep 18, 2021 6:47 am at Sat Sep 18, 2021 6:47 am
>
> 
Wait, how did you just get that complete model of brutus? Using hex2obj?The parameters are in the xmb files, see here (click up arrow):

> Reply from shakotay2 ↑Sat Jul 17, 2021 12:38 am at Sat Jul 17, 2021 12:38 am
>
> Then I put them into hex2obj, yes.

> Did you somehow use the numbers in my screenshot from the thing I sent in anyway for that?No. (Counts, if any, are unreadable for me)

> Also can you link an .obj or fbx file for him?Here's the H2O files (not sure whether it's for Brutus or a "feral colonist", though):
.


 BrutusOrNotBrutus.zip
(794 Bytes) Downloaded 15 times

Load objects-m01_b.ivd into hex2obj, then a H2O file. Press 'mesh' button.
(Use File\SaveAs mesh for exporting as wavefront obj file.)

btw: it would help if you had the vertex counts for "the real" Brutus' body parts, then I could search for them among a hundreds of parts.

(The tool for getting the params from xmb files was tested with two of them only, I might release it after further tests.)
## Post #38
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-18T17:56:30+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

I'll have to find out Brutus' vertex things later then. 

The model ended up actually being the Feral Shaman model. 
I will have to get the textures for him through renderdoc, so when I do i'll post them in here. There is no proper working texture extractor from the game except for one which only works with 1 file, and isn't too functional.
[wo.png](https://xentaxbackup.github.io/file/20830_wo.png)
## Post #39
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-18T19:13:22+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

It appears something is up with this model when used with the proper textures it's asking for ingame.
The UV Map is also different than the actual texture of Brutus himself.
Perhaps the texture for this character is not accessible in renderdoc, but I will keep looking for it.
[verystrange.png](https://xentaxbackup.github.io/file/20831_verystrange.png)
## Post #40
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-18T22:22:09+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Oh, fixed it. Just couldn't find the right textures. This model here is (actually) the Yellow feral outcast shaman. 
Here i've modified the UV map so it would redirect to the green parts of the texture itself to match though. It's hard to get the exact textures in renderdoc that you want.
[newshaman.png](https://xentaxbackup.github.io/file/20832_newshaman.png)
## Post #41
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-18T22:24:44+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Here are the textures for the model extracted of the feral outcast shaman.
[NewBaseShamanOutCast.png](https://xentaxbackup.github.io/file/20835_NewBaseShamanOutCast.png)
## Post #42
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-18T22:25:03+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from manbig343 ↑Sun Sep 19, 2021 6:24 am at Sun Sep 19, 2021 6:24 am
>
> 
Here are the textures for the model extracted of the feral outcast shaman.
[newBaseShaman.png](https://xentaxbackup.github.io/file/20836_newBaseShaman.png)
## Post #43
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-18T22:27:24+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

The model I've put together with a rig from mixamo.com, the rig can be deleted afterward if not necessary for use.
It goes with the 2 textures I've posted.
[feralshamanUVMODIFIED.rar](https://xentaxbackup.github.io/file/20837_feralshamanUVMODIFIED.rar)
## Post #44
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-19T13:03:50+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

well, I see, you've got some motivation!  

Me, I don't have the time to finish the extraction tool so I'll leave here some H2O files and a short crash course on "How to use them":

BruteForce, use of H2O files explained (more or less)
-----------------------------------------------------
Understand how to use it and don't blame me!
(Please give a feedback on errors, if any, of course!)

Finishing the tool costs me too much time so I'll upload here
some intermediate H2O and log files for objects-m01_b.ivd 
which should do the trick, too.

So you'll need objects-m01_b.ivd for this!
------------------------------------------
(Doesn't work for other .ivd files. This should be obvious, but some guys, well...)

The 631 H2O files in the zip are derived from the xbm file, that's why xbm_ is part of their names.

Looking into one of them you'll find a line like this:
0xdb0 3

So, yeah, each of these (first) lines will contain a face indices count of 3.
That's NOT a bug, it's, well, a workaround.

The good news: I'll show how to find the face index counts.
                         ---------------------------------
example (.txt files are in the zip file)
-------

```

- open "m01b xmb, params-log.txt" in notepad or any other text editor

- lines contain this;
  <no of H2O file>, startAddrFIs, vertex count (at) vertex startaddr

- as an example I start with this entry:
  504. 1d840, # 207 at 0x15ac74

- load the H2O file "objects-m01_b.xmb_504.h2o" into hex2obj
  check for addr 15ac74 and count 207 in the editboxes of step 3

- now for the face indices
  1) use 1d840 (address for step 1) for search in m01_b FIs.txt
     (which you need to open in notepad, too)

     The result is
     426. 1d840 480 -> vCnt: 206

    (Ignore the 426. It's just for numbering the lines here.)

  2) enter the count 480 in hex2obj, step 1 editbox for count
     (buttons at the right show 'Strip' and 'noPtC')

  3) press Go1 button, scroll down in the lower left list box,
     last line says: max face index: 207

  4) perfect! Press mesh button - wow, a chair.
     Enter 16 for UVpos in step 2.

     Use File/SaveAs mesh to export as a wavefront obj file.

(It's point 1) to 4) here, don't confuse it with step 1/ step 3
 in hex2obj, btw.)
```


------------------------------
yeah, now for a weird example, as there are many of them.
(Use the above as a guide in case you lost the overview somehow.)

I'll choose  459. 176c0, # 430 at 0x1144c4 from the ..params-log.txt file. 

To speed up the procedure you could switch to 'PtCld' or 'Fake',
then press 'mesh' for a pre check of the object. This one looks uninteresting to me - well, next try: 

486. 2d9c8, # 739 at 0x12f6b4

(486. in the ..params-log.txt file is the H2O number, so load that file into hex2obj)

Use 2d9c8 from step 1 (in hex2obj) for the search in m01_b FIs.txt (see point 1) above).

Result is: 
```
---------------------------
Cannot find "2d9c8"
```

ok, manual search to be done, scroll down in that file 'till
-----------------------------
615. 2d9d4 1706 -> vCnt: 6140

This should be what we're searching for.
It's very important to use both params here, the address 2d9d4 AND the count 1706

(That's because the address is "off" some bytes in objects-m01_b.xmb for some unkn reason.)

Switch back to 'noPtC' in case it isn't active.
Change 2d9c8 to 2d9d4, replace 3 by 1706.

Point 3), see above gives us: max face index: 24573, what?

Reduce 1706 by 10, press Go1 (still wrong max face index) 
and again (so 1686 now)
max face index: 739, perfect

Press 'mesh', interesting "wires"
----------------------------------

Attention:
- you may need to swap from 'Strip' to 'no Str' incase the meshviewer shows an ugly object.
- even if all parameters appear to be correct some sub meshes are spoiled for some unknown reason.
.


 objects-m01_b.xmb_H2O.zip
(122.34 KiB) Downloaded 14 times
## Post #45
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-19T13:20:02+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

This is the result when you use
571. 327b8, # 1308 at 0x189f94
from .. params-log.txt file in the zip in above post:
.



whoever.png (115.46 KiB) Viewed 43 times


But I didn't find the head so I decided to let other people do it.
## Post #46
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-19T18:06:59+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

I'll have to sit down and learn how to use what you've shown/given here, this is a very big step forward I feel though I wish I had been educated in this sooner, since for a long time I myself have always worked with premade assets and models instead of creating them from the ground up or looking for data in games like this. Thanks for showing these things here.

By the way as well, every characters Eye model is separate from their body as well. So to get a full character there needs to be a search for their eyes.
The Shaman head you extracted from the data was missing his eyes, for example. So for future extraction of these models completely anyone who tries it will need to make sure they can find every piece if possible. Specifically for the brute force squad themselves from the common .ivd (I don't think brutus, tex or flint/hawk are in any other level file but they probably might be) this is important, since they are the main goal.

I hope some beta models still exist in the game. There are alot of weapons that had their models changed and Tex also used to look like a huge mech-suited soldier. The rocket launcher used to belong to the Ferals, and had a bigger design like the Halo rocket launcher. But then they changed it to be slightly smaller and more futuristic looking.

Here are brutus' vertices values on his head model when viewed in renderdoc (I think), I hope this is correct and use-able for your hex2obj program though i'm not sure.
[verticesmaybe.png](https://xentaxbackup.github.io/file/20843_verticesmaybe.png)
## Post #47
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-19T18:35:45+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Thanks. To get the vertex count one needs to count all vertex lines in the "v0 table". There's 16 to be seen only.
(I assume the highest value in the VTX column is identical to the vertex count.)
## Post #48
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-19T19:00:04+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Mon Sep 20, 2021 2:35 am at Mon Sep 20, 2021 2:35 am
>
> 
Thanks. To get the vertex count one needs to count all vertex lines in the "v0 table". There's 16 to be seen only.
(I assume the highest value in the VTX column is identical to the vertex count.)

This is the .csv for his head. If opened in Excel, it will show the entire list.
[None](https://xentaxbackup.github.io/file/20844_None)
## Post #49
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-19T19:11:46+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

3919 vertices for one head? Well, that's a lot.

-----------------------------
I guess I found the data of arms and Helmet for the previous posted body,  in updated objects-m01_b.xmb_570.h2o:

0x30F70 3098
Vb1
32 16
0x180914 1204
021000
0x0 255
.



Whoever_Helmet.png (193.75 KiB) Viewed 107 times

(2 faces missing in the left arm, dunno why)
## Post #50
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-19T19:16:33+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Mon Sep 20, 2021 3:11 am at Mon Sep 20, 2021 3:11 am
>
> 
3919 vertices for one head? Well, that's a lot.

-----------------------------
I guess I found the data of arms and Helmet for the previous posted body,  in updated objects-m01_b.xmb_570.h2o:

0x30F70 3090
Vb1
32 16
0x180914 1204
021000
0x0 255

It isn't just the head though cause it has his torso. I can't extract it without that part.
I will look into putting together the model of the character you showed.
## Post #51
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-19T19:16:50+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Mon Sep 20, 2021 3:11 am at Mon Sep 20, 2021 3:11 am
>
> 
3919 vertices for one head? Well, that's a lot.

-----------------------------
I guess I found the data of arms and Helmet for the previous posted body,  in updated objects-m01_b.xmb_570.h2o:

0x30F70 3098
Vb1
32 16
0x180914 1204
021000
0x0 255
.
Whoever_Helmet.png(2 faces missing in the left arm, dunno why)

Can you send me his files?
## Post #52
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-19T19:19:51+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

objects-m01_b.xmb_570.h2o is in the zip file of the "crash course post", just replace 0x30f64 3 in its first line by 0x30F70 3098.

(yes, face indices start address corrected, that's the reason why a crash course was required  )
## Post #53
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-19T19:39:27+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Mon Sep 20, 2021 3:19 am at Mon Sep 20, 2021 3:19 am
>
> 
objects-m01_b.xmb_570.h2o is in the zip file of the "crash course post", just replace 0x30f64 3 in its first line by 0x30F70 3098.

(yes, face indices start address corrected, that's the reason why a crash course was required  )

Thanks. I got it together, and I will be uploading him here once I find his textures.
## Post #54
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-19T20:22:02+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Mon Sep 20, 2021 3:19 am at Mon Sep 20, 2021 3:19 am
>
> 
objects-m01_b.xmb_570.h2o is in the zip file of the "crash course post", just replace 0x30f64 3 in its first line by 0x30F70 3098.

(yes, face indices start address corrected, that's the reason why a crash course was required  )

I can't seem to get the UV for the head and arms in hex2obj once I replaced the line in the hex data for 570 xmb.
How do I fix this?

Oh never mind. Found out why. I got it now
## Post #55
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-20T03:22:54+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

[https://drive.google.com/file/d/11X5CzU ... sp=sharing](https://drive.google.com/file/d/11X5CzUmzum60RHWdDHH_CbLMZ9vN883_/view?usp=sharing)

I've put this asset pack together of everything useable so far from the game we got extracted up to 9/19/2021
 
There are a bunch of common textures from the game that were extracted through the use of a Noesis script someone made. These will be in a separate pack. Including the HUD, Icons, and more.

Appropriate credits and such are inside the folder itself in a text file I've made.

Anyone who browses/lurks amongst this thread and can see this, don't be a stranger. If you know anyone who potentially could help, post a message here. If you don't even have an account and you're seeing this - and you do know someone, make one and say something. It's simple. Let us know.
This game doesn't deserve to die off into the void. And a couple people in a little forum like this is definitely not enough to do everything.

"I've lived - and died my whole career for moments like these.
 You'll probably get to die again on this rock - 
The spirits will rejoice at the end of this day.
And we might get to see them..."  Final quote from Brute Force squad before the final mission takes place.

Models include:
-----------------------
Rigged Confed Marine

Rigged Feral Shaman (no proper neck bones)

Sweeper V rocket launcher Fully Intact

Cowboy Hat (no texture yet) Missing a couple pieces of model

Tex .csv broken model rip

Brutus .csv broken model rip

Confed Lazer Weapon

Bower 20 renderdoc ripped model (not 100% perfect, no UV map)

etc.
-------------------------------------------
[None](https://xentaxbackup.github.io/file/20847_None)
## Post #56
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-09-21T01:02:27+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Loving the stuff, everyone! It means a lot to me that one of my childhood games is finally getting the attention it really needed. Using some of the assets from the pack I was able to create this alongside a couple new addons. I tried using Hex2Obj again and after several unsuccessful attempts I just accepted the fact that not everyone can use it..   

Anyways, here's some artwork using the ripped marines and their weapons, generated and upscaled a bumpmap and specular mask for them.


Looking forward to more content!

All the best!
## Post #57
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-21T15:14:30+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from Pepsee ↑Tue Sep 21, 2021 9:02 am at Tue Sep 21, 2021 9:02 am
>
> I tried using Hex2Obj again and after several unsuccessful attempts I just accepted the fact that not everyone can use it..Well, ok.
Maybe this tool might ease your mind?
Tested with objects-m01_b.xmb and  objects-m01_b.ivd (and objects-common) only so might fail for others.
.


 Make_H2O-BruteForce.zip
(128.86 KiB) Downloaded 16 times


(Far from being perfect and all meshes clumped together.)
Some meshes are spoiled, crash course "how to fix 'em" included.

For some of them only a simple swap from 'Strip' to 'noStr' is required in hex2obj after loading an ivd file and a single H2O file.
## Post #58
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-21T15:18:20+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

clumpMe.png (52.63 KiB) Viewed 54 times
## Post #59
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-21T19:09:08+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Tue Sep 21, 2021 11:18 pm at Tue Sep 21, 2021 11:18 pm
>
> 
clumpMe.png

Your whole process you created, Shako - works for any of the other files in the game as well it seems.
I got Brutus out of the common .ivd thanks to this whole thing, we're working on fixing the model. 
If you could figure out why the models get these glitchy triangles or if you know why that would help.
[BrutusLetsfriggingo.png](https://xentaxbackup.github.io/file/20859_BrutusLetsfriggingo.png)
## Post #60
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-21T19:13:27+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from manbig343 ↑Wed Sep 22, 2021 3:09 am at Wed Sep 22, 2021 3:09 am
>
> Your whole process you created, Shako - works for any of the other files in the game as well it seems.Good to hear.   (Are the uvs correct, too?)

> If you could figure out why the models get these glitchy triangles or if you know why that would help.Did you read Brute force FIs - howtoFix.txt in the crashCourseFIs folder in the zip file?
If that doesn't help, I have no idea.

Ah, well, the accompanying files m01_b FIs.txt and "m01b xmb, params-log.txt" apply to objects-m01_b only.
But with some basic understanding of 3D formats and hex2obj they shouldn't be needed.
## Post #61
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-21T19:26:21+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Full model of Brutus recovered. Needs to be rigged, but I'll put this here.
[BrutusLetsfriggingo.png](https://xentaxbackup.github.io/file/20860_BrutusLetsfriggingo.png)
## Post #62
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-21T19:27:52+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Wed Sep 22, 2021 3:13 am at Wed Sep 22, 2021 3:13 am
>
> 
manbig343 wrote: ↑Wed Sep 22, 2021 3:09 amYour whole process you created, Shako - works for any of the other files in the game as well it seems.Good to hear.   (Are the uvs correct, too?)
If you could figure out why the models get these glitchy triangles or if you know why that would help.Did you read Brute force FIs - howtoFix.txt in the crashCourseFIs folder in the zip file?
If that doesn't help, I have no idea.

Ah, well, the accompanying files m01_b FIs.txt and "m01b xmb, params-log.txt" apply to objects-m01_b only.
But with some basic understanding of 3D formats and hex2obj they shouldn't be needed.

UV's are perfectly fine except for when those pesky triangles are over them before being fixed
## Post #63
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-21T20:03:15+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Running into some worrying problems with finding the other characters through the OBJ's created using Shako's  program, and renaming the "objx's" to "obj" seems to either work or corrupt the file.
[bf21.png](https://xentaxbackup.github.io/file/20861_bf21.png)
## Post #64
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-21T20:11:22+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Wed Sep 22, 2021 3:13 am at Wed Sep 22, 2021 3:13 am
>
> 
manbig343 wrote: ↑Wed Sep 22, 2021 3:09 amYour whole process you created, Shako - works for any of the other files in the game as well it seems.Good to hear.   (Are the uvs correct, too?)
If you could figure out why the models get these glitchy triangles or if you know why that would help.Did you read Brute force FIs - howtoFix.txt in the crashCourseFIs folder in the zip file?
If that doesn't help, I have no idea.

Ah, well, the accompanying files m01_b FIs.txt and "m01b xmb, params-log.txt" apply to objects-m01_b only.
But with some basic understanding of 3D formats and hex2obj they shouldn't be needed.
[https://drive.google.com/file/d/1ZqCe8e ... sp=sharing](https://drive.google.com/file/d/1ZqCe8et6Zt1KrPupGAmRhgWmVvLjal7L/view?usp=sharing)

Here is common .ivd and common .xmb, the most important 2 files of brute force - if you think you can dabble with them.
It contains the main characters of course.
## Post #65
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-21T20:53:50+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

yeah, see, 25 objx files. Sadly I don't have the time to care for them.
I usually offer users possibilities to help themselves. See the crash course I mentioned.
Learn the basics, read the crash course. That's no rocket science.

edit: faster approach, 
> Reply from shakotay2 ↑Thu Sep 23, 2021 5:09 am at Thu Sep 23, 2021 5:09 am
>
> 

Procedure for objects-common_5_%_.objx: first line, objects-common.xmb_13.h2o
This needs to be corrected (H2O file):

0xd3b0 1716
Vb1
32 16
0x2d790 868
021000
0x0 255

So load objects-common.ivd into hex2obj, then said H2O file.
(Upper part of pic: ivd file in a hex editor.)
.



objects-common.xmb_13-h2o.png (105.15 KiB) Viewed 85 times



FAQ: so then why doesn't the tool correct this if it's so simple? 
A: Two files to handle (xmb AND ivd)!? No, one tool, one input file: less troubles. So, it's only a hobby of mine...

Also take the chance to understand what's happening in the "background".
## Post #66
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-21T22:20:36+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Wed Sep 22, 2021 4:53 am at Wed Sep 22, 2021 4:53 am
>
> 
yeah, see, 25 objx files. Sadly I don't have the time to care for them.
I usually offer users possibilities to help themselves. See the crash course I mentioned.
Learn the basics, read the crash course. That's no rocket science.

Procedure for objects-common_5_%_.objx: first line, objects-common.xmb_13.h2o
This needs to be corrected (H2O file):

0xd3b0 1716
Vb1
32 16
0x2d790 868
021000
0x0 255

So load objects-common.ivd into hex2obj, then said H2O file.
(Upper part of pic: ivd file in a hex editor.)
.
objects-common.xmb_13-h2o.png

FAQ: so then why doesn't the tool correct this if it's so simple? 
A: Two files to handle (xmb AND ivd)!? No, one tool, one input file: less troubles. So, it's only a hobby of mine...

Also take the chance to understand what's happening in the "background".

I understand so far. We're getting many models, and trying to piece together what you've been describing to us. (I know now english isn't your first language so that's fine) There's just so many roadblocks in this that it makes it hard to perfectly do everything. 
Plus no one else seems to be saying anything. It's been the 3 of us this whole time on this post talking back to back.
[bf21.png](https://xentaxbackup.github.io/file/20863_bf21.png)
## Post #67
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-21T22:24:46+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

In the end I think there's a true purpose for all this:

Getting these characters back to life in HD, and finally being able to be used once again for projects

And

Remaking the game using the assets potentially.

2 big things.
[The Hidden goodbye_waifu2x_photo_noise3_scale_tta_1.png](https://xentaxbackup.github.io/file/20864_The Hidden goodbye_waifu2x_photo_noise3_scale_tta_1.png)
## Post #68
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-22T18:54:05+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Will be uploading a new asset pack once we have extracted enough models.
## Post #69
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-22T21:09:24+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from manbig343 ↑Wed Sep 22, 2021 4:03 am at Wed Sep 22, 2021 4:03 am
>
> , and renaming the "objx's" to "obj" seems to either work or corrupt the file.Well, it's a very simple fix:

example: in objects-common_7_%_.objx delete the marked lines (<<<) then rename from .objx to .obj:

# 0xe118: faceIndices= 3932, triangles= 1310 (strips?)
f 6141/6141 5/5 7/7   <<<
f 5/5 1/1 7/7   <<<
f 7/7 1/1 6145/6145   <<<
f 1/1 24225/24225 6145/6145   <<<
f 6145/6145 24225/24225 1/1   <<<
f 24225/24225 2/2 1/1   <<<
f 1/1 2/2 3/3
f 4/4 2/2 5/5
f 2/2 6/6 5/5
f 5/5 6/6 7/7
f 6/6 8/8 7/7
f 7/7 8/8 9/9
...

f 1919/1919 1807/1807 1920/1920
f 1807/1807 1921/1921 1920/1920
f 1920/1920 1921/1921 6141/6141   <<<
f 1921/1921 5/5 6141/6141   <<<
f 6141/6141 5/5 1/1   <<<
-----------------------------
result:
.



fix_objx.png (67.86 KiB) Viewed 66 times
## Post #70
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-23T00:56:08+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Thu Sep 23, 2021 5:09 am at Thu Sep 23, 2021 5:09 am
>
> 
manbig343 wrote: ↑Wed Sep 22, 2021 4:03 am, and renaming the "objx's" to "obj" seems to either work or corrupt the file.
Well, it's a very simple fix:

example: in objects-common_7_%_.objx delete the marked lines (<<<) then rename from .objx to .obj:

# 0xe118: faceIndices= 3932, triangles= 1310 (strips?)
f 6141/6141 5/5 7/7   <<<
f 5/5 1/1 7/7   <<<
f 7/7 1/1 6145/6145   <<<
f 1/1 24225/24225 6145/6145   <<<
f 6145/6145 24225/24225 1/1   <<<
f 24225/24225 2/2 1/1   <<<
f 1/1 2/2 3/3
f 4/4 2/2 5/5
f 2/2 6/6 5/5
f 5/5 6/6 7/7
f 6/6 8/8 7/7
f 7/7 8/8 9/9
...

f 1919/1919 1807/1807 1920/1920
f 1807/1807 1921/1921 1920/1920
f 1920/1920 1921/1921 6141/6141   <<<
f 1921/1921 5/5 6141/6141   <<<
f 6141/6141 5/5 1/1   <<<
-----------------------------
result:
.
fix_objx.png

Okay, i'll look into this.
## Post #71
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-23T03:14:04+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

We have Tex now as well but he is still needing to be worked on, as he is missing parts of his model due to the work that was done to him (lots of removing of those broken glitchy triangle meshes from Hex2obj's model extraction)

The other 2 characters, Hawk and Flint, seem to be missing their Hair models in the common .ivd, there's no way to find them so far.
They will take much longer to get done.
[tex8.png](https://xentaxbackup.github.io/file/20870_tex8.png)
## Post #72
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-23T07:28:33+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from manbig343 ↑Thu Sep 23, 2021 11:14 am at Thu Sep 23, 2021 11:14 am
>
> 
We have Tex now as well but he is still needing to be worked on, as he is missing parts of his model due to the work that was done to him (lots of removing of those broken glitchy triangle meshes from Hex2obj's model extraction)It's not a problem of hex2obj, it's a problem of wrong parameters (start address of face indices) in the xmb files.

To solve it in a simple manner see my previous post. You'll need some basic understanding of the wavefront obj format, though, to know which lines to delete.

btw: maybe, it's not "wrong" but an offset merely. To decide which addresses to be patched and which not would require additional programming, accessing the ivd file; I'm a little bit tired of that...

I could add a small patch to hex2obj's multi mesh feature but that would be for Brute Force only and the tool is meant to be kept general. 

(Maybe some "private" version, I'm thinking about this..)
## Post #73
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-23T10:37:32+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Thu Sep 23, 2021 3:28 pm at Thu Sep 23, 2021 3:28 pm
>
> 
manbig343 wrote: ↑Thu Sep 23, 2021 11:14 am
We have Tex now as well but he is still needing to be worked on, as he is missing parts of his model due to the work that was done to him (lots of removing of those broken glitchy triangle meshes from Hex2obj's model extraction)It's not a problem of hex2obj, it's a problem of wrong parameters (start address of face indices) in the xmb files.

To solve it in a simple manner see my previous post. You'll need some basic understanding of the wavefront obj format, though, to know which lines to delete.

btw: maybe, it's not "wrong" but an offset merely. To decide which addresses to be patched and which not would require additional programming, accessing the ivd file; I'm a little bit tired of that...

I could add a small patch to hex2obj's multi mesh feature but that would be for Brute Force only and the tool is meant to be kept general. 

(Maybe some "private" version, I'm thinking about this..)

If you could get the patch done and have a special "brute force only" hex2obj thing we could get all the character models alot easier then, and we'd be golden. we've been trying our best to understand your program but there's only so much time that can be spent trying to learn all this hex data and numbers, vertices, etc. you've obviously mastered this to a degree and it's astounding what you've created here for us and how you've tried your best to explain everything. We wouldn't have got this far if it wasn't for your program in the first place. we'd be sitting ducks.

This picture would not exist if it wasn't for the h20 maker you made in the first place recently for the brute force xmb's, seriously.
We got alot of weapon models recently as well and are trying to get some more map objects too, since they contain weapons in them.
Very soon i think I'll be uploading V2 of the asset pack.
[I've lived and died.png](https://xentaxbackup.github.io/file/20871_I've lived and died.png)
## Post #74
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-23T18:08:03+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

For the broken glitchy triangle meshes:
well, I see, there is one important sentence in "Brute force FIs - howtoFix.txt", CrahCourseFIs folder
which you obviously overread:

> Attention:
>
> - you may need to swap from 'Strip' to 'no Str' incase the meshviewer shows an ugly object.

So you'll need to take the first solution I described here (with pictures, click up arrow):

> Reply from shakotay2 ↑Wed Sep 22, 2021 4:53 am at Wed Sep 22, 2021 4:53 am
>
> 

Do NOT use the "faster approach" there in this case because when fixing a *.objx you will not be able to swap the triangle stripped face indices  to standard triangle FIs.
H2O in question is objects-common.xmb_51.h2o, FI params need to be changed from addr 20dd4, count 1392 
to 20de0, 1370. Then toggle from Strip to noStr:
.



don't strip me.png (94.28 KiB) Viewed 39 times



I totally understand your confusion.

This is when there's no basic understanding of face indices, how they are built, what they mean.
It would help to know about the difference between standard triangles and triangle strips: [https://en.wikipedia.org/wiki/Triangle_strip](https://en.wikipedia.org/wiki/Triangle_strip)

strips, faces ABC, BCD, CDE and DEF
Plain to see: 2 vertices of a face are contained in the previous face.

For standard triangles (faces) is usually reads ABC, DEF, GHI.

Instead of ABC better try 123:
------------------------------------
So triangle strips: 123 234 345 456  (for the above example it's 123 243 345 465, so some vertex numbers swapped for correct winding)

Standard triangles: 123 456 789
## Post #75
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-23T23:32:28+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Fri Sep 24, 2021 2:08 am at Fri Sep 24, 2021 2:08 am
>
> 
For the broken glitchy triangle meshes:
well, I see, there is one important sentence in "Brute force FIs - howtoFix.txt", CrahCourseFIs folder
which you obviously overread:
Attention:
- you may need to swap from 'Strip' to 'no Str' incase the meshviewer shows an ugly object.

So you'll need to take the first solution I described here (with pictures, click up arrow):
shakotay2 wrote: ↑Wed Sep 22, 2021 4:53 am

Do NOT use the "faster approach" there in this case because when fixing a *.objx you will not be able to swap the triangle stripped face indices  to standard triangle FIs.
H2O in question is objects-common.xmb_51.h2o, FI params need to be changed from addr 20dd4, count 1392 
to 20de0, 1370. Then toggle from Strip to noStr:
.
don't strip me.png

I totally understand your confusion.

This is when there's no basic understanding of face indices, how they are built, what they mean.
It would help to know about the difference between standard triangles and triangle strips: https://en.wikipedia.org/wiki/Triangle_strip

strips, faces ABC, BCD, CDE and DEF
Plain to see: 2 vertices of a face are contained in the previous face.

For standard triangles (faces) is usually reads ABC, DEF, GHI.

Instead of ABC better try 123:
------------------------------------
So triangle strips: 123 234 345 456  (for the above example it's 123 243 345 465, so some vertex numbers swapped for correct winding)

Standard triangles: 123 456 789

Tried to copy the process you used in the brutus picture example where you said to delete the lines in the hex data of the characters to fix them, before renaming to .OBJ but the model never changed. 
Had done this on a character from another mission.
## Post #76
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-24T07:06:41+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from manbig343 ↑Fri Sep 24, 2021 7:32 am at Fri Sep 24, 2021 7:32 am
>
> 
Tried to copy the process you used in the brutus picture example where you said to delete the lines in the hex data of the characters to fix them, before renaming to .OBJ but the model never changed. 
Had done this on a character from another mission.Which one?
## Post #77
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-24T07:33:50+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Thu Sep 23, 2021 5:09 am at Thu Sep 23, 2021 5:09 am
>
> 
manbig343 wrote: ↑Wed Sep 22, 2021 4:03 am, and renaming the "objx's" to "obj" seems to either work or corrupt the file.
Well, it's a very simple fix:

example: in objects-common_7_%_.objx delete the marked lines (<<<) then rename from .objx to .obj:

# 0xe118: faceIndices= 3932, triangles= 1310 (strips?)
f 6141/6141 5/5 7/7   <<<
f 5/5 1/1 7/7   <<<
f 7/7 1/1 6145/6145   <<<
f 1/1 24225/24225 6145/6145   <<<
f 6145/6145 24225/24225 1/1   <<<
f 24225/24225 2/2 1/1   <<<
f 1/1 2/2 3/3
f 4/4 2/2 5/5
f 2/2 6/6 5/5
f 5/5 6/6 7/7
f 6/6 8/8 7/7
f 7/7 8/8 9/9
...

f 1919/1919 1807/1807 1920/1920
f 1807/1807 1921/1921 1920/1920
f 1920/1920 1921/1921 6141/6141   <<<
f 1921/1921 5/5 6141/6141   <<<
f 6141/6141 5/5 1/1   <<<
-----------------------------
result:
.
fix_objx.png

This one. I really hope we don't run into a stand still on the characters. By the way, we got every single weapon model now (they were never messed up) literally all we need to figure out is getting the characters in perfect condition, thats the next big thing. Thats why I hope you could make the special brute force hex2obj patch. Though I have no idea how hard or easy that would be to do so on your end for us. We just need brute force squads models (which tex and brutus are done, and many soldiers too that were fixed manually) and the rest of the characters from the game. 

Then, perhaps if you do know, I can send you an animation file? maybe the skeletons exist within them. They have xmbs and ivds for the animation files. I wonder if they could then be extracted and converted just like the h20 files into something.
## Post #78
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-24T12:53:25+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from manbig343 ↑Fri Sep 24, 2021 3:33 pm at Fri Sep 24, 2021 3:33 pm
>
> Thats why I hope you could make the special brute force hex2obj patch.Pmed you (usually I don't create special versions, for good reasons).
(The only reason I did it now is that the advanced GetMaxFI feature could come in handy for the "official" version.)

There's still the "strips/no strips" issue. Maybe there's a simple flag which I couldn't find so far, anyways, the patched Make_H2O is my nearest hit.

> Then, perhaps if you do know, I can send you an animation file? maybe the skeletons exist within them.My spare time for Brute Force has expired now, more or less. So, sorry, no.
## Post #79
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-24T15:26:28+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Fri Sep 24, 2021 8:53 pm at Fri Sep 24, 2021 8:53 pm
>
> 
manbig343 wrote: ↑Fri Sep 24, 2021 3:33 pmThats why I hope you could make the special brute force hex2obj patch.Pmed you (usually I don't create special versions, for good reasons).
(The only reason I did it now is that the advanced GetMaxFI feature could come in handy for the "official" version.)

There's still the "strips/no strips" issue. Maybe there's a simple flag which I couldn't find so far, anyways, the patched Make_H2O is my nearest hit.
Then, perhaps if you do know, I can send you an animation file? maybe the skeletons exist within them.My spare time for Brute Force has expired now, more or less. So, sorry, no.

Alright. I understand.
## Post #80
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-26T16:19:52+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

it seems as though the brute force models have more vertices than thought initially? 
Using this in Hex2OBJ by random guessing I nailed the full model of Flints face while having opened the .h20 file containing it 

Using fake with these settings, also leads to her entire model appearing albeit covered in triangles. I think something may be happening that we didn't know before. I have followed and learned all the steps we were taught but they result to models missing mesh pieces, but looking alright beside that...but with this idk what to say or what this could really mean. The hair model also showed up but isn't made into an h20 at all.
[new1.png](https://xentaxbackup.github.io/file/20893_new1.png)
## Post #81
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-26T16:21:57+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Here is the result from the hex2obj settings on the h20 containing flints head, which is objects-common.xmb_33
[new1.png](https://xentaxbackup.github.io/file/20894_new1.png)
## Post #82
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-26T16:23:17+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

The monster model that is loaded when using "fake" with these settings on the head h20

Note the hair appears AND her entire body.
[new1.png](https://xentaxbackup.github.io/file/20895_new1.png)
## Post #83
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-26T17:07:10+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Aaaaaaaaand...

Full model of flint recovered (No hair yet, that has to be discovered specifically what area or whatever it actually is located in her h20/somewhere near its listing of data)
[new1.png](https://xentaxbackup.github.io/file/20896_new1.png)
## Post #84
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-26T18:16:57+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from manbig343 ↑Mon Sep 27, 2021 12:19 am at Mon Sep 27, 2021 12:19 am
>
> 
it seems as though the brute force models have more vertices than thought initially?Some of them, yes. 

> Using this in Hex2OBJ by random guessing I nailed the full model of Flints face while having opened the .h20 file containing itWhat I can say is that these are the correct parameters for the head which gives senseful uvs, "random guessing" doesn't make sense to me here:
.



flint_head.png (74 KiB) Viewed 112 times


Crossing the "borders" to find the hair should be done different. I'd be surprised if "your way" lead to good results (for the hair).
Sadly I don't have the time for more research on Brute Force.

Also I think there's a separate H2O for the body, isn't it? (xmb_35.h2o is for arms and legs)
xmb_36.h2o is for the body, so no "random guessing" will help you here in any way.  
And I don't know why you're saying: "Full model of flint recovered".  

That sounds as if the patched hex2obj_BF.exe is working in a wrong way. I would beg you for showing more respect, sir.
You don't need to recover anything (except the hair, for example). Just use the corrected parameters hex2obj_BF.exe
writes as first line in the created obj file, if required.

Just in case you didn't get that. Read the instructions for hex2obj_BF.exe again, then.
--------------------------------------

BUT: there is a gap between 0xb0530 and 0xb3730 (where hands&shoes start) which is 400 vertices (FVFsize 32).
The point cloud seems to show the hair!

Well, where is the concerning face index block? 
done: (click up arrow) 
> Reply from shakotay2 ↑Tue Sep 21, 2021 11:14 pm at Tue Sep 21, 2021 11:14 pm
>
> 

It's _78.H2O which will create the missing hair mesh (one face missing, afaics).
## Post #85
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-26T19:11:35+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Mon Sep 27, 2021 2:16 am at Mon Sep 27, 2021 2:16 am
>
> 
manbig343 wrote: ↑Mon Sep 27, 2021 12:19 am
it seems as though the brute force models have more vertices than thought initially?Some of them, yes. 
Using this in Hex2OBJ by random guessing I nailed the full model of Flints face while having opened the .h20 file containing itWhat I can say is that these are the correct parameters for the head which gives senseful uvs, "random guessing" doesn't make sense to me here:
.
flint_head.png
Crossing the "borders" to find the hair should be done different. I'd be surprised if "your way" lead to good results (for the hair).
Sadly I don't have the time for more research on Brute Force.

Also I think there's a separate H2O for the body, isn't it? (xmb_35.h2o is for arms and legs)
xmb_36.h2o is for the body, so no "random guessing" will help you here in any way.  
And I don't know why you're saying: "Full model of flint recovered".  

That sounds as if the patched hex2obj_BF.exe is working in a wrong way. I would beg you for showing more respect, sir.
You don't need to recover anything (except the hair, for example). Just use the corrected parameters hex2obj_BF.exe
writes as first line in the created obj file, if required.

Just in case you didn't get that. Read the instructions for hex2obj_BF.exe again, then.
--------------------------------------

BUT: there is a gap between 0xb0530 and 0xb3730 (where hands&shoes start) which is 400 vertices (FVFsize 32).
The point cloud seems to show the hair!

Well, where is the concerning face index block? I dunno - you can't interpolate that because the blocks are assigned in an order I don't understand.
That's hard: you need to exclude all FI blocks in use, then try out the remaining ones for the hair's vertex block.

It's hard, because many of the FI start addresses from the xmb files don't match the ones from the 0000 0100 0200 search. Thus they have to be corrected. I could log the corrected ones, of course, then delete them from the afore mentioned search list... maybe next month

I didn't mean any disrespect, I meant that we have the model now using what you gave us.
We're diving deeper over time and now have Hawk completely.
You can take the time you need to rework things and whatnot. You did alot for us.
[new1.png](https://xentaxbackup.github.io/file/20899_new1.png)
## Post #86
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-27T03:08:36+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

The Squad is back together.

It was a long road, of tears, struggle, and desperation. Waiting.

Many steps. Learning, Trial and error. Guesswork, and searching.

All done by basically 3 people and a small amount of input from those who were here in the beginning.

Now all that is left is to bring everything into the asset pack I'll upload, and after years of a forum being lost, and then found - 
The models are actually done. But there's still many more characters in the game, map pieces and hidden things. 
Other file types, animations - skeletons waiting to be digged up. Hopefully we can manage to find others who can help for those.

I leave this here for now until I prepare the pack. This compressed image of a team that will return to the front lines very soon.
[3.png](https://xentaxbackup.github.io/file/20904_3.png)
## Post #87
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-29T03:58:06+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Parameters for the missing hair mesh (seems you've got them already):
.



Flint'shair.png (87.27 KiB) Viewed 79 times



(Vertex address is in xmb file, so I need to check why I missed it.)

done, updated Make_H2O-BruteForce here (click up arrow):
.

> Reply from shakotay2 ↑Tue Sep 21, 2021 11:14 pm at Tue Sep 21, 2021 11:14 pm
>
>
## Post #88
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-29T04:48:17+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Wed Sep 29, 2021 11:58 am at Wed Sep 29, 2021 11:58 am
>
> 
Parameters for the missing hair mesh (seems you've got them already):
.
Flint'shair.png

(Vertex address is in xmb file, so I need to check why I missed it.)

Thank you man. We had to use a hair model from another game. But i'll replace the one we had with that new one.
## Post #89
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-29T04:56:43+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Ok, you may check the updated version of Make_H2O-BruteForce (see link in my post above), which creates more H2O files.

Keep in mind to treat _strips_ H2Os separately. So there's two sets of H2Os with identical params, only difference is 'strips' or 'noStrips'.

Thus each set will produce some weird obj files, which are correct for the other version and vice versa.
(Usually "strips" is the most used, afaics. So start with those "_strips_" H2Os.)

(This was the easiest way to treat this rather than searching for a strips_or_nostrips flag in the xmb files, if any.)
## Post #90
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-10-03T18:10:08+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

In about a week or so I'll be sharing all the models we've got so far. Got a few more characters.
## Post #91
- Username: imagine
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 23, 2021 3:31 pm
- Post datetime: 2021-10-10T06:37:27+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Check this out, [https://steamcommunity.com/sharedfiles/ ... earchtext=](https://steamcommunity.com/sharedfiles/filedetails/?id=2607913480&searchtext=) [https://steamcommunity.com/sharedfiles/ ... 2607927759](https://steamcommunity.com/sharedfiles/filedetails/?id=2607927759)
Is this someone from this community or did they do this independently?
## Post #92
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-10T07:58:51+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Never heard of Dopey. Since it's "Brute Force - Animated Playermodels" I guess they did it independently. Because I cared for the meshes here only.
(Posted 21 Sep, nice coincidence, though.  )

no wait, read the comments:

Dopey  [author] 26 Sep @ 2:02pm 
@thedogting A really difficult and lengthy process involving renderdoc and hex2obj
## Post #93
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-10-10T10:23:35+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Sun Oct 10, 2021 3:58 pm at Sun Oct 10, 2021 3:58 pm
>
> 
Never heard of Dopey. Since it's "Brute Force - Animated Playermodels" I guess they did it independently. Because I cared for the meshes here only.
(Posted 21 Sep, nice coincidence, though.  )

no wait, read the comments:

Dopey  [author] 26 Sep @ 2:02pm 
@thedogting A really difficult and lengthy process involving renderdoc and hex2obj

It's Pepsee here from the forum. Me and him worked together this entire time during all of this.
## Post #94
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-10-10T10:28:55+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Sun Oct 10, 2021 3:58 pm at Sun Oct 10, 2021 3:58 pm
>
> 
Never heard of Dopey. Since it's "Brute Force - Animated Playermodels" I guess they did it independently. Because I cared for the meshes here only.
(Posted 21 Sep, nice coincidence, though.  )

no wait, read the comments:

Dopey  [author] 26 Sep @ 2:02pm 
@thedogting A really difficult and lengthy process involving renderdoc and hex2obj

Yup, that's me. Put em together with the help of manbig343. Wasn't expecting them to grow too popular haha
## Post #95
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-10T11:33:28+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from Pepsee ↑Sun Oct 10, 2021 6:28 pm at Sun Oct 10, 2021 6:28 pm
>
> Yup, that's me. Put em together with the help of manbig343. Wasn't expecting them to grow too popular hahaNow all the world knows that you are Dopey.
## Post #96
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-10-11T09:08:33+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from shakotay2 ↑Sun Oct 10, 2021 7:33 pm at Sun Oct 10, 2021 7:33 pm
>
> 
Pepsee wrote: ↑Sun Oct 10, 2021 6:28 pmYup, that's me. Put em together with the help of manbig343. Wasn't expecting them to grow too popular hahaNow all the world knows that you are Dopey.

That sounded kinda creepy ngl
## Post #97
- Username: imagine
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 23, 2021 3:31 pm
- Post datetime: 2021-10-24T04:11:12+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Is the full asset pack still getting posted here too?
## Post #98
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-11-22T07:53:48+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from imagine ↑Sun Oct 24, 2021 12:11 pm at Sun Oct 24, 2021 12:11 pm
>
> 
Is the full asset pack still getting posted here too?

gonna do it soon just alot of things came up. dont worry
## Post #99
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-11-22T08:14:52+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Here is the Brute Force Asset Pack Folder, complete with everything we had gotten done to a certain point. Dunno if we'll ever go back to the game to get every single thing from it in one big folder, but it's not impossible. map assets are easy to get from the game pretty much, as the program made for it gets each asset made for the levels accurately and complete (with some huge objects being incomplete or some objects just missing like ships). But characters will always have problems being ripped in some way cause of the issue of learning the hex data stuff (biggest obstacle of this whole thing, they're complex)

[https://drive.google.com/file/d/1sxEhTN ... sp=sharing](https://drive.google.com/file/d/1sxEhTNLMXOq9xQt-s4dEUZOGe7jN7TJL/view?usp=sharing)

The game does not use conventional normal maps, so use other means to create automatic ones we didn't get done for the textures to look nice on the models. I believe every single thing we did is in here. There were attempts to get other characters besides the ones inside this, but it was just too hard, as the models weren't loading properly/missing too much and it would involve much trial and error/asking for help constantly on how to use the program made for the files.

If any expert 3d modeler ever turns up or eventually we revisit this it could be possible to get the rest of the characters through reconstruction of their incomplete ripped models in the folder perhaps, as I got a couple characters full model but they just had lots of missing vertices. (which I think could be sculpted and modified by someone skilled enough one day) That's all for now, the folder also contains bonus DVD assets from an exclusive Brute force disc compiled with halo trailers.
## Post #100
- Username: imagine
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 23, 2021 3:31 pm
- Post datetime: 2022-02-17T11:42:08+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

Hey, I've been organising and setting up the models from the latest pack posted, just to check them out. The Flint model doesn't have UVs setup for the body, so I can't apply textures, but I noticed the Flint model in the Garry's Mod pack is fully textured. Is that a different version, are there more updates? There's still a couple of characters I can't properly texture, don't have Garry's Mod, so haven't seen all that's in there just yet. But thanks for sharing, it's amazing to have access to these.
## Post #101
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2022-05-04T18:43:09+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Models

> Reply from imagine ↑Thu Feb 17, 2022 7:42 pm at Thu Feb 17, 2022 7:42 pm
>
> 
Hey, I've been organising and setting up the models from the latest pack posted, just to check them out. The Flint model doesn't have UVs setup for the body, so I can't apply textures, but I noticed the Flint model in the Garry's Mod pack is fully textured. Is that a different version, are there more updates? There's still a couple of characters I can't properly texture, don't have Garry's Mod, so haven't seen all that's in there just yet. But thanks for sharing, it's amazing to have access to these.

sorry for the late reply but I think it was because flint has a second UVmap on parts of her body, and the second one is the one that reads the texture properly. Would have to just delete the UVmap that doesn't show anything in blender. Check out how to find that in blender if you can.
