## Post #1
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-04-23T09:26:38+00:00
- Post Title: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

Hello  , I have already mentioned this subject without finding answers. I have problems with the .msh files which contain one or more 3d models. The files are from the game Star Wars Episode III: Revenge of the Sith [Xbox] 2005.
There has already been a post: [viewtopic.php?f=16&t=12359](https://forum.xentax.com/viewtopic.php?f=16&t=12359)
which offers a "Make_H2O_StarWarsEp3-XBOX.zip", which is not perfect but is often used only on characters with a lot of submeshes. (I'm not complaining, but the majority of .msh files are objects whose architecture, and "[*]Make_H2O_StarWarsEp3-XBOX.zip" doesn't work  ). This is why I create this post, I would like to know if it is possible (difficult?) to create a script which automatically extracts all the 3d models of a .msh file. I give you samples of .msh and some that I can't extract. For me, just for 3 .msh I take almost 20 minutes, knowing that sometimes it lacks polygons.
Thank you very much  

Samples .msh: [https://www.mediafire.com/file/9z8s5juo ... h.rar/file](https://www.mediafire.com/file/9z8s5juovqz7426/Samples_.msh.rar/file)
Samples .msh  that i can't extract: [https://www.mediafire.com/file/am2ng2lc ... t.rar/file](https://www.mediafire.com/file/am2ng2lcdlsfwku/Samples_.msh_that_i_can%27t_extract.rar/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-23T10:03:41+00:00
- Post Title: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

attention: you'll need the Make_H2O.exe as of 13th of Sept, 2015 for this!

m03_droidcontrolship: just switched from 'Strip' to NoStrip for the first 2 submeshes:
.



m03_droidcontrolship-msh.png (22.28 KiB) Viewed 195 times
## Post #3
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-04-23T10:35:26+00:00
- Post Title: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

Yes, this is what is used
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-23T12:20:52+00:00
- Post Title: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

Try out this exe (not for character models!):


 Make_H2O_SW_EP3_noChars.zip
(38.04 KiB) Downloaded 25 times



(For m03_droidcontrolship msh_2 and msh_3 need a correction as described in my last post above. Numbers changed because there's 2 more meshes now.  )

You need the dll files in the zip from this post (exe there is for character models!):

> Reply from shakotay2 ↑Fri Apr 24, 2020 12:25 am at Fri Apr 24, 2020 12:25 am
>
> 

> Reply from SilesVyr ↑Thu Apr 23, 2020 5:26 pm at Thu Apr 23, 2020 5:26 pm
>
> For me, just for 3 .msh I take almost 20 minutes, knowing that sometimes it lacks polygons.Life is hard!  (What do you think how much time I spent coding?)
## Post #5
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-04-23T14:04:42+00:00
- Post Title: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

Thank you so much
## Post #6
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-04-23T17:34:36+00:00
- Post Title: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

There are some .msh files that crash "Make_H2O_SW_EP3_noChars" for no reason.
samples .msh files crash: [https://www.mediafire.com/file/xqpofik2 ... K.rar/file](https://www.mediafire.com/file/xqpofik29kmxm1f/MSH_DOES_NOT_WORK.rar/file)
And sometimes some .msh make this error "error with FVFsize!" and it even creates .h2o file
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-23T19:31:05+00:00
- Post Title: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

> Reply from SilesVyr ↑Fri Apr 24, 2020 1:34 am at Fri Apr 24, 2020 1:34 am
>
> 
There are some .msh files that crash "Make_H2O_SW_EP3_noChars" for no reason.Thanks for reporting!
Updated the zip in my previous post.
fixed 
control_station_tulip.msh, 4 submeshes (FVFsize changed here)
fixed
component_vent.msh -> one submesh

> And sometimes some .msh make this error "error with FVFsize!" and it even creates .h2o fileAnd can't seem to find that error message in the actual code for non-char meshes.  
(There's "error: FIs border crossing!" only, maybe a warning, don't remember 5 years later.  )
Which .msh has that problem?
## Post #8
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-04-23T20:31:43+00:00
- Post Title: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

The error message seems to no longer appear.
There is a major problem, on some .msh files, Make_H2O creates extra .h2o files, and when hex2obj create the 3d models in .obj, extra 3D models are empty or simply unnecessary. (tell me if you understand  )
Example: control_station_tulip.msh has only 2 3d models, and Make_H2O creates 2 more.  
I give you the affected .msh files: [https://www.mediafire.com/file/bpc2zmsc ... D.rar/file](https://www.mediafire.com/file/bpc2zmscnfvntov/MSH_AFFECTED.rar/file)

And last thing, i don't really think that this is another real problem, but in almost all 3d models .obj, it lacks a polygon, and I am certain that it is related to the last values here:


value.PNG (3.78 KiB) Viewed 144 times
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-23T21:20:35+00:00
- Post Title: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

> Reply from SilesVyr ↑Fri Apr 24, 2020 4:31 am at Fri Apr 24, 2020 4:31 am
>
> There is a major problem, on some .msh files, Make_H2O creates extra .h2o files, and when hex2obj create the 3d models in .obj, extra 3D models are empty or simply unnecessary. (tell me if you understand  )yeah, that was an extended feature (finding extra face indices) for the character files, iirc. It was rather cool, but doesn't seem to apply for static meshes.  
(updated the concerned zip)


> And last thing, i don't really think that this is another real problem, but in almost all 3d models .obj, it lacks a polygon, and I am certain that it is related to the last values here:value.PNGHmm, for m03_droidcontrolship.msh for example all 6 obj files seem to be correct.

well, from what I see it happens to control_station_tulip.msh, SM0, right?

When you switch to 'noStr' for no reasons (don't do it when not required)

But I get
...
f 171 171 279 
f 281 281 283 
f 283 284 285 
f 285 286 286 

then
## Post #10
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-04-23T21:34:07+00:00
- Post Title: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

For example control_station_tulip.msh, but I am sure that it concerns all 3d models... look:


1.PNG (29.22 KiB) Viewed 134 times


And when i put 423 in count, the problem is fixed...(I don't think it works the same way for other 3d models)

ps: Your last updated seems to be corrupt, i can't extract it
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-23T22:13:35+00:00
- Post Title: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

> Reply from SilesVyr ↑Fri Apr 24, 2020 5:34 am at Fri Apr 24, 2020 5:34 am
>
> 
For example control_station_tulip.msh, but I am sure that it concerns all 3d models... look:1.PNG
And when i put 423 in count, the problem is fixed...(I don't think it works the same way for other 3d models)Thanks for reporting. Well, that one index makes a difference of one face (three indices) - magic.

missing face
...
f 171 281 279
f 283 284 285

fixed
...
f 171 281 279
f 283 284 285
f 286 288 287 

You might check whether adding 1 to the face indices count does the trick for all concerned meshes.
That would be a simple fix.  

(But guess there might be a little problem with the triangle strips algo.   )

> ps: Your last updated seems to be corrupt, i can't extract itfixed.
## Post #12
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-04-23T22:34:44+00:00
- Post Title: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

I will check the face count indices of differents 3d models tomorrow, thank you again for your help
## Post #13
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-04-24T06:56:04+00:00
- Post Title: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

Well, yes, i checked around fifty 3d models, and everytime, so that the models have all of their polygons, i have to add 1 in "count" in the .h2o files.  
Ex: throne_light_rack (model 1), count: 1087 ---> 1088
      throne_light_rack (model 2), count: 106 ---> 107

And it seems to be the same for Make_H2O chars, just add 1 in "count"
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-24T07:46:59+00:00
- Post Title: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

done as you wished
## Post #15
- Username: SilesVyr
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-04-24T10:23:43+00:00
- Post Title: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

Thank you very much!  
It works perfectly except on .msh containing large spacecraft, i just have 2 examples:
m03_droidcontrolship.msh


bug.PNG (217.01 KiB) Viewed 76 times


and on jedicruiserlo.msh on the engine part

link: [https://www.mediafire.com/file/ejd4whct ... g.rar/file](https://www.mediafire.com/file/ejd4whct50i07j1/bug.rar/file)
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-24T11:12:20+00:00
- Post Title: Re: Extracting .msh files Star Wars: Ep III - RotS (2005) [XBOX]

> Reply from SilesVyr ↑Fri Apr 24, 2020 6:23 pm at Fri Apr 24, 2020 6:23 pm
>
> 
Thank you very much!  
It works perfectly except on .msh containing large spacecraft, i just have 2 examples:
m03_droidcontrolship.mshNeeds manual correction:
> Reply from shakotay2 ↑Thu Apr 23, 2020 8:20 pm at Thu Apr 23, 2020 8:20 pm
>
>
