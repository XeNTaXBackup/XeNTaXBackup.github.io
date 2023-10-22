## Post #1
- Username: Idogftw
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 05, 2020 3:14 pm
- Post datetime: 2020-06-05T08:38:08+00:00
- Post Title: RSCF Model Format Help

Alright so i'm new to this whole scene and i've recently, the past couple of days, have been trying to Rip models from Aliens vs Predators 2010. I've managed to unpack the zlib and export individual files from it. I have been tinkering with the pistol from the game and trying to figure out the offsets for it and I have managed to get it looking like a gun but it's flat, i've been using hex2obj to get a preview of the model but like I said it's flat I feel I have the offsets correct, obviously not but I would like some help, not to necessarily tell me what to do but give hints or something of the sorts on how to figure this out. Heres the file I have been using, the image that I get when I put in my offsets and my offsets and counts. Basically if anyone could just point me in the right direction and let me know what I did wrong that would be awesome! 

[https://mega.nz/file/L3hxRSRa#ugswYRx68 ... B3jTmUkOe0](https://mega.nz/file/L3hxRSRa#ugswYRx686ERsH-a_MUBM_uS2cTQ1avUPB3jTmUkOe0)


Offsets for Verts:
Starting: FB
Ending: 3E41B
Count: 3980
Block Size: 64 bytes

Also here is my hex2obj settings:


Thanks all!  

PS: Sorry if this is the wrong section, I figured it would be.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-05T09:51:13+00:00
- Post Title: RSCF Model Format Help

A, well, simple enough  , the model itself uses floats while uvs are half floats.
(create an empty .txt file, copy below 6 lines into it and save as whatever.H2O)

0x3E445 6603
Vb1
64 56
0x105 3981
021100
0x0 255

(another uv pos (half floats): 52. At 0x129 and 0x131 normals and tangents? start.)
## Post #3
- Username: Idogftw
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 05, 2020 3:14 pm
- Post datetime: 2020-06-05T16:21:30+00:00
- Post Title: RSCF Model Format Help

Oh wow ok, i was off a good bit on my starting offset and 1 by my count. Would you mind telling me how you got the correct vert offset, or was it trial and error and i was off by 1 for my faces too. Also how did you get that as the face count too?

Thanks a lot though
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-05T18:43:10+00:00
- Post Title: RSCF Model Format Help

> Reply from Idogftw ↑Sat Jun 06, 2020 12:21 am at Sat Jun 06, 2020 12:21 am
>
> how you got the correct vert offset, or was it trial and errorMore experience than T&E  Once you know how to recognize F0 0F AC BC or 00 00 80 3F as (IEEE 754) floats things are growing easier.

> Also how did you get that as the face count too?It's not the "face count" it's the face indices count (1 face: 3 indices for standard triangles)
(0x417DF - 0x3E445) / 2 = 0x19CD = 6605 (dec.)
2 (bytes): size of face indices
## Post #5
- Username: Idogftw
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 05, 2020 3:14 pm
- Post datetime: 2020-06-05T20:48:12+00:00
- Post Title: RSCF Model Format Help

Oh ok, yea with the verts i was assuming they were shorts or half floats . Yea my bad i meant to say face indices. So i when i did those settings in the hex2obj and hit mesh it seems that the slide is not in the right position, its like in the middle of the gun for some reason.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-05T21:10:03+00:00
- Post Title: RSCF Model Format Help

Usually I don't care for pistols   - but as a general remark: 3D mesh files may consist of submeshes with separate location offsets. These are not handled by hex2obj. You need to do a deeper file research for getting them, if any.

As a workaround you can do it manually in this case: after File/SaveAs mesh (.obj file creation)

insert the following "g submesh" lines into the .obj file then load the .obj into blender for example, in the outliner window select sm_5 and sm_6, then move manually in the 3D window:
[...]
f 1998/1998 2000/2000 1999/1999
g sm_5
f 2001/2001 2002/2002 2003/2003
[...]
f 2497/2497 2498/2498 2499/2499
g sm_6
f 2500/2500 2501/2501 2502/2502
[...]
f 2998/2998 2999/2999 3000/3000
g sm_7
f 2999/2999 3001/3001 3000/3000
## Post #7
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-06-09T21:02:44+00:00
- Post Title: RSCF Model Format Help

I tried to make a noesis script based on the file you posted, but I failed, the model is coming out plan:



pistol.png (25.79 KiB) Viewed 61 times
## Post #8
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-06-09T21:13:14+00:00
- Post Title: RSCF Model Format Help

Here is the script:

 fmt_AliensVsPredators.zip
(893 Bytes) Downloaded 15 times


I believe that in position 0xAD there is the number of bytes that must be skipped to find the beginning of the vertices, but I don't know how to deal with it.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-09T21:50:50+00:00
- Post Title: RSCF Model Format Help

> Reply from reh ↑Wed Jun 10, 2020 5:13 am at Wed Jun 10, 2020 5:13 am
>
> 
I believe that in position 0xAD there is the number of bytes that must be skipped to find the beginning of the vertices, but I don't know how to deal with it.Maybe. But you can't judge from one file, can you?

(I've the strong feeling that searching for the pattern 000000000100000000000000 may help, there's 10 findings and interestingly they have a constant distance, 0x18 bytes.)
last address is 0xF9 + length of pattern (0x0C) = 0x105, start of first submesh

btw: the model is 3D in case you comment out these 2 lines:
#Voffset= bs.readUInt()
#print("hex Voffset: ",hex(Voffset))

and put a bs.readUInt() after the reading of the VBuff bytes.
## Post #10
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-06-11T16:37:28+00:00
- Post Title: RSCF Model Format Help

Thank you for making this script work.

> Reply from shakotay2 ↑Wed Jun 10, 2020 5:50 am at Wed Jun 10, 2020 5:50 am
>
> 
Maybe. But you can't judge from one file, can you?
Really, we would need some samples to confirm.
