## Post #1
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2013-09-27T11:33:48+00:00
- Post Title: PSX Silent Hill Model Format Help

Using the fairly recent Silent Hills Tools pack [blog/?cat=471](http://forum.xentax.com/blog/?cat=471) the archive .HILL file can be extracted into its directorys and base files.  Im genuinely trying to learn about 3d model formats but if anyone would like to take a look it would be a big help. (Looking at the models in wireframe mode with epsxe i can tell that the map models are based on 8x8 square blocks)

A few Items are TMD that are openable with milkshape, Ive included them in the zip attached as a reference incase the other model formats are loosly based on TMD. Ive included two of each file IPD (map model) ILM (Char model) & PLM (Enemy Model)

Rename the SH Model formats.7z to SH Model formats.zip
[SH Model formats.7z](https://xentaxbackup.github.io/file/6649_SH Model formats.7z)
## Post #2
- Username: Triangle90
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 29, 2013 4:32 pm
- Post datetime: 2013-10-30T04:03:28+00:00
- Post Title: PSX Silent Hill Model Format Help

Hello, This is my first post here.

I am also interested in getting these models into a readable format. Modding for Silent Hill 1 is pretty limited at the moment, mainly due to
a lack of documentation for the formats and tools that can actually edit the files.

The tools that were released are great, but it would be nice if we were able to view the models/maps of the game somehow.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-30T08:57:29+00:00
- Post Title: PSX Silent Hill Model Format Help

IPD: strange format. Don't have a clue on the vertices.

When you start reading 378 face indices from 0x943 as big endian DWORDs (the first two bytes ignored)
in APU00FE.IPD there's a max index of 256.
But there are too many faces containing only even or only odd indices. 
So they are very unlikely to be faces.

f 1 2 4 
f 6 8 10 
f 12 14 16 
f 18 20 22 
f 24 26 28 
f 30 32 34 
f 36 38 38 
f 39 41 43 
f 45 47 49 
f 51 53 55 
f 57 59 61 
f 63 65 67 
f 69 71 73 
f 75 75 76 
f 78 80 82 
f 84 86 88 
f 90 92 94 
f 96 98 100 
f 102 104 106 
f 108 110 112 
f 112 113 115 
f 117 119 121 
f 123 125 127 
f 129 131 133 
f 135 137 139 
f 141 143 145 
f 147 149 149 
f 150 152 154 
f 156 158 160 
f 162 164 166 
f 168 170 172 
f 174 176 178 
f 180 182 184 
f 186 186 187 
f 189 191 193 
f 195 197 199 
f 201 203 205 
f 207 209 211 
f 213 215 217 
f 219 221 223 
f 223 224 226 
f 228 230 232 
f 234 236 238 
f 240 242 244 
f 246 248 250 
f 252 254 256 
f 2 4 4 
f 5 7 9 
f 11 13 15 
f 17 19 21 
f 23 25 27 
f 29 31 33 
...

(If you read them as WORDs garbage seems to be generated:)
f 44 1 45 
f 2 45 4 
f 45 6 45 
f 8 45 10 
f 45 12 45 
f 14 45 16 
f 45 18 45 
...
f 51 108 51 
f 110 51 112 
f 53 112 54 
f 113 54 115 
f 54 117 54 
f 119 54 121 
f 54 123 54 
f 125 54 127 
f 54 129 54 
...

If someone could convert FOOK.TMD and UNQ60.TMD to obj using milkshape if possible
and upload them this might be helpful.
## Post #4
- Username: Triangle90
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 29, 2013 4:32 pm
- Post datetime: 2013-10-30T10:09:56+00:00
- Post Title: PSX Silent Hill Model Format Help

Wish I had a better grasp of this stuff, I'm still reading the DGTEFF.  

Here are the converted .TMD files:

[http://www.mediafire.com/?d389twlll1oge44](http://www.mediafire.com/?d389twlll1oge44)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-30T13:50:05+00:00
- Post Title: PSX Silent Hill Model Format Help

Thx!  

Well, now let's have a look at UNQ60.TMD, which appears to be a bottle from what is in the obj.

At 0x14c0 we find some regular patterns:

8E 00 12 01 00 00 00 00 
64 00 12 01 64 00 00 00 
64 00 1F 00 64 00 00 00 
8E 00 1F 00 00 00 00 00 
8E 00 C4 FF 00 00 00 00 
26 00 3F FF 26 00 00 00 
35 00 3F FF 00 00 00 00 
4B 00 2A FF 00 00 00 00 
4B 00 0C FF 00 00 00 00 
35 00 0C FF 35 00 00 00 
56 00 2B 01 56 00 00 00 
00 00 12 01 8E 00 00 00 
00 00 1F 00 8E 00 00 00 
64 00 C4 FF 64 00 00 00 
00 00 3F FF 35 00 00 00 
35 00 2A FF 35 00 00 00 
00 00 0C FF 4B 00 00 00 
00 00 2B 01 7A 00 00 00 
9C FF 12 01 64 00 00 00 
9C FF 1F 00 64 00 00 00 
00 00 C4 FF 8E 00 00 00 
DA FF 3F FF 26 00 00 00 
00 00 2A FF 4B 00 00 00 
CB FF 0C FF 35 00 00 00 
AA FF 2B 01 56 00 00 00 
72 FF 12 01 00 00 00 00 
72 FF 1F 00 00 00 00 00 

Assuming this to be a vertices list as half floats (3x2= 6 bytes, so with an assumed VBSize of 8 we skip the 00 00 at lines' end) you'll get this:
# 0x14c0: verts= 135
v -0.000366 0.000733 0.000031 
v 1024.000000 0.000733 1024.000000 
v 1024.000000 0.006836 1024.000000 
v -0.000366 0.006836 0.000031 
v -0.000366 -4.996094 0.000031 
v 0.023438 1.999023 0.023438 
v 0.312500 1.999023 0.000031 
v 14.000000 0.054657 0.000031 
v 14.000000 0.000305 0.000031 
v 0.312500 0.000305 0.312500 
v 96.000000 0.054718 96.000000 
v 0.000031 0.000733 -0.000366 
v 0.000031 0.006836 -0.000366 
v 1024.000000 -4.996094 1024.000000 
v 0.000031 1.999023 0.312500 
v 0.312500 0.054657 0.312500 
v 0.000031 0.000305 14.000000 
v 0.000031 0.054718 49152.000000 
v -0.004879 0.000733 1024.000000 
v -0.004879 0.006836 1024.000000 
v 0.000031 -4.996094 -0.000366 

As easily can be seen: this is not a bottle.  

The sequential version looking better but still: no bottle.
# 0x14c0: verts= 135
v -0.000366 0.000733 0.000031 
v 0.000031 1024.000000 0.000733 
v 1024.000000 0.000031 1024.000000 
v 0.006836 1024.000000 0.000031 
v -0.000366 0.006836 0.000031 
v 0.000031 -0.000366 -4.996094 
v 0.000031 0.000031 0.023438 
v 1.999023 0.023438 0.000031 
v 0.312500 1.999023 0.000031 
v 0.000031 14.000000 0.054657 
v 0.000031 0.000031 14.000000 
v 0.000305 0.000031 0.000031 
v 0.312500 0.000305 0.312500 
v 0.000031 96.000000 0.054718 
v 96.000000 0.000031 0.000031 
v 0.000733 -0.000366 0.000031 
v 0.000031 0.006836 -0.000366 
v 0.000031 1024.000000 -4.996094 
v 1024.000000 0.000031 0.000031 
v 1.999023 0.312500 0.000031 
v 0.312500 0.054657 0.312500 
v 0.000031 0.000031 0.000305 
v 14.000000 0.000031 0.000031 
v 0.054718 49152.000000 0.000031

(I would like to share a H2O file for hex2obj.exe but I had to some manual corrections.
That's the problem with some "crude" formats.)
## Post #6
- Username: Triangle90
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 29, 2013 4:32 pm
- Post datetime: 2014-01-23T08:30:55+00:00
- Post Title: PSX Silent Hill Model Format Help

Bump! Has anyone had any luck with solving this?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-23T11:40:32+00:00
- Post Title: PSX Silent Hill Model Format Help

guess, you're on your own now.

For TMD you have an obj from Milkshape. So compare UNQ60.TMD
to the bottle UNQ60.obj (135 verts, 131 tex coords, 188 tris).

concerning the face indices it's just another "great" puzzle.  

The vertices are fxxxing weird, too. For example interpreting them as words
(big endian) from 0x14C0 (with each 4th word 0000 skipped) this point cloud appears:



unq60_14C0_point_cloud.JPG (7.53 KiB) Viewed 557 times



so not worth to mention (remember: it should look like a bottle!)

anyway - good luck...
## Post #8
- Username: Triangle90
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 29, 2013 4:32 pm
- Post datetime: 2014-01-26T03:10:29+00:00
- Post Title: PSX Silent Hill Model Format Help

That's okay, I will probably need to learn more about 3d models anyway. Thank-you for your assistance.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-11T17:08:21+00:00
- Post Title: PSX Silent Hill Model Format Help

I had a last glimpse at TMD format when I realized that
there is a format description on Xentax (probably since ages).
But noone of this splendid forum gave a hint. Have to think about that.

Would have spared me tons of lifetime since the face indices simply to be read from the primitives.
Finally: 


bottle_yeah.jpg (106.79 KiB) Viewed 491 times
## Post #10
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2014-11-15T11:22:26+00:00
- Post Title: PSX Silent Hill Model Format Help

awesome stuff shakotay2,  
Since my original post I started to remake the Ps1 silent hill city ..manually 
Do you think it would be possible to whip up a QuickBMS script (or something) to make the TMDs compatible with milkshape?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-15T15:32:22+00:00
- Post Title: PSX Silent Hill Model Format Help

> Reply from ReeceMix
>
> awesome stuff shakotay2,
well, I just used the format description from here:
[http://wiki.xentax.com/index.php/Playstation_TMD](http://wiki.xentax.com/index.php/Playstation_TMD)

> Since my original post I started to remake the Ps1 silent hill city ..manually
what does that mean exactly? Did you use existing 3D models?
Or did you build each model from scratch? (No, you didn't - did you?  )

> Do you think it would be possible to whip up a QuickBMS script (or something) to make the TMDs compatible with milkshape?afaik can milkshape import TMDs.
There are about 10 types of possible primitives in TMDs.
So guess some are not handled by milkshape?

If you told me which TMDs can't be imported by milkshape I could have a look at.

In the TMDs search for 04030020 (olen = 0x04; ilen =0x03; flag =0x00; mode =0x20;)

or any other of the 9 patterns (06040030,... ,09080135) to know which type of primitives is contained in a TMD
## Post #12
- Username: AndrewSFX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 27, 2014 10:26 pm
- Post datetime: 2014-11-27T16:15:37+00:00
- Post Title: PSX Silent Hill Model Format Help

Hi.
Perhaps it makes sense 

to try getting 3d with a program like 3D-Ripper-DX 
(or similar for GL) with emulator?

Maybe it's more easy way ?
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-27T18:35:55+00:00
- Post Title: PSX Silent Hill Model Format Help

> Reply from AndrewSFX
>
> Maybe it's more easy way ?Maybe.

But with the format known it makes more sense to write some import code.
Without my question answered I won't give it a try:

> If you told me which TMDs can't be imported by milkshape I could have a look at.
## Post #14
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2014-12-04T18:53:06+00:00
- Post Title: PSX Silent Hill Model Format Help

> Reply from shakotay2
>
> ReeceMix wrote:awesome stuff shakotay2, 
well, I just used the format description from here:
http://wiki.xentax.com/index.php/Playstation_TMD
Since my original post I started to remake the Ps1 silent hill city ..manually 
shakotay2 wrote:what does that mean exactly? Did you use existing 3D models?
Or did you build each model from scratch? (No, you didn't - did you?  )

I've started to build from scratch, when viewing Silent Hill in WireFrame mode it shows that the entire town is built on square grids , its pretty simple to just copy the original pattern,  it also shows that each model is loaded on an 8x8 square grid (you can see where wireframe lines overlap every 8 squares 

I also created Xploder codes for epsxe to remove the fog and camera to get a better view of the models ingame

What I meant with the Quick BMS comment was really , can you make a TMD extractor?  The TMDs that arnt stored in the 'silent' or 'hill' files (i forget which) are the ingame Items


As far as I know Epsxe doesnt work with 3D rippers because (like the original release of NullDC) it doesnt have a 'stereoscopic' plugin.  Which means it cant grab 'depth'  it just creates a flat 2D sheet of polygons (However this was about 5 years ago, things may have changed), It always seems best to follow the 'extraction' route
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-04T19:30:14+00:00
- Post Title: PSX Silent Hill Model Format Help

> Reply from ReeceMix
>
> What I meant with the Quick BMS comment was really , can you make a TMD extractor?yep, but it would take me too much time to handle all ten different model types.
If you uploaded a model sample I could have a look at.
## Post #16
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2014-12-04T20:21:08+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

> Reply from shakotay2
>
> ReeceMix wrote:What I meant with the Quick BMS comment was really , can you make a TMD extractor?yep, but it would take me too much time to handle all ten different model types.
If you uploaded a model sample I could have a look at.

The attached file (APU0000.IPD) contains city model files 

```
KOYA_BAC        SAKU            PIPE11_B        PIPE10_B        FLR01_BA       IRON5_BA       TRASHCAN       APUG03_B       GAITO3         PIPE4_BA       PIPE6_BA       PIPE3_BA        YANE1_NE        KOYA1_NE        KOYAUND_        SIGN_NEA        APU01_1         SAKU3_4         PIPE12_B        SAK4_BAC        SAK3_BAC        INPOLE_N        UMA1_HID        MGR_DRL_        FENCE           MGR01           SAKU7_FA        SAKU6_FA        APU0102         SAK2_BAC        SAK1_BAC        SAKU4_FA        SAKU5_FA        APU0
```


a TMD header is 4100 0000 0000 0000, each model file contains a 1400 0000 0000 0000 (typical hex reversal thing) 

each model file also contains descriptions , like above and for characters and monsters (Chest Arm01 Arm02 etc), I thought these were model part locations.

Hmm i dont understand a 'single' type of TMD , let alone 10 variations lol .. its OBJ i really want 
Im also working on a Mafia & Shenmue conversion too , and silent hill is a lesser project (the goal is to use all silent hill games to create an entire SH city around the lake) 

I found this information about editing the 'SILENT' container directly by editing Hex to swap models , im not really sure if any infomation here is usefull to extract the city models
[http://www.silenthillforum.com/viewtopi ... =2&t=25734](http://www.silenthillforum.com/viewtopic.php?f=2&t=25734)
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-04T22:33:45+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

well, after having had a closer look at the IPD file I've to confess that it's not as easy as I thought
to extract a TMD from IPDs.

There is none of the ten possible primitive lists contained.
Sadly I don't have the time to restart a format analysis.

You might try for yourself to get a decent point cloud. Maybe you'll get something better than this:



APU0000-IPD.jpg (78.24 KiB) Viewed 227 times



If so I would give it another try.
## Post #18
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-12-05T00:28:03+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

> Reply from shakotay2
>
> well, after having had a closer look at the IPD file I've to confess that it's not as easy as I thought
to extract a TMD from IPDs.

There is none of the ten possible primitive lists contained.
Sadly I don't have the time to restart a format analysis.

You might try for yourself to get a decent point cloud. Maybe you'll get something better than this:
APU0000-IPD.jpg

If so I would give it another try.

I will try to check the IPD files with this specifications and also I will dump the psx ram for check if the IPD are decompressed  


edit:   in file APU00FF.IPD I have obtained  point clouds from  something similar to a bulding + street
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-05T09:31:46+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

Kudos for your assistance! 

> Reply from luxox18
>
> edit:   in file APU00FF.IPD I have obtained  point clouds from  something similar to a bulding + streetrotating your scene I would guess it's not.

> [...]I will dump the psx ram for check if the IPD are decompressedthat's very likely since the uploaded IPDs are of small sizes (<44kB).

As a hint: the 4100 0000 0000 0000 TMD header ReeceMix mentioned
is contained only once in APU00FE.IPD so it should be a good one to start with.

(though in APU0000.IPD you'll find 4100 0000 0001 0000, 4300 0000 0000 0000 and similar patterns so it might not be TMD headers here)
## Post #20
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2014-12-05T22:13:01+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

> I will dump the psx ram for check if the IPD are decompressed

> that's very likely since the uploaded IPDs are of small sizes (<44kB).

I am obvs still a noob but I believe that 44kb is right for each Town Map piece, Silent Hill was a Fully 3D 'Open World' game, and on the PSX despite the towns size is pretty damn impressive , the game loads map parts in small chunks 8x8 squares being the biggest area loaded (hence why fog was used, and reallllllly noticeable when i use my 'no fog code')

These pics are just an example of how the map appears as I roatate the view (using my HighCam ActionReplay code)

the overlapping lines are the edge of each model  


My point being is that there are a lot of 44kb IPBs, there are also many many MAP.bin files .. Im fairly certain they dont contain model files and are things like triggers and area interaction/loading data

I have downloaded hex2obj and will have a look at the object, there is no specific APU0000 image but several with an APU prefix
(APU refers to Amusement Park 'Underworld') so I know Its not a street
## Post #21
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2015-04-09T12:07:03+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

Just thought I would give this thread one last request for help, I really want this town, if not I will just continue to do it by hand
## Post #22
- Username: AndrewSFX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 27, 2014 10:26 pm
- Post datetime: 2015-04-28T17:16:28+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

> 8 x 8 squares

4 x 4 you probably mean ?

It would be cool to rip SH1 scenery's and use with Unity 3D (e.g.)

don't know, what I can do to help,
except remodeling and texturing, of course

[http://silenthillcommunity.com/viewtopi ... 5&t=437110](http://silenthillcommunity.com/viewtopic.php?f=3335&t=437110)
Is your project?
## Post #23
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2015-04-30T00:33:22+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

> Reply from AndrewSFX
>
> 
http://silenthillcommunity.com/viewtopi ... 5&t=437110
Is your project?

No thats not mine , thats really awesome , just looks like I had the same idea (epsxe line mode recreation etc)
My idea was for a GTA map 'Silent City' where all the areas from the franchise were rebuilt and combined as one map.
Probablly wont happen , cool idea though

This is as far as I got
## Post #24
- Username: AndrewSFX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 27, 2014 10:26 pm
- Post datetime: 2015-04-30T09:38:45+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

this guy has been working on a tool to visualize the 3D models from Silent Hill:
[http://silenthillcommunity.com/viewtopi ... 5&t=436504](http://silenthillcommunity.com/viewtopic.php?f=3335&t=436504)
Maybe, it's a way to get models.
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-05T20:23:50+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

> Reply from AndrewSFX
>
> this guy has been working on a tool to visualize the 3D models from Silent Hill:
http://silenthillcommunity.com/viewtopi ... 5&t=436504
Maybe, it's a way to get models.that guy is putting of people since about 1 and a half year now.
So simply forget about him.  

But the other guy, Giromancy, which you linked to in your previous post, told us, how to do it:
"I use the ¨Line Mode¨ in ePSXe for reference to build each building in G.Sketchup in 1x1 square meters, then
i export it to Wings 3D to apply the UV Map, then i create the textures with Photoshop and finally export it into 
Unity 3D in 3DS Format."

I looked at level0 from his osh_demo:



osh_demo_.JPG (39.26 KiB) Viewed 127 times


So it's possible to recreate levels if you use that emulator 
(didn't try myself, to be honest  so I don't know what he means by "use for reference".
Not sure if you can rip the buildings/levels off from the emulator or have to recreate them from scratch
what seems a little bit tedious and waste of life to me.)

Sry for necroying this thread but I was astonished why there was no progress here.

(Myself I'm not too interested in SH but the levels have some disturbing aura, love it.  )
## Post #26
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2015-12-06T08:16:18+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

I've already shown that its possible to copy the grid structure 

but I dont have the time or patcience to recreate the entire thing when a form of 3D ripping/extraction could do it in minuites.

It is possible to 3D grab from epsxe , but there is no stereoscopic plugin to give the ripped model any depth , so you just end up with a mass of 2D polys, ususually when it comes to 3D model extraction if you find someone capable with the desire to do it , it gets done, so basically no-one cares enough .. *sniff*
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-06T11:29:27+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

> Reply from ReeceMix
>
> It is possible to 3D grab from epsxe , but there is no stereoscopic plugin to give the ripped model any depth , so you just end up with a mass of 2D polys,[...]thanks for clearifying.
Well, that's not nice. But as I said, I wouldn't wait for that guy, CharlesM, iirc.
## Post #28
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-06T17:07:07+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

[moved to [viewtopic.php?f=16&t=13636](http://forum.xentax.com/viewtopic.php?f=16&t=13636)]
## Post #29
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2015-12-06T21:18:39+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

I'm Pretty sure Model Viewers & Rippers Exist for Silent Hill 2 & 3 & 4 (They are all DX9 so completely rippable with 3d ripper dx or dx/ninja ripper.
I originally just wanted to make a gta sa map, I'd rather this thread stay on topic , search for Silent Hill modding tools it will take you to dedicated websites that host existing tools
## Post #30
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-07T09:30:55+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

> Reply from ReeceMix
>
> I originally just wanted to make a gta sa map, I'd rather this thread stay on topic ,sry for that. (I've moved it to a new topic now.)

> search for Silent Hill modding tools it will take you to dedicated websites that host existing toolsthx - but as you can see from the pics I've alreday found a solution.
## Post #31
- Username: Giromancy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 21, 2014 11:11 am
- Post datetime: 2016-02-23T16:58:58+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

Hi, i found a better way to build a SH1 level exactly like in the game, even using the original textures from the game disc.

Its not a rip program, you have to build the level by your own.

You have to use a program called Crocotile 3D, this program allows you to build a 3D
level using tilesets. The only problem here is, that you have to fix the colors in each textures ripped from the game, once you have the textures fixed, you can 
build a simple level in just a few minutes, you can use the ePSXe emulator with 3D Ripper DX to activate and deactivate the wireframe mode in any time for reference.

Here are two videos i made using this program:

Silent Hill 1 - 3D Tile Map (TEST) #1 
[https://www.youtube.com/watch?v=91yBN2OAd5k](https://www.youtube.com/watch?v=91yBN2OAd5k)

Silent Hill 1 - 3D Tile Map (TEST) #2 
[https://www.youtube.com/watch?v=bHb8fjWZCkQ](https://www.youtube.com/watch?v=bHb8fjWZCkQ)

As you know, almost every texture of SH1 is made by 256x256 pixels, and each texture is composed with 64 quads (squares) each square corresponds to a different texture:


In this case, this image has every texture used for sidewalks,streets, sewer cover,grass etc etc.
So you can recreate any sidewalks, street from the game using this simple texture.


Here is the same image with all the textures separated from each other for better view:
You can build anything you want using those squares, you just have to assign the UV Tile size in the Tileset window to 32x32 in Crocotile 3d and start to build your own model or recreate any part of the game.


The same rule apply for every building or level in the game, all the textures use 32x32 pixels.
This texture for example have some doors that use two squares 64x32.


ORIGINAL THREAD:
[http://silenthillcommunity.com/viewtopi ... 2&t=437581](http://silenthillcommunity.com/viewtopic.php?f=3322&t=437581)

Im currently working on the Alchemilla Hospital using Crocotile 3D and i have the entire hospital with every room already finished, this includes, BF,1F,2F,3F and even a RF. Im doing some adjustments to make it look better, openable doors with sounds, reverb zones, lighting etc.
## Post #32
- Username: Klaus
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Mar 01, 2016 5:59 am
- Post datetime: 2016-02-29T22:09:29+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

I'm using the same method as Giromancy, in 3ds Max, mapping tiles on 1x1 snapping planes. But i didn't deactivate the fog and elevate the cam, i'de be glad if someone can explain to me how it's done in ePSXe.

Edit : I found a Cheat Engine table.
## Post #33
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2016-03-01T08:33:34+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

I made the higher cam and no fog/ash codes using an Xploder Cartridge for the PSX and the codes worked for Dr Hells Action Replay GPU Wrapper in espxe
These codes are INF Heath, INF ammo, Higher Cam, No Fog, No LensFlare (other sprite stuff I forget)

800BA0BE 00000006
800BA008 0000000F
800B9D18 00008C00
800B9D1C 00008C00
800B9D24 00008C00
800B9D28 00008C00
800C4168 00000001

BUT they probabally wont work with an regular NTSC or PAL image of the game,  its a really old image that I converted from NTSC to PAL so I assume that the offsets will be different on both versions due to the conversion process.

i dont know if Cheat Engine works with epsxe but there should be a epsxe trainer , getting the codes is pretty easy , Inside there is no Fog outside there is , so thats your starting on/off yes/no variable , for the hight in the 1st DogHouse House you enter the Camera is fixed to the ceiling I just used that for Higher/Lower variables to get the codes.  I'd love to see an entire silent hill city built oneday but I have abandoned this project myself
## Post #34
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2017-10-01T06:05:05+00:00
- Post Title: Re: PSX Silent Hill Model Format Help

Hello, I with my colleagues at [Silent Hill Community](http://silenthillcommunity.com/viewforum.php?f=3335) made a tremendous job at cracking the file formats

You can read the beginning [here](http://silenthillcommunity.com/viewtopic.php?f=3335&t=438090) and latest news [here](http://silenthillcommunity.com/viewtopic.php?f=3335&t=437620&start=20) (the most importantly are the latest posts)

But I will go straight to the point. Could you please help me to understand what parts do these red squares point? One must be vertexes, faces etc. Thank you for your help!
