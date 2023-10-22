## Post #1
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-12T18:10:12+00:00
- Post Title: The Getaway (ps2) models

Hi there, just joined after finding the unpacker for this game on Zenhax: [http://zenhax.com/viewtopic.php?t=2625](http://zenhax.com/viewtopic.php?t=2625)

Saw that the engine was the same base as god of war and there was some discussion of that games 3d format here so used that as a starting point. Have some idea how to break up the data now but thought someone here might see something obvious i'm missing. Doesn't seem like hex2obj would like this format as I think the faces must be inferred through tri-strips.

This is where i'm at so far:

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
6D 6F 64 65 6C 00 00 00 "model" header

A0 00 00 00 byte size of mesh data (excludes next four bytes)
20 67 23 00 x,y,z offset?

00 00 00 00 6B BF 67 43 - 16 bytes of stuff
00 00 00 00 87 14 6D 43 

A3 0E 1C 0C 07 00 09 00 VIF codes (used to create faces recursively from vertices, 07's next to 69 = vertex count. 5th byte seems to equal vertex count if only one submesh)
01 00 00 CD 00 00 00 00 
00 80 02 69 07 00 1C 0C 
08 00 CD CD 00 00 00 00 
02 80 07 69 .................

...............00 7D 00 7D Vertices
00 00 00 83 00 7D 00 00 
00 7D 43 5C 00 00 00 83 
43 5C 00 00 00 7D 43 5C 
00 00 00 83 00 00 00 00 
00 7D 00 00 00 00 00 00

01 80 07 6A 00 00 80 00 Normal - 7 x 3(3x1 byte) with zero padding keeping 8 byte alignment, ps2 is 64bit
00 80 01 00 81 00 00 81 
00 00 80 00 00 81 01 00 
81 00 00 00 00 00 00 00 

00 80 07 65 3E 00 00 00 UV - 7 x 4(2x2 byte)
33 03 00 00 3E 00 8C 04 
33 03 8C 04 3E 00 8C 04 
33 03 EB 00 3E 00 EB 00 
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Guessed the normals and UV would be the same as God Of War - FurryFan found the same two 4 byte tags there, vertices seem to have '69' instead of '6D' in tag, maybe devs were feeling naughty.
viewtopic.php?f=16&p=68272#p68272

Any help would be appreciated.
[00002c38.zip](https://xentaxbackup.github.io/file/12993_00002c38.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-12T19:56:23+00:00
- Post Title: The Getaway (ps2) models

I'd guess for quads but autocreation of face indices might be the wrong idea:



02c38-por.jpg (245.13 KiB) Viewed 411 times


In fact there's a good chance that they use byte indices (0..255) since the model might be split up into 105 submeshes (but not sure).
## Post #3
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-12T21:00:01+00:00
- Post Title: The Getaway (ps2) models

Hmm, vertices in your example look ok, kind of building shaped. Can see what looks like storeys in the fake FI's picture, will have to try your settings and play around with faces a bit.

Maybe it will be easier if I can find a recognisable building and snapshot it in pcsx2 for comparison.

EDIT:The object you used there Shakotay started with a 'lineseg' header viewing in a hex editor, could that mean it's not meant to have faces somehow? seems those use float whereas objects starting with the 'model' header use shorts for vertices.
## Post #4
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-14T13:25:05+00:00
- Post Title: The Getaway (ps2) models

Here's a screen of one model I grabbed with fake indices, need to clean up some extra triangles but I think you can see a shop front in there.



Desktop 06.14.2017 - 13.55.24.02.png (142.48 KiB) Viewed 391 times



Had a look at the texture format too, should help to test if the mesh results match up. The format starts with the 'header image16' and seems to come after the mesh (not always alternating, sometimes two meshes before two textures, maybe for the two stories of buildings).

Unsurprisingly it's 16 bit per pixel, 128 square (Texmod gave me the res). Transparency is used in the game so I guess 5 bit per colour with 1 bit alpha makes sense.

The second two lines here seem to match the layout of the 'model' sections (2 bytes with 2 byte zero padding) so maybe some kind of header which applies to both assets.

Sample:
69 6D 61 67 65 31 36 00------------------------------------------ 'image16'
00 01 00 00 -------------------------------------------------------- Part of header? seems to be fixed value
5F 12 00 00 -------------------------------------------------------- 2 bytes, second is always 12 so maybe just a single byte variable
50 50 7B 7B 7B 7B 7B 7B 7B 7B 7B 7B 50 7F 4F 7F ------------- pixel block
6D 6D 6D 6D 15 15 15 96 EF 15 EF EF 15 15 96 EF 
6D 6D 15 6D 6D 6D 6D 6D 6D 6D 15 15 6D 6D 6D 15 
6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 15 
6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 
6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 
6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 
6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 
6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 
6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 
6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 
CA 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 6D 15 96 
6D 6D 6D 5A 6D 16 6D 6D 6D 5A 6D 16 6D 6D 95 6D 
9E 9E 9E 95 9E 3B 3B 08 9F 19 95 95 9E 9E 9E 95 
9E 9E 95 95 95 08 08 19 08 93 19 95 95 95 95 9E 
9E 9E 95 95 95 3B 3B 3B 95 95 95 96 96 96 9E 96
## Post #5
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-14T19:28:07+00:00
- Post Title: The Getaway (ps2) models

Just realised the pixel block seems to only have enough data for one row or column of 16 bit pixels, guess that must mean some kind of compression. the texmod output does seem to have some artefacts like a jpeg



Untitled.png (22.45 KiB) Viewed 382 times
## Post #6
- Username: TheGift
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 13, 2015 4:19 pm
- Post datetime: 2017-06-15T10:28:28+00:00
- Post Title: The Getaway (ps2) models

Hi



I made several Getaway 3d model rip projects, most are not done.
I can give you some insight in the format.


For the textures:

The image16 struct consists of:

unint64 Header; // image16.
uint32 always_256; 
uint32 Gim_ID;
char data[256];


The Gim_ID is the most important one.The gim textures are located in the pak file.


GIM Texture 

uint32 GIM_HEADER;
uint32 SIZE;
uint32 UNPACKED_SIZE;
uint32 NULL;
uint32 GIM_HEADER_2;
uint32 Ccccc;
uint32 UNK;
uint32 TEXTURE_ID; 


They are your usual swizzled ps2 textures, however I tried to get a texture out of them using "Console Texture Explorer".I have come close, but no sigar.

I will give more info later on the polystrips and the 256 data in the image16.
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-15T13:37:42+00:00
- Post Title: The Getaway (ps2) models

> Reply from TheGift
>
> GIM Texture
Noesis has native support for *.gim textures
## Post #8
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-16T18:13:25+00:00
- Post Title: The Getaway (ps2) models

Cheers Gift, nice to see some other people still interested in this game haha.

Ah, makes sense that the 'image16' is just a GIM reference, realised there were other sizes of texture when i used texmod again.

Again may be able to crack the format if I can find a way to link the texmod output to a particular GIM.

Ace I couldn't get Noesis to open the GIM, seems to be modified from the common psp format (starts with a GIM header rather than MIG), the actual important data might be similar to some other GIM though.
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-16T22:55:26+00:00
- Post Title: The Getaway (ps2) models

> Reply from DentistGuba
>
> Ace I couldn't get Noesis to open the GIM, seems to be modified from the common psp format (starts with a GIM header rather than MIG), the actual important data might be similar to some other GIM though.
can you upload some not working gim samples for examination please?
## Post #10
- Username: TheGift
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 13, 2015 4:19 pm
- Post datetime: 2017-06-17T08:32:19+00:00
- Post Title: The Getaway (ps2) models

I hope someone can crack the gim format, ps2 swizzling is a nightmare for me  .In the attachment are gim textures from The Getaway:Blackmonday
[Getaway Gim.rar](https://xentaxbackup.github.io/file/13004_Getaway Gim.rar)
## Post #11
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2017-06-18T06:15:18+00:00
- Post Title: The Getaway (ps2) models

Just as I suspected, you're looking at VIF code:

```
0x0010 |   V3_16             : +FLAG             : ADDR:20,  NUM:60
0x0180 |   V3_8              : +FLAG             : ADDR:10,  NUM:60
0x0240 |   V2_16             : +FLAG             : ADDR:0,   NUM:60
0x0340 |   V3_16             : +FLAG             : ADDR:0,   NUM:2
0x0350 |   V3_16             : +FLAG             : ADDR:20,  NUM:17
0x03C0 |   V3_8              : +FLAG             : ADDR:10,  NUM:17
0x0400 |   V2_16             : +FLAG             : ADDR:0,   NUM:17

```


Note that the VIF codes start at offset 0x20 after 'model' header, and is 16-byte aligned.
Apologies if I don't have more data to provide, my [VIF parser](https://github.com/Fireboyd78/driver-tools/blob/dev/GMC2Snooper/Program.cs) is horribly buggy/unfinished at the moment and was written for another game. I had to hack together code and turn off a lot of checks in order to even get this output. Also note that the "ADDR" and "NUM" stuff is part of the official spec for VIF tags used by the PS2, so it's very very low-level stuff I suppose. A lot of it is independent to each game how its processed and used, etc.

Hopefully this is useful to someone out there!
## Post #12
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-18T11:09:00+00:00
- Post Title: The Getaway (ps2) models

Thanks CarLuver, with this stuff it helps a lot to 'know what you don't know' haha.

Updated my original post with a VIF section, think I got it right.
## Post #13
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-18T16:10:03+00:00
- Post Title: The Getaway (ps2) models

Think I may have found the building I was testing with hex2obj, grabbed the texture too which seemed to fit with flatten mapping (haven't made a script yet to test uv's)



Untitled.png (182.01 KiB) Viewed 306 times



Looks a lot flatter in game so possibly meshes are normalised to use all the limited precision of short vertex coordinates (at least in the 'depth' axis).
## Post #14
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-18T19:06:31+00:00
- Post Title: The Getaway (ps2) models

Just tried a manual cleanup of the straight tri-strip model I ripped before (from 00002b1e.por in the extracted blocks at offset 32020).

30 out of 48 were 'real' faces (axis aligned edges). 

the scrap faces were:
3,4,
7,8,
11,12,
15,16,
19,20,
23,24,
27,28,
31,32,
35,36,

Here's how it looks in vertex tri-strips (blue=filling vertex buffer, red=skip face):
1,2,
3,4,
5,6,
7,8,
9,10,
11,12,
13,14,
15,16,
17,18,
19,20,
21,22,
23,24,
25,26,
27,28,
29,30,
31,32,
33,34,
35,36,
37,38,
39,40,41,42,43,44,45,46,47,48,49,50

So kind of quad based but why discarded quad padding rather than just skipping a single triangle to start the next strip. The front face of the building does form a nice neat tri-strip so maybe the dev's tools could only strip co-planar faces.

Not exactly efficient memory use, using the weld modifier in 3ds max (well gmax, I don't exactly have 2 grand to spare each year for the same program) got this model down to 20 verts - under half the original mesh. Could there be some runtime reason for this storage?
[00002b1e.zip](https://xentaxbackup.github.io/file/13013_00002b1e.zip)
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-18T19:53:59+00:00
- Post Title: The Getaway (ps2) models

dunno which face indices you used in the end but seems you're on a good way:



2B1E-por 0x32064.jpg (21.24 KiB) Viewed 299 times



(as a deja vue only: [https://forum.xentax.com/viewtopic.php? ... ds#p103400](https://forum.xentax.com/viewtopic.php?f=16&t=12561&p=103400&hilit=+dwords#p103400))

edit: upps, well, see I'm growing too old, you've posted that picture already...
## Post #16
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-19T12:58:51+00:00
- Post Title: Re: The Getaway (ps2) models

I had a look at another mesh which is a single seat bench, still seems like there are no valid single tri faces so considering a simple script to strip any lone triangles. Will have to check some more examples though. 

This bench did have some non co-planar quads in a strip together, in a partial face-loop spread between blocks.

With this model I noticed that it's split into 5 submeshes/mixed blocks with the first four being 60 vertices and the last being 40; there is no real order to the way they are separated (some quads seem to be shared between two) and I couldn't find any blocks longer than 60 elsewhere. I believe this means that is the max block length allowed (maybe to do with ps2 VU1 performance when creating faces etc?).

Might add a screenshot to show how this mesh is broken up later.
## Post #17
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-19T15:58:19+00:00
- Post Title: Re: The Getaway (ps2) models

Another random little find, was thinking about a good way to organise the OBJ files output of a script to make reassembling a scene easier (there are 'instance' blocks among the others in the archive so would be nice to enable a script to load models by name from there). For this purpose I went looking for any kind of id tag within the 'model' block.

Not yet sure if each mesh has an id given to it or if 'instance' just gives an offset to the correct one but I did find that the four bytes after the 'model' header (08 offset) seem to give the byte size of the model data (after the 16 byte header line) as a 32 bit int (or 16 bit zero padded, doubt there's any model in this game over 65kb).

6D 6F 64 65 6C 00 00 00 ---'model'
70 01 00 00 -----------------byte length
5C 81 1B 00 -----------------x,y,z offset?

As this value appears not to include the next four bytes surely they must be part of the header, should be something 'special'. I haven't seen the fourth byte be non zero and there are a lot of models with only one byte difference here so could this be x,y,z offset? (unless 'model' objects only get placed on the map by 'instance').
## Post #18
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-19T23:00:10+00:00
- Post Title: Re: The Getaway (ps2) models

Just another little update, started working on a little maxScript to import the meshes; had a fair bit of trouble til I switched from fileStream to binStream, now managed to get a 'model' header scanning function. Need to add an end of file check by reading the file size to avoid crashes if no header is found now so I can then iterate through all meshes in a file (and so max doesnt crash if you pick a file without 'model').

Now have a more robust search function, able to find and count all the 'mesh' headers in a file. Takes advantage of the 16 byte alignment by scanning the first byte of each row for 'm' before checking for 'o' and 'd' following so a fair bit quicker than string searching. got to work on reading each mesh now, already got the mesh data size and what I guess is position.
## Post #19
- Username: oldschooler95
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 07, 2016 11:17 am
- Post datetime: 2017-06-21T20:27:23+00:00
- Post Title: Re: The Getaway (ps2) models

Keep up the good work, dying to see more progress on this. 
I suspect all of the cut vehicle models (including the Capri, Cortina .etc) are still in the files along with their textures, and that Team Soho put flags to block loading certain models ingame.
## Post #20
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-21T22:51:02+00:00
- Post Title: Re: The Getaway (ps2) models

hello oldschooler, this is a fairly oldschool game haha.

here's a little more progress then, got my gmax script (similarly oldschool program) to actually show something in 3d rather than just text logs.



One of the more fun shapes i got, looks like a circus tent haha. gmax-getaway import.png (208.99 KiB) Viewed 301 times



only works with models having a single vertex block for now, larger meshes will be cut off after 60 verts so shouldn't be put off too much by the less identifiable ones.
After I add an extra little nested loop to complete these verts, the next task is a cleanup routine for the junk faces (script just tri-strips the whole vertex list) which may be easier if I can get the normal format finalised; thinking I can delete any faces not matching the vertex normals. I know it's 8bit so signed byte with normalisation to -1 to 1 makes most sense? should expect to see lots of 0, 127 and -128 then (say for the shopfront I posted earlier, all axis aligned faces).

takes about 6 seconds to grab the 80 (partial) meshes from the 512kb block file, that's out of just under 300 blocks making up 134MB. Guess it would take 30mins for the whole lot but a couple of seconds out of the six have the log frozen so might just be max waking up and not be duplicated over longer imports.

The EE archive on disk is uncompressed and using a search algo means you could in theory just mount the disk or an ISO and run the script on it directly but crashes at 25 mins in might be a bummer lol. probably best if I can batch the 298 files separately, putting each 'art_grid' block into its own max scene (some files have a couple of these).

As for cars I haven't seen any sign of where to find them yet, racingFreak managed to spawn some beta cars in game, maybe he knows some 'handles' for them. With individual objects like cars you could probably get away with a 3d printscreen type rip as they don't need to fit together perfectly with another object like the map segments. For me the London map is the main thing to save, a lot of the iconic london vehicles have been made in higher detail since anyway, including some by modders.
## Post #21
- Username: oldschooler95
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 07, 2016 11:17 am
- Post datetime: 2017-06-22T06:52:13+00:00
- Post Title: Re: The Getaway (ps2) models

Yes, he got lucky with a quite a few of them. However, stuff like the Audi TT, all of the Fords, the Chrysler Voyager, the VW Golf, the civi Jag XJ6 .etc won't load ingame. I prefer this game's vehicle model artstyle than the fancy schmancy high poly Forza car models of today.
## Post #22
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2017-06-22T07:57:19+00:00
- Post Title: Re: The Getaway (ps2) models

Hi. I can for one confirm that Capri's textures still exist in the files. I will upload samples here later on, for now I can show this:

As you can see, it's a LOD texture. There are more but I haven't extracted them yet. That in itself is exciting enough, these completely cut vehicles are true works of art and comparing them with the "better-detailed" models in newer games is kinda ignorant. For its time, The Getaway models were damn impressive and they will definitely fit other games (even GTA3-GTASA). I'd personally take the initiative to port them to MM2 as I already converted the London map from MCSR. If you're successful in extracting TG's London map I would definitely love to get it in MM2 aswell, as it is simply the best London recreation ever made for a game  

I'm really happy to see people caring about The Getaway. I bet the format isn't much different, so it will be quite easy to extract them. But I'm illiterate in that kind of stuff, so cracking model formats like this is outside my area of knowledge. Thanks and appreciate ya. I attached what I believe are LOD texture and model of the Capri.
[capri.zip](https://xentaxbackup.github.io/file/13023_capri.zip)
## Post #23
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-22T19:28:23+00:00
- Post Title: Re: The Getaway (ps2) models

Thanks RacingFreak, will have to have a peek at those other models once I finish with the map. Will probably attempt to grab the extra areas from black monday to combine into one map as well though (interiors etc). Of course I would love to see people putting this map into any games they can think of, personally I mainly want to get it playable in GTA4 (in particular the UK stuff in the lcpdfr mod). To me IV felt more like a 'getaway new york' reboot than a GTA, not so keen on V and mods for that are on shaky ground right now haha.
## Post #24
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2017-06-22T20:50:41+00:00
- Post Title: Re: The Getaway (ps2) models

That will be greatly appreciated, many thanks! A mix of TG and TGBM maps will be a great idea, as TGBM map has a lot of places missing, and on the other hand TG map doesn't have any garages. Map conversion will be pretty easy once you get hold of it. Also - I recall once glitching the player car models in such way that it loaded random props such as poles, traffic lights, etc, so I strongly believe the format is the same. Speaking of this… I seriously gotta find out how I did that  

Anyway, good luck and looking forward more progress! If you need to spawn inside certain interiors to grab textures, I can help ya.
## Post #25
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-26T13:05:14+00:00
- Post Title: Re: The Getaway (ps2) models

Been having a go at applying normals and UVs to the models in gmax, some good results but some models come out a lot worse than others.

this shows the uv map of what must be a crossroads, looks pretty close to how it should be.



uv test 1.png (115.43 KiB) Viewed 263 times


Also a few issues with faces in that model possibly but it's easy to delete the wrong ones in cleanup.

other models seem to have a bunch of perfect uv faces then a bit of a mess, not sure whats up with those.

might be worth using texmod to replace game textures with a checkerboard for comparison, some of the minor distortions might just be part of the models with textures that don't show it.

Normals also seem ok on a few models but then on others you get one perpendicular to a face, a few models end up with normals all almost pointing in the same direction so they look flat shaded. I just tried averaging the vertex normals to get the face ones, maybe the first vertex in a triangle sets it instead or something. Need to find a way to display the normals in gmax without calling the mesh update which overwrites them to get a useful screenshot.
## Post #26
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-26T14:17:45+00:00
- Post Title: Re: The Getaway (ps2) models

Ok so it was definately a good idea to check uvs in game, turns out the house I 'shotted before actually does have bad uv's as in my gmax import.



GetawayTexmodChecker.png (208.32 KiB) Viewed 261 times



Not sure what program they used to make the models or the game, guess they were in a bit of a hurry to build London haha.

some of the imports do seem too distorted to not notice in game though.
## Post #27
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-26T17:25:40+00:00
- Post Title: Re: The Getaway (ps2) models

And here's my current gmax script if anyone wants to join in looking for clues, kinda fun just trying to identify what you're looking at in itself.

Helps to disable backface culling in gmax and turn on wireframe to quickly spot parallel lines etc with the messier models


 importGetawayV0.zip
(1.88 KiB) Downloaded 55 times


put the file from this zip in scripts/startup then click the hammer icon in gmax, click MAXScript and select this script in the rollout

You can get gmax here: [https://www.turbosquid.com/gmax](https://www.turbosquid.com/gmax)

I think we may have to do some more hacking of the actual game to get confirmations of suspicions about how things work before we can get a useable map. Need to try editing the model values within the iso and test with pcsx2.

Just another little tip, use 'select by name' and 'tools-isolate' to look through the models in gmax as they all appear in one spot currently.
## Post #28
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-28T16:37:14+00:00
- Post Title: Re: The Getaway (ps2) models

Hmm, tried editing the vertex position values in the iso with hexedit but it seems the game then fails to load the 'bigfile¥1.big' chunk correctly and keeps looping through reading it. Could there be some sort of checksum there? maybe it would work better editing live memory.
