## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-07-21T23:21:13+00:00
- Post Title: Project Gotham Racing 4 models (.pak_hrd)

Help me convert models from Project Gotham Racing 4  

[Here the sample](http://www.sendspace.com/file/3j5l9r)
## Post #2
- Username: Tosyk
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-22T00:35:56+00:00
- Post Title: Project Gotham Racing 4 models (.pak_hrd)

this format looks annoying
the file is zlib compressed sections and appears to store information about the extracted files in the original file table.
like the model structure and dds headers.
a custom program would be needed to read these as i do not know how to read zlib easily in max.
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-07-22T00:42:35+00:00
- Post Title: Project Gotham Racing 4 models (.pak_hrd)

> Reply from chrrox
>
> this format looks annoying
the file is zlib compressed sections and appears to store information about the extracted files in the original file table.
like the model structure and dds headers.
a custom program would be needed to read these as i do not know how to read zlib easily in max.
Thanks for the info chrrox. So we need someone who can create that custom program, or maybe converter/extractor from pgr4 archives to tga/dds/dae/smd/obj 

Maybe it will be interesting to Ernegien from [his topic](http://forum.xentax.com/viewtopic.php?f=16&t=4256)
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-22T02:16:55+00:00
- Post Title: Project Gotham Racing 4 models (.pak_hrd)

could be but forza was not compressed.
## Post #5
- Username: ALYX
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Apr 08, 2010 2:33 am
- Post datetime: 2010-08-02T21:59:44+00:00
- Post Title: Project Gotham Racing 4 models (.pak_hrd)

> Most of the data for the car is in the Peugeot_Flux.pak_hrd file. This file contains mostly compressed data chunks with uncompressed data in between. I use the program "offzip" to decompress the data. The decompressed data contains no headers as the header information was already uncompressed.
>
> The compressed data starting at offset 000947ad is almostly certainly the main model's vertex data, however it does not use standard floating point. The compressed data starting at offset 000cf16d is the face array index, which are tristrips that are reset by the bytes "FF FF". This file references a model containing around 17,000 vertexes. The compressed data starting at 0002b07d contains a dds texture. The smallest compressed chunks contain a model that has 31 vertexes.
>
> Over all there are 118 compressed chunks.
Here FurryFan info about compresing. Some tools ofzip can uncompress and then we need a smart guy/girl who can easy make a convertor importer or something.
## Post #6
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2016-06-04T15:37:48+00:00
- Post Title: Project Gotham Racing 4 models (.pak_hrd)

Instead of creating a new topic I'll just bump this one.
Found this, have a nice read!
[http://www.bit-tech.net/news/gaming/200 ... ount_lie/1](http://www.bit-tech.net/news/gaming/2005/10/14/pgr3_poly_count_lie/1)
Very interesting, I've expected a much lower polycount to be honest.
It's definitely pretty impressive for a 2005 game.
## Post #7
- Username: Mondraconus
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Feb 21, 2016 1:29 pm
- Post datetime: 2016-12-21T17:52:51+00:00
- Post Title: Project Gotham Racing 4 models (.pak_hrd)

Guys, I have been opened new thread to discuss about .STREAM2, .PAK and .BPR inside game "Area" folder... I want to rip textures inside .STREAM2 file, since it's very big size, I just want to rip the textures inside it... Maybe anyone can help me please ?

Visit the thread at : viewtopic.php?f=18&t=15625

Thank you
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-03T12:29:52+00:00
- Post Title: Project Gotham Racing 4 models (.pak_hrd)

well, then, seems this thread was the beginning of "all", so let's continue here.

wheel model from "offzipped" .dat:



wheel.JPG (62.16 KiB) Viewed 536 times

(end of FI's block is a little bit hard to track; uvs are looking weird)

going to become tedious:
[](https://www.pic-upload.de/view-33858946/parts.jpg.html)
## Post #9
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-09-06T18:47:30+00:00
- Post Title: Project Gotham Racing 4 models (.pak_hrd)

wow, this's the progress, man!
## Post #10
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2017-09-13T05:31:36+00:00
- Post Title: Project Gotham Racing 4 models (.pak_hrd)

Tagging because it's important ! = D
## Post #11
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-09-14T00:00:55+00:00
- Post Title: Project Gotham Racing 4 models (.pak_hrd)

Can one of you re-upload the original files?
## Post #12
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2021-03-06T11:59:44+00:00
- Post Title: Project Gotham Racing 4 models (.pak_hrd)

Hello there, sorry to bump this thread that is more than 10 years old, although it might not be much help now, it would be interesting for people to know if they want to handle some tips:

.hdr models use zlib comp (78 DA); there are uncompressed headers before each compressed file(for textures it contains all the information regarding the DXT data(it's important to bear in mind that these textures are swizzled, they need an xbox360 script to be converted into normal DDS); for vertexes and faces it contains the count and size of section); strides might change in pgr4, while pgr3 does have a bit more standardized strides; furthermore, vertexes are short_signed(in mrp); normals int10; uvs shorts; with the faces the problem is that you need to understand the header of the whole file to use a list of faces/submaterials(almost every mesh I have seen for cars use multimesh))
.stream2 files(tracks) these change from pgr3 to pgr4; pgr3 still uses zlib(a script like the one for .hrd will work) while pgr4 use deflate(more complex to decomp; especially locating the compressed data, but the headers are much clearer to read) track files have vertexes file + another set of vertex-like + faces(i think it will also share the same problem for multimats but haven't tested as much)

I have decomped the files using python; it's kind of easy to do so by using the "import zlib"; you just need to buffer the data in an array and then you can unpack by "zlib.decompress(bytearray(comped_data))"
keeping the headers for the decompressed data is key to create an autonomous script to make 3d files on the fly, textures work fine enough if you modify the tex_dds script for 360 swizzle for noesis(prolly it was chrrox that coded it?)
## Post #13
- Username: watty256
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 12, 2017 4:29 pm
- Post datetime: 2021-03-06T15:02:16+00:00
- Post Title: Project Gotham Racing 4 models (.pak_hrd)

Sorry if this seem a noob question. So can these tools be made available?
## Post #14
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2021-03-07T12:26:44+00:00
- Post Title: Project Gotham Racing 4 models (.pak_hrd)

there are no tools, its not a tool, just a script for a program called "model researcher pro"; and no i don't have any intention of publicly releasing it, not right now, even if i released the code to unpack, its buggy and the meshes are in binary(the faces/materials problem i have not solved)
## Post #15
- Username: YEAs
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 02, 2022 10:46 am
- Post datetime: 2022-07-02T02:49:43+00:00
- Post Title: Project Gotham Racing 4 models (.pak_hrd)

im sorry for this bump but has anyone made any progress with this stuff? these models seem pretty good and theres some cars in the game that dont exist anywhere else.
## Post #16
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2022-07-02T14:08:57+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

Well, its a bit complex, as said, there is no tools that I know of, but although there are not tools, and honestly I'm a bit lazy to find any of my scripts, if you can unpack the data using the zlib libraries(at least that's what I did using python) you would be able to get raw files, the structure is fairly complex cause there is a lot of information how the game renders vehicles, from the illuminance of the vertexes to the normals, usually you will find something like vertex like information repeated and then the faces, faces are in groups from each sumbaterial....
i have unpacked before and I know of somebody that was able to work with the raw data and extract the 3d data, but honestly, it not easy nor fast.... so yeah, unless you have programming knowledge + 3d raw files knowledge, rn as is there is nothing you can do to get them models
## Post #17
- Username: YEAs
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 02, 2022 10:46 am
- Post datetime: 2022-07-02T18:57:32+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

okay actually i think i've found a way to get the models, ninja ripper 2.0.9 has support for xenia, so i think it'd be possible to rip the models
## Post #18
- Username: YEAs
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 02, 2022 10:46 am
- Post datetime: 2022-07-03T04:24:04+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

Ok update, he was able to rip a model, so it is possible.
## Post #19
- Username: gpktm
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 4:58 am
- Post datetime: 2022-08-24T09:31:50+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

Can you assist with this, please? I am trying to extract a model from PGR3. I managed to extract the pak_hrd and end up with an SCNE folder that contains a .dat file, after that point, I can't find any solution moving forward. I've heard that PGR4 has the same files as 3. You reckon you can give it a go and see if you can extract the file?
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-24T13:46:47+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

Could be helpful if you uploaded that .dat sample.
## Post #21
- Username: gpktm
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 4:58 am
- Post datetime: 2022-08-25T00:50:55+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

Oh, bugger! Sorry mate, I was under the impression that I did already.

No worries, please see attached. Keep in mind that this is a file that I have found in some other forum. By coincidence is exactly the model that I need, so hopefully what the guy uploaded is the actual model and not something else.

[https://sharemods.com/xm499p0l4x7d/00000000.dat.html](https://sharemods.com/xm499p0l4x7d/00000000.dat.html)
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-25T05:03:01+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

Thanx! I see 77 assumed vertices. But the big rest of the data looks to me as if it were still compressed.
Which decompression did you use on the pak_hrd file? I assume zlib. And how? offzip?

Funny, when I offzipped one of these headered blocks I got a face indices block:
.



FIs.jpg (171.07 KiB) Viewed 164 times
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-25T05:29:40+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

and..



circle.jpg (134.21 KiB) Viewed 161 times


Could become tedious, though.
## Post #24
- Username: gpktm
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 4:58 am
- Post datetime: 2022-08-25T09:21:46+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

Hi again

For extracting the content from .pak_hrd I've used Quick BMS. Please see link below for the original pak.hrd file.
[https://sharemods.com/d01fze02utph/Original.7z.html](https://sharemods.com/d01fze02utph/Original.7z.html)
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-25T09:44:26+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

Thanks. .dat/pak_hrd seem to be almost the same files, except for the pak_hrd missing 24 headerbytes and some bytes at the end, starting with 4D495343 ("MISC").
## Post #26
- Username: gpktm
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 4:58 am
- Post datetime: 2022-08-25T10:03:46+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

So is that round thing the only 3d model inside the file?
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-25T10:16:20+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

There's 83 assumed headers, but without knowing what's behind it you'll need to decompress/examine each block separately.
(Probably offzip loses some data. We'll have to check for the usize value in the headers, if any.)
## Post #28
- Username: gpktm
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 4:58 am
- Post datetime: 2022-08-25T10:23:45+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

OK... How do I do this, please? I have no clue about programming. The Ninja Ripper that the other guy mentioned above, doesn't do any job? I wouldn't mind paying for it, as long as I knew that it works.
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-25T10:42:27+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

> Reply from gpktm ↑Thu Aug 25, 2022 6:23 pm at Thu Aug 25, 2022 6:23 pm
>
> 
OK... How do I do this, please? I have no clue about programming.Well, that's not explained in four sentences. Just wait 'till I found some time, sooner or later. 
.



whatever_GothamRacing.jpg (123.37 KiB) Viewed 141 times


Or..

> The Ninja Ripper that the other guy mentioned above, doesn't do any job? I wouldn't mind paying for it, as long as I knew that it works.Didn't test a ripper for years. The ones I knew (including the Ninja) came with no charge and usually worked (sometimes only a scene shot, though, no T-pose and so).
## Post #30
- Username: gpktm
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 4:58 am
- Post datetime: 2022-08-25T12:16:28+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

No worries. Thanks mate!
## Post #31
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-25T13:20:04+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

Strange mix of tris and quads and no idea, where to find the uv data.
.


GothamRacing_whatever_2.jpg (96.81 KiB) Viewed 410 times
## Post #32
- Username: gpktm
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 4:58 am
- Post datetime: 2022-08-25T14:50:38+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

It looks like the correct model. What you have there is the bonnet of the car. The topology seems messed up but I can fix that. I can also see some larger triangles which I presume is the lowest LOD model.
## Post #33
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-25T16:27:26+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

You may trick around with this interior's point cloud:
.


 test-Inter_pct_cloud.zip
(100.61 KiB) Downloaded 22 times


(Sadly the belonging face indices don't fit, dunno why.)

This is the last bigger block I've extracted. (Too tedious to care for all the smaller ones.)
## Post #34
- Username: gpktm
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 4:58 am
- Post datetime: 2022-08-25T22:32:24+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

Thanks, mate. That point cloud will keep me busy, for a while.

In the meantime, can you tell me how is the process that you just did is called, please? So I can lookup for any relevant tutorials on the net and see if I can keep going myself?
## Post #35
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-26T07:57:36+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

> Reply from gpktm ↑Fri Aug 26, 2022 6:32 am at Fri Aug 26, 2022 6:32 am
>
> 
Thanks, mate. That point cloud will keep me busy, for a while.

In the meantime, can you tell me how is the process that you just did is called, please?It's "unzipping" zipped data without using header data (so there's headers but I don't use them).
Finding those headers depends on a signature. But I'd need another sample to tell more.
## Post #36
- Username: gpktm
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 4:58 am
- Post datetime: 2022-08-26T12:55:33+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

Here is your sample. This is another file uploaded on the same forum where I found the GT90 file. I hope it helps.
[https://sharemods.com/ryu5pg5dymfu/Indi ... k_hrd.html](https://sharemods.com/ryu5pg5dymfu/Indigo_Concept.pak_hrd.html)
## Post #37
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-28T20:09:35+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

Some results:
.



GT90_and_Indigo.jpg (216.08 KiB) Viewed 360 times
## Post #38
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2022-10-01T12:33:25+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

ahh, looks like you guys are making some progress on those. keep it up
## Post #39
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-13T23:43:00+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

Since there's no feedback any more I thought I should release what I had done so far (don't expect a "nice" tutorial, sorry):

It's about handling 2 files from the GT90 block0, 00000005.dat (vertices) and 00029f6a.dat (face indices).
hex2obj can't handle separated data. Adding such a feature is a shitload of coding work.

It's much simpler to binary add those files. But this requires to know which face index.dat
belongs to which vertex.dat. Seems not all files in the block folders fit together. That's the problem.
(tool for block folders see next post)

So let's give the actual scenario a last chance, won't we (GT90)?
btw, FVFize is the offs from one vertex to the next one
For floats (4 bytes) it's often 32=8x4 bytes (vvvnnnuu), vertex, normals, uvs.

- In hex2obj
toggle upper button to bigE (big endian)
toggle the 'noPtC' button to 'PtCld'.
select ShortAll (step 3 in hex2obj)

vertices, big endian, FVFsize: 20
size of 00000005.dat: 0x4B103
div 20 -> 15373 = vertex count

- load that .dat file,
press 'mesh' button (view point cloud) -> test.obj being created,

rename test.obj in block_0 to test_0.obj
----------------------------------------

face indices, Strip, terminator FFFF
00029f6a.dat, size 0x125b9
div 2 -> 37596 = face indices count

- load that .dat file,
toggle the 'PtCld' button to 'noPtC'.
press 'mesh' button (ignore the ugly mesh; know why?)

creates test.obj,
- copy face indices from it to test_0.obj:
---------------------------------------
g submesh_0
f 1/1 2/2 3/3
f 2/2 4/4 3/3
f 5/5 6/6 7/7
f 6/6 8/8 7/7
f 9/9 10/10 11/11
f 10/10 12/12 11/11
...
.



GT90_face indices.jpg (194.27 KiB) Viewed 280 times
## Post #40
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-14T00:00:04+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

You need to be familiar with offzip (see my previous posts) to get .dat files.
(Maybe first unzip the appended zip before going through this wall of text.)

You urgently need to understand that you'll need empty block folders for each model file.
You HAVE BEEN WARNED!

Here's explanation and the tool to ease things (a little bit only).

Credits go to Luigi Auriemma for offzip.exe
-------------------------------------------

Extracting Gotham Racing pak_hrd files
--------------------------------------

FAQ: 
Q: there's 97 block directories filled with uncompressed data.
   Do you really expected us to use hex2obj on them?
A: well, I feel your pain. But I'm a little bit exhausted now. 
   Time may come that someone writes a script, who knows...

Q: should I use separate working dirs for each pak_hrd file?
A: that's absolutely required. Create a copy of the unzipped 
   folder for each pak_hrd you want to uncompress.

**************************************************************
   Be sure to start in the correct directoy where all
   block_xx sub directories are EMPTY!

   Otherwise you'll be flooded with hundreds of "overwrite?"
   requests.

   You can stop this only by continuously pressing ctrl-c
   or killing the app process in the taskmanager.

**************************************************************

Use Make_H2O_GR.exe on your own risk!
   -------------------------------------
No responsibility is taken over from my side for any loss, 
   data, nerves, whatever.
   -----------------------

How to...
 Extract the files in the zip. (There's 128 empty "block_xx" dirs contained.)
 copy the .pak_hrd into the app dir. I use GT90_Concept.pak_hrd here.
 Start Make_H2O_GR.exe
 File\open to load a .pak_hrd file

BE SURE to have it in the same directory as Make_H2O_GR.exe.
YOU HAVE BEEN WARNED.
------------------------------------------------------------

- after "the Logging done." message popped up close the app.
------------------------------------------------------------

There's a lot of [absoluteAddr]_block_xx.bin files. You can ignore them for now.
The decompressed data should be found in the block_xx directories.

---------------------------
>>> Let's look into block_0.

I give an expample how to create an obj file (without uvs, so far!)
from the .dat files in the Block_0 directory:
--------------------------------------------
Same example as in the previous post, but more detailed now.
- In hex2obj toggle the 'noPtC' button to 'PtCld'.

vertices, big endian, FVFsize: 20
size of 00000005.dat: 0x4B103
div 20 -> 15373 = vertex count

- load that .dat file,
  press 'mesh' button (view point cloud) -> test.obj being created,

rename test.obj in block_0 to test_0.obj
----------------------------------------
face indices, Strip, terminator FFFF
00029f6a.dat, size 0x125b9
div 2 -> 37596 = face indices count

- load that .dat file,
  toggle the 'PtCld' button to 'noPtC'.
  press 'mesh' button (ignore the ugly mesh; know why?)

creates test.obj, 
- copy face indices from it to test_0.obj:
---------------------------------------
g submesh_0
f 1/1 2/2 3/3 
f 2/2 4/4 3/3 
f 5/5 6/6 7/7 
f 6/6 8/8 7/7 
f 9/9 10/10 11/11 
f 10/10 12/12 11/11 
...

---------------------------------

Another bigger sized candidate, block_42:
(yes, "42 is the answer";-)

Other than the above Block_0 example, the FVFsize is 28 here, surprise!
So size of 00000005.dat: 0x66440 div 28 -> 14960 vertices

(REMEMBER the 'noPtC' button handling, see above.)

- press 'mesh' -> test.obj being created,
  rename it to test_42.obj in Block_42
-----------------------------------
face indices
0003fc2f.dat, size 0x22C8E div 2 -> 71239
div 2 -> 37596 = face indices count

- press 'mesh' button

creates test.obj, 
- copy face indices from it to test_42.obj

-----------------------------------
Loading this interior into blender sadly shows up so much garbage that I'm not sure
whether 0003fc2f.dat is the suiting face indices file?

---------------------------------
Now for those "intermediate" blocks. They were spread all over the pak_hrd file,
but I collected them at the end.

Anyways, block_91
-----------------

I'd start with 0000c0e3.dat, size 0x48D8C, div 20 -> 14919
(well, looks like interior)

wheres the .dat file containing the suiting face indices?
Frankly, my dear, I've got no idea.
.


 Gotham Racing.zip
(226.64 KiB) Downloaded 32 times
## Post #41
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-14T00:20:19+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

How awful. I really hate it.   (and I guess, you will, too...  )

Anyways, here's a merging .dat files tool.

Merging two .dat files ( 1) vertex and 2) face_indices)
There's dozens of .dat files and the riddle to be solved is:
which face_index.dat belongs to which vertex.dat,
BEFORE merging them!
-------------------------------------------------------

Make_H2O_GR_b.exe, choose Extra\Merge dat

Using the exe requires two dll files from previous zip!
(I'm pretty sure, there will be dozens of people who don't get this.
 I really should have linked those dlls statically; next time...  )
-------------------------------------------------------

Name of the merged dat is like so:
nameOfVertexDat(vertex_count)_HexAddressOfFaceIndices_nameOfFaceIndexDat.dat

See picture in zip how to use parameters.

Face index count to be estimated (2.5 x vertexcount?)
until pressing go1 leads to a fitting vertex count
in the lower left list box.


 GothamRacing_merging_dat_files.zip
(165.78 KiB) Downloaded 27 times



edit: for suiting vertex-/faceindex .dat pairs see list here:

> Reply from shakotay2 ↑Sun Jun 11, 2023 5:47 am at Sun Jun 11, 2023 5:47 am
>
> 
Sadly there's not too many fitting pairs. Plus the models are not very detailed and the interest is low.
------------------------------------------------------
Thus I consider this project being finished.
So - not to do: uvs
------------------------------------------------------

last not least here's a quote from gpktm:

> It seems that the DAT files contain two LODs. One high detailed and the other one is low. Once the coordinates of the high LODs finish, it starts creating the low LOD. That's why you see those big polygons overlapping the detailed model.

And a 2nd one:

> Another interesting finding is in the interior in Block_42. The data of the interior up to a point is matching the geometry and then it starts doing some strange leaps from one point to another, then again it starts creating the mesh again properly.
>
> 
>
> 1st Part = Correct Coordinates
>
> 2nd Part = Wrong Coordinates
>
> 3rd Part = Correct Coordinates
>
> 4th Part = Wrong Coordinates
## Post #42
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-06-10T07:00:03+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

To shakotay, recently Nenkai made a documentation of the file format:

[viewtopic.php?p=192218#p192218](https://forum.xentax.com/viewtopic.php?p=192218#p192218)
## Post #43
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-10T21:47:09+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

The format is not the problem (except for the uvs, maybe) as you can see from my results:

> Reply from shakotay2 ↑Mon Aug 29, 2022 4:09 am at Mon Aug 29, 2022 4:09 am
>
> 

If it were someone would have shown a model, using the format description, wouldn't he?

The problem is to find suiting vertices/faces .dat file pairs.

So what the project is missing is a list of counts for all .dat files. (I have no idea why I didn't create it...)
"Face index count to be estimated". (Ok, need to check this. Should be doable...)

I checked W12.pak_hrd and seems there's some problems with offzip.

So I strongly recommend to start with GT90_Concept.pak_hrd as explained in the ...HowTo text file.

edit: made that counts list. .dat files containing face indices have a suffix "_FIs" (surprise  )
The other .dat file lines contain 3 counts, for the FVFsizes of 28, 20 and 14.

Where (11) in "00000004 (11).dat" for example means that I was too lazy to do the files' check recursively. Thus those with the same names/addresses were numbered.

(Files < 3kB excluded)

Sadly there's less matches than expected. Exact matches/pairs for the counts 15373, 14960 and 3475 only, afaics.

GT90_Concept.pak_hrd:

```
 00000004 (11).dat 645, 903, 1290
 00000004 (12).dat 566, 793, 1132
 00000004 (13).dat 566, 793, 1132
 00000004 (14).dat 566, 793, 1132
 00000004 (15).dat 566, 793, 1132
 00000004 (16).dat 462, 648, 925
 00000004 (17).dat 462, 648, 925
 00000004 (18).dat 462, 648, 925
 00000004 (19).dat 462, 648, 925
 00000004 (2).dat 1909, 2672, 3818
 00000004 (20).dat 363, 509, 727
 00000004 (21).dat 360, 504, 720
 00000004 (22).dat 347, 486, 694
 00000004 (23).dat 344, 482, 688
 00000004 (24).dat 344, 482, 688
 00000004 (25).dat 185, 260, 371
 00000004 (26).dat 185, 260, 371
 00000004 (27).dat 185, 260, 371
 00000004 (28).dat 185, 260, 371
 00000004 (29).dat 170, 239, 341
 00000004 (3).dat 1907, 2669, 3814
 00000004 (30).dat 147, 207, 295
 00000004 (31).dat 147, 207, 295
 00000004 (32).dat 116, 163, 232
 00000004 (33).dat 115, 162, 231
 00000004 (34).dat 115, 161, 230
 00000004 (35).dat 115, 161, 230
 00000004 (36).dat 115, 161, 230
 00000004 (37).dat 115, 161, 230
 00000004 (38).dat 111, 156, 222
 00000004 (39).dat 111, 156, 222
 00000004 (4).dat 1905, 2667, 3810
 00000004 (5).dat 750, 1051, 1501
 00000004 (6).dat 727, 1018, 1454
 00000004 (7).dat 652, 914, 1305
 00000004 (8).dat 645, 903, 1290
 00000004 (9).dat 645, 903, 1290
 00000004.dat 1910, 2674, 3820
 00000005 (2).dat 10980, 15373, 21961
 00000005 (3).dat 10656, 14919, 21312
 00000005 (4).dat 3475, 4865, 6950
 00000005.dat 14960, 20944, 29920
 000001b7.dat 111, 156, 222
 000001cf.dat 750, 1051, 1501
 000001e1.dat 185, 260, 371
 000001e6 (2).dat 185, 260, 371
 000001e6.dat 185, 260, 371
 000001eb.dat 185, 260, 371
 00000205.dat 652, 914, 1305
 00000213.dat 727, 1018, 1454
 000004c8.dat_FIs 3475
 00000743.dat 363, 509, 727
 00000d45.dat 347, 486, 694
 00000e04.dat 566, 793, 1132
 00000e13.dat 645, 903, 1290
 00000e34.dat 645, 903, 1290
 00000e44.dat 645, 903, 1290
 000017a7.dat_FIs 1909
 000017de.dat_FIs 1910
 00001e60.dat_FIs 645
 0000251e.dat 645, 903, 1290
 00002779.dat_FIs 914
 0000297a.dat_FIs 914
 00002b21.dat_FIs 1018
 00002bf9.dat 360, 504, 720
 00002d30.dat_FIs 1018
 000030b4.dat_FIs 1051
 000030ee.dat 1910, 2674, 3820
 0000327f.dat_FIs 1051
 000034c7.dat 566, 793, 1132
 00003515.dat 566, 793, 1132
 000039f1.dat 116, 163, 232
 0000437a.dat_FIs 645
 00004bb7.dat 566, 793, 1132
 00005815.dat 462, 648, 925
 00005945.dat 1909, 2672, 3818
 00006fb5.dat 462, 648, 925
 00007006.dat 1905, 2667, 3810
 0000718e.dat_FIs 1907
 000071e1.dat_FIs 1905
 00007745.dat 170, 239, 341
 00008582.dat 344, 482, 688
 00008750.dat 1907, 2669, 3814
 0000a0fd.dat 344, 482, 688
 0000a368.dat 462, 648, 925
 0000bb42.dat_FIs 1910
 0000c0e3.dat 10656, 14919, 21312
 0000cb62.dat 462, 648, 925
 0000db98.dat 115, 161, 230
 0000e1e3.dat_FIs 1905
 0000e305.dat_FIs 1909
 0000f8da.dat_FIs 1907
 00010319.dat 115, 161, 230
 00010387.dat 115, 161, 230
 00011a45.dat 115, 161, 230
 00029f6a.dat_FIs 15373

 000316ca.dat 14960, 20944, 29920
 0003fc2f.dat_FIs 14960
 000712f4.dat_FIs 14960
 00087a43.dat 3475, 4865, 6950
 0009adf0.dat_FIs 3475
 0009e1d3.dat 111, 156, 222

```

Then I merged (old list without FVFsize of 28)
 000316ca.dat 20944 (29920) and 0003fc2f.dat_FIs 14960
( 000712f4.dat_FIs 14960, alternatively?)

to 000316ca(20944)_0x66440_0003fc2f.dat and loaded them into hex2obj.
Surprise, FVFsize is 28, thus the vertex count to be corrected to 14960!
.



000316ca(20944)_0x66440_0003fc2f.png (84.18 KiB) Viewed 178 times



Sadly there's many weird faces, so my motivation is low, again...
## Post #44
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-11T12:35:17+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

Here's the list for Indigo and a result (00000005(27832)_0x87e60_0000e8ef.dat):

```
 00000004 (11).dat 386, 541, 772
 00000004 (12).dat 386, 541, 772
 00000004 (13).dat 386, 541, 772
 00000004 (14).dat 386, 541, 772
 00000004 (15).dat 377, 527, 754
 00000004 (16).dat 377, 527, 754
 00000004 (17).dat 374, 523, 748
 00000004 (18).dat 237, 332, 474
 00000004 (19).dat 237, 332, 474
 00000004 (2).dat 3336, 4670, 6672
 00000004 (20).dat 237, 332, 474
 00000004 (21).dat 237, 332, 474
 00000004 (22).dat 172, 242, 345
 00000004 (23).dat 172, 242, 345
 00000004 (24).dat 171, 240, 342
 00000004 (25).dat 171, 240, 342
 00000004 (26).dat 171, 240, 342
 00000004 (27).dat 171, 240, 342
 00000004 (28).dat 162, 228, 325
 00000004 (29).dat 162, 228, 325
 00000004 (3).dat 3336, 4670, 6672
 00000004 (30).dat 162, 228, 325
 00000004 (31).dat 162, 228, 325
 00000004 (32).dat 159, 222, 318
 00000004 (33).dat 159, 222, 318
 00000004 (34).dat 159, 222, 318
 00000004 (35).dat 159, 222, 318
 00000004 (36).dat 147, 207, 295
 00000004 (37).dat 140, 197, 281
 00000004 (38).dat 140, 197, 281
 00000004 (39).dat 140, 196, 280
 00000004 (4).dat 3336, 4670, 6672
 00000004 (40).dat 116, 163, 232
 00000004 (41).dat 115, 162, 231
 00000004 (5).dat 3336, 4670, 6672
 00000004 (6).dat 771, 1079, 1542
 00000004 (7).dat 769, 1076, 1538
 00000004 (8).dat 615, 861, 1230
 00000004 (9).dat 614, 859, 1228
 00000004.dat 4113, 5759, 8227
 00000005 (2).dat 14960, 20944, 29920
 00000005 (3).dat 10656, 14919, 21312
 00000005 (4).dat 5227, 7319, 10455
 00000005 (5).dat 3874, 5423, 7748
 00000005 (6).dat 3475, 4865, 6950

 00000005.dat 19880, 27832, 39760
 00000030 (2).dat 377, 527, 754
 00000030 (3).dat 377, 527, 754
 00000030 (4).dat 374, 523, 748
 00000030.dat 394, 551, 788
 000001cf.dat 750, 1051, 1501
 000001e1.dat 185, 260, 371
 000001e6.dat 185, 260, 371
 000001eb.dat 185, 260, 371
 00000206.dat 172, 242, 345
 00000207.dat 172, 242, 345
 00000211.dat 171, 240, 342
 0000021b.dat 140, 197, 281
 00000279.dat 5227, 7319, 10455
 00000286.dat 771, 1079, 1542
 00000743.dat 363, 509, 727
 00000e04.dat 566, 793, 1132
 00000e2d.dat 159, 222, 318
 00000e34.dat 645, 903, 1290
 00000e44.dat 645, 903, 1290
 000011cd.dat 386, 541, 772
 000011ce.dat 769, 1076, 1538
 00001f73.dat 615, 861, 1230
 0000251e.dat 645, 903, 1290
 0000267f.dat 237, 332, 474
 000027c0.dat 237, 332, 474
 00002e65.dat_FIs 615 (1827)
 00002e79.dat_FIs 614 (1778)
 000030ee.dat 1910, 2674, 3820
 0000327f.dat_FIs 1051 (2891)
 00003515.dat 566, 793, 1132
 00003a01.dat 237, 332, 474
 00003b6e.dat_FIs 769 (2187)
 00003be0.dat_FIs 771 (2203)
 00003cec.dat 237, 332, 474
 00003e62.dat_FIs 771 (2203)
 00003f0d.dat 3336, 4670, 6672
 0000437a.dat_FIs 645 (1474)
 000049af.dat 171, 240, 342
 00004bb7.dat 566, 793, 1132
 00004d38.dat_FIs 769 (2187)
 00004dd4.dat_FIs 615 (1827)
 000055ce.dat 159, 222, 318
 00005719.dat 140, 197, 281
 0000588d.dat 171, 240, 342
 00005945.dat 1909, 2672, 3818
 000064ba.dat 159, 222, 318
 00006724.dat 386, 541, 772
 00006f94.dat_FIs 3336 (6862)
 00006fb5.dat 462, 648, 925
 00006fc9.dat_FIs 3336 (6792)
 00006fef.dat_FIs 3336 (6860)
 00007014.dat_FIs 3336 (6788)
 0000761d.dat 386, 541, 772
 00007a14.dat 614, 859, 1228
 00008750.dat 1907, 2669, 3814
 00009419.dat 3336, 4670, 6672
 0000a154.dat_FIs 2369 (10410)
 0000a32f.dat 3336, 4670, 6672
 0000a368.dat 462, 648, 925
 0000a889.dat_FIs 614 (1778)
 0000ae9d.dat_FIs 3336 (6862)
 0000b1b7.dat 171, 240, 342
 0000bb42.dat_FIs 1910 (4740)
 0000bdc2.dat 159, 222, 318
 0000cb62.dat 462, 648, 925
 0000cef4.dat 386, 541, 772
 0000db98.dat 115, 161, 230
 0000e0e8.dat 162, 228, 325
 0000e305.dat_FIs 1909 (4799)

 0000e8ef.dat_FIs 19880 (61076)
 0000f8da.dat_FIs 1907 (4917)
 0000fc09.dat 3336, 4670, 6672
 00010387.dat 115, 161, 230
 000103de.dat_FIs 3336 (6792)
 0001133f.dat_FIs 3336 (6788)
 00011a45.dat 115, 161, 230
 00013584.dat 162, 228, 325
 00014516.dat 162, 228, 325
 00014cbb.dat 3874, 5423, 7748
 00014fe8.dat_FIs 7319 (28443)
 00016bf4.dat_FIs 3336 (6860)
 00019e13.dat 162, 228, 325
 00029c9e.dat_FIs 7319 (28443)
 0003fc2f.dat_FIs 14960 (66681)

```

(The Merger emits the FVF20 vertex count (27832) while it's 19880 for FVFsize= 28.)
.



00000005(27832)_0x87e60_0000e8ef-dat.png (100.1 KiB) Viewed 163 times


Faces inside this interior model are weird. Maybe it's several sub meshes?
## Post #45
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-16T09:30:40+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

I'm making a tool, it works with all cars from PGR 3 & 4.
Will be posted soon after some testing.
## Post #46
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-19T12:17:47+00:00
- Post Title: Re: Project Gotham Racing 4 models (.pak_hrd)

Still need more work with car materials and scales. Also started with maps.

Tool will be posted in a new thread there:

[viewtopic.php?t=26989](https://forum.xentax.com/viewtopic.php?t=26989)
