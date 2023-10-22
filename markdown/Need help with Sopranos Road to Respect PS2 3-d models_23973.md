## Post #1
- Username: Nifrigretep
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 30, 2021 12:31 am
- Post datetime: 2021-05-29T16:34:08+00:00
- Post Title: Need help with Sopranos: Road to Respect PS2 3-d models

[https://mega.nz/folder/2a4xnQzB#vrsBXHXGeOEpoLnninl-1Q](https://mega.nz/folder/2a4xnQzB#vrsBXHXGeOEpoLnninl-1Q)

Hey guys, new here      been a long struggle getting these files to what they are currently, had help along the way making the .fs file they were originally stored in to a viewable folder and then some help fixing the hex issue and giving all the files their correct name/types. But I've reached a wall with these .SGP2 files, which are the characters models, and DESPERATELY need help converting them into something more manageable, obj being preferred but I'll take anything besides this SGP2 nonsense. 

I left a megaupload (very top) if anyone wants to have a go at it themselves, but really any help is appreciated, so suggestions, step by step, links to converters is more than what I'm currently working with. And here all the files I'm trying to convert, below



Hope someone thats here can help me out with this, I've almost gone insane trying to figure this out and the current file type that they are in, has being my breaking point.
This is my 1st post, so I'm not sure what to expect, but a friend highly recommended this place and from a little browsing of the board, that seems to be the case.  Thanks and heres to you guys, cheers
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-29T18:15:41+00:00
- Post Title: Need help with Sopranos: Road to Respect PS2 3-d models

Point cloud of vito looks a little bit strange, yeah:
.
edit: correction
[point_cloud_vito.png](https://xentaxbackup.github.io/file/20228_point_cloud_vito.png)
## Post #3
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-29T18:52:42+00:00
- Post Title: Need help with Sopranos: Road to Respect PS2 3-d models

Yeah, it's another one of those PS2 games that uses VIF tags within the data, so it's not a single uninterrupted block of vertex data.  For example, in Vito, the first block has 0x33 vertex entries (the count in the VIF data at 0x55a52.  The second block has 0x34 entries, etc.

Always tricky working with PS2, and it was an exclusive title it seems, so can't even get the data from other versions.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-29T20:06:37+00:00
- Post Title: Need help with Sopranos: Road to Respect PS2 3-d models

yeah, of course (how could I forget about that?  )
## Post #5
- Username: Nifrigretep
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 30, 2021 12:31 am
- Post datetime: 2021-05-29T20:20:36+00:00
- Post Title: Need help with Sopranos: Road to Respect PS2 3-d models

> Reply from shakotay2 ↑Sun May 30, 2021 2:15 am at Sun May 30, 2021 2:15 am
>
> 
Point cloud of vito looks a little bit strange, yeah:
.
edit: correction

COOL! What is it your using to view them? And how did you convert them? Very cool man, I'm amazed right now
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-29T20:28:57+00:00
- Post Title: Need help with Sopranos: Road to Respect PS2 3-d models

That's a story too long to tell.  
You could read here, though (click the up arrow):

> Reply from screenracer ↑Sat May 01, 2021 9:15 am at Sat May 01, 2021 9:15 am
>
> 

(And this is with floats instead of shorts.)
Here's some auto created faces, should do better, but I'm too tired with PS2 for now:
.



vito_auto_face_indices.png (98.88 KiB) Viewed 263 times


(well, Vito's face looks like if he were from Hellraiser...  )
## Post #7
- Username: Nifrigretep
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 30, 2021 12:31 am
- Post datetime: 2021-05-29T20:49:25+00:00
- Post Title: Need help with Sopranos: Road to Respect PS2 3-d models

doubt this helps but these are the textures for Vito. or atleast should be not sure which model for vito that is.
*edit* reading the Roadkill post now, i'll have to go over it a few times, thank you *edit*
  :O) and I know I didnt post this on market but I'm willing to compensate you for this! I'm very impressed!


and to be clear! I can try to help! Just tell me what you need and I can try to give it to you, this part of the process is where I got confused so I'm unsure how all this works and whats needed for it to work, but PLEASE let me know! Thank you!
## Post #8
- Username: Nifrigretep
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 30, 2021 12:31 am
- Post datetime: 2021-05-29T21:17:30+00:00
- Post Title: Need help with Sopranos: Road to Respect PS2 3-d models

> Reply from shakotay2 ↑Sun May 30, 2021 4:28 am at Sun May 30, 2021 4:28 am
>
> 
That's a story too long to tell.  
You could read here, though (click the up arrow):
screenracer wrote: ↑Sat May 01, 2021 9:15 am

(And this is with floats instead of shorts.)
Here's some auto created faces, should do better, but I'm too tired with PS2 for now:
.
vito_auto_face_indices.png
(well, Vito's face looks like if he were from Hellraiser...  )


and I also had a similar issue with previous method for getting the models, using texmod to extract the models straight from the game, it didn't work obviously.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-29T21:23:11+00:00
- Post Title: Need help with Sopranos: Road to Respect PS2 3-d models

> Reply from Nifrigretep ↑Sun May 30, 2021 5:17 am at Sun May 30, 2021 5:17 am
>
> and I also had a similar issue with previous method for getting the models,what is "previous method"?
------------------------- 

> Reply from Nifrigretep ↑Sun May 30, 2021 4:49 am at Sun May 30, 2021 4:49 am
>
> I'd love an explanation of your process if you'd wanna message privately :O)
Read here, similar format:

> Reply from shakotay2 ↑Wed Apr 22, 2020 2:37 am at Wed Apr 22, 2020 2:37 am
>
> 
There's no secrets to tell, it's just searching for 00 80 xx xx (VIF tag), then vertex count (1 byte) follows, then 80 00 00
00 40 02 30, then 8 bytes to skip, 3 floats (position) to follow, FVFsize is 32 bytes.

There is nothing more to tell.

> and I know I didnt post this on market but I'm willing to compensate you for this!I'm not here to be compensated, I'm here to be free!  

> this part of the process is where I got confused so I'm unsure how all this works and whats needed for it to work, but PLEASE let me know! Thank you!Read through the threads/posts I linked to. You need some basic knowledge about PS2 model formats.

And, well, some coding skills could help.
Using hex2obj (view link in my sig) is simpler.

This is the H2O file to start with for Vito:

0x0 3
Vb1
32 99
0x55a64 51
020000
0x0 255

.



Vito_fst_sub_mesh.png (33.81 KiB) Viewed 227 times


(You'll need another 80 sub mesh addresses, though.)
## Post #10
- Username: Nifrigretep
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 30, 2021 12:31 am
- Post datetime: 2021-05-29T21:35:28+00:00
- Post Title: Need help with Sopranos: Road to Respect PS2 3-d models

> Reply from shakotay2 ↑Sun May 30, 2021 5:23 am at Sun May 30, 2021 5:23 am
>
> 
Nifrigretep wrote: ↑Sun May 30, 2021 5:17 amand I also had a similar issue with previous method for getting the models, what is "previous method"?
the previous method

 emulating and using texmod to extract the textures and models from the game, once I had a model I had to use PCSX2 Model converter to "fix" it, then in 3dsmax/blender (used both seeing if they would work differently) I had to clean up the obj. It extracted every model from the scene, so I had to find paulie, delete everything besides him and voilà! A broken still model that I finally realized I couldn't actually do anything with.

From there I found Watto studios, with their program Game Extractor  and they helped A LOT. Got me to the files that I've uploaded and here we are. All I wanted was poseable models of the Sopranos crew, the people who've helped a long the way have my thanks, you included. Seeing Vito like that has been the highlight of my month, thank you.
## Post #11
- Username: bojangles099
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 12, 2021 1:01 am
- Post datetime: 2021-10-11T20:46:24+00:00
- Post Title: Need help with Sopranos: Road to Respect PS2 3-d models

Has anyone figured this out yet? I'm currently struggling with the same issue and I have 0 experience with models but I'm trying to figure out a way to get these models into L4D2. Anyone who could maybe help with this process?
## Post #12
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-12-01T17:23:28+00:00
- Post Title: Need help with Sopranos: Road to Respect PS2 3-d models

Any progress on this as well?
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-02T13:27:37+00:00
- Post Title: Need help with Sopranos: Road to Respect PS2 3-d models

As long as no one gives more usable information nothing will happen I guess. (We're stuck at the point cloud(s) so far. Creating faces is, ... ugly. Only  Nifrigretep could handle it.)
## Post #14
- Username: gg1983
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 05, 2022 5:08 am
- Post datetime: 2022-07-04T21:46:07+00:00
- Post Title: Need help with Sopranos: Road to Respect PS2 3-d models

This might be a necropost, but has there been any progress made lately? would be huge
## Post #15
- Username: mazarcharts
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 14, 2022 5:39 pm
- Post datetime: 2022-10-14T09:41:10+00:00
- Post Title: Need help with Sopranos: Road to Respect PS2 3-d models

hello i would like to know if someone could get the textures i.e. .png
