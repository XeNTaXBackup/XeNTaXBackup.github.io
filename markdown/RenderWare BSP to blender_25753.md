## Post #1
- Username: Erik The Born
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jun 10, 2015 11:01 pm
- Post datetime: 2022-08-30T14:22:42+00:00
- Post Title: RenderWare BSP to blender?

Hello, I have some really old BSP files from a childhood game that I want to import to blender but I can't seem to find a way to import them... I managed to import the games DFF files with Dragon DFF for GTA but it is unable to get their BSP files in.

[https://drive.google.com/file/d/12Uxhtw ... sp=sharing](https://drive.google.com/file/d/12UxhtwehnnpzUF-9waScZ2durtM8xeYq/view?usp=sharing)

if someone could take a look and help with it I would be very thankful!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-30T15:37:18+00:00
- Post Title: RenderWare BSP to blender?

Is it a PS2 sample?

Some point clouds (no time to fiddle around with face indices):
.



BSP.jpg (43.01 KiB) Viewed 168 times



(Need to check my BSP Make_H2O project from 2015... can't find it atm.)
## Post #3
- Username: Erik The Born
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jun 10, 2015 11:01 pm
- Post datetime: 2022-08-30T15:51:19+00:00
- Post Title: RenderWare BSP to blender?

> Reply from shakotay2 ↑Tue Aug 30, 2022 11:37 pm at Tue Aug 30, 2022 11:37 pm
>
> 
Is it a PS2 sample?

Some point clouds (no time to fiddle around with face indices):
.
BSP.jpg

(Need to check my BSP Make_H2O project from 2015... can't find it atm.)

Thanks for replying! No, its from a PC game called Rummel och Rabalder i Snarkofagens Skugga. It's Swedish so I doubt you would know about it. 

Interesting to see you actually got something there!
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-30T16:04:22+00:00
- Post Title: RenderWare BSP to blender?

> Reply from Erik The Born ↑Tue Aug 30, 2022 11:51 pm at Tue Aug 30, 2022 11:51 pm
>
> Thanks for replying! No, its from a PC game called Rummel och Rabalder i Snarkofagens Skugga.Haha, what? (All I know is "Ragnarok" but that's assumed to be norsk.)

Some ugly meshes:
.



BSP2.jpg (139.4 KiB) Viewed 151 times
## Post #5
- Username: Erik The Born
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jun 10, 2015 11:01 pm
- Post datetime: 2022-08-30T16:15:34+00:00
- Post Title: RenderWare BSP to blender?

> Reply from shakotay2 ↑Wed Aug 31, 2022 12:04 am at Wed Aug 31, 2022 12:04 am
>
> 
Erik The Born wrote: ↑Tue Aug 30, 2022 11:51 pmThanks for replying! No, its from a PC game called Rummel och Rabalder i Snarkofagens Skugga.Haha, what? (All I know is "Ragnarok" but that's assumed to be norsk.)

Some ugly meshes:
.
BSP2.jpg

Hey! You actually got meshes out of it! I am excited boyo now
## Post #6
- Username: Erik The Born
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jun 10, 2015 11:01 pm
- Post datetime: 2022-08-30T18:49:54+00:00
- Post Title: RenderWare BSP to blender?

> Reply from shakotay2 ↑Wed Aug 31, 2022 12:04 am at Wed Aug 31, 2022 12:04 am
>
> 
Erik The Born wrote: ↑Tue Aug 30, 2022 11:51 pmThanks for replying! No, its from a PC game called Rummel och Rabalder i Snarkofagens Skugga.Haha, what? (All I know is "Ragnarok" but that's assumed to be norsk.)

Some ugly meshes:
.
BSP2.jpg

Do you think u could fix up?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-30T19:20:13+00:00
- Post Title: RenderWare BSP to blender?

Motivation: low. But I could show how to get the meshes yourself, after having finished my current projects.
## Post #8
- Username: Erik The Born
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jun 10, 2015 11:01 pm
- Post datetime: 2022-08-30T19:25:32+00:00
- Post Title: RenderWare BSP to blender?

> Reply from shakotay2 ↑Wed Aug 31, 2022 3:20 am at Wed Aug 31, 2022 3:20 am
>
> 
Motivation: low. But I could show how to get the meshes yourself, after having finished my current projects.

That would be very helpful!
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-01T11:06:03+00:00
- Post Title: RenderWare BSP to blender?

Using hex2obj (view link in my sig), this should give you an idea of the basic sub mesh structure:
.



world-BSP_0xABD5C.jpg (89.9 KiB) Viewed 123 times

(Didn't care for uvs so far.)

Use a hex editor to check for the startaddress of vertices, 0xABD5C, to understand how to find other vertex blocks.
## Post #10
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2023-03-01T21:48:11+00:00
- Post Title: RenderWare BSP to blender?

there you go


 rwbsp2obj.zip
(10.91 KiB) Downloaded 34 times
## Post #11
- Username: Erik The Born
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jun 10, 2015 11:01 pm
- Post datetime: 2023-03-04T14:12:44+00:00
- Post Title: RenderWare BSP to blender?

> Reply from DCxDemo ↑Thu Mar 02, 2023 5:48 am at Thu Mar 02, 2023 5:48 am
>
> 
there you go
rwbsp2obj.zip

WHO SH**T MAN UR AMAZING! THANK YOU!
