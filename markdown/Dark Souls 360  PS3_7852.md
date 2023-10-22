## Post #1
- Username: finale00
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-12T23:08:09+00:00
- Post Title: Dark Souls 360 / PS3

Here is an archive extractor for Dark Souls 360 / PS3

```
#quickbms script by chrrox
open FDDE BHD5 0
open FDDE BDT 1
endian BIG
idstring "BHD5"
get NULL long
get ONE long
get ARCSIZE long
get TABLES long
GET TABLEPOS long
for j = 0 < TABLES
goto TABLEPOS
get FILES long
get OFFSET2 long
savepos TABLEPOS
goto OFFSET2
for i = 0 < FILES
get HASH long
get SIZE long
get OFFSET longlong
goto OFFSET 1
get TYPE long 1
if TYPE == 0x44435800
math OFFSET + 0x4C
getdstring NULL 0x18 1
get SIZE long 1
get ZSIZE long 1
clog "" offset zsize size 1
else
log "" offset size 1
endif
next i
next j

```
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-12-12T23:41:15+00:00
- Post Title: Dark Souls 360 / PS3

I can confirm the PS3 data files have the same format.
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-13T06:31:41+00:00
- Post Title: Dark Souls 360 / PS3

that is perfect thx
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-13T06:54:29+00:00
- Post Title: Dark Souls 360 / PS3

Can anyone have a look up to bnd files pelase i think in there are texts ?

```
http://dl.dropbox.com/u/38234344/dvdbnd1.rar
```
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-13T11:20:37+00:00
- Post Title: Dark Souls 360 / PS3

bnd files are archives very simple format ill post an extractor for them if no one else does tonight.
## Post #6
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-13T13:54:20+00:00
- Post Title: Dark Souls 360 / PS3

> Reply from chrrox
>
> bnd files are archives very simple format ill post an extractor for them if no one else does tonight.

Thx chrrox. It would be repacker or just unpacker ? Reason is i would like to translat this game into my lang.

thx
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-14T10:06:00+00:00
- Post Title: Dark Souls 360 / PS3

> Reply from chrrox
>
> bnd files are archives very simple format ill post an extractor for them if no one else does tonight.

Any news pls ?
## Post #8
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-12-14T17:04:51+00:00
- Post Title: Dark Souls 360 / PS3

I just tried the script on a PS3 version and I got the following:

Error: The compressed zlib/deflate input it wrong or incomplete (-3)

Error: There is an error with the decompression. The returned output size is negative (-1)
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-14T17:51:49+00:00
- Post Title: Dark Souls 360 / PS3

You need to rip the file yourself from the ps3 there are bad rips floating around the internet.
## Post #10
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-12-15T08:43:16+00:00
- Post Title: Dark Souls 360 / PS3

Okay, the script works fine on a proper scene release of Dark Souls.

Thank you so much Chrrox
## Post #11
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2011-12-16T23:25:28+00:00
- Post Title: Dark Souls 360 / PS3

this is nito! anyway I got sucked into this game and here I am noobin.

