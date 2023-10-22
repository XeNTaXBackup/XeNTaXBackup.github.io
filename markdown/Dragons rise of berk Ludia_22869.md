## Post #1
- Username: tontonGrim
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 17, 2019 1:40 am
- Post datetime: 2020-10-20T15:15:00+00:00
- Post Title: Dragons rise of berk Ludia

Hello,

I would like to extract textures, 3d models and animations from the game Dragons rise of berk on mobile from Ludia (mobile android version)

I think I succed to extract the files with Quickbms (ok for pvr and wav files), but I get some .dat files, which I cannot read with Neosis ...

Could someone help me on this?

Thank you

ps: i joined a this mail a example of folder with .dat files
[dragon_blb.7z](https://xentaxbackup.github.io/file/18870_dragon_blb.7z)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-10-20T21:46:36+00:00
- Post Title: Dragons rise of berk Ludia

headerless model files  



000004be.png (22.95 KiB) Viewed 229 times
## Post #3
- Username: tontonGrim
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 17, 2019 1:40 am
- Post datetime: 2020-10-21T07:09:34+00:00
- Post Title: Dragons rise of berk Ludia

Hello, Acewell


Thank you for your comeback.

is this a model contained in the file?

If so what did you use as a tool to do this?

can we recover the meshes and the animation (I would like to import them into unity after)

i tried to use neosis to extract some things
but without success

You are a joker because you don't tell me anything! ...  

i tried to go here...:
[viewtopic.php?t=10894](https://forum.xentax.com/viewtopic.php?t=10894)

But is too complicated for me ...

Tontongrim
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-10-21T19:00:32+00:00
- Post Title: Dragons rise of berk Ludia

> Reply from tontonGrim ↑Wed Oct 21, 2020 3:09 pm at Wed Oct 21, 2020 3:09 pm
>
> 
is this a model contained in the file?
yes this was the model in the 000004be.dat sample

> Reply from tontonGrim ↑Wed Oct 21, 2020 3:09 pm at Wed Oct 21, 2020 3:09 pm
>
> 
If so what did you use as a tool to do this?
i used Hex2obj and Hxd and windows calculator

> Reply from tontonGrim ↑Wed Oct 21, 2020 3:09 pm at Wed Oct 21, 2020 3:09 pm
>
> 
can we recover the meshes and the animation
you can get anything you want if you know what to look for in hex editor.  

> Reply from tontonGrim ↑Wed Oct 21, 2020 3:09 pm at Wed Oct 21, 2020 3:09 pm
>
> 
You are a joker because you don't tell me anything!
the offsets and counts in the image tells you everything.
## Post #5
- Username: tontonGrim
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 17, 2019 1:40 am
- Post datetime: 2020-10-21T19:31:24+00:00
- Post Title: Dragons rise of berk Ludia

Hello Acewel

Thank you,

i repeated your parameters and i found the mesh for the 000004be...

but how find the otht parameters for others files ? (ex for the 00000497.dat etc.... he have more 40000 files !!!! ... ((((  )

i refind this topic: 
[viewtopic.php?t=20733](https://forum.xentax.com/viewtopic.php?t=20733)

But I don't understand how Hex2Obj works ....(and i m french....  )

is there any other way than using hex2obj?
## Post #6
- Username: tontonGrim
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 17, 2019 1:40 am
- Post datetime: 2020-10-30T20:19:40+00:00
- Post Title: Dragons rise of berk Ludia

Hello,

I come back !

I used Models Researcher 2.7 with the file 00000497.dat (see attach file).

I found the vertices (see attach file), but i cant find the faces..... can you help me ?


 files.7z
(149.2 KiB) Downloaded 13 times



Best regards
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-10-31T00:12:21+00:00
- Post Title: Dragons rise of berk Ludia

face indices start at 0x13128
looks like there is 8016 of them.
## Post #8
- Username: tontonGrim
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 17, 2019 1:40 am
- Post datetime: 2020-10-31T17:03:23+00:00
- Post Title: Dragons rise of berk Ludia

Thank you Acewell,

i tried it  but i have error message "mismatch of faces and vertices"...  
(see the picture)

Where is the problem ? format of face ? padding ? i tried several parameters but without success

i don't understand why ...  



Capture d’écran 2020-10-31 175241.png (81.66 KiB) Viewed 151 times



ps : i put 8016 in count parameters but i have a other message "can not read data" the system is out of limit, for the moment i put 10 in the count parameters (see the picture)

thank you for your help
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-11-01T09:16:58+00:00
- Post Title: Dragons rise of berk Ludia

i guess you need to change the Type for faces to "short".



00000497dat.png (47.58 KiB) Viewed 143 times
## Post #10
- Username: tontonGrim
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 17, 2019 1:40 am
- Post datetime: 2020-11-02T20:06:59+00:00
- Post Title: Dragons rise of berk Ludia

Hello Acewell,

thank you very much for your help !

I tried to choose "short" in the type of face, but it's not sufficient...

But i don't understand why, if i use Hex2Obj i can create a good obj and texture (with your informations)

but if i want try to do the same thing with 3D models researcher....

I can't do.... and i obtained this.....  

I tried to modifing padding, padd inter etc.... but nothing...

Thank you

ps: In your previous picture, at what corresponding the FVFSive  parameter ?
[Capture d’écran 2020-11-02 210055.png](https://xentaxbackup.github.io/file/18944_Capture d’écran 2020-11-02 210055.png)
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-11-02T23:23:31+00:00
- Post Title: Dragons rise of berk Ludia

> Reply from tontonGrim ↑Tue Nov 03, 2020 4:06 am at Tue Nov 03, 2020 4:06 am
>
> 
In your previous picture, at what corresponding the FVFSive  parameter ?
FVFsize is the stride in bytes for vertex information. i don't use 
3dmodel researcher so i can't help you there, maybe ask the developer.
## Post #12
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2020-11-03T08:57:50+00:00
- Post Title: Dragons rise of berk Ludia

00000497.dat_Tue_Nov__3_15-56-24_2020.png (86.3 KiB) Viewed 119 times
## Post #13
- Username: tontonGrim
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 17, 2019 1:40 am
- Post datetime: 2020-11-07T13:04:16+00:00
- Post Title: Dragons rise of berk Ludia

Hello Mr Lazov !

Thank you very much, it' works ! 

i don't know how you do to find the good parameters in particular the "padding" parameters... can you explain me ? i don't know how find this information...

Now I will start to search the textures..

Thank you very muh for your help.

 I go back to train again, to find the parameters from a other models with your informations
## Post #14
- Username: tontonGrim
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 17, 2019 1:40 am
- Post datetime: 2020-11-07T17:11:41+00:00
- Post Title: Dragons rise of berk Ludia

i think understood the vertices and faces parameters   thank to you !



Capture d’écran 2020-11-07 180136.png (118.45 KiB) Viewed 90 times
## Post #15
- Username: tontonGrim
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 17, 2019 1:40 am
- Post datetime: 2020-11-08T11:47:46+00:00
- Post Title: Dragons rise of berk Ludia

Hello,

Now i would like find the texture, i think be near to the solution. 

but it's not perfect... can you help me ? (you have files attachments: .ab file and texture file in the next post)



Capture d’écran 2020-11-08 123646.png (24.65 KiB) Viewed 78 times



thank you
## Post #16
- Username: tontonGrim
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 17, 2019 1:40 am
- Post datetime: 2020-11-08T11:48:15+00:00
- Post Title: Re: Dragons rise of berk Ludia

Files attachments
[Bureau.zip](https://xentaxbackup.github.io/file/18986_Bureau.zip)
## Post #17
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-11-08T17:06:55+00:00
- Post Title: Re: Dragons rise of berk Ludia

> Reply from tontonGrim ↑Sun Nov 08, 2020 7:47 pm at Sun Nov 08, 2020 7:47 pm
>
> 
Hello,

Now i would like find the texture, i think be near to the solution. 

but it's not perfect... can you help me ? (you have files attachments: .ab file and texture file in the next post)

Capture d’écran 2020-11-08 123646.png

thank you

Offset: 0x1c
Padding: 28
## Post #18
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2020-11-09T15:04:18+00:00
- Post Title: Re: Dragons rise of berk Ludia

tontonGrim



count24.png (41.77 KiB) Viewed 58 times
## Post #19
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2020-11-09T15:05:36+00:00
- Post Title: Re: Dragons rise of berk Ludia

Template:
v 0x0 2579 24 0 Float XYZ
f 0x16aac 3250 0 0 Short Triangles
vt 28 2579 28 0 Float UV
vn 0xc 2579 24 0 Float XYZ



00000091.dat_Mon_Nov__9_22-02-38_2020.png (181.22 KiB) Viewed 58 times
## Post #20
- Username: tontonGrim
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 17, 2019 1:40 am
- Post datetime: 2020-11-09T17:04:25+00:00
- Post Title: Re: Dragons rise of berk Ludia

Hello !!

Thank you very much !!!

everything is working well thanks to you all !

I think understood the padding 24 for the vertices but not the 28 of padding for the UVs... i would like explications 



In using your application, i found 2 little bug :

-When i save a template, the status of texture Flip and the way of file of the texture does'nt save in the template.

-When we want compared the polygonal texture and the draw texture they doesn't the same size.... (the draw is more small), it's very difficult to see if the polygons or Points are correctly superposed

Maybe add a zoom system ?



Mr Lazov you program is very very interesting and very powerful when you understand how it works (not easy ...)

I can't wait to see the next releases! including the recovery of animations!
[https://www.youtube.com/watch?v=Y951j875Xak](https://www.youtube.com/watch?v=Y951j875Xak)

Have a date to give us for this option? I can't wait !!
