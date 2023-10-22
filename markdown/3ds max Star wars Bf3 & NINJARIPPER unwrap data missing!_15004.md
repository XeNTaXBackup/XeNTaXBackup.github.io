## Post #1
- Username: projinf3d
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jul 17, 2016 8:56 am
- Post datetime: 2016-09-06T03:40:49+00:00
- Post Title: 3ds max Star wars Bf3 & NINJARIPPER unwrap data missing!?

Can someone please help me out with this model??.
Attached are images of the A-Wing I extracted from SWBF3 via Ninja Ripper x64 (this I don't understand this as the game is x32 and NRx32 doesn't work when try to extract, though the x64 version does!?) 

Once imported into 3ds max via NR max script, I add the 'Unwrap UVW' modifier to the model..
Problem is when you go into the UV Editor within the modifier, it fails to display the model unwrapped!?
I've done the same process with Disney Infinity 3.0, add the modifier and the model is already unwrapped but no luck with this game? 
I know.. different game/different engine etc but I'm praying that I can find a workaround to avoid redoing the unwrap & seams.

I'd greatly appreciate anyone's suggestions!!!?

[https://artist-forum-prod.s3.amazonaws](https://artist-forum-prod.s3.amazonaws). ... d12e83.jpg
[https://artist-forum-prod.s3.amazonaws](https://artist-forum-prod.s3.amazonaws). ... d9f0db.jpg
## Post #2
- Username: projinf3d
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jul 17, 2016 8:56 am
- Post datetime: 2016-09-10T04:25:58+00:00
- Post Title: 3ds max Star wars Bf3 & NINJARIPPER unwrap data missing!?

BUMP! ... PLEASE ANYONE!? ..shocked I have no replies as this is one of the most resourceful forums Ive encountered when it comes model extraction/importing

PLEASE!!!!
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-10T07:20:40+00:00
- Post Title: 3ds max Star wars Bf3 & NINJARIPPER unwrap data missing!?

how should anyone help you without having the model sample?

Probably your ripped model doesn't contain uv data.
Don't remember it for max but in blender you could do an automatic unwrap then.

Problem is that the texture images won't fit to the autocreated uv map in 99.9% of the cases.
## Post #4
- Username: projinf3d
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jul 17, 2016 8:56 am
- Post datetime: 2016-09-12T09:21:34+00:00
- Post Title: 3ds max Star wars Bf3 & NINJARIPPER unwrap data missing!?

Yes of course.

mesh:
[https://1drv.ms/u/s!AHcV6g8hQidnhR4](https://1drv.ms/u/s!AHcV6g8hQidnhR4)

texture map:
[https://1drv.ms/u/s!AHcV6g8hQidnhR8](https://1drv.ms/u/s!AHcV6g8hQidnhR8)

Ever so greatful if someone could have a look & help me out.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-12T15:24:22+00:00
- Post Title: 3ds max Star wars Bf3 & NINJARIPPER unwrap data missing!?

looks like the UVs are at position 64 in the stride  



Mesh_0000_rip.png (191.65 KiB) Viewed 131 times
## Post #6
- Username: projinf3d
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jul 17, 2016 8:56 am
- Post datetime: 2016-09-13T01:48:59+00:00
- Post Title: 3ds max Star wars Bf3 & NINJARIPPER unwrap data missing!?

Oh I have so much to learn!!!, I've only attempted Hex2obj with chunk/.meshset files and failed miserably. How do you get it to display the mesh & UV data!? from a .rip file!?... I need a Hex2obj for dummies video tutorial.. but very little around from what ive seen.

Anyone know of any decent tutorials on Hex2obj and a recommended hex editor?

PS: potentially dumb question - UV position 64? ... can i change it to this value in max in order to display correctly?
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-13T03:18:57+00:00
- Post Title: 3ds max Star wars Bf3 & NINJARIPPER unwrap data missing!?

> Reply from wubbaworwee
>
> .... - UV position 64? ... can i change it to this value in max in order to display correctly?
yeah i guess so, i don't use 3dsmax so i don't really know how the plugin works 

> Reply from wubbaworwee
>
> Anyone know of any decent tutorials on Hex2obj and a recommended hex editor?
all the tutorials are "decent", no one can teach you start addresses though, 
you just have to brush up on your pattern recognition so you can identify
where data starts and stops.   

i just use Hxd and windows calculator in scientific mode   

the color of that ship in my previous post is suppossed to be red but it looks
blue because Unwrap3d swapped the red and blue channel for some reason
## Post #8
- Username: projinf3d
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jul 17, 2016 8:56 am
- Post datetime: 2016-09-13T05:37:36+00:00
- Post Title: 3ds max Star wars Bf3 & NINJARIPPER unwrap data missing!?

Yeah, I've come across that before... its the config of the .dds texture map... you open it in DxtBmp; Photoshop, its displays blue... though it shows up correctly in Gimp and max!?..

This is the interface for the ninja ripper import script. any idea is there a section here i would input 64??.. I know you said you don't use max but maybe this might tell you something??

[https://1drv.ms/i/s!AHcV6g8hQidnhSM](https://1drv.ms/i/s!AHcV6g8hQidnhSM)
## Post #9
- Username: projinf3d
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jul 17, 2016 8:56 am
- Post datetime: 2016-09-13T06:18:02+00:00
- Post Title: 3ds max Star wars Bf3 & NINJARIPPER unwrap data missing!?

> Reply from wubbaworwee
>
> Yeah, I've come across that before... its the config of the .dds texture map... you open it in DxtBmp; Photoshop, its displays blue... though it shows up correctly in Gimp and max!?..

This is the interface for the ninja ripper import script. any idea is there a section here i would input 64??.. I know you said you don't use max but maybe this might tell you something??

https://1drv.ms/i/s!AHcV6g8hQidnhSM

SOLVED!!! (at least for this model)... bit of experimenting goes a long way!!! .. the UV coord's needed to be at U: 16 V: 17 
The results speak for themselves!!!   

[https://1drv.ms/i/s!AHcV6g8hQidnhSQ](https://1drv.ms/i/s!AHcV6g8hQidnhSQ)

Thanks heaps Acewell!!!
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-13T15:15:21+00:00
- Post Title: 3ds max Star wars Bf3 & NINJARIPPER unwrap data missing!?

> Reply from wubbaworwee
>
> .. the UV coord's needed to be at U: 16 V: 17
ah that makes sense too, the rip files store data as floats and a float is 4 bytes
the UV position in this particular model is at 64 and 68 as seen in Hex2obj
in the 3dsmax plugin you set it to 16 and 17
16 * 4 = 64
17 * 4 = 68