Game uses [http://en.wikipedia.org/wiki/PhyreEngine](http://en.wikipedia.org/wiki/PhyreEngine) and seems to have similar files as Armored Core and others.
nice article kind of..as i look for PhyreEngine file types [http://www.eurogamer.net/articles/digit ... s-face-off](http://www.eurogamer.net/articles/digitalfoundry-dark-souls-face-off) & [http://research.scee.net/files/presenta ... Engine.pdf](http://research.scee.net/files/presentations/gdc2011/2011-GDC-PhyreEngine.pdf)

dvdbnd0 files
bnd - 3,072 files. Archived HKX, TPF, FLEV, SIBCAM files?
bdf - 111 files
bhf - 77 files. Archived environmental TPFs and HKXs
dat - 300 files.
edf - 1 file. 
eld - 26 files.
evd - 27 files.
fev - 251 files. Fmod Event files
flv - 1,364 files. FLEV Models
fsb - 248 files. sound PCM WAV
fss - 2 files.
tpf -12 files.  Archived Graphics - DCXs maybe (multipage PCX)?
map -2 files. Archived "Mapstudio" MSB files
mof - 3 files.
neo - 16 files. Archived SIB files.
npf - 1 file.
obj - 16 files.


dvdbnd1 files seems to be dashboard, start up and game menu stuff
bnd - 41 files. Archived camera, fx, language PARAM files
brd - 3 files.
dat - 2 files. Various parameters for fx and networking.
img - 7 files.
png - 3 files. Just a png (3 identical dashboard game icons - darksouls logo)
tae - 1 file. Parameters
tpf - 47 files. Archived Menu, lighting fx and font graphics
ttf - 2 files. Not windows standard TTF
## Post #12
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-19T06:59:22+00:00
- Post Title: Dark Souls 360 / PS3

anyone news pls ?
## Post #13
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-01-03T20:54:27+00:00
- Post Title: Dark Souls 360 / PS3

anything new in regards to the FLEV 3d format in use here?
## Post #14
- Username: Phrexeus
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 04, 2012 10:43 am
- Post datetime: 2012-01-04T02:47:24+00:00
- Post Title: Dark Souls 360 / PS3

Would also be very interested if anyone can shed light on the FLEV format or anything to do with getting 3D assets into mainstream 3D software.

Thanks chrrox for the extractor, i'll try it soon.
## Post #15
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-01-04T14:06:33+00:00
- Post Title: Dark Souls 360 / PS3

The BND files that you get from the main BDT seem to contain havoc hkx, tpf textures and flev 3d files... But how to extract the bnd!

and I would guess even if we do exctract it, we will have the same tpf files that are in the BDT which don't seem to open with anything and FLEV files that are identical to the FLV files.
## Post #16
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-01-07T22:03:42+00:00
- Post Title: Re: Dark Souls 360 / PS3

> Reply from chrrox
>
> bnd files are archives very simple format ill post an extractor for them if no one else does tonight.

The  Dark Souls BND doesn't get unpacked by offzip. Perhaps it has data that is encrypted or all over the place? The header is BND307D7R6 while BNDs from other from soft games have BND3JP100 and easily extract.

edit: well if you use offzip -a -z -18 or -15 you do catch some random files but not the tpfs, hkxs or flevs
## Post #17
- Username: hatyn
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-08T00:02:02+00:00
- Post Title: Re: Dark Souls 360 / PS3

here is the bnd extractor script

```
idstring "BND307D7R6"
goto 0x10
get files long
get start long
goto 0x20
savepos tbl
for i = 0 < files
goto tbl
get unk01 long
get zsize long
get offset long
get unk02 long
get nameoff long
get size long
savepos tbl
math nameoff + 3
goto nameoff
get name string
if zsize == size
log name offset zsize
else
clog name offset zsize size
endif
next i
```
## Post #18
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-01-08T00:25:38+00:00
- Post Title: Re: Dark Souls 360 / PS3

huge thanks, works a charm!

* the files we now have are FLVER, TPF and HKX.

- FLVER files won't open with an existing blender import script posted by a user on the forum just yet

- TPF files are a mystery but seem to be packed graphics. Some olf TPF extraction tools don't work with them. Perhaps source code will help.

- HKX files might be able to be opened after conversion to XML havok format. Here is a link. Will check it myself later on. [https://github.com/figment/hkxcmd](https://github.com/figment/hkxcmd)
## Post #19
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-01-08T08:28:26+00:00
- Post Title: Re: Dark Souls 360 / PS3

> Reply from hatyn
>
> huge thanks, works a charm!

* the files we now have are FLVER, TPF and HKX.

- FLVER files won't open with an existing blender import script posted by a user on the forum just yet

- TPF files are a mystery but seem to be packed graphics. Some olf TPF extraction tools don't work with them. Perhaps source code will help.

- HKX files might be able to be opened after conversion to XML havok format. Here is a link. Will check it myself later on. https://github.com/figment/hkxcmd

Does any files contains texts pls ?
## Post #20
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-01-08T14:31:09+00:00
- Post Title: Re: Dark Souls 360 / PS3

*EDIT

I guess you mean texts for the SUBTITLES! argh..ill have a look. I think someone on the internet already knows where they are - will see if they can tell.

here are text dumps someone made before:
[http://dl.dropbox.com/u/21923599/ds1.txt](http://dl.dropbox.com/u/21923599/ds1.txt)
[http://dl.dropbox.com/u/21923599/ds2.txt](http://dl.dropbox.com/u/21923599/ds2.txt)



-----------------------------------------
They all sometimes have text.

FLEV and FLVs - have text that seems to be texture map file locations in UTF: 
```
 “§...N.:.\.F.R.P.G.\.d.a.t.a.\.I.N.T.E.R.R.O.O.T.\.m.t.d.\.s.f.x.\.S.[.D.]._.A.d.d...m.t.d...N.:.\.F.R.P.G.\.d.a.t.a.\.S.f.x.\.T.e.x.\.s.0.4.0.1.0...t.g.a...g._.D.i.f.f.u.s.e.....g._.D.e.t.a.i.l.B.u.m.p.m.a.p...M.a.t.e.r.i.a.l. .#.1.1...N.:.\.F.R.P.G.\.d.a.t.a.\.I.N.T.E.R.R.O.O.T.\.m.t.d.\.s.f.x.\.S.[.D.]._.A.d.d...m.t.d...N.:.\.F.R.P.G.\.d.a.t.a.\.S.f.x.\.T.e.x.\.s.0.4.0.1.1...t.g.a...g._.D.i.f.f.u.s.e.....g._.D.e.t.a.i.l.B.u.m.p.m.a.p.........H.D._.A._.9.5.0.0...B.D._.A._.9.5.0.0._.B.0.1.. 
```
 

TPFs - have some sort of file name data, most likely graphics files archived within. (TPFs that were not inside the main dvd archive don't seem to have any text.) Example of main directory TPF:

```
EnvDif_m16_000.EnvSpc_m16_000.EnvSpc_m16_001.EnvSpc_m16_002.EnvSpc_m16_003.m16_obj_pot3.m16_obj_pot3_n
```


FFXs (header says FXR) - maybe some visual effects scripts to animate the textured flver models. No text data

HKX - archived Havok engine data. Can be skeletons, animation, intelligent animation behavior or brekable models data. Example text:

```
WààW.ÀÀ................................Khk_2010.2.0-r1.ÿ....ÿÿÿÿ__classnames__.....ÿ...Ð...Ð...Ð...Ð...Ð...Ð...Ð__types__..........ÿ... ........................__data__...........ÿ... ...€...À.......P...P...PuX^ö.hkClass.\~¤Â.hkClassMember.Š6.Ï.hkClassEnum.ÎoŠl.hkClassEnumItem.'rÁ..hkRootLevelContainer.Â¤aä.hkpPhysicsData.ÿrL..hkpPhysicsSystem.uøØ..hkpRigidBody.[ ¥÷.hkpConvexTranslateShape.4DÒÕ.hkpBoxShape.ÿÿÿÿÿÿ........€...................Physics Data........hkpPhysicsData......................€...........................................€...........€...........€...........€...........................................Default Physics System..........
```
## Post #21
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-08T16:00:35+00:00
- Post Title: Re: Dark Souls 360 / PS3

Here is a texture viewer for the tpf files in noesis.
[fmt_dark_souls_tpf.rar](https://xentaxbackup.github.io/file/4965_fmt_dark_souls_tpf.rar)
## Post #22
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-01-08T16:06:50+00:00
- Post Title: Re: Dark Souls 360 / PS3

ofcourse i means subtitles  . Well i would like to know if anyone working on text editor ?
## Post #23
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-01-08T16:13:47+00:00
- Post Title: Re: Dark Souls 360 / PS3

> Reply from chrrox
>
> Here is a texture viewer for the tpf files in noesis.

Awesome! you are on a roll! I am reading your tutorials and wiki on 3D file exploration. If its possible to figure it out then I will do it, but if you know that I can run into difficulties with my low experience then please say so 

michalss - well maybe we will!
## Post #24
- Username: Phrexeus
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 04, 2012 10:43 am
- Post datetime: 2012-02-02T09:00:12+00:00
- Post Title: Re: Dark Souls 360 / PS3

The texture viewer works for some .tpf's, here are some examples (shrunk down):



But, many of the .tpf files still don't work using this script with Noesis, they just give the default grey screen.  In fact I've browsed through all of the hundreds of texture files, but only a handful were environment textures, and many of the enemies were missing, so there is a huge load still to find.

And I couldn't get the .bdf or .bhd archives to extract properly.  Using Chrrox's script I got some 0-1kb dud files from the .bhf archives, and from the .bdf all I get is some empty folders.  I have looked at the headers of these files with a hex editor, and they appear to have the same format:

.bnd = BND307D7R6
.bhf = BHF307D7R6
.bdf = BDF307D7R6

But the .bdf's seem to have different archiving, no list of files in the header like the .bnd's.

The .bdf's are 900MB in total so I am eager to get into them.  The .bhf's are only 300k in total so I'm not sure what they contain or if it is of great importance.  If anyone can shed light or make adjustments to the script it would be great.

Still no progress with the .flv or .flver 3D files either.  The blender import script from Szkaradek123 is the closest thing, but it doesn't work with the dark souls files.
## Post #25
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-02T09:50:59+00:00
- Post Title: Re: Dark Souls 360 / PS3

every file i tested that did not work for the textures were just thousands of particle effects. what file did you see that you think is some kind of character texture that is not supported.
## Post #26
- Username: Phrexeus
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 04, 2012 10:43 am
- Post datetime: 2012-02-02T10:33:43+00:00
- Post Title: Re: Dark Souls 360 / PS3

> Reply from chrrox
>
> every file i tested that did not work for the textures were just thousands of particle effects. what file did you see that you think is some kind of character texture that is not supported.
s00002.tpf all the way to s15394.tpf

So you know for sure that these are only particle effects?  They are all small files though, so I doubt any of them are environment/character/monster textures.

The others must all be in the .bdf's which I haven't been able to extract.
## Post #27
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-02T12:54:13+00:00
- Post Title: Re: Dark Souls 360 / PS3

anyone pls do repacker for texts ?? I wold love to transtalte this game
## Post #28
- Username: xcomplex
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon May 16, 2011 11:42 am
- Post datetime: 2012-03-28T14:39:27+00:00
- Post Title: Re: Dark Souls 360 / PS3

anybody got any info about *dcx? 
I can't find any info about about it via google.. 

file: [http://www.4shared.com/file/Hgu5FRBK/ga ... ambnd.html](http://www.4shared.com/file/Hgu5FRBK/gameparampatchparambnd.html)?
## Post #29
- Username: Jyouji
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 10, 2012 7:49 pm
- Post datetime: 2012-08-30T01:40:11+00:00
- Post Title: Re: Dark Souls 360 / PS3

Sorry to necro this thread, but is it possible to repack these archives? I'd like to play with the particle effets on the pc ver (they use the same archives AFAIK)
## Post #30
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-02T14:50:36+00:00
- Post Title: Re: Dark Souls 360 / PS3

Rick's got an unpacker for the PC game.
I think he wrote one for the console version as well.

[viewtopic.php?p=77853#p77853](http://forum.xentax.com/viewtopic.php?p=77853#p77853)
## Post #31
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-09-02T20:44:06+00:00
- Post Title: Re: Dark Souls 360 / PS3

Format is virtually the same, just endian difference and a few differences in the header.
## Post #32
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-09-09T03:06:41+00:00
- Post Title: Re: Dark Souls 360 / PS3

My repo now has 100% completion on file names for PC version.
## Post #33
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-09-09T06:22:58+00:00
- Post Title: Re: Dark Souls 360 / PS3

> Reply from Rick
>
> My repo now has 100% completion on file names for PC version.

Hi Rick Can you please also do repacker with file names for X360?
## Post #34
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-09-15T15:51:58+00:00
- Post Title: Re: Dark Souls 360 / PS3

trying to find a ps3 iso that I can unpack with scripts or tools..but failing hard. Have you guys ever got the ps3 archives to unpack? I am hunting for some interface textures.
## Post #35
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-09-15T21:36:45+00:00
- Post Title: Re: Dark Souls 360 / PS3

so I have a healthy PS3 BDT archive now, but haven't been able to use Chroxx's PS3/Xbox script to unpack. I am guessing there is a bug in there for the ps version as the header is different.
## Post #36
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-09-19T14:31:03+00:00
- Post Title: Re: Dark Souls 360 / PS3

> Reply from chrrox
>
> Here is a texture viewer for the tpf files in noesis.

having some trouble with a ps3 version tpf.. I can provide an example tpf
## Post #37
- Username: whiteraven
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 17, 2012 4:20 am
- Post datetime: 2012-10-18T15:17:04+00:00
- Post Title: Re: Dark Souls 360 / PS3

bm, would you be able to upload a rip of all of the bnd files? The exporter im using gets the mesh data, but it doesnt work for the uvs >_<.
## Post #38
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2014-01-13T15:05:54+00:00
- Post Title: Re: Dark Souls 360 / PS3

> Reply from hatyn
>
> chrrox wrote:Here is a texture viewer for the tpf files in noesis.

having some trouble with a ps3 version tpf.. I can provide an example tpf

I get the same error for almost all textures. I'm using the PC version so I guess that makes sense. However I found that if I open the texture in a hex editor, delete everything before the characters "DDS", then save the file as a .dds, I can open them with no issue in any dds reader. This is definitely the slow way to do it. I'm working on a XVI32 script to do it automatically, but it's slow going.
## Post #39
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2014-01-14T17:19:41+00:00
- Post Title: Re: Dark Souls 360 / PS3

> Reply from Rick
>
> My repo now has 100% completion on file names for PC version.

Is there a compiled unpacker available at your repo as well? I don't completely know how to compile from repos, but would try my luck with unpacking the .bnd archives.
## Post #40
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2014-01-15T01:34:50+00:00
- Post Title: Re: Dark Souls 360 / PS3

> Reply from Rion
>
> Rick wrote:My repo now has 100% completion on file names for PC version.

Is there a compiled unpacker available at your repo as well? I don't completely know how to compile from repos, but would try my luck with unpacking the .bnd archives.

Rick's tools are brilliant, but you might want to check out [nyxo's](http://forum.xentax.com/viewtopic.php?f=16&t=7876&start=165) [DSExplore](https://app.box.com/s/zv2cvd8q26afc59patf5), which has been updated recently.
