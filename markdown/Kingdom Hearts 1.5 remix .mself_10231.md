## Post #1
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-03-17T06:42:42+00:00
- Post Title: Kingdom Hearts 1.5 remix .mself

So I took a look at the KH 1.5 remix files and the main data for each game seems to be in files like kingdom.mself, rcom.mself, with files that seem to accompany them called kingdom.self and recom.self.

are there any extractors for mself files?

i'm not sure what people need to look at to help out with this so tell me what you need and i'll try to get it. i'm really interested at the models in this game
## Post #2
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2013-03-17T09:59:10+00:00
- Post Title: Kingdom Hearts 1.5 remix .mself

Here a bms script, use the 4gb.exe to extract the >4GB files,
ALL files are encrypted with the Sony sdata 4.0.0.W Encryption, 
so far only a jailbroken PS3 can decrypt that, no PC tool (or i didn't found a working tool).

```
# by Falo
# script for QuickBMS http://quickbms.aluigi.org
# Note: All files are encrypted with sdata V4

endian big

idstring "MSF"

goto 0x10
get numFiles long
get ofsTable long
goto ofsTable

for x = 0 < numFiles

GetDString Name 0x20
get Offset LONGLONG
get Size LONGLONG
get empty LONGLONG
get empty LONGLONG

log Name Offset Size

next x
```
## Post #3
- Username: fadedsoulz
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 02, 2010 3:46 am
- Post datetime: 2013-03-29T04:34:38+00:00
- Post Title: Kingdom Hearts 1.5 remix .mself

I was able to decrypt the .sdat files. Tested with bgm and .mp4 cutscenes. Is there anyway to extract the .mself while maintaing the folder structure. The model formats seem to be the same/similar. Also, Is it possible to extract maps for this release?
## Post #4
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2013-04-02T23:59:33+00:00
- Post Title: Kingdom Hearts 1.5 remix .mself

If we had any of the decrypted files, we could try to load or otherwise figure out the maps/models' formats. How similar are the models?
## Post #5
- Username: fadedsoulz
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 02, 2010 3:46 am
- Post datetime: 2013-04-04T04:30:53+00:00
- Post Title: Kingdom Hearts 1.5 remix .mself

I'm not so sure anymore.. the new MDLS files seem to be a combination of everything. I found SFX within the models. It won't load up in noesis with the plugin relevation wrote. It may or may not be an easy fix. 

I'm going to upload an example right now. It's the biggest model so far. 

[http://www.mediafire.com/download.php?msd117589ioozuc](http://www.mediafire.com/download.php?msd117589ioozuc)

Sidenote: Do you still have all of the tools for KH1, KH2, and KH BBS? (e.g. extractors, viewers, etc) It looks like most of the links were taken down.
## Post #6
- Username: fadedsoulz
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 02, 2010 3:46 am
- Post datetime: 2013-04-04T05:43:56+00:00
- Post Title: Kingdom Hearts 1.5 remix .mself

Could someone write a bms script to extract the files within the model such as the .gtf files?
## Post #7
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2013-04-04T17:57:08+00:00
- Post Title: Kingdom Hearts 1.5 remix .mself

The uploaded model should be the Ansem/Guardian boss of the World of Chaos, not exactly an easy start.
What are .gtf files?
## Post #8
- Username: fadedsoulz
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 02, 2010 3:46 am
- Post datetime: 2013-04-04T22:14:17+00:00
- Post Title: Kingdom Hearts 1.5 remix .mself

> Reply from Azurfan
>
> The uploaded model should be the Ansem/Guardian boss of the World of Chaos, not exactly an easy start.
What are .gtf files?

.GTF files contain the textures. It's a format specific to the PS3. Mainly it serves as a way to store textures in the way that the RSX is supposed to handle them. It can be converted if we are able to extract them from the mdls file itself.
## Post #9
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2013-04-05T03:06:42+00:00
- Post Title: Kingdom Hearts 1.5 remix .mself

> Reply from fadedsoulz
>
> I'm not so sure anymore.. the new MDLS files seem to be a combination of everything. I found SFX within the models. It won't load up in noesis with the plugin relevation wrote. It may or may not be an easy fix. 

I'm going to upload an example right now. It's the biggest model so far. 

http://www.mediafire.com/download.php?msd117589ioozuc

Sidenote: Do you still have all of the tools for KH1, KH2, and KH BBS? (e.g. extractors, viewers, etc) It looks like most of the links were taken down.
Yes, I keep a vast collection of extraction and model viewing tools for KH1, KH2, BBS, 358/2 Days, and Re:coded. What are you missing specifically?
Also, this mdls file doesn't have the same header as the original MDLS file format, and as such no existing plugin can read it.
## Post #10
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2013-04-05T07:45:48+00:00
- Post Title: Kingdom Hearts 1.5 remix .mself

Really simple format:

```
# by Falo
# script for QuickBMS http://quickbms.aluigi.org

set MAX_FILES 1024

for x = 0 < MAX_FILES

GetDString Name 0x20
get Offset long
get Size long
get empty long
get empty long

math Offset += 0xC000

if Size == 0
cleanexit
endif

log Name Offset Size

next x
```

the model is the xa_ew_3020_mdlsc0.cvbb
## Post #11
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2013-04-05T14:27:20+00:00
- Post Title: Kingdom Hearts 1.5 remix .mself

Interesting, the textures have the exact same size as their originals. So much for HD.
## Post #12
- Username: fadedsoulz
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 02, 2010 3:46 am
- Post datetime: 2013-04-06T00:34:37+00:00
- Post Title: Kingdom Hearts 1.5 remix .mself

Falo can you write another script for this file? It appears to be an SFX archive. 

Also does anyone remember what letters corresponds to each world? Like EW, TW, AL, TZ, PC, DI, AW, HE, NM, PO.


Here's the file:
[http://www.mediafire.com/download.php?v9baarcrx7td101](http://www.mediafire.com/download.php?v9baarcrx7td101)
## Post #13
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2013-04-06T08:13:02+00:00
- Post Title: Kingdom Hearts 1.5 remix .mself

> Reply from fadedsoulz
>
> Falo can you write another script for this file? It appears to be an SFX archive. 

Also does anyone remember what letters corresponds to each world? Like EW, TW, AL, TZ, PC, DI, AW, HE, NM, PO.

The file has the exact same format as the mdls.

```
AW = Alice in Wonderland
DC = Disney Castle
DI = Destiny Island
DH = Dive to the Heart
EW = End of the World
EX = Extra (?)
GB = ???
HE = Hercules
LM = Little Mermaid
NM = Nightmare on Christmas
PC = (Princess Castle ?) Hollow Bastion
PI = Pinocchio
PO = Winnie Poo
PP = Peter Pan
SU = Summons
TW = Traverse Town
TZ = Tarzan
ZZ = ???
```
## Post #14
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2013-04-06T11:23:55+00:00
- Post Title: Kingdom Hearts 1.5 remix .mself

This is a combination of abbrevations SquareEnix used for KH, KHII, 358/2 Days, Re:coded and BBS. I don't know what "GB" is though, I never encountered it.

```
AW = Wonderland
BB = Beast's Castle
CA = Port Royal
CD = Castle of Dreams
DC = Disney Castle/Disney Town
DI = Destiny Islands
DH = Dive to the Heart
DP = Land of Departure
EH = The World That Never Was
ES = Realm of Darkness
EW = End of the World
EX = Extra, multiple worlds
GB = ???
HB = Hollow Bastion (KHII)
HE = Olympus Coliseum
JB = Jungle Book World (cut)
KG = Keyblade Graveyard
LK = Pride Lands
LM = Atlantica
LS = Deep Space
MU = The Land of Dragons
NM = Halloween Town
PC = Hollow Bastion (KH)
PI = Monstro
PO = 100 Acre Wood
PP = Neverland
RG = Radiant Garden
SB = Enchanted Dominion
SU = Summons
SW = Dwarf Woodlands
TR = Space Paranoids
TT = Twilight Town
TW = Traverse Town
TZ = Deep Jungle
VS = Mirage Arena
WI = Timeless River
XM = Christmas Town
YT = Mysterious Tower
ZZ = Castle Oblivion
```
## Post #15
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2013-04-29T10:28:10+00:00
- Post Title: Kingdom Hearts 1.5 remix .mself

has anyone have had luck in extracting the models/textures?
## Post #16
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2013-05-07T21:51:30+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Obviously fadedsoulz has done it and thanks to Falo's script it's not really that complicated. The major obstacle here is to have a jailbroken PS3 with a custom firmware higher than 4.00 because the encryption key for V4 SDAT is still unknown.
## Post #17
- Username: fadedsoulz
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 02, 2010 3:46 am
- Post datetime: 2013-05-17T18:48:51+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Is anyone still willing to help with figuring out the models and other data from the game?

I can start decrypting more files, but it's a labor intensive process. I can only decrypt 15 files at a time.
## Post #18
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2013-05-18T20:11:18+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Falo, kkdf2, revelation and yaz0r are the experts on these formats. The ReCoM models should be more closer to the mldx format, maybe they can still be displayed with the viewers around here.
## Post #19
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2013-05-19T06:09:29+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

we count on those 3 geniuses!
## Post #20
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-09-15T14:09:32+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

> Reply from fadedsoulz
>
> I was able to decrypt the .sdat files.
Uhm.... how?
## Post #21
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2013-09-28T13:41:50+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Some years ago I had a look at the original RE:CoM models and they were fairly simple to figure out (once you figured out the SPR compression, which was the hard part xD).

This files seems to have some common part, for example, in the PS2 version, 3D models would come with mesh + skeleton in a single file (MDL), however, in this example, the cvbb file seems to be just the skeleton matrix data, and they don't have names or hierarchy information. Matrices themselves are in the same format that the PS2 version. I haven't found the mesh data yet... But assuming it's in the same format than the PS2 version... it should be fairly simple to decode.

~Sky

EDIT: Figured out SCD sound:

-In PS2 it was ADPCM-XA Stereo 4 bits samples
-In PS3 it's LAME3 encoded MP3.

Here is all the sound present in the example file:

[http://www.mediafire.com/listen/7698jgi ... _SOUND.mp3](http://www.mediafire.com/listen/7698jgic521p534/xa_ew_3020_SOUND.mp3)

...

EDIT2: Textures are 32 bit direct color images, some of them are zwizzled, and some other aren't. Here is one example, maybe somebody can identify the model from this? Following the name convention, it should be an enemy from the End of the World...



...

EDIT3: Found the mesh data (I think) in the same cvbb file, I'll try to decode it, but it seems to be a bunch of meshed with bone data in the middle, so we'll see...

...

EDIT4: 1st mesh is 94 vertices and the 2nd one is 740, just gotta figure out what data is XYZ coordinates (and now my 3DSMax trial is over -.-), let's see...

...

EDIT5: Ouch, I forgot that, as the PS3 uses a power-PC arc processor, all it's data is in Big-Endian format... time to invert endianness!!

...

EDIT6: Alright, inverted the endianness of the 2 meshes (there are 35, but let's go step by step lol), and installed 3dsmax on the laptop. As I said, the 3D format is qute simpple. For each vertex, we 1st have normals, UV, and positions; there is some extra data (skinning), but I'm ignoring it for now. Face info is nowhere to be found, so maybe vertices are in order (I haven't tested). If I get a nice pic (I suck @ 3dsmax w/ trackpad), I'll upload it 

...
## Post #22
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2013-09-28T16:19:38+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

great news  
so ps3 has actually lower quality?
## Post #23
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2013-09-28T16:45:57+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Not really, I'd have to compare models from both versions to actually say.

In the meantime, if someone knows how to read big endian floats in maxscript, that would be great. So far I've inverted the endianness of a pair of meshes and imported them using a simple script, maybe someone can recognize this...



It's just one mesh. I can parse the entire the entire model, but as I said, it's kinda useless if one can't read big endian floats. (still no big deal, I could write y own 3D viewing program but I kinda pass xD).

~Sky

EDIT: Never mind, figured out how to read big endian floats, now, where are those faces...? (but really 3dsMax on trackpad -> wtf )

...
## Post #24
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-09-28T17:14:01+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

model sample?
## Post #25
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2013-09-28T17:53:52+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

yeah, you know, the file posted in the previous page.
Anyway, I finished the model parser, at least works with that example file. I'd need some more model files to make sure it works with all of them xD.
The parser scans normals, UV's and positions. It ignores bones/skining nad faces (there are no faces here?).

UV's are kinda useless without faces, but vertices may be sorted as triangle strip... this is how the model looks sorting vertices as indivicual triangles (pretty recognizable... Well, not by be, since I'm not a big KH fan xD):

These are all 36 meshes in the file, he kinda looks like Bahamut to me xD:



If we find the a way to sort triangles correclty, the we can decode textures and put them in the model (since we vave UV's...) 

Anyway, I'll leave this here for now, I might come back and research a little bit more if people is interested .  Regards:

~Sky
## Post #26
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2013-09-28T21:52:21+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

It's so scrambled that it's kinda impossible to figure out what it is. It looks like Marluxia's 2nd form or Marluxia's 3rd form reaper.
If you provide an original decrypted sample I may be able to do something about the triangle sorting. Looks like some faces are sharing index values and that's why it looks like that.
## Post #27
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2013-09-30T01:07:29+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

The model should be the World of Chaos endgame boss (the upper part to be exact), which looks like this:


It's probably the most complicated model of the game and not a good start to figure out how they work. I can't unpack them from the game though, so maybe fadedsoulz can provide a simplier one.
## Post #28
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2013-09-30T12:26:23+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Thanks Azurfan, you must be right, judging by that model's base, which looks exactly like the big mesh I extracted. Also the pipes right above it matches my previous texture (which also has Ansem's hands). It's also impossible for me to extract the files themselves (my PS3 can't have a CFW), so if someone's willing to post some more files, I'll be down to have a look at them 

~Sky
## Post #29
- Username: gledson999
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Mar 18, 2012 10:59 am
- Post datetime: 2013-10-07T10:29:23+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

> Reply from SkyBladeCloud
>
> Some years ago I had a look at the original RE:CoM models and they were fairly simple to figure out (once you figured out the SPR compression, which was the hard part xD).
...

Skyblade CLoud can you dend for me the Font compressed and decompressed? I found the way to input the files back edited

you can insert the font without compression, but bigger than normal, but if you edit LBA work perfectly

Kingdom Heart 1 work same thing
Kingdom Heart 2 Work with compression and without compression too

I finished the KH2 translation and translating KH1 now look this [http://gledson999.blogspot.com.br/](http://gledson999.blogspot.com.br/)
## Post #30
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2013-10-20T03:42:07+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Would like to hear more info going on about this. Wish I had cfw.
## Post #31
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2014-01-09T16:37:52+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

BUMP
## Post #32
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-04-16T21:11:15+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Well, I have 2/3 things to say.
First, the mself format isn't complicated at all. For completing the bms script, keytotruth(or truthkey) added on github an extractor, ya can check it here: [https://github.com/Truthkey/KH_1.5_MSELF_EXTRACTOR](https://github.com/Truthkey/KH_1.5_MSELF_EXTRACTOR)
Btw, stupid anecdote but I learned to truthkey how to use github :p proof: [http://puu.sh/8brBp.png](http://puu.sh/8brBp.png). I sended this pic' to him: [http://image.noelshack.com/fichiers/201 ... ed-git.png](http://image.noelshack.com/fichiers/2014/16/1397682180-how-to-used-git.png) (ya, url b\c it will take all the screen).

Anyways, all files are encrypted using the SDATA v4 encryption, created by $0ny. All files are encrypted on AES-CBC-256. The decryption key is that: 0D655EF8E674A98AB8505CFA7D012933

So why can't we just decrypt those files? Well there's another thing: a compression. I studied a little bit him a while ago and got a compression/decompression algo reversed from the ps3 sdk. For everyone who wants them they are available here: [http://pastebin.com/rYdQPmBx](http://pastebin.com/rYdQPmBx) and [http://pastebin.com/nw3R4RsJ](http://pastebin.com/nw3R4RsJ)
I never studied too much 1.5, I'm more on KH2FM. I'm just posting that for everyone who wants to know exactly how is 1.5

Bye!, GovanifY

EDIT: Since I found the compression used by the SDATA algorithm was a variant of the LZRC one, I just wanted to make a quick soft that can decrypt and decompress those file. I can thx IDA Pro and my old pastebin, they were usefull^^

Here's the link: [http://www.govanify.x10host.com/_files/SDATA_DEC.exe](http://www.govanify.x10host.com/_files/SDATA_DEC.exe)
Good romhacking
## Post #33
- Username: fadedsoulz
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 02, 2010 3:46 am
- Post datetime: 2014-10-05T05:18:19+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

I just took a look at the mself files from KH 2.5 Remix. It seems like the sdat file names are scrambled. Do you think we could get file names for the files? 
"b4c65e127b71abaf.sdat" is one of the file names from kingdom2.mself

-
Edit: there seems to be an index.dat for each folder that contains an .mself. Maybe that can help with the file names?
## Post #34
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-10-05T06:25:52+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

from the japanese version?
## Post #35
- Username: fadedsoulz
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 02, 2010 3:46 am
- Post datetime: 2014-10-05T11:46:51+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

> Reply from Devilot
>
> from the japanese version?

Yeah.. I've been looking through the files since it was released. Falo's mself script seems to be working for the new files, but I'm concerned with some of the sdat files. When I decrypted an sdat that was a TIM2 file, the header seemed to be off. I had to trim the first 16 bytes for Noesis to recognize it. I'm also having trouble with the "mlds" script for the larger files from "kingdom2.mself". The format for the files containing gtf textures seems to be similar, but I'm unable to extract anything from the archive. Either the offset is wrong or the SDAT decryption is off. I've been using Govanify's sdat tool instead of using the PS3 to decrypt, so that could have made a difference. Anyway, I'm hoping that there will be more progress on this release compared to 1.5.
## Post #36
- Username: mysis
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Aug 14, 2014 6:45 pm
- Post datetime: 2014-10-05T14:11:30+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

you might want to use the npdtool by belmondo and user ©2014 to decrypt the sdat-files. its perfectly working.

[http://www.psdevwiki.com/ps3/Dev_Tools#NPDTool_v4d](http://www.psdevwiki.com/ps3/Dev_Tools#NPDTool_v4d)
## Post #37
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-10-05T14:40:54+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

if you succeed, can you post them?
## Post #38
- Username: Namichan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 08, 2011 2:41 am
- Post datetime: 2014-10-05T19:50:21+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

-
## Post #39
- Username: mysis
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Aug 14, 2014 6:45 pm
- Post datetime: 2014-10-06T14:35:00+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

> Reply from Namichan
>
> Can anyone tell me if it is possible to extract the prerendered cutscenes/CGIs from the bbsmovie.mself and kh2movie.mself files with any of these tools/scripts?
I already tried to use the Nova Extractor, but that resulted in unplayabled swf files for me

the mself format is same as on kingdom hearts 1.5 hd remix.
the prerendered movies/cgi are in mp4 format. so after you extracted them from mself the next step would be to remove sdat encryption - doable with the npdtool i linked above.
## Post #40
- Username: Namichan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 08, 2011 2:41 am
- Post datetime: 2014-10-06T15:18:13+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

-
## Post #41
- Username: fadedsoulz
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 02, 2010 3:46 am
- Post datetime: 2014-10-06T17:34:56+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

> Reply from mysis
>
> you might want to use the npdtool by belmondo and user ©2014 to decrypt the sdat-files. its perfectly working.

http://www.psdevwiki.com/ps3/Dev_Tools#NPDTool_v4d

Thanks for sharing! I originally tried an older version that didn't work with SDAT V4. It works fine on the .mp4 files but I'm not sure about the ones with the sdat compression. I'll test that later. Do you have any idea about the "index.dat" files in each folder that has an "mself"? In addition, could someone help out with the "model" format? I'm not sure what to call it since the file names are obfuscated, but I do know that SFX and textures are contained in the dat archives after decryption. If you need to post anything, let me know!
## Post #42
- Username: crazycatz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 13, 2012 4:27 am
- Post datetime: 2014-10-08T08:30:59+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Just going to dump what I know...

> Reply from fadedsoulz
>
> Do you have any idea about the "index.dat" files in each folder that has an "mself"?The index.dat contains a list of file hashes, their size, and an incrementing number:

```
for each file:
    uint64 Hash
    uint32 Size
    uint32 File # in mself? (Starts at 0, increments by 1 for each file)
```
I know the game loads (or at least has code to load) this file when it loads the corresponding mself. I'm guessing it's used to load files without converting the hash to a string (as is stored in mself filenames).

---

All files seem to be wrapped in a common header, which is:

```
uint   DataSize
uint   AdditionalFileCount
byte*8 Padding?
foreach additionalFile:
    byte*32 FileName
    uint    Absolute Offset
    uint    ?
    uint    Size
    uint    Padding?
byte*dataSize Data
foreach additionalFile:
    byte*Size Data
```
I've only tested this on models (?; the ones with the GTFs), but it should work for any file:

```
# by Crazycatz
# script for QuickBMS http://quickbms.aluigi.org

endian big

get Size LONG
get H_Files LONG
goto 8 0 SEEK_CUR

# xmath fails for me ~.~
math Offset = H_Files
math Offset *= 48
math Offset += 16
get Name BASENAME
string Name += ".bin"
log Name Offset Size

for i = 0x0 < H_Files
    GetDString Name 0x20
    get Offset LONG
    get Unknown LONG
    get Size LONG
    goto 4 0 SEEK_CUR
    log Name Offset Size
next i
```
Though most filetypes don't have any additionalFiles, so often times the first 16 bytes can just be removed.

---

Random notes:

Audio files have the signature "SEDBSSCF", and are mostly (all?) 192 kbps CBR MP3. (I can't play a few of them.)
    bd21b6eb3dc3dc52 is a version of Dearly Beloved with interlaced channels or something.
The KH2 mself has BAR and IMD files, which are the format used in the PS2 version. I don't know if they're used, but they are in big-endian (PS2 was little-endian).
## Post #43
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2014-10-12T08:54:21+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Thanks for the script crazycatz.
## Post #44
- Username: crazycatz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 13, 2012 4:27 am
- Post datetime: 2014-10-12T19:32:22+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Quick update, I got the hashing algorithm and a program that can extract the MSELF with names.
[http://crazycatz00.x10host.com/KH/files ... 25Tools.7z](http://crazycatz00.x10host.com/KH/files/app_KH25Tools.7z)
(For the cautious, it's written in .NET, so Reflector or something can open.)

The hash method is actually MD5, but cut in half.
So "00battle.bin" has the MD5 "764d15394e82c389afdc883ed4ba8f5a" and 2.5 uses "764d15394e82c389". (Note that, because I was lazy and forgot, my program prints hashes in little endian, so it would say "89C3824E39154D76". It does work right otherwise though.)
## Post #45
- Username: Haevens
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 15, 2014 11:40 pm
- Post datetime: 2014-10-14T15:28:30+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

@crazycatz
Is it possible to have the same for KH BBS?
because that the files no name comes out.
## Post #46
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-10-16T06:43:39+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

> Reply from crazycatz
>
> Quick update, I got the hashing algorithm and a program that can extract the MSELF with names.
http://crazycatz00.x10host.com/KH/files ... 25Tools.7z
(For the cautious, it's written in .NET, so Reflector or something can open.)

The hash method is actually MD5, but cut in half.
So "00battle.bin" has the MD5 "764d15394e82c389afdc883ed4ba8f5a" and 2.5 uses "764d15394e82c389". (Note that, because I was lazy and forgot, my program prints hashes in little endian, so it would say "89C3824E39154D76". It does work right otherwise though.)
Hello my friends link has expired, be able to upload
## Post #47
- Username: raulr
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 25, 2014 11:23 pm
- Post datetime: 2014-10-25T15:26:56+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

I couldn't extract the files in ReCODED.mself.
How can I extract them?
## Post #48
- Username: mysis
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Aug 14, 2014 6:45 pm
- Post datetime: 2014-11-10T13:33:09+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Hi, 

i updated the noesis plugin for kingdom hearts 1.5 hd mdls files, but its not quite working..

it reads + exports textures fine, the only problem is displaying bones/models...



i'm pasting the code here if anyone wants to participate updating it

[http://pastie.org/private/frmctfymczyre8kxb8m8jq](http://pastie.org/private/frmctfymczyre8kxb8m8jq)
[kingdom_hearts_ps3.rar](https://xentaxbackup.github.io/file/8060_kingdom_hearts_ps3.rar)
## Post #49
- Username: jadentheman
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Oct 24, 2014 7:21 am
- Post datetime: 2014-11-30T14:31:41+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

2.5 models still work teh same way, but it's textures are gtf right?

So we can modify the old KH2 and BBS scripts to read big endian and convert gtf?
## Post #50
- Username: mysis
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Aug 14, 2014 6:45 pm
- Post datetime: 2014-12-05T12:49:29+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

theoretically yes.
## Post #51
- Username: Silverwarrior
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 23, 2012 11:13 pm
- Post datetime: 2015-05-21T13:46:04+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Hii this thread has been really helpful.

I've extracted the files from the KH2.mself file, and i've got a bunch of mdlx which i ran through quickbms, which spat out the gtf files, but I'm lost at how to view the models in noesis. Am I missing something?
## Post #52
- Username: mysis
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Aug 14, 2014 6:45 pm
- Post datetime: 2015-05-22T13:00:14+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

the plugin doesnt work for the ps3 models
## Post #53
- Username: Silverwarrior
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 23, 2012 11:13 pm
- Post datetime: 2015-05-24T16:52:50+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Ah thanks, I thought that might have been the case. No worries 

Am I also right in thinking that there is no way to unpack the BBS.mself into a directory structure similar to KH2?
## Post #54
- Username: mysis
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Aug 14, 2014 6:45 pm
- Post datetime: 2015-05-24T17:10:23+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

just leaving this here
## Post #55
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2015-05-25T04:19:17+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Does anyone have this Noesis plugin available for download?
## Post #56
- Username: Silverwarrior
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 23, 2012 11:13 pm
- Post datetime: 2015-05-31T22:26:58+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

To add to the above, how does one extract the files from the BBS.Mself so that they're not random bin files?
## Post #57
- Username: happymulan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 16, 2015 10:39 am
- Post datetime: 2015-10-23T04:58:56+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Any news for a tool to rip the models from 1.5? Is been a while that nobody has upload something in this discussion...
## Post #58
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2015-10-30T06:34:48+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

I'm also still interested in the HD models of Birth by Sleep, has Mysis' Noesis plugin surfaced somewhere?
## Post #59
- Username: telespentry
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 15, 2016 1:02 am
- Post datetime: 2016-01-14T17:06:49+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

> Reply from mysis
>
> just leaving this here

Any progress on this?
## Post #60
- Username: headgehof
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jun 27, 2010 10:11 pm
- Post datetime: 2016-05-25T05:17:19+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

[http://crazycatz00.x10host.com/KH/files ... 25Tools.7z](http://crazycatz00.x10host.com/KH/files/app_KH25Tools.7z)

please re upolod this tool
## Post #61
- Username: Sora6645
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 24, 2014 4:16 am
- Post datetime: 2016-05-28T02:59:38+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

is there any way to get the text from 1.5 HD? I am working on the english patch and i wanted to know if the text is easy enough to get.
## Post #62
- Username: PuNkY
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 22, 2020 2:38 pm
- Post datetime: 2020-12-22T07:09:04+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Hi ! I REALLY sorry to wake this thread from the deads.
This board is one of the only source of information about KH 1.5 .mself and .scd files over the internet, and maybe you are the only one who can help me.

What I am trying to do is to import french, german and spanish (F/G/S)  voices(dubbing) that was available on the original PS2 game into the 1.5 HD Remix on Playstation 3. 

Before you ask :
-It IS because some people here in europe are very nostlagic of these voices. (Disney's characters are all dubbed with their F/G/S official voices).
-Not having all the final mix cutscenes dubbed in F/G/S  is not a problem for me.
-I know it is not in HD audio quality but I don't mind. 

What I have done :

-Extracted all voices vset/vbs files from Europeeans KH1 PS2 isos.
-Unpacked all .vbs files from this sames sources to VAG + WAV files with the same names
-Unpacked kingdom.mself
-Unpacked all of the _vbs.hqa files to access the .scd files (that can be renamed to mp3 and played).
-Replaced all PS3 vset files in extracted .mself folder with PS2's vset files (file names and size matching perfectly)

What I know :

PS2 .vbs files names are matching with PS3 _vbs/.ps3.scd files names. Is ok.
Tool to extract ;vbs to mutliple .wav exist but not one to convert .vbs to one file MP3 (so I can replace .ps3.scd voice files with PS2 .vbs voice files converted to mp3)

What is blocking me :
-I don't know how to repack the .mself to replace original kingdom.mself by my modded kingdom.mself. 
-I don't know how to repack my .scd files into .hqa

My Questions

How to repack .scd to vsb_hqa AND how to repack .mself files ?
-What is vset.hqa files ? What's the difference with .vset ? Are they important ?

I am a litteral noob don't judge me, I am just trying to please a bunch of EU players (and me too btw, I love the french dubbing of this game)
Thank you for your answers and have a nice day.

To be clear : I own US and Eu versions of the PS3 Games AND the PAL versions of KH 1 for PS2. The final goal is to make a patch, not to release an undubbed iso.
## Post #63
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-12-22T10:11:23+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

Can you upload samples of the files you want to repack?
What programs do you use to unpack .scd and .mself?
## Post #64
- Username: PuNkY
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 22, 2020 2:38 pm
- Post datetime: 2020-12-22T10:34:45+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

> Reply from ikskoks ↑Tue Dec 22, 2020 6:11 pm at Tue Dec 22, 2020 6:11 pm
>
> 
Can you upload samples of the files you want to repack?
What programs do you use to unpack .scd and .mself?

I have used KH1.5_mself extractor (found here : [https://www.patreon.com/posts/kingdom-hearts-1-27294064](https://www.patreon.com/posts/kingdom-hearts-1-27294064) )to extract both mself and hqa.

Here is sample zip with 1 PS2 .vsb file and PS3 .scd and hqa for the same voiceclips : [https://we.tl/t-ewFz2Rox55](https://we.tl/t-ewFz2Rox55)


Edit : I read that PS3 Game Extractor ([https://www.psx-place.com/resources/ps3 ... actor.824/](https://www.psx-place.com/resources/ps3-game-extractor.824/)) can pack/unpack .mself but I can't make it work the soft always say he can't find filelist.xml wherever I try to unpack or repack kingdom.mself
## Post #65
- Username: VincentHuntBleh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 20, 2021 11:20 am
- Post datetime: 2023-06-10T12:25:00+00:00
- Post Title: Re: Kingdom Hearts 1.5 remix .mself

> Reply from PuNkY ↑Tue Dec 22, 2020 6:34 pm at Tue Dec 22, 2020 6:34 pm
>
> 
ikskoks wrote: ↑Tue Dec 22, 2020 6:11 pm
Can you upload samples of the files you want to repack?
What programs do you use to unpack .scd and .mself?


I have used KH1.5_mself extractor (found here : https://www.patreon.com/posts/kingdom-hearts-1-27294064 )to extract both mself and hqa.

Here is sample zip with 1 PS2 .vsb file and PS3 .scd and hqa for the same voiceclips : https://we.tl/t-ewFz2Rox55


Edit : I read that PS3 Game Extractor (https://www.psx-place.com/resources/ps3 ... actor.824/) can pack/unpack .mself but I can't make it work the soft always say he can't find filelist.xml wherever I try to unpack or repack kingdom.mself

Did anyone ever made any progress with this ?
