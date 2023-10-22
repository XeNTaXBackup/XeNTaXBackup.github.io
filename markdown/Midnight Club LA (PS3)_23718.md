## Post #1
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-08T19:15:27+00:00
- Post Title: Midnight Club LA (PS3)

I was able to decompress the files using many tools. The final result is a nameless file that holds data. I was able to find some patterns. 
[](https://ibb.co/SP2D35b)
Hopefully im not showing wrong screen shots but im pretty sure this is a buffer of some kind. The vertices start on the blue ususally.... 
[](https://ibb.co/Jtk00g8)
Although I did save this one where they seem to start directly after the faces but i think this is wrong. I took many screenshots. Sorry if this isn't right.
[](https://ibb.co/QckHfxf)
This is what the shell looks like which seems to be correct.
[](https://ibb.co/F0dMHrJ)
Uv's also come out correct. So this seems to be right.
[](https://ibb.co/SRpSSM2)
Until I run into an issue like this. These faces are in the same vertex buffer. Yet if i load 1 more face it throws an error. I found that by searching for another offset of faces reveals the other meshes. But its very time consuming. Is there anyway to parse the model data by a script ?

Samples 
[https://drive.google.com/file/d/1vrkLRG ... sp=sharing](https://drive.google.com/file/d/1vrkLRGzZtQth0GN7oxQbB5asxnOgof0d/view?usp=sharing)
Thanks in advance
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-08T21:59:58+00:00
- Post Title: Midnight Club LA (PS3)

> Reply from Sharppy ↑Fri Apr 09, 2021 3:15 am at Fri Apr 09, 2021 3:15 am
>
> But its very time consuming. Is there anyway to parse the model data by a script ?I wouldn't know, why not - but it's also very time consuming.  

Counts are to be found in the ..._unpacked files, that's good.

Get the start_of_face_indices_blocks by searching for  0000 0001 0002 in 0xf9785b04_unpacked:

```
# 2aae0
# 2bcb0
# 36000
# 3a000
# 3d000
# 3ed80
# 40c40
# 41c10
# 42b60
# 45ef0
# 46ee0
# 48000
# 49000
# 49810
# 4a000
# 4a800
# 4f000
# 4f1e0
# 4f3c0
# 4f5a0
# 4f780
# 4f950
# 50000
# 501b0
# 50360
# 50510
# 51500
# 52180
# 521c0
# 63930
```
(have to be validated, 0x63930 is a false find, for example)

(If I have more spare time I could put this to the Make_H2O project. But not to soon.)
## Post #3
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-09T00:09:18+00:00
- Post Title: Midnight Club LA (PS3)

Thank you that was how i was cutting the files for extraction because some faces aren't directly after the vertex. Well it was worth a shot. DKDave just responded on it aswell. Seems the original tool didnt do that good at decompressing the .rpf file.
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-04-09T16:43:59+00:00
- Post Title: Midnight Club LA (PS3)

I'm always interested in car models, so I wouldn't mind getting these.  I've also extracted the files myself and get the same resulting unnamed files as you, so they are most likely correct.

The format itself is very convoluted, with pointers all over the place to various bits of data.  The addresses are odd due to the fact that they are all in the format 0x50nnnnnn (not sure what the 0x50 signifies, but it doesn't seem relevant as far as I can tell).

From my analysis of the file, there's an offset at 0x08 that seems to point to a "master list" of mesh info.  This points to a list of mesh offsets which have offsets to mesh header info, which has offsets to vertex and face info, which have offsets to the actual vertex and face data for each section.  So the vertices and related faces could be anywhere in the file, and often aren't together by the look of it.

I might attempt writing a script if I can properly make sense of it enough to do so.
## Post #5
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-04-09T20:07:17+00:00
- Post Title: Midnight Club LA (PS3)

Here's my first attempt at parsing your sample file(s).  Seems ok so far, but still lots of unknown stuff.
## Post #6
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-09T20:43:54+00:00
- Post Title: Midnight Club LA (PS3)

Oh wow thank you so much thats amazing.  did you do each part at a time or the whole model at once ? Great work man truly. Thanks for your time and effort on this. There are parts there i havent seen yet.
## Post #7
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-04-09T21:42:19+00:00
- Post Title: Midnight Club LA (PS3)

Each file is a separate part of the whole model, so one file is just a seat or chassis, etc.  Some are lower detail versions too.  I just put some of the pieces together in Blender.  The rims/tyres and stored separately as well.  So there may be some "setup" file covering the whole model somewhere.

It's odd, though, because I've also extracted the files myself from the PS3 version and they seem to be slightly different in structure to yours.  Which vehicle is your samples from, so I can check mine and see if they are the same?

It's a long way from being a useable script, but it's a start...
## Post #8
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-09T23:03:55+00:00
- Post Title: Midnight Club LA (PS3)

Strange. I hope I didnt get these files confused with the XBOX version. Im pretty sure them files were encrypted with no tools. Here is my whole folder i uploaded it to archive the files. 

[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1a0iMLkH1zt2RMPAjZQ5gu5soCvxH_qHV?usp=sharing)

I attempted to put it together to and added some things but it took about 10 hours to get this far
[](https://ibb.co/NY2nhKb)
## Post #9
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-04-10T00:17:09+00:00
- Post Title: Midnight Club LA (PS3)

Yeah, those are XBox 360 ones (including your other sample).

It's no big deal, just so I know which version I'm looking at.  I think the XBOX version is slightly easier format than the PS3.  It seems like I can get the info for all meshes from the X360 versions, although still a few issues to iron out before I can get anywhere near a proper working script!
## Post #10
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-10T01:31:01+00:00
- Post Title: Midnight Club LA (PS3)

Sorry about that, I had extracted both but i could of swore the XBOX ones were not opening for me. So if these are the XBOX ones that would mean I couldn't get the PS3 ones to open. So you got further than me on that. I tried everything too to decompress the files. Sorry about the confusion. Hopefully the files aren't too different. What tools did you use to decompress the .RPF. then the _unknown data files ? Was it one program or several ?
## Post #11
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-04-10T10:11:19+00:00
- Post Title: Midnight Club LA (PS3)

I just used RPFTool to get the initial files - it seems to work the same for both versions.

The resulting "CSR" files are compressed with standard zlib for PS3, and xmemlzx for XBox 360, so I just did a QuickBMS script that decompresses both versions (attached).


 rsc.zip
(428 Bytes) Downloaded 58 times
## Post #12
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-28T02:58:20+00:00
- Post Title: Midnight Club LA (PS3)

Any updates DK?
## Post #13
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-04-28T19:52:22+00:00
- Post Title: Midnight Club LA (PS3)

It's a complicated format.  Here's my crappy script so far.  All it does is get the basic geometry data for each file - multiple files make up the whole car.  UVs are often messed up too.  There are various LOD levels which aren't obvious from the random filenames, so I have no idea how to tell what files go together.  If I get more info I can update - some nice cars in there, so I'd like to get them properly.


 fmt_mcla_xbox360.zip
(1.41 KiB) Downloaded 60 times
## Post #14
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-28T20:06:15+00:00
- Post Title: Midnight Club LA (PS3)

Thank you anything is better than manually extracting each part. This helps so much.
## Post #15
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-29T01:30:52+00:00
- Post Title: Midnight Club LA (PS3)

[](https://ibb.co/kHSx40n)

I see the stages failed but looking at it in MR i see the padding is 24 for them. 

I also made a edit to the script to dump .mcla files instead of the _dec names. 

Thanks again for all you did. Im hoping we can get the stages too from this aswell.
## Post #16
- Username: dudex
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 16, 2021 11:47 am
- Post datetime: 2021-06-16T04:12:42+00:00
- Post Title: Re: Midnight Club LA (PS3)

> Reply from DKDave ↑Thu Apr 29, 2021 3:52 am at Thu Apr 29, 2021 3:52 am
>
> 
It's a complicated format.  Here's my crappy script so far.  All it does is get the basic geometry data for each file - multiple files make up the whole car.  UVs are often messed up too.  There are various LOD levels which aren't obvious from the random filenames, so I have no idea how to tell what files go together.  If I get more info I can update - some nice cars in there, so I'd like to get them properly.

fmt_mcla_xbox360.zip
DK, are there any updates to the plugin?
## Post #17
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-06-16T12:10:04+00:00
- Post Title: Re: Midnight Club LA (PS3)

No, I haven't done any more with it yet.
## Post #18
- Username: eyewee
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2018 2:46 am
- Post datetime: 2022-01-22T15:49:58+00:00
- Post Title: Re: Midnight Club LA (PS3)

Hey guys, what's up with all this? No signs of any progress since the last post..
## Post #19
- Username: icxcone
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 11, 2023 2:00 am
- Post datetime: 2023-10-10T18:29:44+00:00
- Post Title: Re: Midnight Club LA (PS3)

Anyone have a script or a way to change the textures??? also i'm working on solving the "DEV menu" in the game but I get an error about memory mapping", the dev menu is in the game and can be activated but i freeze when i click it.
