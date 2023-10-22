## Post #1
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2013-08-09T21:32:43+00:00
- Post Title: [PS2] Wild Arms 3 .bin archive

Hello, people.

I have become very interested in the models of characters and enemies in the PS2 RPG Wild Arms 3, and I would like some assistance on research for unpacking the models that might be inside the BTLMON.BIN file. Anyone interested?

[https://www.dropbox.com/s/yeyvkc5ycpat06j/BTLMON.BIN](https://www.dropbox.com/s/yeyvkc5ycpat06j/BTLMON.BIN)
## Post #2
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2013-11-21T21:04:28+00:00
- Post Title: [PS2] Wild Arms 3 .bin archive

My sincerest apologies for this bump, but is there anyone out there who can help?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-21T21:46:10+00:00
- Post Title: [PS2] Wild Arms 3 .bin archive

Maybe you should post a hexdump of the first 1024 (=64x16) bytes of BTLMON.BIN.
## Post #4
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2013-11-22T00:05:21+00:00
- Post Title: [PS2] Wild Arms 3 .bin archive

> Reply from shakotay2
>
> Maybe you should post a hexdump of the first 1024 (=64x16) bytes of BTLMON.BIN. I'm sorry if I sound stupid here, but where can I find a program to perform such hexdump?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-22T00:27:37+00:00
- Post Title: [PS2] Wild Arms 3 .bin archive

any hex editor will do
## Post #6
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2013-11-22T00:56:26+00:00
- Post Title: [PS2] Wild Arms 3 .bin archive

[http://www.mediafire.com/view/wdxb5q57b ... 000001.txt](http://www.mediafire.com/view/wdxb5q57b5k2dk9/BTLMON000001.txt)

Is this piece good for you, or do I have to do something else with HxD?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-22T01:29:44+00:00
- Post Title: [PS2] Wild Arms 3 .bin archive

just open the file. The pic should look like this:
[](http://www.pic-upload.de/view-21405767/boot_sek_file.jpg.html) (edit: with other values of course since this is an example file only)
## Post #8
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2013-11-22T01:49:45+00:00
- Post Title: [PS2] Wild Arms 3 .bin archive

[http://www.mediafire.com/view/h7al22e2q ... review.png](http://www.mediafire.com/view/h7al22e2qmef7al/btlmon%20preview.png)

These could be different .BIN files.

Either way, here's to the end of 000100
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-22T08:39:12+00:00
- Post Title: [PS2] Wild Arms 3 .bin archive

> Reply from SmashFan127
>
> http://www.mediafire.com/view/h7al22e2q ... review.pngthx.

> These could be different .BIN files.Of course they are.

> Either way, here's to the end of 000100As you can see this won't help since there are too many zeroes. You'll have to post another part from the next address after 0x100 where are less zeroes.

And at least 0x400 bytes are required. Or more maybe 0x800 or 0x1000 (4096 bytes).
## Post #10
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2013-11-22T21:28:45+00:00
- Post Title: [PS2] Wild Arms 3 .bin archive

[http://www.mediafire.com/view/0b7g7yb35 ... 20dots.png](http://www.mediafire.com/view/0b7g7yb35pi51bq/bit%2520after%2520first%2520dots.png)

Does not resume until 0x230, but I am sure this would be satisfying.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-22T22:12:45+00:00
- Post Title: [PS2] Wild Arms 3 .bin archive

I'm unsure whether this is a compressed file because of the regular patterns.
Maybe you should load the bin into TextureFinder to see whether/where texture are included.

Is there plain ASCII text in the bin?
## Post #12
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2013-11-22T22:31:04+00:00
- Post Title: [PS2] Wild Arms 3 .bin archive

> Reply from shakotay2
>
> I'm unsure whether this is a compressed file because of the regular patterns.
Maybe you should load the bin into TextureFinder to see whether/where texture are included.

Is there plain ASCII text in the bin?
[http://www.mediafire.com/view/28b19s6qa ... esults.png](http://www.mediafire.com/view/28b19s6qap32auw/texturefinder%2520results.png)

There seems to be some sort of info in this file, took this at the beginning offset.

[http://www.mediafire.com/view/w8wv668fd ... %25201.png](http://www.mediafire.com/view/w8wv668fd5154rd/ascii%2520results%25201.png)

Here are the results starting at offset 0x200
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-22T23:06:00+00:00
- Post Title: [PS2] Wild Arms 3 .bin archive

well, looks like there are no textures contained.
(I guess you tried all radio buttons, also the DXT ones, several widths 256, 128, 64?)

(And of course you scrolled down in the data, didn't you?  )

For the ASCII, well I meant is there something readable, such as filenames, bonenames (bip01) or anything else?
## Post #14
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2013-11-22T23:37:16+00:00
- Post Title: [PS2] Wild Arms 3 .bin archive

[http://www.mediafire.com/view/lz551rkva ... %25201.png](http://www.mediafire.com/view/lz551rkvazz7d5v/texturefinder%2520results%25201.png)

Well, I found some textures in the BTLODT.BIN file, but no bones like you said appear in ASCII.
## Post #15
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2013-11-29T04:58:39+00:00
- Post Title: [PS2] Wild Arms 3 .bin archive

My apologies for the bump.
## Post #16
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-01-12T01:54:05+00:00
- Post Title: Re: [PS2] Wild Arms 3 .bin archive

Is there anyone out there?
## Post #17
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-04-23T18:21:29+00:00
- Post Title: Re: [PS2] Wild Arms 3 .bin archive

Update:

Using TextureFinder, I was able to look inside the STGEVTD.BIN file and see what appeared to be every character portrait. Please let me know what you think.
## Post #18
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2020-10-04T00:50:28+00:00
- Post Title: Re: [PS2] Wild Arms 3 .bin archive

Quick update.

I was browsing STGEVTP.BIN in a hex editor when I came across this at the beginning.



outmap.bin? Well, there's no such file in plain sight when looking at the files on the disc. Could this be maps or...?

On another part of the file, I discover this...



There are also .bin files like these, it seems. There are sorted in order; t01.bin to t13.bin, not to mention there are "d" versions of these files as well. I can certainly come to the conclusion "t" stands for "town" while "d" stands for dungeon. There are also "e" variations, which I assume are "event" maps.

EDIT:

A while back, I found some textures inside BTLODT.BIN. I recently viewed it in a hex editor to reveal some formats as seen in the following image.

As far as I know, the extensions seen in the file are easily recognizable. I assume "vu" refers to the UV coordinates used on the textures I discovered using TextureFinder. Bone files can be seen here, along with the .mdl format and .msh, I can say must be mesh. Aside from the that, texture files are housed here, most notably .tim format.

ANOTHER EDIT:

Again, I found some more stuff inside STGEVTD.BIN. It seems to be made up of dialogue with certain numbers standing for names...

A brief example showing an in-game line of Janus, whose number is 072.



NOTICE: To anyone who would like to help with unpacking archives, let me know you are interested and I will gladly send sample files your way.

EDIT.... again...:

I can definitely say there are a ton of files for use with models of enemies inside BTLODT.BIN. The problem is writing a script to extract the files. Is there anyone who can help if I send the sample file?
## Post #19
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-01-12T08:20:27+00:00
- Post Title: Re: [PS2] Wild Arms 3 .bin archive

I used VGM toolbox to extract each model. But I noticed several things. The way they are stored isn't like anything ive ever seen. I been looking into all the .BIN files here is what I found. 

[BTL]
BTLANM.BIN - Animations (118)
BTLMED.BIN - Animations (111)
BTMEP.BIN - ?
BTLOD.BIN - Textures (128), Animations (33)
BTMON.BIN - Models (362), Textures (827), Animations (5973)
BTLOVR.BIN - ?
BTLSE.BIN ?

[STG]
BTLKAR.BIN - ?
OUTANM.BIN - Animations (32)
STGANM.VIN - Animations (178)
STGEVTD.BIN - Textures (266)
STGEVTP.BIN - ?
STGMAP.BIN - ?
STGOBJ.BIN - Animations (15)
STGOUT.BIN - Animations (247)
STGSE.BIN - ?

[Strings Used]
53536864FFFFFFFF (.tex)
82BE82DD (.model)
0A414E4D (.amn)

After getting some help from Reh over at Zenhax he showed me my .tex are actually readable. 
[](https://ibb.co/TMJWY1h)

Offset is usually 2196 and the palette is at 1170-1174. I noticed a few times it was 1172 and 1174 so just have to check. But once you do that save a .bmp. This will make it nice to get the textures from all area's without playing the game. 
Or you can do it the old way from PCSX2 and manually saving them.
[](https://imgbb.com/)
Either way textures aren't too bad. Its the models that have been a struggle. I looked at the raw information and its hard for me to decrypt. I found that I cant get anything by the raw data. Not yet at least. 
As for the save states. That's a different story. shakotay2 helped me with the script a few months ago but we still weren't able to get a proper extractor. 
[](https://ibb.co/WV6WMzX)
The results of the output were not proper uv channels. I don't know where the error is I've looked at the script for about 2 months now. I cant seem to find it. If I shift the bytes x04 i get the world.
[](https://ibb.co/Rb7VFV3)
Then I think if I shift -0x04 bytes I get this..
[](https://ibb.co/8DWTpsz)
Which appears to be the missing faces from the 1st image. Not sure what's going on there. I noticed that this was the post from some years ago. Which included a .blend file. Which i think is the key to all this.
[](https://ibb.co/BCLN3Ks)
Because in this tutorial of the extractor all the uv's look correct and he supplied all 4 main characters uv mapped.
[](https://ibb.co/KLgpvCg)
Here is the extractor he made for the eememeory 
[https://drive.google.com/file/d/195iKgJ ... sp=sharing](https://drive.google.com/file/d/195iKgJ0MIK1QNsLXW_P44jn9DcXp3KHV/view?usp=sharing)
If anyone could help with this game that would be extremely helpful! Its been quite some time.
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-24T23:54:11+00:00
- Post Title: Re: [PS2] Wild Arms 3 .bin archive

well, seems I mixed the uv channels.  

Here's an updated exe (to be copied into the Make_obj folder from the zip in sharppy's google drive):
.


 Make_obj_WA3-uvs.zip
(38.95 KiB) Downloaded 15 times


(I could add the 2nd channel after someone confirms it's working correctly now.)

edit: added 3ds.exe (uses # before comments now)
(updated Make_obj.exe to net log superfluous vt 0.0 0.0 at obj files end)

Usually you use a batch file (*.cmd) for 3ds.exe containing such line:
3ds.exe %1 > %1.obj

(to log the output into an obj file)
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-24T23:55:35+00:00
- Post Title: Re: [PS2] Wild Arms 3 .bin archive

WA3_uvs_channel1.png (45.89 KiB) Viewed 124 times
## Post #22
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-01-25T00:41:42+00:00
- Post Title: Re: [PS2] Wild Arms 3 .bin archive

Here is the updated script. Thanks again!
[WildArms3_eememory.zip](https://xentaxbackup.github.io/file/19387_WildArms3_eememory.zip)
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-25T11:29:05+00:00
- Post Title: Re: [PS2] Wild Arms 3 .bin archive

To avoid confusion I'd suggest to comment out this line (adding #) in the bms file:
#Log "fInd.bin" 0 sizefInd MEMORY_FILE3 ;

Because the fInd0000000x.bin files contain face indices that are already in the 1.3ds.obj for example.

.bin format (example, first 16 bytes) is
00 00 01 00 02 00 00 00 00 00 02 00 01 00 00 00
->
f 1 2 3, dummy 0, then f 1 3 2 (maybe for the back faces? because of counter winding), dummy 0
as a result, first face (normals not handled)
f 1/1 2/2 3/3
f 4/4 5/5 6/6
f 7/7 8/8 9/9
f 10/10 11/11 12/12
...
----------------------
The whole process (adding uvs)
```

You should get some 3ds files AND uvs.bin files (choose rename on the quickbms request!)
You will get uvs.bin, uvs00000001.bin, uvs00000002.bin,...,uvs00000007.bin

In the tools chain below
be sure to combine 1.3ds with uvs.bin, 2.3ds with uvs00000001.bin and so on.
############################################################################

- On a windows command line type
WA3_verts.cmd 1.3ds
or drag&drop 1.3ds onto the cmd file

- 1.3ds.obj being created
-------------------------------------------

change to Make_obj folder, start Make_obj.exe

File/open uvs.bin
(You may need to switch to the folder where the uvs.bin is contained.)

- Makeobj_log.obj being created, contains vt lines
(Be sure to close the tool before accessing that obj file!)

(2.3ds and uvs00000001.bin are the next "pair".)
-----------------------------------------

- copy/paste the contents of Makeobj_log.obj (vt lines) into 1.3ds.obj
  before the face indices lines

- load obj into your preferred 3D rendering software
```

(You could change the bms script to have an increasing number starting with 0: uvs0.bin, uvs1.bin,...
without the need of pressing 'r' then.)
## Post #24
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-01-30T04:11:50+00:00
- Post Title: Re: [PS2] Wild Arms 3 .bin archive

I found that if you change line 27 in the script from seek 15 to 31 you can extract the stages. There seems to be 1 triangle missing tho in each submesh. Might be the way the script is parsing faces in the new order of bytes perhaps ? Uv's are a tangled mess aswell. I found this by examining the original script to this one. 
[](https://ibb.co/4pMbdF0)
