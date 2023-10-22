## Post #1
- Username: Pengulord
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Aug 21, 2007 5:21 pm
- Post datetime: 2008-06-13T14:32:13+00:00
- Post Title: [PC] Devil May Cry 4

Heya,

the first official demo to Devil May Cry 4 is finally out. It's 800 MB big and downloadable here:
[http://www.gamershell.com/download_27216.shtml](http://www.gamershell.com/download_27216.shtml)

I thought of posting here because it has an order called ''nativePC'' where all Ressources to the demo(Sounds, icons, enemies, Nero   ,etc.) is in there... my computer tells me those are winzips, but I can't somehow open them ( ''invalid header'').
And the sounds are in ''.srq'' format.

Any idea how to rip them?
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2008-06-13T17:33:13+00:00
- Post Title: [PC] Devil May Cry 4

All data is compressed or encoded into .arc files. But no prgram, that can handle this files. The Lost Planet ARC extractor can open this, but the exported data is unusable.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-06-13T18:00:47+00:00
- Post Title: [PC] Devil May Cry 4

If you could upload examples or use the FileCutter to hack the first and last MB of a large file and upload it on some file sharer, that would be nice.
## Post #4
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-06-13T22:01:37+00:00
- Post Title: [PC] Devil May Cry 4

/dev/ cracked this down at [http://darkmatter.de-coder.net](http://darkmatter.de-coder.net) (mario's website)
It's meant for DR, but it works on all X360 arc files.

it's just a zlib compression container. nothing complicated.
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-06-13T22:25:51+00:00
- Post Title: [PC] Devil May Cry 4

Still, that's nice stuff you got there, Jamesuminator!
## Post #6
- Username: rood_boy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 23, 2006 6:23 pm
- Post datetime: 2008-06-16T12:45:11+00:00
- Post Title: [PC] Devil May Cry 4

can somebody compile zpipe.c    it says that gcc it`s required (I don`t have ubuntu to run that), so any help
## Post #7
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2008-06-16T18:05:40+00:00
- Post Title: [PC] Devil May Cry 4

I found this, but doesn't work for me.
[http://hpcmonex.net/zpipewin32.zip](http://hpcmonex.net/zpipewin32.zip)
## Post #8
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-06-17T15:10:02+00:00
- Post Title: [PC] Devil May Cry 4

yes, same was happening to me.
I couldn't properly compile zpipe.c :(.

It's really odd actually O_o, I've gotten all the official header files.
Maybe someone can rewrite the decompressor :\.
The extractor still works as it's the archive contents that are encrypted and not the archive itself.

:\, It's really odd how it won't compile. I've been trying for a while, but I thought I was just doing a noob mistake ^_^.
## Post #9
- Username: juskrey
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 01, 2008 5:50 pm
- Post datetime: 2008-06-24T16:52:52+00:00
- Post Title: [PC] Devil May Cry 4

DMC4 does not use zlib.
It uses some custom (not MS) LZX compression
## Post #10
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-06-24T18:07:06+00:00
- Post Title: [PC] Devil May Cry 4

Really?  I only assumed it was Zlib because the arc container seemed exact to Dead Risings (both made by Capcom too).  I don't know anything about compressions though, so I'll take your word for it :P
## Post #11
- Username: ScFreak
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 30, 2008 7:57 am
- Post datetime: 2008-06-30T06:03:51+00:00
- Post Title: [PC] Devil May Cry 4

Yes, Dead Rising is zlib, but it appears that DMC4 is not. They both use the same .arc file format, but the compression's not the same. I wrote a simple .arc extractor to extract the compressed files, but it can't decompress the data yet.

This is the layout of the .arc file format as far as I've been able to decipher it:

```
{
    int magic;
    short versionNumber;
    short fileCount;
};

// One for each file, these entries start right after the ARCHeader
struct Entry
{
    char filename[64]; // null terminated
    int unk1; // unknown
    int packedSize;
    int unpackedSize; // Seems to actually be a 3-byte field; ignore the high byte
    int offset;
};

```


The magic number will always be 0x41 0x52 0x43 0x00 ("ARC\0") or 0x00 0x43 0x52 0x41 ("\0CRA") depending on endianness. Files will be little-endian if obtained from a PC game (eg. Devil May Cry 4 PC Trial Version), and big-endian if obtained from the Xbox 360.

I haven't yet figured out what the unk1 field does, but it seems to be pretty regular throughout the files. Perhaps it's some sort of file type identifier?

Anyway, all compressed extracted files from Dead Rising begin with the two bytes 0x78 0x9C, a magic number indicating that it's zlib compressed. Sure enough, if you run these files through zpipe, they decompress correctly.

The same doesn't apply for DMC4, though. Unlike Dead Rising, there isn't a magic number at the top of each file, so finding the type of compression is proving difficult (I'm not very experienced with compression/encryption techniques).

Anyone had any breakthroughs regarding Devil May Cry 4? I seem to have been refused registration over at [Dark-Matter](http://darkmatter.de-coder.net/) (where I registered under "Sc4Freak"), so I posted this info here instead. If someone has a registration there and could put in a good word for me, that'd be much appreciated.
## Post #12
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-07-06T16:29:22+00:00
- Post Title: [PC] Devil May Cry 4

Odd, it should let you register :\
I'll talk to mario about it.

Interesting job there, I hope the compression isn't too hard.  I've never had any experience with compression, so I'm clueless.  I hope someone figures it out :)
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2008-07-08T10:59:50+00:00
- Post Title: [PC] Devil May Cry 4

I doubt the compression algorithm is the same of one of the following and we are so lucky anyway trying doesn't cost anything:

[http://aluigi.org/mytoolz/unlzw.c](http://aluigi.org/mytoolz/unlzw.c)
[http://aluigi.org/mytoolz/unlzwx.c](http://aluigi.org/mytoolz/unlzwx.c)
[http://aluigi.org/mytoolz/unlzss.h](http://aluigi.org/mytoolz/unlzss.h)

outlen = algorithm(out, sizeof(out), in, sizeof(in));

hope it helps although I doubt
## Post #14
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-07-08T12:00:50+00:00
- Post Title: [PC] Devil May Cry 4

well the good part is that all SNGW files are OGG!

who needs the rest when you got the audio?!!!
## Post #15
- Username: juskrey
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 01, 2008 5:50 pm
- Post datetime: 2008-07-08T13:51:41+00:00
- Post Title: [PC] Devil May Cry 4

> Reply from Bugtest
>
> I doubt the compression algorithm is the same of one of the following and we are so lucky anyway trying doesn't cost anything:

http://aluigi.org/mytoolz/unlzw.c
http://aluigi.org/mytoolz/unlzwx.c
http://aluigi.org/mytoolz/unlzss.h

outlen = algorithm(out, sizeof(out), in, sizeof(in));

hope it helps although I doubt

I have tried all of that, thay not even look much the same. Disasm of DMC4 algo is much more complicated
## Post #16
- Username: Pengulord
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Aug 21, 2007 5:21 pm
- Post datetime: 2008-07-12T15:58:20+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Strobe
>
> well the good part is that all SNGW files are OGG!

who needs the rest when you got the audio?!!!

And how do I get them out?
## Post #17
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2008-07-12T17:10:13+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Pengulord
>
> Strobe wrote:well the good part is that all SNGW files are OGG!

who needs the rest when you got the audio?!!! 

And how do I get them out?
Rename to OGG and play in you music player.
## Post #18
- Username: ichigoogle
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 01, 2008 12:09 pm
- Post datetime: 2008-07-31T18:16:14+00:00
- Post Title: Re: [PC] Devil May Cry 4

some progress here:

[http://z9.invisionfree.com/Hells_Atelie ... t=20&#last](http://z9.invisionfree.com/Hells_Atelier/index.php?showtopic=121&st=20&#last)
## Post #19
- Username: juskrey
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 01, 2008 5:50 pm
- Post datetime: 2008-07-31T18:22:47+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from ichigoogle
>
> some progress here:

http://z9.invisionfree.com/Hells_Atelie ... t=20&#last

Actually, they are trying to use zlib there, but there is no zlib in DMC4.

I have managed to unpack .arc archives, but that is still too dirty hack, to be released..
## Post #20
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-07-31T19:37:37+00:00
- Post Title: Re: [PC] Devil May Cry 4

lol, that progress is me too ^_^.

I assumed the archives were just DRs.  Theoretically they are, just compressed differently.
## Post #21
- Username: poly
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Aug 28, 2008 8:17 pm
- Post datetime: 2008-08-28T20:40:14+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from juskrey
>
> 
I have managed to unpack .arc archives, but that is still too dirty hack, to be released..

By unpacking the .arc archives you mean you were able to extract the different files or did you actually figure out the compression method used?  If so care to shared which compression method they used?

Thanks.
## Post #22
- Username: ichigoogle
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 01, 2008 12:09 pm
- Post datetime: 2008-09-03T18:55:15+00:00
- Post Title: Re: [PC] Devil May Cry 4

Do these work?

[http://int0thegame.blogspot.com/2007/06 ... n-arc.html](http://int0thegame.blogspot.com/2007/06/lost-planet-extreme-condition-arc.html)

[http://forums.maxconsole.net/showthread.php?t=6193](http://forums.maxconsole.net/showthread.php?t=6193)
## Post #23
- Username: logokas
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 04, 2008 6:14 am
- Post datetime: 2008-09-03T22:23:33+00:00
- Post Title: Re: [PC] Devil May Cry 4

I'm looking for the sound effects of the game, but apparently i'm blind, or they don't exist in the form of sngw/ogg files.

Anybody here know where they are? If they're stuck in an ARC file then i guess i'll just have to wait it out. :/
## Post #24
- Username: poly
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Aug 28, 2008 8:17 pm
- Post datetime: 2008-09-07T11:41:22+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from ichigoogle
>
> Do these work?

http://int0thegame.blogspot.com/2007/06 ... n-arc.html

http://forums.maxconsole.net/showthread.php?t=6193

No to both.  First one will extract the files but they will be empty because the compression method changed between Lost Planet and DMC4 as already mentioned, while the structure of the arc file did not.

In short all you can get is the tree structure of the files (and files names) extracted, but no actual data in uncompressed form.

As far as the sound effects, they are stored in compressed format within the arc files, so unless the compression method is found the only alternative is to manually record them, assuming you can find a quiet place in the game where to isolate the sounds you need.
## Post #25
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-01-05T14:11:39+00:00
- Post Title: Re: [PC] Devil May Cry 4

Some progress.

The .msg files contain unicode text, with MSG2 header. The texts encoded, maybe XOR or something like that, because I see the unicode format.
The .tex files with TEX header is simple .DDS files without header.

I installed the Russian DMC4 version(The eng to rus patch is 36MB->Google), and the modified files inside the .arc files, are not compressed. For example, the nowloading.arc. (I attached the uncompressed file.)
The uncompressed .tex (or .msg) file inside the arc, is not so simple edit or view. Just every 5th byte is the really data. (sample in attachment)
I hope now someone can write an extractor/repacker to arc.
[dmc4.zip](https://xentaxbackup.github.io/file/1800_dmc4.zip)
## Post #26
- Username: shekofte
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-01-24T01:02:42+00:00
- Post Title: Re: [PC] Devil May Cry 4

I have extracted the archives from this game 
Here is the tool to do it.
[http://www.sufi.cc/aionemu/RPGViewer_3. ... d1024_.zip](http://www.sufi.cc/aionemu/RPGViewer_3.0__Build1024_.zip)
## Post #27
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-01-24T17:59:21+00:00
- Post Title: Re: [PC] Devil May Cry 4

That's cool, thx.
But still no import.
## Post #28
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-01-24T18:29:59+00:00
- Post Title: Re: [PC] Devil May Cry 4

why not try extracting the archive then removing the archive and replacing it with that folder most of the time this will work.
## Post #29
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-01-24T18:49:37+00:00
- Post Title: Re: [PC] Devil May Cry 4

Not working.
## Post #30
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-01-24T20:53:34+00:00
- Post Title: Re: [PC] Devil May Cry 4

did you figure out how to import the models into xsi?
what did you want to mod?
## Post #31
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-01-24T21:07:09+00:00
- Post Title: Re: [PC] Devil May Cry 4

Most of all textures and text files. I want to make a hungarian translation. I can import with my own hands the uncompressed files, but this is too time-consuming and complicated.
## Post #32
- Username: Pengulord
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Aug 21, 2007 5:21 pm
- Post datetime: 2009-01-25T15:00:27+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from evin
>
> Not working.

Me too, I can't even open the RPG viewer.
Something wrong with ma Vista?
## Post #33
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-01-25T15:29:40+00:00
- Post Title: Re: [PC] Devil May Cry 4

Read the read me file that comes with rpg viewer.
you need to install the 2008 visual studio files download able for free from Microsoft.
## Post #34
- Username: ichigoogle
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 01, 2008 12:09 pm
- Post datetime: 2009-03-09T22:10:49+00:00
- Post Title: Re: [PC] Devil May Cry 4

works

Did anyone figure out how to import the .mod files to 3DSmax?
## Post #35
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-03-17T09:37:34+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi there!
I got my hands lately on a DMC4 ARC extractor called RPGViewer and I have to tell that the 
file formats are almost identical to those used by the Lostplanet, it was very easy to figure out the file formats (some of them hehehe) given that I already made numerous programs to export Lostplanet models.
Here are some pics from both (Dmc & LP), more is still to come, Enjoy!!
[Lp.JPG](https://xentaxbackup.github.io/file/1921_Lp.JPG)
## Post #36
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2009-03-17T13:01:09+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> Hi there!
I got my hands lately on a DMC4 ARC extractor called RPGViewer and I have to tell that the 
file formats are almost identical to those used by the Lostplanet, it was very easy to figure out the file formats (some of them hehehe) given that I already made numerous programs to export Lostplanet models.
Here are some pics from both (Dmc & LP), more is still to come, Enjoy!!
Wow, are your Lost Planet tools availlable for download anywhere?
## Post #37
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-03-17T18:03:18+00:00
- Post Title: Re: [PC] Devil May Cry 4

I haven't used forum posts for ages, that's why the second pic didn't appear, I don't know why, ... anyways..


Yes, not only Lostplanet tools will be soon available but also DMC4's since the file formats are almost the same, even the source code will be available for those interrested and of course the work is in progress.
[Dmc4Small.JPG](https://xentaxbackup.github.io/file/1923_Dmc4Small.JPG)
## Post #38
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-03-18T10:49:46+00:00
- Post Title: Re: [PC] Devil May Cry 4

I have a question: why can't I attach more than one file? when I select the file, nothing happens.

Since I can only post one file at a time I'll post this:
LostplanetArc: an extractor for LostPlanet (PC version of course), it will batch extract all the .arc files of the game with a single click (I'm saving you the trouble of typing the filenames .

all you need to do is place the program in the nativePC directory of the game then it will automatically scan the subfolders for .arc files and extract them, this will take about 30 minutes to complete (extract the whole game archives).

Unlike other .arc extractors available out there, this program gives the extracted files an extension making them easier to distinguish (textures, models, ...) those extensions are based on the file headers and ARC header info.

Coming soon:
- Lostplanet Texture converter
- DMC4 texture converter
.. and more
[LostplanetArc.rar](https://xentaxbackup.github.io/file/1926_LostplanetArc.rar)
## Post #39
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2009-03-18T21:35:19+00:00
- Post Title: Re: [PC] Devil May Cry 4

awesome, simply awesome
## Post #40
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-03-21T10:59:14+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi, here's some other programs for DMC4 & Lostplanet

DMC4Extract
this program will give the files extracted from DMC4 (PC) using the RPGViewer3 tool an extension based on the file header (ex: nameXYZ --> nameXYZ.tex or nameXYZ.mod). just put it in the upper directory and let do its work.

LostplanetTex
a Tex -> DDS converter for Lostplanet, the original TEX files will be replaced by the DDS files, I use WTV (Woody's Texture Viewer), makes it easy to view/browse DDS files. since there are too many texture files to handle in a single shot, it may be necessary to put the converter not in the root directory (nativePC) but in the child directories (ZZPack1 then ZZPack2 ...)

Dmc4Tex
the same as the LostplanetTex but for DMC4, the only difference is that DXT5 textures are no longer supported (changed format) so these file are left untouched until a later release, but there aren't so many of them (dxt5 files).

remark: both LostPlanetTex and DMC4Tex can't handle cubemap textures.

So to recap:
Lostplanet:
- extract the files using LostPlanetArc.exe
- Convert textures using LostPlanetTex.exe

DMC4: 
- extract the files using RPGViewer
- give the files extensions (very important) with DMC4Extract.exe
- convert the textures using DMC4Tex.exe

More is still to come.
[dmc4extract+dmc4tex+losplanetTex.rar](https://xentaxbackup.github.io/file/1930_dmc4extract+dmc4tex+losplanetTex.rar)
## Post #41
- Username: Hipolito
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 23, 2009 9:47 am
- Post datetime: 2009-03-23T12:28:01+00:00
- Post Title: Re: [PC] Devil May Cry 4

Good morning   

I am wanting to translate the game to Portuguese, but I am not finding the files in text, captions.  


Surveyor   
you have some tool to extract the files to and then I change it for the game.


thanks, Surveyor
## Post #42
- Username: ichigoogle
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 01, 2008 12:09 pm
- Post datetime: 2009-03-24T00:54:37+00:00
- Post Title: Re: [PC] Devil May Cry 4

DMC4 tools work, great job

surveyor, how did you import the .mod files to 3dsmax?

and will there be a way to repack the arc files?
## Post #43
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-03-25T09:20:45+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi,
I wrote a Mod -> Obj converter (because obj file format is simple). For me it's enough because I'm planning to make a Direct3D viewer (not mod the game).

If 3ds max is the most used here then I'll write an import plugin, other wise (maya or something else then I'll just write a Mod to OBJ converter, the problem with this is that 3dsmax doesn't handle normals so there is data lost when using Max...)

Right now I'm fighting against a deadly virus on my computer so there will be some delays on the work.

text files are the ones with MSG2 extensions, I'll take a look at those later. About the repack thing, I don't know because the compression algorithm is unknown to me (I just used RPGViewer for DMC4, and I didn't try such a thing for Lostplanet)

Stay tuned here at Xentax because more is still to come!!!
## Post #44
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2009-03-25T12:44:03+00:00
- Post Title: Re: [PC] Devil May Cry 4

This is fantastic news, although I'm sorry to hear about your virus. Personally, I use 3dsmax 7, but I would appreciate a mod to .obj converter!  Will your tools retain all of the texture mapping info? (.mtl files?)
## Post #45
- Username: Hipolito
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 23, 2009 9:47 am
- Post datetime: 2009-03-25T23:49:49+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> Hi,
I wrote a Mod -> Obj converter (because obj file format is simple). For me it's enough because I'm planning to make a Direct3D viewer (not mod the game).

If 3ds max is the most used here then I'll write an import plugin, other wise (maya or something else then I'll just write a Mod to OBJ converter, the problem with this is that 3dsmax doesn't handle normals so there is data lost when using Max...)

Right now I'm fighting against a deadly virus on my computer so there will be some delays on the work.

text files are the ones with MSG2 extensions, I'll take a look at those later. About the repack thing, I don't know because the compression algorithm is unknown to me (I just used RPGViewer for DMC4, and I didn't try such a thing for Lostplanet)

Stay tuned here at Xentax because more is still to come!!!

ok!

I will be waiting then this tool to extract the files from text and then be able to play.


Wanting to start much this translation.

The Brazil would be eternally happy and grateful.
## Post #46
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-03-26T11:36:15+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> 
text files are the ones with MSG2 extensions, I'll take a look at those later. About the repack thing, I don't know because the compression algorithm is unknown to me (I just used RPGViewer for DMC4, and I didn't try such a thing for Lostplanet)
The (dmc4) arc files compressed with LZX. (Like the M$ CAB files.)
## Post #47
- Username: Hipolito
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 23, 2009 9:47 am
- Post datetime: 2009-03-27T03:22:43+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from evin
>
> Surveyor wrote:
text files are the ones with MSG2 extensions, I'll take a look at those later. About the repack thing, I don't know because the compression algorithm is unknown to me (I just used RPGViewer for DMC4, and I didn't try such a thing for Lostplanet)

The (dmc4) arc files compressed with LZX. (Like the M$ CAB files.)

Evin   

You can extract? these files from texts?   
or there is no tool?

not the textures, but the texts!!


[]s
## Post #48
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-03-27T07:42:26+00:00
- Post Title: Re: [PC] Devil May Cry 4

Like I sad: The (dmc4) arc files compressed with LZX. Not the MSG2 with msg extension! This text files are not comperessed, just encrypted, like Shadow of Memories game's text files.
And no, there is no tool, as i know. And I can't "extract" the texts, yet.
## Post #49
- Username: Hipolito
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 23, 2009 9:47 am
- Post datetime: 2009-03-27T11:34:24+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from evin
>
> Like I sad: The (dmc4) arc files compressed with LZX. Not the MSG2 with msg extension! This text files are not comperessed, just encrypted, like Shadow of Memories game's text files.
And no, there is no tool, as i know. And I can't "extract" the texts, yet.

thanks!

I will be expecting something new!
## Post #50
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-03-28T09:20:46+00:00
- Post Title: Re: [PC] Devil May Cry 4

If you need something new, there is it. This is the dmc4's abc (not complete yet). The character and the hex code in msg2.
I want to write an editor to this, but just after summer. (If until no one can.)

```
1-
2-
3-
4-
5-
6-
7-
8-
9-
!-17 14
?-3c 16
(-
)-
 -28 1c
&-
-----------
:
;
,-16 24
.-17 26
"-
'-17 2a
~-
--20 2e
+-
/-
@-
$-
A-61 38
B-
C-52 3c
D-5b 3e
----------
E-51 40
F-4d 42
G-
H-4f 46
I-
J-47 4a
K-54 4c
L-4b 4e
M-6f 50
N-
O-
P-
Q-
R-51 5a
S-4d 5c
T-51 5e
----------
U-
V-
W-7d 64
X-
Y-50 68
Z-49 6a
a-3d 6c
b-47 6e
c-40 70
d-45 72
e-41 74
f-2b 76
g-43 78
h-45 7a
i-1d 7c
j-18 7e
----------
k-46 80
l-1c 82
m-6d 84
n-44 86
o-45 88
p-46 8a
q-44 8c
r-2c 8e
s-3b 90
t-28 92
u-46 94
v-41 96
w-5f 98
x-
y-43 9c
z-37 9e
----------
[-
]-
_-
_-
_-
_-
_-
Á-
_-
_-
_-
_-
É-
_-
_-
_-
----------
Í-
_-
_-
_-
_-
Ó-
Ő-
Ö-
Ú-
Ű-
Ü-
_-
_-
á-
_-
_-
----------
_-
_-
é-
_-
_-
_-
í-
_-
_-
_-
_-
ó-
ő-
ö-
_-
ú-
----------
ű-
ü-46 0102

fffe-0410
enter-0403

pagebreak between subtitles(every time need, except 0410)
0411
0406
0406
0401
0410
```
## Post #51
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-03-28T12:03:06+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi,
here's a first release of the model converter for you to try.
all you need to do is type in the model filename you want (ex: model/model01.mod) and the program will create the corresponding .OBJ file.

at the moment only position data is exported, tex coords and normals will come in a later release.

stage model seems OK, but human models, enemies, bosses need some rescaling so I'll leave this to you!

don't hesitate to report any bugs or suggestions.

enjoy!
[Dmc4Model.rar](https://xentaxbackup.github.io/file/1944_Dmc4Model.rar)
## Post #52
- Username: Hipolito
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 23, 2009 9:47 am
- Post datetime: 2009-03-28T13:57:31+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> Hi,
here's a first release of the model converter for you to try.
all you need to do is type in the model filename you want (ex: model/model01.mod) and the program will create the corresponding .OBJ file.

at the moment only position data is exported, tex coords and normals will come in a later release.

stage model seems OK, but human models, enemies, bosses need some rescaling so I'll leave this to you!

don't hesitate to report any bugs or suggestions.

enjoy!

very good tool.


I am still waiting for the tool to extract the subtitles in the game to change.


hugs.
## Post #53
- Username: Hipolito
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 23, 2009 9:47 am
- Post datetime: 2009-03-30T23:10:10+00:00
- Post Title: Re: [PC] Devil May Cry 4

Does anyone know which file is the *. ARC texts (captions) of the game??.

I will try to make a tool to extract the text.
## Post #54
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-03-31T06:23:10+00:00
- Post Title: Re: [PC] Devil May Cry 4

All MSG file. Like this: DEVILMAYCRY4\nativePC\movie\adv_for\*.msg
The DMC4 not use this files, but the adv_e.msg file contain the beginning video's subtitle (DEVILMAYCRY4\nativePC\movie\rom_for\adv_for.wmv)
## Post #55
- Username: Hipolito
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 23, 2009 9:47 am
- Post datetime: 2009-04-06T18:42:00+00:00
- Post Title: Re: [PC] Devil May Cry 4

is there any tool to open these files MSG?


any news on the import of files of textures for the game?
## Post #56
- Username: ichigoogle
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 01, 2008 12:09 pm
- Post datetime: 2009-04-16T19:48:48+00:00
- Post Title: Re: [PC] Devil May Cry 4

nvm, got it.
## Post #57
- Username: Hipolito
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 23, 2009 9:47 am
- Post datetime: 2009-05-15T05:24:20+00:00
- Post Title: Re: [PC] Devil May Cry 4

up!
sorry!

news?
## Post #58
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-05-15T07:18:43+00:00
- Post Title: Re: [PC] Devil May Cry 4

Test stuff(pre-pre-pre-alpha):
[Video](http://evinhun.extra.hu/00/dmc4_teszt.avi)
[File](http://evinhun.extra.hu/00/dmc4_teszt.7z)

MSG or Arc repacker editor NOT exist! I made this with hex editor.
## Post #59
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-06T14:15:12+00:00
- Post Title: Re: [PC] Devil May Cry 4

sorry for bumping   but where are the characters located :S nativePC\rom\...\...
## Post #60
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-07-06T19:46:28+00:00
- Post Title: Re: [PC] Devil May Cry 4

You mean this?
DEVILMAYCRY4\nativePC\rom_pc\system\lang_eng.arc (default font)
## Post #61
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-06T20:17:23+00:00
- Post Title: Re: [PC] Devil May Cry 4

lulz i mean the characters from game / nero / dante / lady / trish etc
## Post #62
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-07-07T11:10:20+00:00
- Post Title: Re: [PC] Devil May Cry 4

They're located in Libra, specifically the pl named files.

~CapCom\Devil May Cry 4\nativePC\rom\id\libra

However, the model converter doesn't work well. It's lacks Texture UV's/Coordinates and has some flipped normals. Not having UV's means textures won't work on models...
## Post #63
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-07T11:27:14+00:00
- Post Title: Re: [PC] Devil May Cry 4

i just need the models  i can handle the other things in maya  

btw in the location that u said are only textures
## Post #64
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-07-07T15:40:07+00:00
- Post Title: Re: [PC] Devil May Cry 4

Well, good luck with the Textures and UV then, you'll need it.

As for the location, go in there where I previously listed, select one of the files (don't know which one is which, but PL models are the Hero characters) and in RPGViewer go to 'Addon' and go in Archive -> Extract.

You should see a list of files, extract them. In the Directory folder of the models a new folder should be generated with the names of the Archive...explore abit and use the DMC4Model converter on the first model file and it should generate a OBJ model...

Well, that's about what I found so far...
## Post #65
- Username: Krysia
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jul 05, 2009 5:11 am
- Post datetime: 2009-07-11T07:23:34+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> Hi,
here's a first release of the model converter for you to try.
all you need to do is type in the model filename you want (ex: model/model01.mod) and the program will create the corresponding .OBJ file.

at the moment only position data is exported, tex coords and normals will come in a later release.

stage model seems OK, but human models, enemies, bosses need some rescaling so I'll leave this to you!

don't hesitate to report any bugs or suggestions.

enjoy!

Hi are there any news about the new release (with texture coordinates) of this great tool?
I can't wait to try it out.
## Post #66
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-07-15T09:47:35+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi guys!!
I must admit that I got too lazy these days and although most of the models file format is clear, I didn't write a single line of code  .

I promise though, I will do something and release at least a complete model exporter   .
## Post #67
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-07-15T12:57:08+00:00
- Post Title: Re: [PC] Devil May Cry 4

No problems mate, take your time.

It's atleast good news to hear that you're around and still kicking
## Post #68
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-07-16T07:07:35+00:00
- Post Title: Re: [PC] Devil May Cry 4

I'm almost done with the MSG2 editor program. Only the default character-set supported (english, german, french etc.) by reading. The writer part support the most ASCII characters, yet.
Maybe not this is the best program, but at least works fine with the most msg2 file.
.NET 2.0 required.

(The ARC file injector is under development. I can't handle the "arc-compress", that's why will the program only append the new uncompressed data to the end of file.)
[MSG2Editor.zip](https://xentaxbackup.github.io/file/2198_MSG2Editor.zip)
## Post #69
- Username: poly
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Aug 28, 2008 8:17 pm
- Post datetime: 2009-07-17T20:06:06+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> Hi guys!!
I must admit that I got too lazy these days and although most of the models file format is clear, I didn't write a single line of code  .

I promise though, I will do something and release at least a complete model exporter   .

Hey Surveyor, awesome job!
Have you already figured out how to export the skeleton for the characters and the skinning?
I'm interested in doing this. In case you need help in figuring that part out, I'd like to try to help.

Please let me know, thanks!
## Post #70
- Username: shekofte
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-17T20:50:08+00:00
- Post Title: Re: [PC] Devil May Cry 4

The model converter works with Resident evil 5 meshes also.
## Post #71
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-07-20T09:31:24+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi,
Here's some new stuff on the DMC4. As you can see, 

now texture coordinates work pretty well on character 

models nut not for the stages, and there is some 

small issues regarding the scalings. The head is a 

little too big so I made a little rescaling to make 

it fit with the body.

Enjoy!
[Nero2.JPG](https://xentaxbackup.github.io/file/2213_Nero2.JPG)
## Post #72
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-07-20T09:39:39+00:00
- Post Title: Re: [PC] Devil May Cry 4

Agggggh, this forum is making me crazy!!! why only 1 file per post ???? anyways, here's the updated model exporter!
Have fun!
[Dmc4Model.zip](https://xentaxbackup.github.io/file/2215_Dmc4Model.zip)
## Post #73
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-07-20T09:47:40+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hey chrrox !!
You say the converter works for RE5??, I'd like to see that, but which version: PC, x360, ??

Poly, about the skinning and skeletons, yes I figured some of the data but when I tried to export to Max, it was a headache!! If you could show me a way to import this into max I'd be grateful!

Later!

Ohh! I just figured out that I didn't include any help file for the model exporter so here's the help: To use the exporter, it's better to place the .exe in the same directory as the model to be converted then type the name of this model et voila !!!
## Post #74
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-07-20T11:16:12+00:00
- Post Title: Re: [PC] Devil May Cry 4

You're amazing! Thank you!
## Post #75
- Username: Krysia
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jul 05, 2009 5:11 am
- Post datetime: 2009-07-20T11:19:08+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> Hi,
Here's some new stuff on the DMC4. As you can see, 

now texture coordinates work pretty well on character 

models nut not for the stages, and there is some 

small issues regarding the scalings. The head is a 

little too big so I made a little rescaling to make 

it fit with the body.

Enjoy!

Hi Surveroy, thanks for a really great job with this tool.
But I found out that some models (for example high-res head) do not have proper texture coordinates or they don't have it at all. Do you have any idea why?
## Post #76
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-20T11:52:10+00:00
- Post Title: Re: [PC] Devil May Cry 4

same as Krysia ^
## Post #77
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-07-21T09:13:55+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi there!
Texture coords may be funky sometimes because of different vertex formats on the same vertex buffer: this is crazy!

But these texture coords are being fixed and as you can see in this pic, the head is a HiRes model and it works pretty well.

Another thing to notice is that normals are still uncorrect, I don't know, 3ds max doesn't support them on OBJ files anyway. Maybe if you try the models on Maya to see...

This work is still in progress and I'll be posting the updated model converters as soon as I can, so stay tuned here on Xentax!!
[Lady.JPG](https://xentaxbackup.github.io/file/2216_Lady.JPG)
## Post #78
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-07-21T13:30:40+00:00
- Post Title: Re: [PC] Devil May Cry 4

All I did in Max for the normals was keep the Edit Mesh status and unified the Normals through the modifier panel.

It's not hassle at all, infact, it's pretty good considering the quick strides you're making for a converter.

And thank you, can really learn alot here.
## Post #79
- Username: poly
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Aug 28, 2008 8:17 pm
- Post datetime: 2009-07-21T20:48:02+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> Hey chrrox !!
You say the converter works for RE5??, I'd like to see that, but which version: PC, x360, ??

Poly, about the skinning and skeletons, yes I figured some of the data but when I tried to export to Max, it was a headache!! If you could show me a way to import this into max I'd be grateful!

Later!

Ohh! I just figured out that I didn't include any help file for the model exporter so here's the help: To use the exporter, it's better to place the .exe in the same directory as the model to be converted then type the name of this model et voila !!!

Nice to know you figured out the skeleton format!
I'm not an expert on max myself, but I have a friend that once wrote a plug-in for it, he might be able to help.

Can you share some code that reads out all the relevant data for the vertices and skeleton?
## Post #80
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-07-22T03:11:40+00:00
- Post Title: Re: [PC] Devil May Cry 4

The contents of this post was deleted because of possible forum rules violation.
## Post #81
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-01T14:17:10+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi there,
Here's a Direct3D stage viewer I'm coding right now and as you can see different texture layers now can be applied, still I need to take a lesson or two on shaders to make the final render with bump mapping and per pixel lighting and some more cool stuff. But before that I need to figure out where the lights are, and suddenly I noticed something! since RPGViewer3 can't handle extensions, there are some files with the same name and different extensions that get overwritten, example:

model.mod
model.sdl
model.col

in the end you get only the last model.col without extension!
[01_nobind.JPG](https://xentaxbackup.github.io/file/2240_01_nobind.JPG)
## Post #82
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-01T14:25:41+00:00
- Post Title: Re: [PC] Devil May Cry 4

sdl contains a lot of information.
in resident evil 5 it contains enemy spawns, cutscene information, and lighting information.
## Post #83
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-01T14:28:08+00:00
- Post Title: Re: [PC] Devil May Cry 4

Now textured ... Hey chrrox you are faster than me !!!!
[02_textured.JPG](https://xentaxbackup.github.io/file/2241_02_textured.JPG)
## Post #84
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-01T14:32:48+00:00
- Post Title: Re: [PC] Devil May Cry 4

... and normal textures ...
[03_normal.JPG](https://xentaxbackup.github.io/file/2242_03_normal.JPG)
## Post #85
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-01T14:34:30+00:00
- Post Title: Re: [PC] Devil May Cry 4

... specular mapping ...
[04_specular.JPG](https://xentaxbackup.github.io/file/2243_04_specular.JPG)
## Post #86
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-01T14:36:27+00:00
- Post Title: Re: [PC] Devil May Cry 4

And lightmapping ....thank you  
[05_lightmap.JPG](https://xentaxbackup.github.io/file/2244_05_lightmap.JPG)
## Post #87
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-08-01T16:40:27+00:00
- Post Title: Re: [PC] Devil May Cry 4

Holy bloody anchovies, that is amazing! You're like a 3D-Decompiler version of Flash!
## Post #88
- Username: Krysia
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jul 05, 2009 5:11 am
- Post datetime: 2009-08-01T17:48:52+00:00
- Post Title: Re: [PC] Devil May Cry 4

Amazing! Will this viewer allow to make any changes or it is just for preview purposes?
Any news about the uvs issue and DM4model.exe? I've noticed that in one file, for example,
the face has no texture coordinates and the eyes and mouth have proper coordinates. Bizzare.
## Post #89
- Username: magnum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jul 27, 2009 3:43 am
- Post datetime: 2009-08-01T20:58:17+00:00
- Post Title: Re: [PC] Devil May Cry 4

Surveyor,

I tested your Dmc4Model program, and noticed that you are improperly interpreting the face data.

Here is some sample code demonstrating how the faces should be read:

```
int face_data_length; // length of the array
...

bool backface = false;
for( int i = 0; i < face_data_length - 3; i++ ) {
	unsigned short a = faces[i];
	unsigned short b = faces[i+1];
	unsigned short c = faces[i+2];

	backface = !backface;

	if( a != b && b != c && a != c ) {
		if( backface ) {
			printf( "f %d/%d %d/%d %d/%d\n", c,c,b,b,a,a );
		} else {
			printf( "f %d/%d %d/%d %d/%d\n", a,a,b,b,c,c );
		}
	}
}

```


You should be skipping any time that the vertex indices are the same, and every other set of 3 is a backface.
## Post #90
- Username: poly
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Aug 28, 2008 8:17 pm
- Post datetime: 2009-08-02T20:00:47+00:00
- Post Title: Re: [PC] Devil May Cry 4

Awesome progress!

Any news on the model's skeleton front?
My offer to help is still up, I'm especially interested in that part!
## Post #91
- Username: magnum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jul 27, 2009 3:43 am
- Post datetime: 2009-08-06T02:05:28+00:00
- Post Title: Re: [PC] Devil May Cry 4

I'd be willing to help too if you're willing to share the source. I managed to decipher the SF4 format, including the skeleton, and I noticed the face indices are stored in the same fashion for this game, so there might be other similarities that I can help with.
## Post #92
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-08-06T10:20:25+00:00
- Post Title: Re: [PC] Devil May Cry 4

MASTER Surveyor , magnum
working on skeleton is awesome !  
I follow your progress avidly   
Surveyor it is an exclusive converter !
## Post #93
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-08-06T10:23:50+00:00
- Post Title: Re: [PC] Devil May Cry 4

post repeated with my mistake ! sorry
## Post #94
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-08-06T13:24:53+00:00
- Post Title: Re: [PC] Devil May Cry 4

I plan on looking into these formats as well when i get the chance.  Still finishing up some things on FFX, RE4, and MGS2 at the moment though (and have a few others i still want to get to as well).  I may take a break from those and see what i can find.  Should also be able to help verify some things once i get to stepping through the actual executable code (assuming the assembly isn't too convoluted).  Will have to see how things go once i get to it.

Let me know if there is anything i can help with in the meantime.
## Post #95
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-08T11:15:56+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Krysia
>
> Will this viewer allow to make any changes or it is just for preview purposes?
preview only! changes may be made under your favorite 3D modeler once we can inject those files back to the .arc files.

> Reply from Krysia
>
> I've noticed that in one file, for example,
the face has no texture coordinates and the eyes and mouth have proper coordinates.
and here I thought I completely fixed this problem, can you tell which files present this issue so I can take a look?

Magnum: your trick on fixing the backface issue is most welcome and I'm happy to plug it into my program. Now with this trick you must unckeck the Normals and Unify boxes. You'll find the updated model converter attached below!

Magnum, poly! you see I definitely need your help on those skeleton data and I'll soon post the source code, It's nice to see some people willing to help for the sake of the community!!
[Dmc4Model.zip](https://xentaxbackup.github.io/file/2264_Dmc4Model.zip)
## Post #96
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-08T11:19:20+00:00
- Post Title: Re: [PC] Devil May Cry 4

And here are today's main news: I now completed a PLA file decompiler for you to try, PLA files stand for "play" which means they hold all the gameplay data like how many orbs are in those breakable objects, how the enemies behave, ... the decompiler will show a humanly readable interpretation of these binary files.... just give it a try and feel free to comment out... for now the program only plots the data into the screen, later I'll make plot them into a separate text file!!

SDL, XFS and CFG files will be next !!!

Have fun!!
[Dmc4Pla.zip](https://xentaxbackup.github.io/file/2265_Dmc4Pla.zip)
## Post #97
- Username: shekofte
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-08T11:55:28+00:00
- Post Title: Re: [PC] Devil May Cry 4

I have gotten the files injected back into the game 
If you want to have the game load any .mod file open the arc file containing the .mod
take note of the path.
now change anything about the path so if it said \stage\  change it to \stag1\
now the game will no longer look in the arc file
but instead it will look for the uncompressed file in the location you changed
\nativepc\stage\xxx.mod
here is a video of it in action I can explain the process in detail if needed.
[http://www.youtube.com/watch?v=b16UVOEQazk](http://www.youtube.com/watch?v=b16UVOEQazk)

and here is a video guide for the arc edit just replace the trexture mod with replacing the actual .mod files.
[http://www.youtube.com/watch?v=5_Mu_TwonaA](http://www.youtube.com/watch?v=5_Mu_TwonaA)

Edit*
How are you getting the file extension names out of the numbers they have listed the only way I could do it is bye making the game throw an error saying it coul dnot find the file or looking at the first 3 letters of the header in hex.
## Post #98
- Username: Krysia
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jul 05, 2009 5:11 am
- Post datetime: 2009-08-08T13:42:13+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> Krysia wrote:I've noticed that in one file, for example,
the face has no texture coordinates and the eyes and mouth have proper coordinates.
and here I thought I completely fixed this problem, can you tell which files present this issue so I can take a look?

It looks that your latest modifications to the exe fixed the problem so great thanks to you
## Post #99
- Username: poly
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Aug 28, 2008 8:17 pm
- Post datetime: 2009-08-09T17:00:15+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> Magnum, poly! you see I definitely need your help on those skeleton data and I'll soon post the source code, It's nice to see some people willing to help for the sake of the community!!

We are both ready when you are!
## Post #100
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-10T09:26:59+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from chrrox
>
> I have gotten the files injected back into the game
Chrrox what you did here is amazing!! (i didn't watch the videos btw) since I spent many hours trying to inject the files into the .arc without much success and now you did it!

we are in the right direction aren't we !?

I'll post the file extensions used by the game later!!

> Reply from poly
>
> We are both ready when you are!
here you go, the source code!!

Have fun!
[Dmc4ModelSrc.zip](https://xentaxbackup.github.io/file/2271_Dmc4ModelSrc.zip)
## Post #101
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-10T09:29:11+00:00
- Post Title: Re: [PC] Devil May Cry 4

And here's also the PLA decompiler that will this time plot the data into a separate text file. let me know if there are bugs or something or if you want the source code for this one.
[Dmc4Pla.zip](https://xentaxbackup.github.io/file/2272_Dmc4Pla.zip)
## Post #102
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-11T12:47:42+00:00
- Post Title: Re: [PC] Devil May Cry 4

Here are the different files used by the games (dmc4/LP), those numbers are found in the arc header, I hope this help you out!!

GRAPHICS
	0x3CAD8076:	texture file (TEX)
	0x27CE98F6:	cubemap textures (RTX) used for envmaps and mirrors
	0x1041BD9E:	model (MOD)
	0x234D7104:	model (CDF)
	0x139EE51D:	actor motion (LMT)
	0x264087B8:       facial animation event (FCA)
	0x4F6FFDDC:	facial pattern event (FCP)
	0x55A8FB34:	.anm file for HUD drawings (header: binary)
	0x34A8C353:	.spr_map sprite layout for HUD, header: XFS
	0x4E32817C:	shader file (BFX)

COLLISION
	0x11C82587:	collision om file (OBJA)
	0x1D35Af2B:	collision2 om file (same filename as above) (HIT)
	0x3900DAD0:	map collision file (SBC1) found on stages with 2 names: ataris and tamas, ex: s205 -> ataris205 and tamas205

EFFECT
	0x03FAE282:	effect1 (EFA)
	0x528770DF:	effect2 (EFS)
	0x482B5B95:	effect3 (ESL)
	0x21034C90:	xml effect (ARCS)
	0x44E79B6E:	event1 (SDL)
	0x5EF1FB52:	event3 (LCM)

HAVOK
	0x6C3B4904:	HAVOK link collision file, header: XFS
	0x57BAE388:	HAVOK constraint file, header: XFS
	0x5435D27B:	HAVOK file, contains nothing but padding, no header
	0x1AEB54D1:	HAVOK vertex file, xml based, only 2 of them in the whole packages!
	0x3C3D0C05:	png format HUD files, but something else for stages, HAVOK related, header: 0x75e0e075

SOUND
	0x33AE5307:	sound (SPAC)
	0x29948FBA:	sound (DNRS)
	0x6C1D2073:	sound (SREQ)
	0x3821B94D:	sound (Ogg) used for musics, ambient sounds and character voices
	0x07D5909F:	sound (STRQ)
	0x2E47C723:	sound (XFS)
	0x7A038F4C:	.rev_win sound, header: XFS
	0x094973CF:	.scs sound, header: SCST
	0x340F49F9:	.sds sound, header: SDST
	0x3D007115:	.spc sound, header: WED
	0x5A3CED86:	.srd sound, header: RRD
	0x48459606:	.srq sound seq_bgs file, header: seq0

MISSION
	0x338C1FEC:	mission tool 1, header: XFS
	0x54503672:	mission tool 2, header: XFS
	0x0D3BE7B5:	mission tool 3, header: XFS
	0x652071B0:	mission tool 4, header: XFS
	0x71D6A0D4:	mission tool 5, header: OSF
	0x2B93C4AD:	mission route file, header: XFS
## Post #103
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-11T19:05:28+00:00
- Post Title: Re: [PC] Devil May Cry 4

One Thing I noticed are xfs Files are not really ending with an extension .xfs.
If you use the resident evil 5 benchmark there are .xfs files that when removed complain about different extensions like .jcl and some other weird ones.
you can tell what it is meant to be as most of the xfs files are inside a folder that is the same as the extension name.
so to have the game load new content.

Step1.
Extract the 2 arc files you want to do the model swap or file swap with into a folder.

Step2.
Open the arc file containing the content you want to modify and locate the location in the file table
Ex. \NativePC\Dante\pl0100 (not a real file)

Step 3 Change the name to anything else it does not matter
Ex \Native99\Dante\pl0100

Step4 
Now the game will look for pl0100.mod in the original location of
\NativePC\Dante\pl0100.mod

Step5
Place your modified or another .mod file in that location and rename it to pl0100.mod

Step6.
Start the game and it will load your new file 

If there are any questions let me know and ill explain it better.
## Post #104
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-12T09:58:38+00:00
- Post Title: Re: [PC] Devil May Cry 4

I'll try your method as soon as I get my hands on a computer that supports pixel shader 3.0, right now the two (very old) computers I have can barely run a hex editor + 3ds max + visual c++ at the same time!!

ok, thanks chrrox!
## Post #105
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-08-12T15:00:46+00:00
- Post Title: Re: [PC] Devil May Cry 4

just wanted to say that I like this thread because of the info but mostly it's really nice to people actually helping eachother. Often it seems like people are doing their own stuff but here it's a pure collab  Just like street fighter seems to be evolve through people helping eachother very much
## Post #106
- Username: poly
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Aug 28, 2008 8:17 pm
- Post datetime: 2009-08-13T18:03:14+00:00
- Post Title: Re: [PC] Devil May Cry 4

Ok so here are some of my progress and fixes.... and problems.

For the models that are skinned, all the positions are stored in shorts, to get back the correct proportions scaling them with the AABB values works well for all the models.
I suspect there are some other more official values stored in there somewhere, but was unable to find them!

I was able to render the skeleton hierarchy in 3D by using the BoneInfo's parent and position values (all the positions are relative to their parent).

The problem now is to correctly index each bone index in the vertices back to the right bone in the hierarchy. There should be somewhere either a table to re-index them, or some offset value.
Anyone got any idea on where to look for those?
## Post #107
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-14T16:56:13+00:00
- Post Title: Re: [PC] Devil May Cry 4

Chrrox, I finally got to try your method and guess what: it works! right now I'm experimenting different file extensions. We already know that .mod and .tex files work fine, I tried the .bfx (shader files) and they also worked, .sdl files will most probably work.
The problem is that capcom games in general don't have a robust error handlig system, something like "could not load COLLISION file c:/game/TheCollision.col !" that will hint to the type of file missing, instead, there this stupid "Don't send" message (we call it like this) that crashes the game immediately without any info.

And hey poly, skeleton data is evil so keep it up!! btw, I didn't notice those AABB, I think they will hint the rescaling thing.

This is a pic to demonstrate how I abused nero to make him even more devilish ... poor nero.
[Poor Nero.jpg](https://xentaxbackup.github.io/file/2278_Poor Nero.jpg)
## Post #108
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-14T17:05:16+00:00
- Post Title: Re: [PC] Devil May Cry 4

You know all this reminds me of a previous post about the RPGViewer3 being unable to handle file extensions. The thing is, the number of files extracted from an archive is less than the number of files that are in the original archive, look at the attached pic and you'll see what I mean: the tool actually extracts all the files but some files will overwrite others so in the end we only get 1 file instead of 4 (see pic)

I wrote a message to the author of the RPGViewer3 hoping he would provide the decompression routines so that I would write the proper .arc extraction tool. The answer was no and without it we can't extract all the filetypes. But at least we still have the textures and models to mess with and that's a good start. 

I'm thinking about a tool that'll make the game run all the textures and models outside the archives in a single shot.
[ViewArchive.JPG](https://xentaxbackup.github.io/file/2279_ViewArchive.JPG)
## Post #109
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-14T19:04:23+00:00
- Post Title: Re: [PC] Devil May Cry 4

If you want to see the error messages run the re5 benchmark it includes the extensions when it has an error 
If you want to extract the files write a tool that modifies the archive file so it reads the number and adds it to the file name in the archive
that way when rpg viewer extracts them it will not overwrite the files.
Great progress I am glad my method worked for you
## Post #110
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-08-14T20:57:00+00:00
- Post Title: Re: [PC] Devil May Cry 4

Great the to see the progress you guys doing here
## Post #111
- Username: ThinRedPaste
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 15, 2009 2:58 am
- Post datetime: 2009-08-15T01:33:20+00:00
- Post Title: Re: [PC] Devil May Cry 4

is there any progress being made toward editing files that contain parameters regarding the actual function of things the game?  I saw mention of .PLAs, but from the ones I looked at, it doesnt seem like there's much of interest there.  What I did see was a couple PLP files such as pl006_param..PLP (yes it has two consecutive dots) and these intrigue me.  But there's nothing in them I can even use as a foothold to understanding them via a hex editor.
## Post #112
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-15T10:12:01+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from ThinRedPaste
>
> is there any progress being made toward editing files that contain parameters regarding the actual function of things the game?

Yes there will be progress as soon as we figure out the correct file extensions.

> Reply from chrrox
>
> If you want to see the error messages run the re5 benchmark it includes the extensions when it has an error

Resident Evil 5 - 3D Stereo Benchmark.EXE ( 595 MB ): this is too much for my connection, I prefer waiting for the final release and by the complete game.

> Reply from chrrox
>
> If you want to extract the files write a tool that modifies the archive file so it reads the number and adds it to the file name in the archive
that way when rpg viewer extracts them it will not overwrite the files.

Chrrox, that might just be the trick I was looking for, you're a genius!!
## Post #113
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-19T11:09:48+00:00
- Post Title: Re: [PC] Devil May Cry 4

Now here are the tools I've been talking about: Dmc4Patch_01 & Dmc4Patch_02:

IMPORTANT NOTE:
if you are using Dx10 version then you need to delete the shader.arc before you start, otherwise (Dx9) just delete the shader10.arc.

Dmc4Patch_01 will patch all the arc files so that when you use RPGViewer3, all the files will be extracted with extensions and without any losses. Since the program changes the filenames, you must run the program on a copy of the game because the original files have to be untouched! Put the program where the DevilMayCry4_DX9.exe is then run it, now use the RPGViewer on those freshly modified files and extract everything.

There is a little bug in RPGViewer, when extracting too many files, the tool overflows and crashes so it's better to run it on a smaller amount of .arc files. I did this by changing the path and extracting then quit then run RPGViewer then change the path the extract then quit ... And remember, extract the files into one same location (ex: "c:/Dmc4Out/")

Now it's Dmc4Patch_02 turn: copy the extracted files into the nativePC directory of your game, the one that you will use to play. Put Dmc4Patch_02.exe where DevilMayCry4_DX9.exe is and run it. The program will alter the filenames of the files that will run outside the archives. So far, only some files can run outside those archives, the rest have incorrect extensions and are under research.

files that can run outside the ARC files:

ARCEXT_MODEL		.mod
ARCEXT_TEXTURE		.tex
ARCEXT_RTEXTURE		.rtx
ARCEXT_SHADER		.bfx
ARCEXT_ANIMATION	.anm
ARCEXT_SCHEDULE		.sdl
ARCEXT_SOUND_OGG	.sngw
ARCEXT_SOUND_STRQ	.stq
ARCEXT_SBCOLLISION	.sbc
ARCEXT_PLAY		.pla
ARCEXT_MOTION		.lmt

This whole explanation is a little louzy so here's a recap:

DirectoryA	7.4GB	holds the original game files
DirectoryB	7.4GB	same as A but Dmc4Patch_01 will be applied here
DirectoryC	7.4GB	a safe copy, you never know when my tools turn crazy
DirectoryD	5.3GB	holds the extracted game files to mess with

1) use patch_01 on B
2) extract files using RPGViwer3 from B to D
3) use patch_02 on A
3) copy contents of D to A, now A should be about 12GB

run the game and enjoy messing with different file formats 
[Patch1&2.zip](https://xentaxbackup.github.io/file/2297_Patch1&2.zip)
## Post #114
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-19T12:02:04+00:00
- Post Title: Re: [PC] Devil May Cry 4

Can you post the source so I can modify the program to work with re5 the same way?
Thanks in advance and great job with this
## Post #115
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-08-23T10:34:33+00:00
- Post Title: Re: [PC] Devil May Cry 4

Okay ... but you will need to make some modifictions to reflect the new RE5 file formats, I doubt the still use the (old) DMC4 format, although I'm sure that models/texturtes are still the same. Capacom uses what they call the MT Framework engine for all their games, I suggest you take a look at these links:

[http://www.cgtantra.com/index.php?optio ... &Itemid=35](http://www.cgtantra.com/index.php?option=com_content&task=view&id=254&Itemid=35)
[http://www.softimage.jp/user_case/lostplanet/index.html](http://www.softimage.jp/user_case/lostplanet/index.html)

The second article is in japanese, I had the english link but I lost it. Anyways...

Hey poly, any news on the skeleton/animation data?
[Dmc4Patch1&2_Src.zip](https://xentaxbackup.github.io/file/2309_Dmc4Patch1&2_Src.zip)
## Post #116
- Username: poly
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Aug 28, 2008 8:17 pm
- Post datetime: 2009-08-24T18:28:31+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> Hey poly, any news on the skeleton/animation data?

Sadly I'm still stuck at trying to figure out how to properly skin the vertices.
Anyone that got to work with the file format that has any idea about ways to attack the problem is welcome to give me suggestions, either way I'll keep going!
## Post #117
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2009-08-31T09:28:44+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi everybody. I have trouble with mod-to-obj converter (Dmc4Model.zip - [download/file.php?id=2215](http://forum.xentax.com/download/file.php?id=2215)  ). Can anybody help me? 
1. File pl009.mod I rename to model01.mod
2. File location C:\test\model01.mod
3. I copy Dmc4Model.exe in my test derictory -> C:\test\
4. Double click on Dmc4Model.exe
5. In opened black window i trying type ->    model01.mod    (press enter)   -> window is closed
then trying type ->                                   \test\model01.mod   (press enter)   -> window is closed
then trying type ->                                    C:\test\model01.mod    (press enter)   -> window is closed
and nothing OBJ creates     
What is wrong I do?
Please help.
## Post #118
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-09-02T17:06:24+00:00
- Post Title: Re: [PC] Devil May Cry 4

So this is my ARCInjector. This can remake the arc files. But this program can't recompress the new data, just inject into the arc file!
Because this is a translator tool, only tex/dds/msg supported fully. Other format not tested.
The program based on Inside the game's source of Lost Planet ARC Extractor ([http://int0thegame.blogspot.com](http://int0thegame.blogspot.com)). Thanks the source.

Translation tutorial and updated MSG2Editor attached.
[dmc4_up.zip](https://xentaxbackup.github.io/file/2340_dmc4_up.zip)
## Post #119
- Username: zombiemkii
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 05, 2009 4:40 am
- Post datetime: 2009-09-05T00:53:48+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi,guys.I'm new , and have got really useful information here.
Thanks you for this great work.

Forgive my pool English...  

Current I manage to write a program for unpack arc Packages.  
I readed this thread, extract compressed entry, then google bring me a lzx decompression libs call cabextract，but cabextract doesn't work. Can anyone tell me the right way for decompression? Please. (libs,  code segment...). Any advice will be welcome.
## Post #120
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-09-08T08:45:56+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi there!!

> Reply from poly
>
> Hi everybody. I have trouble with mod-to-obj converter (Dmc4Model.zip - download/file.php?id=2215 ). Can anybody help me? 
1. File pl009.mod I rename to model01.mod
2. File location C:\test\model01.mod
3. I copy Dmc4Model.exe in my test derictory -> C:\test\
4. Double click on Dmc4Model.exe
5. In opened black window i trying type -> model01.mod (press enter) -> window is closed
then trying type -> \test\model01.mod (press enter) -> window is closed
then trying type -> C:\test\model01.mod (press enter) -> window is closed
and nothing OBJ creates   
What is wrong I do?
Please help.
Yeah the program quits whatever the outcome, to prevent this, you need to run the game
from the dos console, just click start->run and type cmd, move to your local directory and
try again. this time the window won't close and you will see what messages are there for you!!

> Reply from evin
>
> Current I manage to write a program for unpack arc Packages. 
I readed this thread, extract compressed entry, then google bring me a lzx decompression libs call cabextract，but cabextract doesn't work. Can anyone tell me the right way for decompression? Please. (libs, code segment...). Any advice will be welcome.
Hi,guys.I'm new , and have got really useful information here.
Thanks you for this great work.

Forgive my pool English...  

Current I manage to write a program for unpack arc Packages. 
I readed this thread, extract compressed entry, then google bring me a lzx decompression libs call cabextract，but cabextract doesn't work. Can anyone tell me the right way for decompression? Please. (libs, code segment...). Any advice will be welcome.
Sorry I can't help! I've been stuck in this for some time. when I emailed the author of RPGViewer, he said the compression was a modified LXZ (not the regular one) and he used 
some assembly code extracted from the game exe to make his tool extract the data.

It seems there is some problem with the forums, it's not poly nor evin who wrote the previous posts!!
## Post #121
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2009-09-15T17:24:32+00:00
- Post Title: Re: [PC] Devil May Cry 4

PC version of RE5 is released now and I've been trying to do some basic modding myself. I tried to replace Chris and Sheva with Jill and Wesker, but hit some rather big obstacles.

I've got more info here: [http://z6.invisionfree.com/Resident_Evi ... topic=9687](http://z6.invisionfree.com/Resident_Evil_4_PC/index.php?showtopic=9687)
## Post #122
- Username: DMCdesigns
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 16, 2009 4:56 am
- Post datetime: 2009-09-15T22:02:02+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> This is a pic to demonstrate how I abused nero to make him even more devilish ... poor nero.

How did you edit the model? I mean when I use your converter and try to import the *.obj file in Autodesk Maya 2009 an error appears... However I used the Autodesk FBX Converter to open the file, but the more important thing is that I can't export into a file that works with the game... And I don't have a *.obj to *.mod converter... So can you tell me exactly how you did that? I also tried to edit the model with HEX - it worked, but I got just a few distorted vertices...
## Post #123
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2009-09-18T20:58:54+00:00
- Post Title: Re: [PC] Devil May Cry 4

Please evin, I need some help here. Your MSG2Editor tool is working fine extracting txt from msg2 file, but I am a little lost on how to compile text back. With "msg2editor mes_event_e.MSG2 -r" params I only got a zero-length file named mes_event_e.MSG22 (files mes_event_e.MSG2.txt and mes_event_e.MSG2 are in the same folder). Thanks in advance.
## Post #124
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-09-18T21:28:46+00:00
- Post Title: Re: [PC] Devil May Cry 4

In this case, I need the original msg2 and the new txt.
## Post #125
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2009-09-18T21:44:27+00:00
- Post Title: Re: [PC] Devil May Cry 4

The files are attached, thanks a lot.

 files.zip
(33.11 KiB) Downloaded 182 times
## Post #126
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-09-19T06:08:17+00:00
- Post Title: Re: [PC] Devil May Cry 4

The facts:
-this is a DMC4 topik
-my program compatible only with DMC4 .msg2 files
-this is a Resident Evil 5 msg2 file!
-I don't have the game, to update my program to RE5 (I need to testing)
## Post #127
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-09-19T13:00:29+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi 

> Reply from Sectus
>
> PC version of RE5 is released now and I've been trying to do some basic modding myself.
Where I live, RE5 PC isn't available in stores yet so I can't tell, IMO simply switching the models won't garantee a correct behaviour: the different models have different bone count and an animation for model A with lets say 50 bones doesn't fit with model B with more or less bones.

> Reply from Sectus
>
> How did you edit the model?
I just used a hex editor and messed with bone offsets, you know those matrices that determine the bind pose for the models. This modification was only to show that we could modify a file and still run the game properly.

> Reply from Sectus
>
> but the more important thing is that I can't export into a file that works with the game..
Export function is unavailable right now. Once I have a full understanding of the model/animation formats I'll try to make a complete import/export
## Post #128
- Username: DMCdesigns
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 16, 2009 4:56 am
- Post datetime: 2009-09-19T15:17:01+00:00
- Post Title: Re: [PC] Devil May Cry 4

Thanks for the reply and good luck with the tools.
## Post #129
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2009-09-19T22:27:30+00:00
- Post Title: Re: [PC] Devil May Cry 4

Sorry evin, my bad. Hope we could have RE5 support soon 
Thanks anyway.
## Post #130
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2009-09-21T06:25:17+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> Hi  
Where I live, RE5 PC isn't available in stores yet so I can't tell, IMO simply switching the models won't garantee a correct behaviour: the different models have different bone count and an animation for model A with lets say 50 bones doesn't fit with model B with more or less bones.
Did you watch my youtube video in that link?

[http://www.youtube.com/watch?v=BKEn4Jiyj8U](http://www.youtube.com/watch?v=BKEn4Jiyj8U) - Animation wise the mod works pretty well. I'm not too knowledge about 3D animation, but I get the impression the game uses a system where animations are usable on just about all character models. The only major animation problems I hit was if I changed Chris into one of the female characters, then some of the dynamic parts of the model didn't work (like ponytail and boob bounce). Another problem is that the generic animations (walk/run/aim etc) is something I haven't been able to replace so far. I dunno where the animation files for those are, or if it's something which could be changed anyway. I'd give anything for an SDK right now!

Where do you live by the way? I thought the game was released worldwide by now.
## Post #131
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2009-09-22T21:54:01+00:00
- Post Title: Re: [PC] Devil May Cry 4

One quick question to chrrox: Can you remember where the model files for Gloria, Trish and Lady are stored in DMC4?
## Post #132
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-09-26T09:25:40+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from zeeh
>
> Sorry evin, my bad. Hope we could have RE5 support soon
THere will be a Re5 thread separate from this one for the sake of clarity, I hope nobody sees any inconvenience in this!!

> Reply from Sectus
>
> Did you watch my youtube video in that link?
No I didn't, my connection can't allow this!

> Reply from Sectus
>
> here do you live by the way?
In some place that ressembles to the bermuda triangle where nothing works as it's supposed to.
## Post #133
- Username: dexter
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 06, 2009 2:29 am
- Post datetime: 2009-10-06T23:21:14+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi guys, I want change the characters in DMC4 like this: -> [http://www.youtube.com/watch?v=b16UVOEQazk](http://www.youtube.com/watch?v=b16UVOEQazk)
So I got this tool to extract all the game's content "Dmc4Patch_01.exe" and when I ran to open the window and began to progress: 
[](http://img254.imagevenue.com/img.php?image=73258_teste_devil_122_436lo.JPG)
But seconds later it closed, I scared because she did not borrow any place to save files. And to my unhappiness when I run the game now it did not work!
There is another method to only modify the file we want and not the whole game? And about this tool is what I did wrong, I ran into the same folder where was the game's executable.
## Post #134
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2009-10-07T08:37:05+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from dexter
>
> Hi guys, I want change the characters in DMC4 like this: -> http://www.youtube.com/watch?v=b16UVOEQazk
So I got this tool to extract all the game's content "Dmc4Patch_01.exe" and when I ran to open the window and began to progress: 

But seconds later it closed, I scared because she did not borrow any place to save files. And to my unhappiness when I run the game now it did not work!
There is another method to only modify the file we want and not the whole game? And about this tool is what I did wrong, I ran into the same folder where was the game's executable.
I haven't used that specific tool myself, but I always create a temporary directory and only copy the arcs I need when I mod RE5, to make sure I don't accidentally mess up other files. Did you check if the .exe files were renamed? To be on the safe side, you could simply reinstall the game (the savegame files are in My Documents so they should be safe).

I was planning on trying a similar mod myself, but I just have no idea where the model files are for Gloria, Trish and Lady.
## Post #135
- Username: swordzero
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 17, 2009 2:07 am
- Post datetime: 2009-10-11T01:44:30+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi, Im trying to extract the models of DMC4 this is what i did:

1 Use RPGViewer and search for the game files
2 Use Addon - Advance Extract
3 Use DMC4Extract to add extensions to files
4 Use DMC4Tex to change textures to .dds
5 Use DMC4Model.exe to convert the .mod to .obj

I did all this but theres no .mtl for the obj. How do i get it

Thanks in Advance

PS: I wanted to ask if when I extract the file of Dante and Nero (from the player file not enemy or cutscene) I get the Devil Trigger of both, Im asking because with RPGViewer I can see textures for DT.

Another thing after I get the .arc files that i want can I uninstall DMC4, Im running short on space.

Thanks.
## Post #136
- Username: swordzero
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 17, 2009 2:07 am
- Post datetime: 2009-10-14T22:30:45+00:00
- Post Title: Re: [PC] Devil May Cry 4

Ok... I read the Resident Evil 5 Post and that works, sorry I didn't read it before but my HDD was almost full and I was gonna install the RE5 once I finished ripping DMC4.
Thanks anyways
## Post #137
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-21T12:37:49+00:00
- Post Title: Re: [PC] Devil May Cry 4

just tested in this moment and the compression used in DMC4 is XMemCompress:
- XMemCompress for compressing the data
- XMemDecompress for decompressing it

the decompression is supported natively in quickbms.
another mistery revealed :)
## Post #138
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-21T13:58:44+00:00
- Post Title: Re: [PC] Devil May Cry 4

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

comtype XMemDecompress
idstring "ARC\0"
get DUMMY short
get FILES short
for i = 0 < FILES
    getdstring NAME 0x40
    get TYPE long
    get ZSIZE long
    get SIZE long
    get OFFSET long

    if SIZE & 0x40000000
        math SIZE -= 0x40000000
    endif

    # I don't know why but wants at least 8 bytes more... mah
    # clog NAME OFFSET ZSIZE SIZE
    log MEMORY_FILE OFFSET ZSIZE
    for j = 0 < 8   # zeroing at least 8 bytes
        putvarchr MEMORY_FILE ZSIZE 0
        math ZSIZE += 1
    next j
    clog NAME 0 ZSIZE SIZE MEMORY_FILE
next i
```
as written in my comment I don't know why but seems that must be added some other bytes (at least 8) after the input data... don't ask me why, I have spent no time on the reversing of the executable.

I have also compared the files obtained from uPlayerDante.arc with quickbms and RPGViewer and the result is identical
## Post #139
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-10-27T14:54:03+00:00
- Post Title: Re: [PC] Devil May Cry 4

i have used the lost planet arc extractor and extracted some arc files from dmc4. but when I click the dmc4 extract program, a window pops up and disappears. Am i missing something? also how to use the mod2obj tool? sry for asking so much question cuz im new to this stuff.
## Post #140
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-10-28T08:04:24+00:00
- Post Title: Re: [PC] Devil May Cry 4

To .arc files, use the RPGViewer. Download link on the first pages, description on previous page, last post.
## Post #141
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-10-28T15:03:39+00:00
- Post Title: Re: [PC] Devil May Cry 4

thanks for the reply.
i do have rpgviewer but i don no how to use it. i tried using it, but cant get it to work eiither.
## Post #142
- Username: wizard
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 28, 2009 11:55 pm
- Post datetime: 2009-10-28T15:59:56+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hey guys.
Some of you may know me from the Re4 & Re5 PC modding forums, I'm the admin there.

Last night I spent about 4 hours just going through a ton of DMC4 level files, seeing what is what, and what the effect was. I made a list as I went along, I figured I'd post it here, as well.

scr\st001\sdl (st001 is the stage ARC, same files in most level ARC's, just differnt names and coding)

st001.sdl = Calls for all files inside of the SDL folder (If blanked out, entire level goes black)
st001-f00.sdl = Enviromental Lighting, calls for a few sky textures (sun, stars)
st001_snd.sdl = Something to do with audio, not sure what it is though.
st001-md00.sdl = Calls for all trasperncy files for enviroment, which are :
st001-md01.sdl = Enviromental transperncy
st001-md02.sdl = Enviromental transperncy
st001-md03.sdl = Enviromental transperncy
st001-md04.sdl = Enviromental transperncy
st001-md05.sdl = Enviromental transperncy
st001-md07-enkei.sdl = Enviromental transperncy
st001-md10.sdl = Enviromental transperncy
st001-md12-kage.sdl = Enviromental transperncy
st001-ml00.sdl = Character, enemy and breakable enviroment lighting
st001-sl00.sdl = No idea
st001-sl01.sdl = No idea
st001-sl02.sdl = No idea

scr\st001\cam
st001.stc = Camera Information.

\scr\st001\data
emset001.pla = Enemy Spawn Information (If blanked out, enemies don't spawn)
st001-em000-00.miss1 = Something to do with enemies
st001-ground-00.miss1 = Something to do with enemies

\scr\st001\etc
Can't touch this folder yet. When I redirect the files in the ARc so I can load a edited version, OR normal verison, game goes all flashy, audio works but controls stop, forced to close game out.

st001\system\filter
GhostMask.tex = Filter Texture

st001\system\texture
FlowingWaterNormal_NM.tex = Water Texture

st001\sound (4 folders)
ARC[folder] = No Idea
bgm[folder] = Background Music / Ambience (sngw sounds can be renamed to .OGG, and edited in GoldWave (Program) and put back in by renamed extension back to .SNGW
se[folder] = Foot steps sounds , and maybe a few other things
seg[folder] = No Idea

st001\effect (4 folders)
There is 4 folders in the effect folder, some have multiple files. I didn't test any of them but they will all obviously be something Speical Effect related to the level.

st001\id\map
st001_map_NOMIP_BM_HQ.tex = Map of Area (Used for mini-map in-game)

st001\id\area_name
st001.msg = Coding for location of area display name
st001_NOMIP_BM_HQ.tex = Texture for area display name (has alpha channels on it)

st001\id\localize (5 folders)
5 differnt folders, each being a differnt languages of the same thing as Area Name above.

\st001\language
I don't think I really need to explain this one 

st001\model\game\orb000
orb000.mod = Red Orb Model
RedOrb_BM-01.tex = Red Orb Texture
RedOrb_MM-01.tex = Red Orb Special Texture (diffuse or something)

st001\scr\arc
st001.xml = No idea, when blanked out, no differnce is made.

st001\scr\st001\stage
This folder holds all the level's non-breakable enviromental models, and textures. (Collison is built onto the models)

st001\scr\ware\ko011 
ko011-m30e-bench.mod = Bench Model [Breakable]
ko011-m30-bench.mod = Bench Model [Breakable]
st001-t-bench_BM.tex = Bench Texture
ko011.col = Bench Collison

st001\scr\ware\ko014
ko014-m00e-gomibako.mod = Jar [Breakable]
ko014-m00-gomibako.mod = Jar [Breakable]
ko012-t-gomibako_BM.tex = Jar Texture
ko012-t-gomibako_MM.tex = Jar Texture
ko012-t-gomibako_NM.tex = Jar Texture
ko014.col = Jar Collison


All levels will be similar to this, but obviously there folders like Ware, will have different breakable objects, but this list gives you an idea how each level is set up.
## Post #143
- Username: ResiHax
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Sep 27, 2009 7:54 am
- Post datetime: 2009-10-28T20:34:36+00:00
- Post Title: Re: [PC] Devil May Cry 4

As I said Wizard, Hell's Altelier wan'ts you. xD

Nice contribution.
## Post #144
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-10-31T13:53:51+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi!!
There's finally some progress on the model skinning, now simple models fully support bone skinning and I hope soon complex models will do the same ...
The reason why this is dificult is: models have some bone groups ex: in nero high res model, there is a group for the left arm (the one holding the sword, starting from the spine), another for the right arm (devil arm, another spine for this), the broken arm has also a bone set and finally the regular body bones with another spine!!!
Of course the tricky part is how to make the link between all those. I'll keep looking and will update you with whatever I find 
[Skinning.JPG](https://xentaxbackup.github.io/file/2488_Skinning.JPG)
## Post #145
- Username: poly
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Aug 28, 2008 8:17 pm
- Post datetime: 2009-10-31T14:54:02+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hey Surveyor that looks awesome!
You seem to be way ahead of my progress 

Did you then figure out the remapping? I'm still struggling with the info you gave me in the last personal message, any update on that front?
## Post #146
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-11-01T06:59:41+00:00
- Post Title: Re: [PC] Devil May Cry 4

congratulation    Surveyor
## Post #147
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-11-02T14:06:24+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hello!
I have a question, is somebody here good at max script or max in general? because I tried to import vertex normals and look what happens!!
When I choose edit mesh and select faces/polygons/elements, the normals work fine bt when I'm out of the edit mesh modifier normals simply disapear!!
I don't understand!!! It seems like if normals are only valid inside the edit mesh scope. One trick I found was to select all the polygons and go to smoothing groups, click on the button that holds the number 1 and then click again. This'll make the normals work even when not in the edit mesh scope. But, when I try to touch the mesh (delete a vertex, make an edge invisible, ...) the normals get back to normal (no normals that is)!!!!

And now for the good news  now skinning behaves better and better and soon there will be a full support for all the Lostplanet/DMC4/RE5 models (hires + lowres)
As you can see in the pic below, the models look like some unfinished wood sculptures (because of the normals)!!
[Skinning2.JPG](https://xentaxbackup.github.io/file/2491_Skinning2.JPG)
## Post #148
- Username: Wudan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 13, 2009 11:44 pm
- Post datetime: 2009-11-02T17:48:04+00:00
- Post Title: Re: [PC] Devil May Cry 4

Surveyor, what is the triangle ordering (the indexes or whatever you call them) for humanoid models?  I always get strange triangles, but the vertices look good.
## Post #149
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-02T20:33:56+00:00
- Post Title: Re: [PC] Devil May Cry 4

Have you tried welding the verts with .001 on the models?
## Post #150
- Username: famesethu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 06, 2009 8:22 pm
- Post datetime: 2009-11-06T20:22:44+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hey Guys Pls try these ingame moded Cutscenes.........
[http://www.youtube.com/watch?v=ffE4JKyKskc](http://www.youtube.com/watch?v=ffE4JKyKskc)
[http://www.youtube.com/watch?v=MUk-oWWzRR8](http://www.youtube.com/watch?v=MUk-oWWzRR8)
[http://www.youtube.com/watch?v=4Eh7mtiDJfk](http://www.youtube.com/watch?v=4Eh7mtiDJfk)
## Post #151
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-11-06T21:14:47+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from chrrox
>
> 
Have you tried welding the verts with .001 on the models?
Well I'm trying to avoid this trick since when you weld verts, normals will be recalculted the max way and it isn't the same!!

> Reply from Wudan
>
> urveyor, what is the triangle ordering (the indexes or whatever you call them) for humanoid models? I always get strange triangles, but the vertices look good.
Well if you look at the code for the converter, you see this line:
unsigned int i0 = m_pIndex[m_pObject[a].uiStart + b] + m_pObject[a].uiBase + (m_pObject[a].uiBase1 / 32) + 1 + uiIndex;
It took me about a month just to figure out the 32 divisor thing and I doubt the game uses it this way!!! but as long as it works, we're fine 

Edit: Here's a pic to demonstrate how models should appear under max and the difference with the max vertex weld, this difference is most seen in the legs, weapon and binoculars.
[Normal.JPG](https://xentaxbackup.github.io/file/2507_Normal.JPG)
## Post #152
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-11-08T09:55:45+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi guys!!
The new converter now supports skinning on Lostplanet models, the normals problem still persists, no texture coords yet, but I'll keep looking!!
[FullSkinning.JPG](https://xentaxbackup.github.io/file/2509_FullSkinning.JPG)
## Post #153
- Username: Nexus Elite ns
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2009 1:11 am
- Post datetime: 2009-11-09T05:14:48+00:00
- Post Title: Re: [PC] Devil May Cry 4

Really nice job so far, for the normal thing, it just like that even when welding them, all you can do is, redo the smoothing on them your own.
## Post #154
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2009-11-09T18:11:46+00:00
- Post Title: Re: [PC] Devil May Cry 4

Great progress!
## Post #155
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-11-10T13:55:44+00:00
- Post Title: Re: [PC] Devil May Cry 4

Did you try rendering the models with the normals maps applied and with a smooth group of 1?

Believe it or not, some models do not have smooth groups at all other then a single channel. The normal map is the thing that is doing all the work.

Just take a look at some of the Doom inorganic models.

Not sure if this is the case here.
## Post #156
- Username: famesethu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 06, 2009 8:22 pm
- Post datetime: 2009-11-10T14:44:50+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hey Surveyor,
Can u please post your DMC4 "Direct3D stage viewer"  as u mentioned in the previous post for viewing loaded scene with texture depth,diffused texture and lightmap applied.......
It will be a great help to analyze the game.
thanks
## Post #157
- Username: famesethu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 06, 2009 8:22 pm
- Post datetime: 2009-11-10T19:30:05+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hey Surveyor,
                I'm stuck with your "DMC4Model" tool  ,the remaining arc extraction and texture conversion works fine.
By converting the Mod models of DMC to obj format the scaling to three axis arent in proportion.I get contracted mesh.


This is what i Get when imported to MAX.I'm using 3DS Max 2009


This is what it suppose to get.This one is manualy scaled by me.


This was my Obj importet settings

Could you please help....?The same is for all the models.
## Post #158
- Username: Nexus Elite ns
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2009 1:11 am
- Post datetime: 2009-11-11T07:11:18+00:00
- Post Title: Re: [PC] Devil May Cry 4

It just how the tool is, at the moment. It just flat them out, so you just wait for the update one.
## Post #159
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-11-11T21:46:49+00:00
- Post Title: Re: [PC] Devil May Cry 4

sry for being a noob but i cant get the mod file to get converted with the Dmc4Model extracter. i know someone said to run the extracter thru cmd, but wut do u type to run it?
## Post #160
- Username: famesethu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 06, 2009 8:22 pm
- Post datetime: 2009-11-12T08:49:00+00:00
- Post Title: Re: [PC] Devil May Cry 4

So Dmc4Model.exe converts the mod file to obj but flattens them......?Hm......!  
Hey Surveyor,Cant u use the Directx (.x) file format.The necessary documentations are in the DX SDK or google it.
Besides the DX file supports normals,Tangents,animattion,skinning and much more....
Forgive me if i'm wrong but this is just my suggestions.I'm just a rookie among u professionals.  
Thanks...
## Post #161
- Username: famesethu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 06, 2009 8:22 pm
- Post datetime: 2009-11-12T09:36:09+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from onionhead
>
> sry for being a noob but i cant get the mod file to get converted with the Dmc4Model extracter. i know someone said to run the extracter thru cmd, but wut do u type to run it?

1)Use "RPG Viewer 3.0" to extract the arc file.(Addon->Archive->Ectract)
  Then you will get folders like model,effect etc and files in it without any extension.
2)After that execute the DMC4Extract.exe (in root folder) to give file extension to all.Now the model files got extension as .mod
3)Now execute DMC4Tex.exe (in root folder) to convert Tex file to dds format.(if u need textures)
4)Execute Dmc4Model.exe (in model containing folder) and type the "modelname.mod" in the prompt window.
5)The model files will be extracted to obj format.

Quite Simple...
## Post #162
- Username: DMCdesigns
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 16, 2009 4:56 am
- Post datetime: 2009-11-12T12:00:54+00:00
- Post Title: Re: [PC] Devil May Cry 4

Surveyor could you please give me a link to the current version of your converter.
## Post #163
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-11-13T21:06:55+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hello,
Still going through the game code, and i have not been following the information that is already known so far, but i wanted to at least post some of the things i have found so far.  There may still be some of the original comments in the file from the base source released earlier, but overall there are a number of things i have confirmed through stepping through the benchmark executable.  Since there haven't been any updates source code wise i am not entirely sure if a lot of this has already been figured out.  i would especially be interested in if you have found a reliable way to determine the vertex declaration used.  Hopefully i will have some more of this confirmed later, i just wanted to post what i had and see if there was anything i was currently missing.  Posted here as i haven't started comparing against RE5, but so far they seem to have the same format.  Sorry for the naming conventions used, i may have forgotten to update some of the member variables, i'll get to that when i can.  Would really like to complete any information i currently do not have or may currently have wrong.

It's in binary template format for 010 Editor for those that use it.

Thanks.

```
 * mod.bt - Structure definitions for Devil May Cry 4 - mod file related entities.
 *
 *****************************************************************************
 * Revision History:
 *  2009/11/09 - GWC - Original
 */

#include "common-types.bt"

SetReadOnly(true);

// #pragma displayname("mod structures")
// #pragma fileextensions(".mod")

// #pragma byteorder(little_endian)
LittleEndian();

// mark used bytes with a light green background
SetBackColor(cLtGreen);

// MOD_FILE File Structure
struct MOD_FILE
{
//	#pragma lockAt(0x00000000)

	// MOD_FILE File Header Structure - 0x90 (144) bytes
	struct MOD_HEADER
	{
		// 0x00
		char fileID[4]; // "MOD"
		uint16 fileVersion;
		uint16 jointCount;
		uint16 objectCount;
		uint16 materialCount;
		uint32 vertexCount;
		// 0x10
		uint32 indexCount;
		uint32 unknown0x14;
		uint32 vertexDataSize0 <format = hex>; // vertex stream 0 data size
		uint32 vertexDataSize1 <format = hex>; // vertex stream 1 data size
		// 0x20
		uint32 textureCount;
		uint32 unknownCount0x24;
		uint32 unknownCount0x28;
		uint32 jointDataOffset <format = hex>;
		// 0x30
		uint32 unknownOffset0x30 <format = hex>;
		uint32 textureDataOffset <format = hex>;
		uint32 objectDataOffset <format = hex>;
		uint32 vertexDataOffset0 <format = hex>; // vertex stream 0 data offset
		// 0x40
		uint32 vertexDataOffset1 <format = hex>; // vertex stream 1 data offset
		uint32 indexDataOffset <format = hex>;
		uint32 unknown0x48;
		uint32 unknown0x4C;
		// 0x50
		float4 boundingSphere;
		// 0x060
		float3 minBounds;
		uint32 unknown0x6C;
		// 0x70
		float3 maxBounds;
		uint32 unknown0x7C;
		// 0x80
		uint32 unknown0x80;
		uint32 unknown0x84;
		uint32 unknown0x88;
		uint32 unknown0x8C;
	} fileHeader;
	
	if (0 != fileHeader.jointDataOffset &&
		0 < fileHeader.jointCount)
	{
		FSeek(fileHeader.jointDataOffset);
		struct
		{
			struct
			{
				uint8 cId;
				uint8 cParent;			// -1 means no parents
				uint8 cChild;				// child id
				uint8 cUnknown;
				float fData[2];			// maybe forces?
				float3 position;				// translation vector
			} jointInfo[fileHeader.jointCount];
			
			float4x4 relativeTransforms[fileHeader.jointCount];
			float4x4 absoluteTransforms[fileHeader.jointCount];
			
			uint8 unknownData0[0x100];
			struct
			{
				uint32 unknownCount0x00;
				uint8 unknown0x04[0x20];
			} unknownData1[fileHeader.unknownCount0x28];
		} jointData;
	}
	
	if (0 != fileHeader.unknownOffset0x30 &&
		0 < fileHeader.unknownCount0x24)
	{
		FSeek(fileHeader.unknownOffset0x30);
		struct
		{
			uint32 index;
			uint32 unknown0x04[7];
		} unknownData0x30[fileHeader.unknownCount0x24];
	}
	
	if (0 != fileHeader.textureDataOffset &&
		0 < fileHeader.textureCount)
	{
		FSeek(fileHeader.textureDataOffset);
		struct
		{
			char textureName[0x40];
		} textureData[fileHeader.textureCount];
		
		struct
		{
			// 0x00
			uint32 uiUnknown0x00 <format = hex>; // material flags
			uint32 uiUnknown0x04 <format = hex>; // material flags
			uint32 uiUnknown0x08 <format = hex>; // material id
			uint32 uiUnknown0x0C <format = hex>;
			// 0x10
			uint32 uiUnknown0x10 <format = hex>;
			uint32 uiUnknown0x14;
			// 0x18
			uint32 uiLayers[9];		// tex0 ... tex8 -  base 1, 0 means not bound
			// 0x3C
			float fAlpha; // material alpha? - used as float4(1,1,1,fAlpha) in game code
			// 0x40
			float fUnknown0x40[3];
			float fUnknown0x4C;
			// 0x50
			float fUnknown0x50[4];	// [3] - ignored, assumed to be 0
			// 0x60
			float fUnknown0x60[2];
			float fUnknown0x68;		// ignored?
			float fUnknown0x6C;
			// 0x70
			float fUnknown0x70[4];
			// 0x80
			float fUnknown0x80[4];	// [2] - if < 0, = -1, else =1
									// [3] - ignored?
			// 0x90
			uint32 unknown0x90 <format = hex>;		// some sort of flags/masked values
			uint32 unknown0x94;						// index
			uint32 unknown0x98;
			uint32 uiLayer0x9C;						// tex10
		} materialData[fileHeader.materialCount];
	}
	
	if (0 != fileHeader.objectDataOffset &&
		0 < fileHeader.objectCount)
	{
		FSeek(fileHeader.objectDataOffset);
		struct
		{
			struct
			{
				// 0x00
				uint16			usId;				// id from the indes table
				uint16			usMatId;			// material Id
				uint16			usFlag0x04[2];		// 0xFF01, 0, the 3rd flag determines what vertex declaration to use
				uint8			usFlag0x08[4];		// [2] - unknown value, &= 0xFE if (prev.unknown0x0E + 1) != unknown0x2A
													// [2] - &= 0xBF, if 0 == tex4
				uint16			usFlag0x0C;			// 0xFF01, 0, the 3rd flag determines what vertex declaration to use
				uint16			unknown0x0E;		// unknown value, compared to next object.unknown0x2A
				// 0x10
				uint16			usFlag0x10[2];		// 0xFF01, 0, the 3rd flag determines what vertex declaration to use
				uint32			uiBase1;			// base multiple of 32
				uint32			uiZero;
				uint32			uiStart;			// start index
				// 0x20
				uint32			uiCount;			// faces (indices - 2)
				uint32			uiBase;
				uint8			unknown0x28[2];		// [0], [1] - indices, unknown data
				uint16			unknown0x2A;		// unknown value, compared to previous object.unknown0x0E + 1
				uint8			unknown0x2C[4];		// [0] - unknownData count, number of unknownData blocks assigned
													// [1] - if 0x98 == file version, set to ((usFlag0x08[3] >> 1) & 0x0F)
				// 0x30
				uint32			unknown0x30 <format = hex>; // seems to be unused, overwritten with unknownData start address
			} objectData[fileHeader.objectCount];
			
			struct
			{
				// 0x00
				uint32 unknownCount0x00;
				union
				{
					uint8 dataBytes[0x90];
					struct
					{
						// 0x00
						uint32 parentJoint; // index
						uint32 unknown0x04[3];
						// 0x10
						float4 boundingSphere;
						// 0x20
						float4 minBounds;
						// 0x30
						float4 maxBounds;
						// 0x40
						float4x4 transformMatrix;
						// 0x80
						float3 unknown0x80;
						uint32 unknown0x8C <format = hex>;
					} unknownData;
				} unknownData0x04[unknownCount0x00];
			} unknownData;
		} objectData;
	}
	
	if (0 != fileHeader.vertexDataOffset0 &&
		0 < fileHeader.vertexDataSize0)
	{
		FSeek(fileHeader.vertexDataOffset0);
		union
		{
			uint8 dataBytes[fileHeader.vertexDataSize0];
			// NOTE: still need to determine vertex declaration selection
			struct
			{
				int16	x, y, z, w;			// w always 0x7FFF (32767, divisor?)
				uint8	bone[4];
				uint8	weight[4];
				int8	nx, ny, nz, nw;
				int8	tx, ty, tz, tw;		// tangent not textures !!
				int16	u0, v0;
				int16	u1, v1;				// seems to be always 0xFFFF 0xFFFF
			} vertexData[fileHeader.vertexCount];
		} vertexData0;
	}
	
	if (0 != fileHeader.vertexDataOffset1 &&
		0 < fileHeader.vertexDataSize1)
	{
		FSeek(fileHeader.vertexDataOffset1);
		union
		{
			uint8 dataBytes[fileHeader.vertexDataSize1];
			// NOTE: still need to determine vertex declaration selection
		} vertexData1;
	}
	
	if (0 != fileHeader.indexDataOffset &&
		0 < fileHeader.indexCount)
	{
		FSeek(fileHeader.indexDataOffset);
		uint16 indexData[fileHeader.indexCount - 1];
	}
};

struct MOD_FILE fileInfo;

```
## Post #164
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-11-14T20:12:33+00:00
- Post Title: Re: [PC] Devil May Cry 4

I have extract the files as .mod format but they are all 0 bytes. so am i doing someting wrong. and when I run mod 2 obj it treats it as invalid filename even when i typed the filename in correctly. plz help.
## Post #165
- Username: ResiHax
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Sep 27, 2009 7:54 am
- Post datetime: 2009-11-15T02:59:43+00:00
- Post Title: Re: [PC] Devil May Cry 4

Revelation, what exactly is that code you posted?  Im not too much of a programmer, so I can't tell just by looking.
## Post #166
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-11-15T10:08:30+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hey revelation, nice to see you here!!
I have 010Editor but I keep getting errors and can't run the script!!! but I verified its content and yeah most of the data is correct 
So far I've seen only 3 vertex declarations

This is found in stages
0	D3DDECLTYPE_FLOAT3	POSITION
12	D3DDECLTYPE_UBYTE4N	NORMAL
16	D3DDECLTYPE_UBYTE4N	TANGENT
20	D3DDECLTYPE_FLOAT16_2	TEXCOORD
24	D3DDECLTYPE_FLOAT16_2	TEXCOORD
28	D3DDECLTYPE_FLOAT16_2	TEXCOORD

This is used for bone models
0	D3DDECLTYPE_SHORT4N	POSITION
8	D3DDECLTYPE_UBYTE4	BLENDINDICES
12	D3DDECLTYPE_UBYTE4N	BLENDWEIGHT
16	D3DDECLTYPE_UBYTE4N	NORMAL
20	D3DDECLTYPE_UBYTE4N	TANGENT
24	D3DDECLTYPE_FLOAT16_2	TEXCOORD
28	D3DDECLTYPE_FLOAT16_2	TEXCOORD

And the 3rd declaration, makes use of stream1, this is in case verts are influenced by more than 4 bones, very rare though!
0	D3DDECLTYPE_SHORT4N	POSITION
8	D3DDECLTYPE_UBYTE4	BLENDINDICES
12	D3DDECLTYPE_UBYTE4	BLENDINDICES	index1, null all the times
16	D3DDECLTYPE_UBYTE4N	BLENDWEIGHT
20	D3DDECLTYPE_UBYTE4N	BLENDWEIGHT	index1, null all the time
24	D3DDECLTYPE_UBYTE4N	NORMAL
28	D3DDECLTYPE_FLOAT16_2	TEXCOORD

I think we had enough of this MOD format, there is some unknown data that I don't care about, for me, the next steps are skinning and animation 
Of course there are some other formats that are very interresting to study like the sdl (schedule) files that drive the game
## Post #167
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-11-15T19:27:43+00:00
- Post Title: Re: [PC] Devil May Cry 4

Ok, cool.

i have found a few more vertex declarations used by ripping with 3D Ripper DX, but i need to catalog them all and compare to the files again.  Alot of them have the same format for stream 0 with just a few additional bits of data in stream 1.  i just need to catalog how many there actually are and see if i can find some sort of specifier for which is used.  i also have breakpoints for the places LMT files are loaded as well so i can start looking into how those are structured if need be.  i just like to know how the MOD files interpret some of this remaining data so i am not guessing or hard coding which is used, at least in the long term.  As with you and poly i can retrieve the information just fine with what is known now.  What problems are you having with skinning?  i haven't coded up my skeletal animation code yet, but its something i can look into if there are currently issues.  Also, have you found any models that use the additional texture 10 index found at the end of the material?  If you could it would be helpful if you could list which textures you have found associated with which layer indices.  i have found in the code, layers 5 and 7 seem to be somewhat mutually exclusive, but i am still investigating.  i just saw that you had a good deal of the textures for the stages worked out, and knowing the order would be helpfuly.  On that note, did you ever get multitexturing working in your stage viewer?  Once mine code is up and running i will be writing shaders hopefully able to display things correctly.  Also, some of the remaining data may effect how the joint data is processed at runtime, so will be necessary to propery update the skeleton in some cases i believe (unknownData0 and unknownDat1 in the jointData), i am hoping it will not be as involved as the method used in Street Fighter 4 though as i am still working on determining the last bits of the update process.

ResiHax: it is a structure file defining the layout of the MOD file format. it is in a script format use but the 010 Editor hex editor to automatically parse file when they are loaded an present them as structures.  The code ss pretty close to c++ though so should be fairly easy to convert.

Hopefully i will have some more information soon.

Thanks again.
## Post #168
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-11-16T14:49:34+00:00
- Post Title: Re: [PC] Devil May Cry 4

Ok, just another quick update.

i believe i have found where it creates the various vertex declarations used in the game, as well as reading the associated indices into them.  i also think i have a clearer picture of the values used to determine the start vertex and index buffer values and associated rendering setup.  Still a number of unknowns in some areas but for the most part things seems pretty well nailed down to the point that other parts can be delved into.  Still need to record all of the 16 possible vertex declarations and compare them to files that index some of them, as well as revisit the code location where i unknowingly found the indices previously, and further investigate the with the new information i have (as the index values seem to be listed twice in the data, so i need to confirm why this would be).  Hopefully it will all pan out.  Still not sure what things have been found out since the initial code release with regard to what i have posted so far, but i hope to have another update shortly with the new information presented accordingly. Then i hope you all will be able to help confirm or disprove the findings rather quickly i hope, heh.

Either way, back to it i guess.
## Post #169
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-11-16T20:42:57+00:00
- Post Title: Re: [PC] Devil May Cry 4

something like that ?

```

Type CGROUPS Align 1 '//lot of infos are based on IDirect3DDevice9::DrawPrimitiveUP params for faster rendering process
	usId As word '// id from the index table //unsigned short  'could be a degenerate face counter ?
	usMatId As word '// material Id //unsigned short
	
	usFlag[0 To 7] As word '// 0xFF01, 0, the 3rd flag determines what vertex declaration to use //unsigned short
	'//usFlag[4] = vertexcount =>  == (usFlag[6]-usFlag[5]+1)
	'//usFlag[5] 'a end offset in vertex array
	'//usFlag[6] 'a start offset in vertex array
	'//usFlag[7]'always zero ????
	
	%uiBase1 '// base multiple of 32 '// lodmesh id ?: full mesh = 0, > are degenerated lodmesh ?
	%uiZero '//unsigned int
	%uiStart '// start index 		//unsigned int   
	%uiCount '// faces (NBindices - 2)	//unsigned int  =primitivecount
	%uiBase '//
	uiInconnu[0 To 5] As word '//			//unsigned int
	'//uiInconnu[1]= first face vertex id A on ABC == usFlag[6] ->strange to store same info twice ???
	'//uiInconnu[4]= an adress (or offset to an adress) perhaps next lod group id ?
End Type

```
## Post #170
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-11-16T20:49:25+00:00
- Post Title: Re: [PC] Devil May Cry 4

```
{
	// 0x00
	uint16    usId0 : 5;              // used as power of 2, tested against value indexed by usId1
	uint16    usId1 : 11;             // used as an index into a list of 32-bit (4-byte) values
	uint16    usMatId;                // material Id
	uint8     usFlag0x04[2];          // [0] - processing skipped if == 0
	                                  // [1] - tested against an unknown bitmask
	uint16    usFlag0x06;             //
	uint8     usFlag0x08[4];          // [2] - unknown value, &= 0xFE if (prev.endVertex0x0E + 1) != startVertex0x2A
	                                  // [2] - &= 0xBF, if 0 == tex4
	uint16    vertexCount0x0C;        // vertex count
	uint16    endVertex0x0E;          // end vertex - last vertex index used, compared to next object.startVertex0x2A
	// 0x10
	uint32    minVertex0x10;          // min vertex index
	uint32    streamOffset0_0x14;     // start offset for vertex stream 0 (in bytes)
	uint32    streamOffset1_0x18;     // start offset for vertex stream 1 (in bytes)
	uint32    startIndex0x1C;         // start index
	// 0x20
	uint32    indexCount0x20;         // index count - faces (indices - 2)
	uint32    uiBase0x24;             //
	uint8     unknown0x28[2];         // [0], [1] - indices into vertex declarations
	uint16    startVertex0x2A;        // start vertex, compared to previous object.endVertex0x0E + 1
	uint8     unknown0x2C[4];         // [0] - unknownData count, number of unknownData blocks assigned
	                                  // [1] - if 0x98 == file version, set to ((usFlag0x08[3] >> 1) & 0x0F)
	// 0x30
	uint32    unknown0x30 <format = hex>;    // seems to be unused, overwritten with unknownData start address
} objectData[fileHeader.objectCount];

```


Still finalizing some values, and i will post the vertex declarations used as well when i get the chance.  Hopefully this will help verify and find some other things in the format.  i still need to go back through some of the remaining flag values and fins where it specifies which of the 2 vertex declaration indices to use.  The first usually appears to be the bare bones stream 0 format, the second contains more data or slightly different data layout and is usually the one that contains information used with vertex stream 1.  Also trying to nail down the material flags that specify the initial vertex declaration information.  This is also more than like the specifiers for the shaders used, but for now i can only directly tie them to the vertex declarations without digging deeper into some of the directx structures.
## Post #171
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-11-17T15:50:12+00:00
- Post Title: Re: [PC] Devil May Cry 4

ok, getting a little busy with some things, so i wanted to go ahead and post some of th einfo i have so far in hopes that those able to make sens of it will be able to use it accordingly and move things even further forward.

i am still working on determining the purpose of most of the values in the flags fields but i have commented at least the most important one concerning this update, the values used to determine the vertex declaration(s) used.  As i mentioned previously this is probably also a custom material class used by the engine so it probably has shader references as well, but i have not put breakpoints at the other direct3d functions with regard to this yet.

```
{
	// 0x00
	union
	{
		uint32 flags0x00 <format = hex>; // material flags
		struct
		{
			uint32 unknown0x00_00 : 2;
			uint32 unknown0x00_02 : 12;
			uint32 unknown0x00_0E : 8;
			uint32 unknown0x00_16 : 3;
			uint32 unknown0x00_19 : 2;
			uint32 unknown0x00_1B : 3; // vertex declaration formats specifier (0 - 5)
			uint32 unknown0x00_1E : 2; // multiplied by 16, xor'ed with unknown value and and'ed against 0x10
		} flagBits;
	} unknownFlags0x00;
	union
	{
		uint32 flags0x00 <format = hex>; // material flags
		struct
		{
			uint32 unknown0x00_00 : 4;
			uint32 unknown0x00_04 : 2;
			uint32 unknown0x00_06 : 4;
			uint32 unknown0x00_0A : 4;
			uint32 unknown0x00_0E : 4;
			uint32 unknown0x00_12 : 4;
			uint32 unknown0x00_16 : 4;
			uint32 unknown0x00_1A : 6;
		} flagBits;
	} unknownFlags0x04;
	uint32 uiUnknown0x08 <format = hex>; // material id? - replace with an index value after comparison
	uint32 uiUnknown0x0C <format = hex>;
	// 0x10
	uint32 uiUnknown0x10 <format = hex>; // overwritten with first vertex declaration address
	uint32 uiUnknown0x14 <format = hex>; // overwritten with second vertex declaration address
	// 0x18
	uint32 uiLayers[9];		// tex0 ... tex8 -  base 1, 0 means not bound
	// 0x3C
	float fAlpha; // material alpha? - used as float4(1,1,1,fAlpha) in game code
	// 0x40
	float3 fUnknown0x40;
	float fUnknown0x4C;
	// 0x50
	float4 fUnknown0x50;	// [3] - ignored?, assumed to be 0
	// 0x60
	float2 fUnknown0x60;
	float fUnknown0x68;		// ignored?
	float fUnknown0x6C;
	// 0x70
	float4 fUnknown0x70;
	// 0x80
	float4 fUnknown0x80;	// [2] - if < 0, = -1, else =1
							// [3] - ignored?
	// 0x90
	uint32 unknown0x90 <format = hex>;		// some sort of flags/masked values
	uint32 unknown0x94;						// index
	uint32 unknown0x98;
	uint32 uiLayer0x9C;						// tex10
} materialData[fileHeader.materialCount];

```


here is the way the vertex declaration value is used when modifying the material information.  Each material keeps the addresses of 2 of these declaration structures.  i am still in the process of determining how it decides which one to use for each object.  Also since declarations 0 and 5 are the same the objects will usually use 5 in the index values if you look at the files themselves, but so far these values have not been touched again in the code once determined from the object's material index.

```
if 0 == format
- vertex declaration 5
- vertex declaration 0
if 1 == format
- vertex declaration 7
- vertex declaration 2
if 2 == format
- vertex declaration 6
- vertex declaration 1
if 4 == format
- vertex declaration 10
- vertex declaration 11
if 5 == format
- vertex declaration 5
- vertex declaration 12
if 3 == format
- vertex declaration 6
- if 1 == unknownFlags0x04.unknown0x00_16
- - vertex declaration 9
- else
- - vertex declaration 8

```


and here are the data values used in all of the vertex declaration created through the course of the game so far.  The information above determines which are selected, so some of them are not all that important to file formats, those not being used often pertaining to other visual effects not present in the file, like some of the water rendering, etc.  Soory, like i said, i have not coded things up into a viewer yet, so i have not yet taken the time to relate everything back into values relevant to direct3d, but they are simply the values inorder used to populate a D3DVERTEXELEMENT9 structure array for use in CreateVertexDeclaration calls.  If i happen to do this before anyone else gets to it i will post things in code form.

```

// 0EE78680 - [00] - same as [05]
 0,  0, 10,  0,  0,  0
 0,  8,  5,  0,  2,  0
 0, 12,  8,  0,  1,  0
 0, 16,  8,  0,  3,  0
 0, 20,  8,  0,  6,  0
 0, 24, 15,  0,  5,  0
 0, 28, 15,  0,  5,  1
FF,  0, 17,  0,  0,  0

// 0EE787C0 - [01]
 0,  0,  2,  0,  0,  0
 0, 12,  8,  0,  3,  0
 0, 16,  8,  0,  6,  0
 0, 20, 15,  0,  5,  0
 0, 24, 15,  0,  5,  1
 0, 28, 15,  0,  5,  2
 1,  0, 15,  0,  5,  3
FF,  0, 17,  0,  0,  0

// 0EE78860 - [02]
 0,  0, 10,  0,  0,  0
 0,  8,  5,  0,  2,  0
 0, 12,  5,  0,  2,  1
 0, 16,  8,  0,  1,  0
 0, 20,  8,  0,  1,  1
 0, 24,  8,  0,  3,  0
 0, 28, 15,  0,  5,  0
 1,  0, 15,  0,  5,  1
 1,  4,  8,  0,  6,  0
FF,  0, 17,  0,  0,  0

// 0EE782A0 - [03]
 0,  0,  2,  0,  0,  0
 0, 12,  4,  0, 10,  0
 0, 16,  1,  0,  5,  0
FF,  0, 17,  0,  0,  0

// 0EE78330 - [04]
 0,  0,  2,  0,  0,  0
 0, 12,  4,  0, 10,  0
 0, 16,  1,  0,  5,  0
 0, 24,  1,  0,  5,  1
FF,  0, 17,  0,  0,  0

// 0EE78680 - [05] - same as [00]
 0,  0, 10,  0,  0,  0
 0,  8,  5,  0,  2,  0
 0, 12,  8,  0,  1,  0
 0, 16,  8,  0,  3,  0
 0, 20,  8,  0,  6,  0
 0, 24, 15,  0,  5,  0
 0, 28, 15,  0,  5,  1
FF,  0, 17,  0,  0,  0

// 0EE78570 - [06]
 0,  0,  2,  0,  0,  0
 0, 12,  8,  0,  3,  0
 0, 16,  8,  0,  6,  0
 0, 20, 15,  0,  5,  0
 0, 24, 15,  0,  5,  1
 0, 28, 15,  0,  5,  2
FF,  0, 17,  0,  0,  0

// 0EE78720 - [07]
 0,  0, 10,  0,  0,  0
 0,  8,  5,  0,  2,  0
 0, 12,  5,  0,  2,  1
 0, 16,  8,  0,  1,  0
 0, 20,  8,  0,  1,  1
 0, 24,  8,  0,  3,  0
 0, 28, 15,  0,  5,  0
FF,  0, 17,  0,  0,  0

// 0EE78910 - [08]
 0,  0,  2,  0,  0,  0
 0, 12,  8,  0,  3,  0
 0, 16,  8,  0,  6,  0
 0, 20, 15,  0,  5,  0
 0, 24, 15,  0,  5,  1
 0, 28,  4,  0, 10,  0
FF,  0, 17,  0,  0,  0

// 0EE789B0 - [09]
 0,  2,  0,  0,  0,  0
 0, 12,  8,  0,  3,  0
 0, 16,  8,  0,  6,  0
 0, 20, 15,  0,  5,  0
 0, 24, 15,  0,  5,  1
 0, 28,  4,  0, 10,  0
 1,  0, 15,  0,  5,  2
FF,  0, 17,  0,  0,  0

// 0EE78BB0 - [10]
 0,  0, 10,  0,  0,  0
 0,  8,  5,  0,  2,  0
 0, 12,  8,  0,  1,  0
 0, 16,  8,  0,  3,  0
 0, 20,  5,  0,  5,  0
 0, 24, 15,  0,  5,  1
 0, 28, 15,  0,  5,  2
FF,  0, 17,  0,  0,  0

// 0EE78C50 - [11]
 0,  0, 10,  0,  0,  0
 0,  8,  5,  0,  2,  0
 0, 12,  8,  0,  1,  0
 0, 16,  8,  0,  3,  0
 0, 20,  5,  0,  5,  0
 0, 24, 15,  0,  5,  1
 0, 28, 15,  0,  5,  2
 1,  0,  8,  0,  6,  0
FF,  0, 17,  0,  0,  0

// 0EE78D00 - [12]
 0,  0, 10,  0,  0,  0
 0,  8,  5,  0,  2,  0
 0, 12,  8,  0,  1,  0
 0, 16,  8,  0,  3,  0
 0, 20,  8,  0,  6,  0
 0, 24, 15,  0,  5,  0
 0, 28,  4,  0, 10,  0
FF,  0, 17,  0,  0,  0

// 0EE783D0 - [13]
 0,  0,  2,  0,  0,  0
 0, 12,  5,  0,  2,  0
 0, 16,  5,  0,  2,  1
 0, 20,  8,  0,  1,  0
 0, 24,  8,  0,  1,  1
 0, 28,  0,  0,  3,  0
 0, 32,  0,  0,  6,  0
 0, 36,  9,  0,  5,  0
 0, 40,  9,  0,  5,  1
 0, 44,  9,  0,  5,  2
 0, 48,  9,  0,  5,  3
 0, 52,  4,  0, 10,  0
FF,  0, 17,  0,  0,  0

// 0EE78A50 - [14]
 0,  0, 10,  0,  0,  1
 0,  8,  5,  0,  2,  0
 0, 12,  8,  0,  1,  0
 0, 24, 15,  0,  5,  0
 0, 28, 15,  0,  5,  1
 2,  0, 10,  0,  0,  2
 2,  8,  8,  0,  3,  0
 2, 12,  8,  0,  6,  0
FF,  0, 17,  0,  0,  0

// 0EE78B00 - [15]
 0,  0, 10,  0,  0,  1
 0,  8,  5,  0,  2,  0
 0, 12,  8,  0,  1,  0
 0, 24, 15,  0,  5,  0
 0, 28,  4,  0, 10,  0
 2,  0, 10,  0,  0,  0
 2,  8,  8,  0,  3,  0
 2, 12,  8,  0,  6,  0
FF,  0, 17,  0,  0,  0

// 0EE78490 - [16]
 0,  0,  0,  0,  0,  0
FF,  0, 17,  0,  0,  0

// 0EE785E0 - [?0]
 0,  0,  3,  0,  0,  0
 0, 16,  3,  0,  2,  0
 0, 32,  3,  0,  2,  1
 0, 48,  3,  0,  1,  0
 0, 64,  3,  0,  1,  1
 0, 80,  3,  0,  3,  0
 0, 96,  3,  0,  6,  0
 0, 112,  3,  0,  5,  0
 0, 128,  3,  0,  5,  1
 0, 144,  3,  0,  5,  2
 0, 160,  3,  0,  5,  3
 0, 176,  3,  0, 10,  0
 0, 192,  3,  0,  7,  0
FF,  0, 17,  0,  0,  0

// 0EE78520 - [?1] - empty?
 0,  0,  0,  0,  0,  0
FF,  0, 17,  0,  0,  0



-------------------------------------
// 0EE78DA0 - [?2]
 0,  0,  2,  0,  0,  0
 0, 12,  4,  0, 10,  0
 0, 16, 10,  0,  5,  0
 0, 24,  5,  0,  5,  1
 0, 28,  5,  0,  5,  2
FF,  0, 17,  0,  0,  0

// 0EE78E40 - [?3]
 0,  0,  2,  0,  0,  0
 0, 12,  4,  0, 10,  0
 0, 16, 10,  0,  5,  0
 0, 24,  9,  0,  5,  1
FF,  0, 17,  0,  0,  0

// 0F800680 - [?4]
 0,  0,  2,  0,  0,  0
 0, 12,  1,  0,  5,  0
 0, 20,  2,  0,  5,  1
 0, 32,  2,  0,  5,  2
 0, 44,  2,  0,  3,  0
FF,  0, 17,  0,  0,  0

// 0F800720 - [?5]
 0,  0,  2,  0,  0,  0
FF,  0, 17,  0,  0,  0

```


Let me know if there is anything you need clarified.  i'll report when i have any new findings.

Hope this helps.
## Post #172
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-11-17T21:17:18+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi,
It was about time I release something so here's my new MOD to Max converter, this is a whole new approach: the program will generate a max script file to run directly inside 3dsmax. I have max8 and I think this'll work on all the later versions.
All you have to do is run the program, type in the model you want, go to max, type F11, select File->RunScript and choose your freshly created MS file. It'll take some time before the model fully loads into max. On my celeron 2.00Ghz 768Mb ram nvidia fx5200 that bugs all the time, this takes about 4 minutes for each model 
You'll also need to increase the maxscript memory: go to Customize -> Preferences -> MaxScript tab and change the memory amount, the default is 7.5Mb, I changed it to 150Mb and that seemed to work fine on all the models I tested!!
The main feature of this new converter is the full support for bone/skinning on Dmc4 & Lostplanet. But for the rest (texture coords, normals) you'll have to wait. The program also fixes the pancake effect, now all the models are nicely scaled!
You can experience the normal bug on any object, just select an objet, go to edit mesh and notice how normals become normal (correct)
Caution: to use only with bone models, don't try this on stages, items, ....

Now for the technical stuff,
As you know in MOD files, all objects share the same vertex buffer, so I had 2 choices: export objects per vertex buffer basis in which case I get only one object per model and an export per object basis so I get all the objects separated. Each method has it's advantages and disadvantages.
Exporting to OBJ was the easiest way to get the job done: I wrote the whole vertex buffer then went through all the objects and wrote the indices. The 1st approach is exactly what I did with OBJ files, but in max script there isn't any face group separator so all the faces belong to one group and I get only one object per model.
Well the reason Capcom decided to use one vertex buffer for the model is obvious: performance. They also arranged the vert's to make use of the stripping, DirectX Sdk Docs say you should use D3DPT_TRIANGLESTRIP whenever possible and you should minimise the SetVertexBuffer() and SetIndexBuffer() calls to gain performance, 1 SetVertexBuffer() call per model draw is really the minimum. The vertex buffer can hold different vertex types but this doesn't matter as long as you know what vertex declaration to use at a given draw. It's the first time I see such a system so the 1st conclusion is: Capcom did a hell of a job to optimize their data.
The problem with this method is that it is virtually impossible to strip a mesh without duplicating some verts but in the case of MOD files, this is too exagerated: there are way too many duplicate verts: more than 30 identical successive verts can be seen in hex editor and there are not few of these duplications!!! This is seen in the hi res models and as an example I took Nero hi res head model that says there are 49613 verts and 12184 indices. This is relatively very high res for any model and this is only the head!!!
When I click RunScript under max for this head model, there is the "unknwon exception" error in max that simply means that there are way too many verts for a single object. This makes me wonder what is the maximum vertex count an object can have in maxscript. The 2nd conclusion is: Capcom models aren't that optimized!!!
The 2nd approach exports per object basis. Under max script, every mesh must have it's set of verts, meshes can't share some vertex buffer. The 1st problem with this is that on hi res head models, there are too many objects, capcom could've made the head in a sngle object; I wonder why they didn't!!
Another problem with this approach is that on export, verts are rearranged the index buffer way, these index buffers are far from being optimized and there are some duplicate indices here too!!! which leads to duplcate verts on the export!!!! But at least this method doesn't crash maxscript and all the models load OK! This is themoethod used in the converter posted here.

Here are some numbers:
with Mod2Obj I get this:
verts: 5305, faces: 5804, when the verts of this model are weld, I get this:
verts: 2917, faces: 5804, the fact that the face count didn't change shows that there are indeed many duplicate verts. Now with the new converter:
verts: 11935, faces: 11846 and with weld we have:
verts: 2928, faces: 5804
Even if we consider that there are some duplicate verts for a reason (eyelashes for example have 2 sides so usually the artists make the same mesh that points upwards point downwards, this of course leads to duplication), this doesn't exceed 10% of the initial vertex count!!! But here we have a serious duplication problem (from 49613 verts originally to 11935 verts in the worst case). My 3rd conclusion is: Capcom engineers must be drunk to come up with such a nonsense!!! no wonder Lostplanet doesn't perform well even on Core 2 Duo processors!!!

Well all this was just to say that depending on what will be done with the converter (reimport back to game, make renders, torture the poor guy, ...), this may or may not pose problems. Me, I'd like to make a proper Direct3D viewer out of this so this shouldn't annoy me, on the other hand, there is the normals bug that makes my nerves burn!!!!
OK enjoy this new converter and let me know if there are any bugs!
[Mod2Max.zip](https://xentaxbackup.github.io/file/2537_Mod2Max.zip)
## Post #173
- Username: DMCdesigns
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 16, 2009 4:56 am
- Post datetime: 2009-11-17T21:36:00+00:00
- Post Title: Re: [PC] Devil May Cry 4

So is there a way to use this to mod the game now? And can you make it work with Maya?
## Post #174
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-11-18T08:16:38+00:00
- Post Title: Re: [PC] Devil May Cry 4

@Surveyor: Wow, amazing work so far mate. I'll be sure to report ant bugs that might come up.

@DMCdesigns: Don't you think we should wait for a clean version of the script of this version first BEFORE asking for other 3DS Packages Scripts?
## Post #175
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-11-18T11:29:16+00:00
- Post Title: Re: [PC] Devil May Cry 4

ok seems we need some infos , normal bug is not a bug, the normals you import are dynamic normals based on the skeleton pose, they are recalculated dynamicly by the engine ,differently than max do (they need to be rotated by the inverse matrix of the vertex associated joint and normalized after.

the vertex duplication can also be explain easily, when welding vertices, the weld is based on vertex pos and not on uv mapping, so if you weld only this way , the rendering using vertex arrays and indices will completly fuck up the model mapping, the only way to fix it is to add degenerated faces or to duplicate vertices, degenerated faces could not be used here because they optimised the strip indices to get a mutlires mesh strip array, i encountered the same problem while coding my xandreale 3d modeler and getting wrong normals or fucked uv's, then i added a model cleaner that rebuild the mesh by duplicating some vertex an it fixed the problem on uv...

so there is no bug, we just need to add a lot more computations on the whole mesh before exporting and this is another story ...
## Post #176
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-11-18T12:55:12+00:00
- Post Title: Re: [PC] Devil May Cry 4

this is some a+ stuff right here. Good work and so on
## Post #177
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-11-18T15:48:47+00:00
- Post Title: Re: [PC] Devil May Cry 4

to follow on what has been said so far, the main reasons for the vertex duplication are more than likely tri-strip length, uv coordinates and batch size.  All of which affect things differently as it can be very hard to get good tri-strip length when having to also keep uv information intact, even more so with multitexturing where it is not always possible for the textures mapped to use the same uv coordinates (as is very evident given the variation of the vertex declarations).  Lightmaps and Ambient occlusion maps are often big hindrances in this area as well since they do not usually allow for vertices being mapped to the same texel in an image as is possible with the other texture maps used.  As far as batch count goes, even on today's hardware there are not any cards i know of that have a recommended vertex batch size of anywhere near 49000+ vertices as such even if it was all contained in one object it would not be performance friendly to render the whole thing as such.  But at this point i can only speculate as to why capcom chose to go in this direction, heh.

It would be really nice if one or both of either opengl and/or direct3d added support for multiple index streams similar to the way the gamecube/wii works.  Would come in handy for things like this as it would pretty much eliminate the need for duplicate vertices in most cases, and possible cut down a great deal on repeated data in others.  oh well.

How many objects were you getting on the model(s) you were testing?

Once i get things setup in a better way to extract things more efficiently i'll have to look into this more to compare against your findings.

EDIT:
Wow, you weren't kidding.  i'll have to attempt rendering this model, but if i am looking at the same one you mentioned, those really are some small batches.  Will have to play around with these files some.
## Post #178
- Username: poly
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Aug 28, 2008 8:17 pm
- Post datetime: 2009-11-19T18:43:42+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> Hi,
It was about time I release something so here's my new MOD to Max converter, this is a whole new approach: the program will generate a max script file to run directly inside 3dsmax. I have max8 and I think this'll work on all the later versions.
All you have to do is run the program, type in the model you want, go to max, type F11, select File->RunScript and choose your freshly created MS file. It'll take some time before the model fully loads into max. On my celeron 2.00Ghz 768Mb ram nvidia fx5200 that bugs all the time, this takes about 4 minutes for each model 
You'll also need to increase the maxscript memory: go to Customize -> Preferences -> MaxScript tab and change the memory amount, the default is 7.5Mb, I changed it to 150Mb and that seemed to work fine on all the models I tested!!
The main feature of this new converter is the full support for bone/skinning on Dmc4 & Lostplanet. But for the rest (texture coords, normals) you'll have to wait. The program also fixes the pancake effect, now all the models are nicely scaled!
You can experience the normal bug on any object, just select an objet, go to edit mesh and notice how normals become normal (correct)
Caution: to use only with bone models, don't try this on stages, items, ....

Now for the technical stuff,
As you know in MOD files, all objects share the same vertex buffer, so I had 2 choices: export objects per vertex buffer basis in which case I get only one object per model and an export per object basis so I get all the objects separated. Each method has it's advantages and disadvantages.
Exporting to OBJ was the easiest way to get the job done: I wrote the whole vertex buffer then went through all the objects and wrote the indices. The 1st approach is exactly what I did with OBJ files, but in max script there isn't any face group separator so all the faces belong to one group and I get only one object per model.
Well the reason Capcom decided to use one vertex buffer for the model is obvious: performance. They also arranged the vert's to make use of the stripping, DirectX Sdk Docs say you should use D3DPT_TRIANGLESTRIP whenever possible and you should minimise the SetVertexBuffer() and SetIndexBuffer() calls to gain performance, 1 SetVertexBuffer() call per model draw is really the minimum. The vertex buffer can hold different vertex types but this doesn't matter as long as you know what vertex declaration to use at a given draw. It's the first time I see such a system so the 1st conclusion is: Capcom did a hell of a job to optimize their data.
The problem with this method is that it is virtually impossible to strip a mesh without duplicating some verts but in the case of MOD files, this is too exagerated: there are way too many duplicate verts: more than 30 identical successive verts can be seen in hex editor and there are not few of these duplications!!! This is seen in the hi res models and as an example I took Nero hi res head model that says there are 49613 verts and 12184 indices. This is relatively very high res for any model and this is only the head!!!
When I click RunScript under max for this head model, there is the "unknwon exception" error in max that simply means that there are way too many verts for a single object. This makes me wonder what is the maximum vertex count an object can have in maxscript. The 2nd conclusion is: Capcom models aren't that optimized!!!
The 2nd approach exports per object basis. Under max script, every mesh must have it's set of verts, meshes can't share some vertex buffer. The 1st problem with this is that on hi res head models, there are too many objects, capcom could've made the head in a sngle object; I wonder why they didn't!!
Another problem with this approach is that on export, verts are rearranged the index buffer way, these index buffers are far from being optimized and there are some duplicate indices here too!!! which leads to duplcate verts on the export!!!! But at least this method doesn't crash maxscript and all the models load OK! This is themoethod used in the converter posted here.

Here are some numbers:
with Mod2Obj I get this:
verts: 5305, faces: 5804, when the verts of this model are weld, I get this:
verts: 2917, faces: 5804, the fact that the face count didn't change shows that there are indeed many duplicate verts. Now with the new converter:
verts: 11935, faces: 11846 and with weld we have:
verts: 2928, faces: 5804
Even if we consider that there are some duplicate verts for a reason (eyelashes for example have 2 sides so usually the artists make the same mesh that points upwards point downwards, this of course leads to duplication), this doesn't exceed 10% of the initial vertex count!!! But here we have a serious duplication problem (from 49613 verts originally to 11935 verts in the worst case). My 3rd conclusion is: Capcom engineers must be drunk to come up with such a nonsense!!! no wonder Lostplanet doesn't perform well even on Core 2 Duo processors!!!

Well all this was just to say that depending on what will be done with the converter (reimport back to game, make renders, torture the poor guy, ...), this may or may not pose problems. Me, I'd like to make a proper Direct3D viewer out of this so this shouldn't annoy me, on the other hand, there is the normals bug that makes my nerves burn!!!!
OK enjoy this new converter and let me know if there are any bugs!

Hey Surveyor!
So you finally cracked the skinning, awesome!

Would you mind sharing the C++ code so that I can try to develop my COLLADA exporter? Using COLLADA should allow for all DDC application to edit the models (max/xsi/maya).
## Post #179
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-11-22T14:11:34+00:00
- Post Title: Re: [PC] Devil May Cry 4

Finally got around to writing some simple code to preview MOD files.  Not texturing or shaders yet, so hopefully you won't mind the over saturated default direct3d lighting, heh.  Things seems to load pretty well with no modifications between DMC4 and RE5, haven't tried LP yet.  Hopefully i'll have material, shaders, lighting, and skinning support up and running at some point in the near future.  i plan on rewriting this framework in a much more manageable way seeing as i have worked on a number of other formats i have not even coded up for viewing yet.
## Post #180
- Username: DMCdesigns
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 16, 2009 4:56 am
- Post datetime: 2009-11-22T17:18:39+00:00
- Post Title: Re: [PC] Devil May Cry 4

@revelation: Have you flipped Nero's model or your tool is loading it flipped?
## Post #181
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-11-22T17:27:00+00:00
- Post Title: Re: [PC] Devil May Cry 4

not to my knowledge. why would you think that?

EDIT:
Ah, hadn't even noticed.  strange though considering i don't flip the vertices anywhere, computing directly from the bounding box information as given.  i could easily remedy that i guess, but i'll have to take a closer look as to why that would be necessary, hmmm.

EDIT2:
Ah, ok, it appears the game uses the opposite culling flag value i use, which possibly indicates they use a different coordinate system than the default Left Handed coordinate system of direct3d that i am using.  If this is the case then it is more than likely using a flipped x- or z- axis with respect to how i have it.  For now i flipped the axis and culling flags accordingly to match those used in the game.  At some point i guess i will have to go through and handle this appropriately.  Thanks for catching that, heh.  i am guessing this will affect all the games based on this engine.
## Post #182
- Username: famesethu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 06, 2009 8:22 pm
- Post datetime: 2009-11-23T08:46:31+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hey great work surveyor,the Max script you made "Mod2Max.exe".....is awsome
I know this is just a prerelease.Will you please consider the removal of isolated vertices on your next version.
Thanks for the Great work......
## Post #183
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-11-23T16:30:14+00:00
- Post Title: Re: [PC] Devil May Cry 4

[quote="revelation"]
```
{
	// 0x00
	uint16    usId0 : 5;              // used as power of 2, tested against value indexed by usId1
	uint16    usId1 : 11;             // used as an index into a list of 32-bit (4-byte) values
	uint16    usMatId;                // material Id
	uint8     usFlag0x04[2];          // [0] - processing skipped if == 0
	                                  // [1] - tested against an unknown bitmask
	uint16    usFlag0x06;             //
	uint8     usFlag0x08[4];          // [2] - unknown value, &= 0xFE if (prev.endVertex0x0E + 1) != startVertex0x2A
	                                  // [2] - &= 0xBF, if 0 == tex4
	uint16    vertexCount0x0C;        // vertex count
	uint16    endVertex0x0E;          // end vertex - last vertex index used, compared to next object.startVertex0x2A
	// 0x10
	uint32    minVertex0x10;          // min vertex index
	uint32    streamOffset0_0x14;     // start offset for vertex stream 0 (in bytes)
	uint32    streamOffset1_0x18;     // start offset for vertex stream 1 (in bytes)
	uint32    startIndex0x1C;         // start index
	// 0x20
	uint32    indexCount0x20;         // index count - faces (indices - 2)
	uint32    uiBase0x24;             //
	uint8     unknown0x28[2];         // [0], [1] - indices into vertex declarations
	uint16    startVertex0x2A;        // start vertex, compared to previous object.endVertex0x0E + 1
	uint8     unknown0x2C[4];         // [0] - unknownData count, number of unknownData blocks assigned
	                                  // [1] - if 0x98 == file version, set to ((usFlag0x08[3] >> 1) & 0x0F)
	// 0x30
	uint32    unknown0x30 <format = hex>;    // seems to be unused, overwritten with unknownData start address
} objectData[fileHeader.objectCount];

```


ok some help : 

```
	                                  // [1] - tested against an unknown bitmask

```

[0] is always 1 as i have seen
[1] seems to be THE MESH LOD LEVEL !!!! 
lod0 = 255
lod1 = 512
lod3= 0xFc
so the mask could be 255 ?
tested on export and it seems clearly to be it, so surveyor please use this one to your mod2max exporter ...
## Post #184
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-11-23T16:43:55+00:00
- Post Title: Re: [PC] Devil May Cry 4

The mask value tested against is usually 1 when stepping through the code.  Looking at the differences between the versions of the head meshes for chris in RE5 this seems to be the only change between them.  So if the 0 bit of the mask is set it appears you can use this as a test for the base LOD level.  This is only from a quick glance after looking at the info you posted in the RE5 thread and relating it to the information i saw while debugging the benchmark executable for DMC4.  Seems to pan out though, but you may want to check some more model files just to be sure.

Hope it helps.
## Post #185
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-11-23T18:58:36+00:00
- Post Title: Re: [PC] Devil May Cry 4

already tested on some complete models and on individual body parts (excella head, eyes and hair etc...), just have noticed some mesh duplicates on jill's hands that are exactly the same hight res model stored 2 times in the mod file instead of a lod0 and a lod1 lodmesh so it export it twice but it is normal after all...
## Post #186
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-11-25T21:00:49+00:00
- Post Title: Re: [PC] Devil May Cry 4

> normal bug is not a bug, the normals you import are dynamic normals based on the skeleton pose, they are recalculated dynamicly by the engine ,differently than max do (they need to be rotated by the inverse matrix of the vertex associated joint and normalized after.
Then how do you explain the normals behaving correctly inside the edit mesh scope and vanishing outside, The skeleton pose doesn't have anything to do with this, even when I was experimenting without the skin modifier this problem was there!!

> the vertex duplication can also be explain easily, when welding vertices, the weld is based on vertex pos and not on uv mapping, so if you weld only this way , the rendering using vertex arrays and indices will completly fuck up the model mapping, the only way to fix it is to add degenerated faces or to duplicate vertices
I don't think so ... I made a quick check on the head model and guess what: the head model uses only 2 base textures so UV mapping isn't that different from an object to another. Look at the pic below, even with welding the mapping looks great!!

> even more so with multitexturing where it is not always possible for the textures mapped to use the same uv coordinates
In this case, as for the majority of the models of DMC4, the uv coords are the same for all the maps except for the lightmaps which are mainly found in stages.

> even on today's hardware there are not any cards i know of that have a recommended vertex batch size of anywhere near 49000+ vertices
Just try to imagine a head model with 49000+ verts, this would be way too detailed, which isn't the case of nero head, ninja gaiden 2 models for example are more detailed than those of dmc4 without even reaching this amount of verts (check out the ninja gaiden 2 thread).
I made a tool to quickly check vertex duplication and here's what I got:

original nero head model:
verts: 49613
indices: 12184

when eliminating all the duplicate verts, taking into consideration the position, texture coords, normals, binormals, tangents, bone indices and weights, I get this:
verts: 4511
faces: 5804

In terms of memory loss:
49613 verts x 32 bytes per vertex = 1587616 bytes on the video card
4511 verts x 32 = 144352 bytes only !!!! this is less than 10%

The question now is: why waste 1.5Mb on the video card for a model which is only worth 0.2Mb!!!
Another remark is that this difference isn't that big on body models, for example in nero body there is 12269 verts and after optimization I get 10798 verts which is 88% but still ....


> Will you please consider the removal of isolated vertices on your next version.
This is one of the flaws of this program, these vertices aren't considered degenerate by max and thus not deleted, max says a degenerate face is a face that has more than 2 identical indices, the converter exports the data per object basis and thus can't know if a face has some duplicate indices so it makes them unduplicate, I'll try to hack this in the future release.

Ok poly, continuing from the last messages, here's a little explanation on how to fix the bone indices:
MOD files have something called bone groups, each object in the model is influenced by one of these groups, the bone group count is at position 40 from file start.
As said earlier, after you read the bone transforms, you read a bone table, the size is 256 bytes no matter how many bone you have you always read 256.
Then after you read the bone groups, a bone group is something like this:

```
{
	unsigned int	uiBoneNum;	// bones in this group
	BYTE		*pBoneId;
};

// this part was already present in the code, I put it here to help you locate yourself in the human.cpp
// allocate memory for the bone tranforms and read them
m_pBoneTransform = new cBoneTransform[m_usBoneNum];
fread(m_pBoneTransform, sizeof(cBoneTransform), m_usBoneNum, pFile);

// read the bone table
fread(m_pBoneTable, 256, 1, pFile);

// read the bone groups
m_pBoneGroup = new cBoneGroup[m_uiBoneGroupNum];
for(unsigned int a = 0; a < m_uiBoneGroupNum; a++)
{
	fread(&m_pBoneGroup[a].uiBoneNum, 4, 1, pFile);
	m_pBoneGroup[a].pBoneId = new BYTE[m_pBoneGroup[a].uiBoneNum];
	fread(m_pBoneGroup[a].pBoneId, 1, m_pBoneGroup[a].uiBoneNum, pFile);

	// check if the bone count is greater than 32 in which case padding must be applied
	// this is a stupid hack, must pad correctly to x32 later
	if(m_pBoneGroup[a].uiBoneNum > 32)
	{
		// put a marker here
		printf("Hey that can't be !!!\n");
		return false;
	}
	fseek(pFile, 32 - m_pBoneGroup[a].uiBoneNum, SEEK_CUR);
}
```


For each object there is a bone group id, this id byte is located at position 45 for each cObject struct.

Now all is left is this:
for every object
  for every vertex in this object
    do this 4 times since we have 4 bones per vertex
      BYTE cId = m_pVertex[the current vertex].bone[0 .. 3];
        BYTE cTrueId = m_pBoneGroup[bone group to use].pBoneId[cId]

Notice that the bone table isn't used here!!! I'm too lazy to tell why so I'll leave this to you 
I hope this helps you out 
[Waste.JPG](https://xentaxbackup.github.io/file/2561_Waste.JPG)
## Post #187
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-11-26T03:21:26+00:00
- Post Title: Re: [PC] Devil May Cry 4

Thanks for posting the info, reminded me i never changed this information in the template files i posted.  This is the matrix palette information used by the hardware skinning code in the vertex shaders.  i also found that the cChild index in the joint information in the bone's mirror index, if it has one.  Allows for appropriate handling of transforms for animations that can be flipped to work on either side and the like, or at least that is how it would normally be used, haven't tracked it fully through the code yet.  i also hadn't gotten to using the transform data following the object definitions in accordance with this information.  Do you make use of this at all?
## Post #188
- Username: DMCdesigns
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 16, 2009 4:56 am
- Post datetime: 2009-11-26T18:40:17+00:00
- Post Title: Re: [PC] Devil May Cry 4

Using Surveyor's old DMC4Model I've ripped this and I created a few bones to make the render pose. The proportions aren't the best because of the "pancake" effect. 
Quick render using mental ray and maya 2009:
[](http://img687.imageshack.us/img687/1051/81747476.jpg)
## Post #189
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-11-27T18:39:36+00:00
- Post Title: Re: [PC] Devil May Cry 4

When I import a model instead of the bones creates are the points. How can I fix this?
## Post #190
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-12-02T16:06:06+00:00
- Post Title: Re: [PC] Devil May Cry 4

i have finally extracted the arc files with dmc4 extract but the file extensions are neither mod nor tex. 
example: 
d-mov049-xbox.wmv.0&²u 

im thinking that its messed up or somthing. any one no wut to do. cuz mainly i just want to extract lady and trish. can someone plz post the mod file for lady and trish with textures. i could clean the models in max myself. Im only asking becuz im frustrated from not getting any of the stuff working at all.
## Post #191
- Username: diablojin
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Nov 30, 2009 4:24 am
- Post datetime: 2009-12-04T00:43:03+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hey Surveyor got a question with regards to dmc4extract...

Im currently trying to get it working, I use windows 7 if any help and avg flags it up as a trojan and if I ignore this windows will not open it? 

Any help will be appreciated

Cheers
## Post #192
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-12-07T20:24:36+00:00
- Post Title: Re: [PC] Devil May Cry 4

my bad I exported the files instead of extracting it in RPGviewer. but now i have another problem when i use mod2max. there are no proper texture coordinates for trish and lady.
## Post #193
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-12-09T12:14:59+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from onionhead
>
> my bad I exported the files instead of extracting it in RPGviewer
I see you succeded to extract/view the models by now so there's no need to answer but let me say this:
The tools have been here for a while so if people already used them then there's no reason these tools won't work for you (unless you live on some other planet), just read carefully the HOWTOs, you must be missing something.

> Reply from diablojin
>
> Im currently trying to get it working, I use windows 7 if any help and avg flags it up as a trojan and if I ignore this windows will not open it?
You know, I'm no fan of Microsoft products, they always suck in some way, even xbox 360 got the RROD!! As for the AVG, just disable proactive protection while you work with the converter, this perfectly works under XP. And by the way, you have some very nice modelling skills, I saw your works 

Okay here's the updated version of the Mod2Max converter, this time texture coords work fine and I implemented the LOD flags so it's easier now to select the different LODs (useful in RE5 models). The generated scripts are larger in size and thus take longer to execute so be more patient.

Recently, I wanted to mess with DMC4 models and make "very" high res versions out of them (for some renders), Mesh Smouth under max does the job but I'll need to play with the edges a little, weld some parts, ...
The problem is that I don't want to loose the (PRECIOUS) skinning data (which would be the case since attaching meshes alters the skinning info) so I thought of splitting the generated scripts into 2 parts, the 1st exports the mesh data and when I'm done with mesh modifications the 2nd script comes to set the bones and skinning. If somebody has an idea about this then I'd like to hear it.
[Mod2Max.zip](https://xentaxbackup.github.io/file/2607_Mod2Max.zip)
## Post #194
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-12-12T07:22:31+00:00
- Post Title: Re: [PC] Devil May Cry 4

How to use your script to get the bones? I only get the points!
## Post #195
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-12-12T08:48:29+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Tosyk
>
> How to use your script to get the bones? I only get the points!
The converter creates points instead of bones because there's no orientation info for the bones, only position.
This is most frustrating in bones that don't have children, in which case there's no way to guess the bone's orientation so I preffered to make them all points.
## Post #196
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-12-12T15:43:20+00:00
- Post Title: Re: [PC] Devil May Cry 4

Dear Surveyor could you make the creation of the bones, rather than points, closing your eyes to the wrong orientation. Certainly maintaining hierarchy. I have a couple of ideas that may help. But while the role of bones perform point I can not verify.
## Post #197
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-12-14T18:09:15+00:00
- Post Title: Re: [PC] Devil May Cry 4

how do i convert those pink normal maps to the tangent space normal maps with rgb channels. cuz rite now i only see single coloured normal maps. I m trying to use it in 3dsmax.
## Post #198
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2009-12-14T21:17:05+00:00
- Post Title: Re: [PC] Devil May Cry 4

... lots of people making requests. I'm sorry, Surveyor, but I have some too.
Could you add the following functions to your tools, or make new tools with them? Pretty please? It could make dmc4 modding a hell of a lot easier. Here's what I'm asking:

Dmc4tex - DDS-> tex conversion
Dmc4pla - Compiling pla files.
Dmc4patch 2 - Function to tell the program exactly which files to invalidate so they will load outside the .arcs. Ex: Invalidate only wp005.mod in all .arc files.

I know you're probably busy, but it would certainly be a big help for me and the boys, so I thought I'd ask.
## Post #199
- Username: godinhochina
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 22, 2009 6:00 am
- Post datetime: 2009-12-14T22:27:03+00:00
- Post Title: Re: [PC] Devil May Cry 4

I'm translating the game to PT-BR language but I don't found the .msg file of this image:
[](http://img264.imageshack.us/i/devilmaycry4dx102009121.jpg/)

Someone knew where this .msg file are?
Thanks anyway
## Post #200
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2009-12-15T00:18:02+00:00
- Post Title: Re: [PC] Devil May Cry 4

Maybe I can help. Check your inbox.
## Post #201
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2009-12-16T16:14:19+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> The problem is that I don't want to loose the (PRECIOUS) skinning data (which would be the case since attaching meshes alters the skinning info)
As far as I understand it is impossible to fix the messed up faces in models at the moment without losing the skinning data?

What does a modeler do when he wants to alter his rigged model (add something or modify the geometry) in some way? Does he start the skinning process all over again? There must be a way to preserve the skinning data. Any experienced 3dsmax users around here?
## Post #202
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-12-17T16:28:34+00:00
- Post Title: Re: [PC] Devil May Cry 4

firsak: maybe you can try to add a edit poly modifier onto the stack. and fix the geo. Ive never tried it on a skinned mesh but try and see if it works.

edit: I tried adding a edit mesh modifier onto the skin mesh and the skin data is intact. This is for 3dsmax only
## Post #203
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-12-19T08:53:48+00:00
- Post Title: Re: [PC] Devil May Cry 4

For three days I have conducted research in order to receive an automated process to convert models from resident evil 5 (devil may cry 4 and similar to it) in the normal format for 3d max preserving skinning data and automatic creation of biped-skeleton. Studies successfully completed, and that's what happened: 

[](http://s12.radikal.ru/i185/0912/90/c831fcbe56be.png) [](http://s57.radikal.ru/i155/0912/95/0275124073c7.jpg)

However, I want to note that the process that I developed, it is not the result of scripting or voodoo magic, I just took a ready-made tools, mixed them with logic and received a rather unusual conversion scheme, the result of which I was quite satisfied. 

Method: 

1. unpack the game and select the file to convert 
2. convert mod-file tool from the Surveyor to ms-script
3. import model in 3d max (I use 2008 64x) 

----- Now we need to convert the object-point in the bone, for this I use the converter in the smd 

4. export the model in smd, then import the smd-file back to 3d max - as you can see, now we've got the bones, though a bit scattered 

on this, in fact, you can finish. 

I would like to listen to the masters, as it can possibly optimize my method? 

Thank you.
## Post #204
- Username: gics
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Dec 19, 2009 4:12 pm
- Post datetime: 2009-12-19T09:09:03+00:00
- Post Title: Re: [PC] Devil May Cry 4

I love Mod2Max by Surveyor, great work! But when it ready for texture?
## Post #205
- Username: Nexus Elite ns
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2009 1:11 am
- Post datetime: 2009-12-20T18:38:23+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Tosyk
>
> For three days I have conducted research in order to receive an automated process to convert models from resident evil 5 (devil may cry 4 and similar to it) in the normal format for 3d max preserving skinning data and automatic creation of biped-skeleton. Studies successfully completed, and that's what happened: 



However, I want to note that the process that I developed, it is not the result of scripting or voodoo magic, I just took a ready-made tools, mixed them with logic and received a rather unusual conversion scheme, the result of which I was quite satisfied. 

Method: 

1. unpack the game and select the file to convert 
2. convert mod-file tool from the Surveyor to ms-script
3. import model in 3d max (I use 2008 64x) 

----- Now we need to convert the object-point in the bone, for this I use the converter in the smd 

4. export the model in smd, then import the smd-file back to 3d max - as you can see, now we've got the bones, though a bit scattered 

on this, in fact, you can finish. 

I would like to listen to the masters, as it can possibly optimize my method? 

Thank you.
You know i've also tryed this before, when his converter came out, but some reason the export on smd or any other format come out improper import.
## Post #206
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-12-22T17:14:30+00:00
- Post Title: Re: [PC] Devil May Cry 4

so no one knows why the normal maps looks different then usual normal maps. where theres 3 channels. look i just wanna know how to convert it to the usual tangent space normal map ppl use for games. Im looking to use it in 3dmax for lady and trish.
## Post #207
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-12-22T17:45:56+00:00
- Post Title: Re: [PC] Devil May Cry 4

2Nexus Elite ns:

After export smd it needs a little fix in a text editor.

2onionhead:

Do you mean pinkcolor of normal maps?
## Post #208
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-12-22T22:41:00+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Tosyk
>
> 2Nexus Elite ns:

After export smd it needs a little fix in a text editor.

2onionhead:

Do you mean pinkcolor of normal maps?

yes how do u use pink color normal maps
## Post #209
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-12-23T10:40:52+00:00
- Post Title: Re: [PC] Devil May Cry 4

> how do i convert those pink normal maps to the tangent space normal maps with rgb channels. cuz rite now i only see single coloured normal maps. I m trying to use it in 3dsmax.
I use them as they are, I just pass the correct bump map texture and they work fine, you can also set the max driver to use Direct3D and use custom shaders to get a close look to the one used in the game.

> Could you add the following functions to your tools
Tex2dds: why not, sounds simple enough, I'll try that later.
Dmc4pla: no, much is still unknown about the PLA files, mostly the parent/children relationship, more testing will tell.
Dmc4patch: this too sounds easy, I'll try to include this.

> I know you're probably busy, but it would certainly be a big help for me and the boys
Interresting, where are you boys posting, I'd like to see what you're coocking!!

> I love Mod2Max by Surveyor, great work! But when it ready for texture?
What do you mean by texture? texture coords or textures in the viewport?

> maybe you can try to add a edit poly modifier onto the stack. and fix the geo
This wouldn't be sufficent, sometimes there's a need to attach meshes together (in the case of the head models which are insanely split into too many parts) and here skin data is surely lost!

> For three days I have conducted research in order to receive an automated process to convert models from resident evil 5 (devil may cry 4 and similar to it) in the normal format for 3d max preserving skinning data and automatic creation of biped-skeleton. Studies successfully completed
So you succeeded to get the biped bones out from points then there's no need for me to mess with the points, how am I glad!!
## Post #210
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-12-23T11:52:57+00:00
- Post Title: Re: [PC] Devil May Cry 4

> So you succeeded to get the biped bones out from points then there's no need for me to mess with the points, how am I glad!!

And yet, Surveyor, thanks for your work on mod2max! There is still a game with a similar structure - Dead rising, check it as there will be time, OK?
## Post #211
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2009-12-23T14:41:46+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> 
Tex2dds: why not, sounds simple enough, I'll try that later.
Dmc4patch: this too sounds easy, I'll try to include this.
Dude! Thanks! I'll send you some *Happy thoughts*.

> Dmc4pla: no, much is still unknown about the PLA files, mostly the parent/children relationship, more testing will tell.
My main interest in that are the emset***.pla files. They contain the enemy spawn data for each level. Do you have any info that might help interpret them? I tried to compare one with the decompiled version, but no luck.

> Interresting, where are you boys posting, I'd like to see what you're coocking!!
Double taunt: [-LINK-](http://z6.invisionfree.com/DoubleTaunt/index.php)
Anyone registering gets free cookies.

And, depending on who you ask, Hells Atelier too:[-LINK-](http://z9.invisionfree.com/Hells_Atelier/index.php)
## Post #212
- Username: Nexus Elite ns
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2009 1:11 am
- Post datetime: 2009-12-23T20:24:32+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hmm just curious, has anyone checked if lp2 demo one from 360 the same as well?
## Post #213
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-12-23T20:44:47+00:00
- Post Title: Re: [PC] Devil May Cry 4

lost planet 2 is using a newer engine so its not compatible.
## Post #214
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2009-12-24T10:06:17+00:00
- Post Title: Re: [PC] Devil May Cry 4

*Shameless plug*
[Dreadnaught](http://z6.invisionfree.com/DoubleTaunt/index.php?showtopic=70&st=0&)

Figured some people here might be interested.
## Post #215
- Username: gics
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Dec 19, 2009 4:12 pm
- Post datetime: 2009-12-24T15:10:49+00:00
- Post Title: Re: [PC] Devil May Cry 4

> What do you mean by texture? texture coords or textures in the viewport?
I mean textures in the viewport / material
## Post #216
- Username: gics
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Dec 19, 2009 4:12 pm
- Post datetime: 2009-12-24T15:41:14+00:00
- Post Title: Re: [PC] Devil May Cry 4

Does anyone know how to make effect like in DMC 4 / Street Fighter 4? And what about animation/movement in that game, does anyone know how to convert them so we can use in 3D Application?
Sorry for the stupid question
## Post #217
- Username: diablojin
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Nov 30, 2009 4:24 am
- Post datetime: 2009-12-27T13:56:35+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hey Surveyor,

Sorry not replied in a while, currently do not have an internet connection.

With regards to editing your mesh/sorting out the normals etc..

What you can do is add an edit poly above the edit mesh (below the skinning modifier) then collapse the stack down, from the edit poly NOT THE SKIN modifer. 

From here you are free to add and remove polys, weld certain areas of the mesh that are needed as well as removing the triangulation. This is a painstaking process tho and can take agggges. Once you have done with editing the mesh you can then add a turbo smooth above the Edit poly, i recommend ticking isoline display to save on mem depending on your gpu.

All of the above WILL keep within the skinning of the model and you should be fine to pose and do as you please with it. 

Any other question with max then just fire them over to me, be glad to help!

Got a question for you as well 

I havent tried your latest mod2max file yet but does it retain the texture coordinates of the models yet? This is the only thing really holding me back as its such a pain in the arse to remap everything.

To the guy who used the smd exported and importer... is it this one you ued to obtain the biped info?

[http://www.wunderboy.org/3dapps.php#max_smd](http://www.wunderboy.org/3dapps.php#max_smd)

Cheers guys and merryXmas and happy new year!
## Post #218
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-12-27T14:29:21+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from diablojin
>
> To the guy who used the smd exported and importer... is it this one you ued to obtain the biped info?

http://www.wunderboy.org/3dapps.php#max_smd

If you mean me, then yes, I use these plug-ins to convert.
## Post #219
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2009-12-27T15:34:37+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from diablojin
>
> 
All of the above WILL keep within the skinning of the model and you should be fine to pose and do as you please with it.

It will not help attaching meshes to each other - the skinning data will be lost. It will only help editing the existing meshes. And this technique is not a big deal, any average 3ds max user knows how to work with modifiers/stacks.

> Reply from diablojin
>
> I havent tried your latest mod2max file yet but does it retain the texture coordinates of the models yet? This is the only thing really holding me back as its such a pain in the arse to remap everything.
Texture coordinates are there.
## Post #220
- Username: diablojin
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Nov 30, 2009 4:24 am
- Post datetime: 2009-12-27T16:00:46+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from firsak
>
> diablojin wrote:
All of the above WILL keep within the skinning of the model and you should be fine to pose and do as you please with it. 

It will not help attaching meshes to each other - the skinning data will be lost. It will only help editing the existing meshes. And this technique is not a big deal, any average 3ds max user knows how to work with modifiers/stacks.

It depends which of the models you are using, for example Dante and Nero's heads are fine to use and all one mesh (apart from the different morph targets), if your wanting to use lady/sanctus/credo/kyria (not sure about Trish) then it will pose a problem as yes their heads are separated. I havent found a way around them as of yet, but in general the skinning of the head isn't really what I need. I will keep on playing about until I find a work around, thats if any of guys find another way to export the data.

Saying that though, you could always just weld the vertices together on the faces instead of attaching the mesh, I will try this for you when i get home and post results when I can as still dont have a nternet connection.

What part of the skinning are you wishing to use by the way?
## Post #221
- Username: diablojin
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Nov 30, 2009 4:24 am
- Post datetime: 2009-12-27T21:18:54+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hey guys!
Just had a quick go with your new max2mod converter surveyor! Seems to be ALLOT cleaner than before! 

Although.....

I'm still not getting any texture coordinates? Am I doing anything wrong?

I import the model eg dantes body into max

add an unwrap uvw to check the postioning of the coordinates in relation to the corresponding map and they are no where near?

Any 1 can help would be great
## Post #222
- Username: diablojin
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Nov 30, 2009 4:24 am
- Post datetime: 2009-12-27T22:15:45+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from diablojin
>
> firsak wrote:diablojin wrote:
All of the above WILL keep within the skinning of the model and you should be fine to pose and do as you please with it. 

It will not help attaching meshes to each other - the skinning data will be lost. It will only help editing the existing meshes. And this technique is not a big deal, any average 3ds max user knows how to work with modifiers/stacks.



Just had a thought on how we may be able sort the face problem!

I haven't tried it yet but hoping someone can until I get back to my pc!
What if you import the head into max and then export with the smd tools, surely this will export the mesh out in one go with all bone info and then when reimported that bone info ahud be intact going by what was said earlier
## Post #223
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-12-28T21:03:01+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Dude! Thanks! I'll send you some *Happy thoughts*.
Send me money instead  and btw, you have some nice stuff over there, I especialy liked the "Dante has too many swords!, An updated re-release" thing!

> I mean textures in the viewport / material
This will require some additional maxscript knowledge, besides when you have a complex scene this option might screw your computer so I'll leave this to another day.

> And what about animation/movement in that game, does anyone know how to convert them so we can use in 3D Application?
It's been a while now since I started working on animation files without much success, now I'm waiting for some support from Revelation and hopefully this'll lead to something.

> I havent tried your latest mod2max file yet
Well boy you should, the texture coords work fine on this release and it's about time you guys show us something interresting with all those extracted models and textures!

About the skin data,
I tried my approach, the 2 parts scripts that generate the mesh data and the skin data, after doing some modifications on the mesh I got a very clean mesh that reacts beautifully to the meshSmouth modifier (look at the pic below) the difference is very clear between the modified and unmodified hand.
The problem is the 2nd part, the script takes ages to execute, I mean for nero model (with 8000 verts approx) it took my celeron 2Ghz more than 2 hours with 100% cpu usage to complete (needless to say that the script is still under dev and test and I will have to test it more than once !!!!) After inspection and optimization, I figured out that the "ReplaceVertexWeights" (and alternatively "SetVertexWeights") command in maxscript is the one responsible for all this: without it, the whole script runs in 10seconds!!!
Unfortunately this is the only command capable of setting the weights, and I doubt recent processors will perform significantly faster but I'll try that anyway.
And just a reminder, the idea behind all this is that all the meshes in a model share the same vertex buffer, we can do whatever we want with the body parts (weld/attach/clean/...but not change vertex positions) and then correctly apply bone influences on the verts by going through the vertex buffer and checking for the right vertex.
[Smouth.JPG](https://xentaxbackup.github.io/file/2668_Smouth.JPG)
## Post #224
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-12-28T21:06:28+00:00
- Post Title: Re: [PC] Devil May Cry 4

Okay now here's as promised the dds2tex converter, this tool was made "à la va vite" so there's a limited set of functions inside:
- mipmaps: only 1, not more
- textures: normal textures only, by normal I mean not volume or cubemap just regular.
- formats: DXT1, DXT3, DXT5, ARGB32, I think this would be sufficient for you.
The testing was also very quick, I just applied the original tex2dds on a set of textures then applied the newly created dds2tex on the generated dds textures from the last operation then again I applied the tex2dds on those TEX files and the generated DDS files looked OK! It just took me about 3 minutes!! of course this doesn't mean the program is bug free and that's up to you to report.
To make the converter even easier, I made it process all the DDS files present in it's working directory and generate the corresponding TEX files with the exact same filename.

ArcPatchOnDemand
Another tool that'll let you (as requested) invalidate only some of the files in the ARC archives. It works this way: type in the filename AND extension that you want to invalidate (ex: pl000.mod) and the program will go through the present arc files in the current directory and subdirectories and patch them as the original ARC patcher does.
The supported file formats on this patcher are .bfx (shaders), .tex, .lmt, .mod, .msg (case sensitive, this is very important). You'll notice that these fileformats are all present in the 3 Capcom games (re5/dmc4/lp) so the patcher will work on all those games.
This is another -in-1-hour-pose-not-thinked-just-coded- program that I discovered later that the combination of filename+extension may lead to unpredictable results, look at these examples:
stage.tex will invalidate all the textures present in the stage directory AND its subdirectories because the patcher uses the strstr() function that detects the presence of the base name in the filename and "stage/s200/data/bin/whatever.tex" passes the test.
In the same way, model.mod will invalidate all the models!!!! the risk is lessened when the name is unique, for example: hdd-inst03_NOMIP_BM_HQ.tex will only invalidate this file!!
One quick solution is to use more detailed filenames, ex: model\demo\pl000\pl000_01.mod, this'll get the job done as expected and as a conclusion: this tool gives more or less control depending on how you use it, think of using "model\demo\pl000.mod" as the filter: there's no pl000.mod in the model\demo directory but the combination model\demo\pl000+mod will invalidate all the models inside the "model\demo\pl000" directory and we have: pl000.mod, pl000_01.mod, pl000_02.mod, pl000_03.mod, pl000_04.mod and pl000_05.mod.
This tool is more complicated than I thought, and since it's ready then I'll let you have it and test it at you own risk!
[dds2tex+ArcPatchOnDemand.zip](https://xentaxbackup.github.io/file/2669_dds2tex+ArcPatchOnDemand.zip)
## Post #225
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2009-12-28T22:34:12+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> Send me money instead  and btw, you have some nice stuff over there, I especialy liked the "Dante has too many swords!, An updated re-release" thing!
What's that, you want more *happy thoughts*? Sure! Good thing you didn't ask for money.
And glad you liked that pack, there's more on the way.

> -Okay now here's as promised the dds2tex converter, this tool was made "à la va vite" so there's a limited set of functions inside:
>
> -ArcPatchOnDemand
>
> Another tool that'll let you (as requested) invalidate only some of the files in the ARC archives.
Someone wrote "AWESOME!" all over my face. Must've been the cat.

> -of course this doesn't mean the program is bug free and that's up to you to report.
>
> -This tool is more complicated than I thought, and since it's ready then I'll let you have it and test it at you own risk!
Oh, they're gonna be tested alright. And then again. And again, and again...


One other thing. I'm trying to make some RE5 models (The simpler ones, meele weapons, pistols...) work in DMC4. Except I don't actually have RE5, so I don't know a lot about them. Do you think it can work, or have any information that can help getting them to work? Maybe by changing the headers or something? Right now, they get pretty much ignored by the game.

Anyway. Thanks for all that, man. I'm off to do some crazy stuff.
## Post #226
- Username: diablojin
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Nov 30, 2009 4:24 am
- Post datetime: 2009-12-28T22:37:40+00:00
- Post Title: Re: [PC] Devil May Cry 4

Yeah man will show ya what I'm cooking up once I have sorted this model out! Still trying to figure out why the texture coordinates arnt working for me?
You have any thoughts why this may be!?
My process for import is this

either run the maxacript through the maxacript drop down, navigate to file and execute. Or just drag and drop the ms file into the viewport.
Either method imports the model fine but when I add the uvw unwrap the coordinates are way off!
## Post #227
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2009-12-29T12:46:53+00:00
- Post Title: Re: [PC] Devil May Cry 4

The contents of this post was deleted because of possible forum rules violation.
## Post #228
- Username: diablojin
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Nov 30, 2009 4:24 am
- Post datetime: 2009-12-29T13:42:02+00:00
- Post Title: Re: [PC] Devil May Cry 4

The contents of this post was deleted because of possible forum rules violation.
## Post #229
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2009-12-29T18:48:22+00:00
- Post Title: Re: [PC] Devil May Cry 4

2Surveyor
Another request. Can you fix mod2max, so that the names of the meshes do NOT look like this: "lod255_4_model\demo\pl006\pl006_hair_BM", but simply "lod255_4_model" or "mesh01". Having "\" in the names may be a real pain in the butt. One has to rename all the meshes to be able to export it into some formats. Like the mentioned SMD, for instance.
## Post #230
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-12-29T19:03:01+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from firsak
>
> 2Surveyor
Another request. Can you fix mod2max, so that the names of the meshes do NOT look like this: "lod255_4_model\demo\pl006\pl006_hair_BM", but simply "lod255_4_model" or "mesh01". Having "\" in the names may be a real pain in the butt. One has to rename all the meshes to be able to export it into some formats. Like the mentioned SMD, for instance.

I have no problems with / when exporting to smd.
## Post #231
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2009-12-29T19:40:47+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Tosyk
>
> I have no problems with / when exporting to smd.
But there is a problem when importing it. You yourself said the following: "After export smd it needs a little fix in a text editor."
## Post #232
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-12-29T20:00:34+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from firsak
>
> Tosyk wrote:I have no problems with / when exporting to smd.
But there is a problem when importing it. You yourself said the following: "After export smd it needs a little fix in a text editor."

Yes it is! You're right, if the Surveyor will fix the problem it would be great. But I absolutely do not need to strain to remove a few extra lines.

Off-top: strange to speak with someone from the same country that I am in a foreign language, strange and wild) forum rules?))

Add:

I remember someone asking how to combine parts of the body models of characters from Devil May Cry 4 separated into different files. Answer: Just like everything else - through the export / import smd. Thus, the model is unknown to me aunt. A compound, ie composed of body, head and hair. All parts of the body attachment to a biped-skeleton.

[](http://s58.radikal.ru/i160/0912/98/c74a8404b190.jpg) [](http://s06.radikal.ru/i179/0912/b0/8326d5927a48.png)

p.s. Happy New Year
## Post #233
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2009-12-31T12:15:37+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hey, Surveyor?
I've been testing your new tools. Here's some feedback.

dds2tex: It works fine, but with a few oddities. 1: For a given texture, the final filesize is smaller than the original. Which doesn't seem to affect anything. Although it might have something to do with 2: Judging from what you said (Only normal textures) and the results I get, I'm guessing the tool can't handle alpha channels. Is that right? Because many normal textures use them, E.G. the DT's body, so it's a problem.

Arc patch on demand: I can't seem to get it to work properly. Maybe I'm screwing up somewhere, but it doesn't invalidate the files, although it does make some unknown change. Could you test it? And one other thing. Can you make it command prompt-friendly? It would add a new level of usefullness. I would be able to use several filters on several .arcs on different folders via  a single batch file.

BTW, I don't know when you'll read this, but I hope you have a kickass year-end and an epic new year! My year-end isn't going so well, I only got a headache for christmas and there were 4 general sound failures at the movies when I was watching Avatar. Boy was I pissed. Er, anyway. All the best for you.
## Post #234
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-01-07T09:36:30+00:00
- Post Title: Re: [PC] Devil May Cry 4

> What's that, you want more *happy thoughts*? Sure! Good thing you didn't ask for money.

> What's your Paypal?
Don't worry, where I live Paypal doesn't exist anyway so the tools are free of charge!

> Do you think it can work, or have any information that can help getting them to work? Maybe by changing the headers or something? Right now, they get pretty much ignored by the game.
Only testing will tell, as for the headers, the 3 games share the same model file format except for the model version.

> Still trying to figure out why the texture coordinates arnt working for me? You have any thoughts why this may be!?
My only guess is that you're not using the correct mod2max converter, check the latest one, I use Max8 so this shouldn't be the problem since you're most probably using a later version.

> Do those extra edges that are removed have special flags? Or did you actually develop some crazy algorithm that can detriangulate meshes??? If so, you're a genius.
No, I did this by hand, this is my new secret hobby, I found it relaxing to play with the edges after hours of programming especially when I'm stuck, it helps calming my nerves.

> I'd rather leave it to PC to handle in the background while I do something else at the same time, instead of wasting a day to do it manually.
You're right, doing this by hand is out of the question, I just got another idea on how to speed things up!

> Another request. Can you fix mod2max, so that the names of the meshes do NOT look like this: "lod255_4_model\demo\pl006\pl006_hair_BM", but simply "lod255_4_model" or "mesh01". Having "\" in the names may be a real pain in the butt. One has to rename all the meshes to be able to export it into some formats. Like the mentioned SMD, for instance.
You may be forgetting something but when we will figure out the animation format, the original skeleton pose will be needed in order to map the animations and here all your SMD stuff will be useless.

> 1: For a given texture, the final filesize is smaller than the original. Which doesn't seem to affect anything. Although it might have something to do withThis is because the generated TEX image contains no mipmaps, only the base image, the original may contain more than one mipmap and thus is bigger than the generated one. Usually HUD textures don't need to have mipmaps but other textures (minly those used for models, stages, ...) do (for performance/quality). This'll be fixed in the future.

> I'm guessing the tool can't handle alpha channels. Is that right?
No, normal textures are 2d textures and this tool supports all 2d textures, give it a try!!

> Arc patch on demand: I can't seem to get it to work properly. Maybe I'm screwing up somewhere, but it doesn't invalidate the files, although it does make some unknown change. Could you test it?
Well with my old celeron 2Ghz, 768Mb ram, fx5200 the game simply can't run, I'll try to find a stronger PC and test all this stuff.

> BTW, I don't know when you'll read this, but I hope you have a kickass year-end and an epic new year! My year-end isn't going so well,
The year-end for me is just another day in my life, it will not tell me in any way how my last year was or how my new year will be.

> 4 general sound failures at the movies when I was watching Avatar. Boy was I pissed.
And I spent the 31 dec night working on a philipino ship and the crew weren't friendly at all, no party, no juice, nothing, you see you're end-year wasn't that terrible.
## Post #235
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2010-01-07T10:54:11+00:00
- Post Title: Re: [PC] Devil May Cry 4

> The year-end for me is just another day in my life, it will not tell me in any way how my last year was or how my new year will be.
Which doesn't mean it can't be a good day, right?

> And I spent the 31 dec night working on a philipino ship and the crew weren't friendly at all, no party, no juice, nothing, you see you're end-year wasn't that terrible.
Yeah, at least I had some grape juice. Hmmm, grape juice.

> No, normal textures are 2d textures and this tool supports all 2d textures, give it a try!!
Weird. I remember getting screwed up alpha channels. Let's try that again. -Later- And it seems you're right. I guess some random experiment I was doing at the time interfered with my results. Or not. I'll do more testing.

> Only testing will tell, as for the headers, the 3 games share the same model file format except for the model version.

> This is because the generated TEX image contains no mipmaps, only the base image, the original may contain more than one mipmap and thus is bigger than the generated one. Usually HUD textures don't need to have mipmaps but other textures (minly those used for models, stages, ...) do (for performance/quality). This'll be fixed in the future.

> Well with my old celeron 2Ghz, 768Mb ram, fx5200 the game simply can't run, I'll try to find a stronger PC and test all this stuff.
Triple thanks.

> Don't worry, where I live Paypal doesn't exist anyway so the tools are free of charge!
*HAPPY THOUGHTS*!!!!!
## Post #236
- Username: Dtmech
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 14, 2009 8:32 pm
- Post datetime: 2010-01-08T10:25:39+00:00
- Post Title: Re: [PC] Devil May Cry 4

For some reason Mod2Max won't convert .mod files for me, i drag drop , press enter and it just closes.
## Post #237
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-01-08T20:39:21+00:00
- Post Title: Re: [PC] Devil May Cry 4

> For some reason Mod2Max won't convert .mod files for me, i drag drop , press enter and it just closes.

You need to run the program in the same file's folder, and the type the mod file complete name and then press enter, and the program will do all the process.
## Post #238
- Username: Dtmech
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 14, 2009 8:32 pm
- Post datetime: 2010-01-08T21:01:35+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Darko
>
> For some reason Mod2Max won't convert .mod files for me, i drag drop , press enter and it just closes.


You need to run the program in the same file's folder, and the type the mod file complete name and then press enter, and the program will do all the process.

Yes i did that , the mod2max is in the same folder , i draged droped and it shows the full location and name of the model. But when i hit enter , it just closes without giving me my max file.

And i can't convert the texture files to dds aswell.
## Post #239
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-01-09T00:36:52+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Dtmech
>
> Darko wrote:For some reason Mod2Max won't convert .mod files for me, i drag drop , press enter and it just closes.


You need to run the program in the same file's folder, and the type the mod file complete name and then press enter, and the program will do all the process.

Yes i did that , the mod2max is in the same folder , i draged droped and it shows the full location and name of the model. But when i hit enter , it just closes without giving me my max file.

And i can't convert the texture files to dds aswell.

Dude, you have a problem on the problem) does not take to heart) Mod2max does not create a max file, the program creates a ms-file is a script that can be opened by simply dragging and throwing it into the open window of 3d max.
## Post #240
- Username: Dtmech
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 14, 2009 8:32 pm
- Post datetime: 2010-01-09T10:03:16+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Tosyk
>
> Dtmech wrote:You need to run the program in the same file's folder, and the type the mod file complete name and then press enter, and the program will do all the process.

Yes i did that , the mod2max is in the same folder , i draged droped and it shows the full location and name of the model. But when i hit enter , it just closes without giving me my max file.

And i can't convert the texture files to dds aswell.

Dude, you have a problem on the problem) does not take to heart) Mod2max does not create a max file, the program creates a ms-file is a script that can be opened by simply dragging and throwing it into the open window of 3d max.[/quote]


Yes i know i know , i already did it with Lost planet and Re5 , but DMC4 doesn't give me the .ms file , it just closes and that's it i don't get anything.
## Post #241
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-01-09T17:53:31+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Dtmech
>
> Yes i know i know , i already did it with Lost planet and Re5 , but DMC4 doesn't give me the .ms file , it just closes and that's it i don't get anything.
Try to do it with other files, perhaps unpacking archives was not entirely successful. See it all Do you have files with extensions. When I unpacked my archives, I have all the files have no extension and I now have to rename every file manually. Try just mod2max copy the files in the folder, then run mod2max, inscribe the name of the file and press Enter (ie, not via drag-and-drop).
## Post #242
- Username: Dtmech
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 14, 2009 8:32 pm
- Post datetime: 2010-01-09T18:41:58+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Tosyk
>
> Dtmech wrote:Yes i know i know , i already did it with Lost planet and Re5 , but DMC4 doesn't give me the .ms file , it just closes and that's it i don't get anything.
Try to do it with other files, perhaps unpacking archives was not entirely successful. See it all Do you have files with extensions. When I unpacked my archives, I have all the files have no extension and I now have to rename every file manually. Try just mod2max copy the files in the folder, then run mod2max, inscribe the name of the file and press Enter (ie, not via drag-and-drop).

Didn't work. :/

The archives i need to extract are in nativepc/rom/enemy/ ?
## Post #243
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-01-09T19:39:19+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Dtmech
>
> Tosyk wrote:Dtmech wrote:Yes i know i know , i already did it with Lost planet and Re5 , but DMC4 doesn't give me the .ms file , it just closes and that's it i don't get anything.
Try to do it with other files, perhaps unpacking archives was not entirely successful. See it all Do you have files with extensions. When I unpacked my archives, I have all the files have no extension and I now have to rename every file manually. Try just mod2max copy the files in the folder, then run mod2max, inscribe the name of the file and press Enter (ie, not via drag-and-drop).

Didn't work. :/

The archives i need to extract are in nativepc/rom/enemy/ ?

I can not say for sure right now. Put my file model and my copy mod2max. I just tried - everything works fine.

ps: it seems the files with the models should be in the directory \ demo, at least, with the main characters
[em016.rar](https://xentaxbackup.github.io/file/2705_em016.rar)
## Post #244
- Username: Dtmech
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 14, 2009 8:32 pm
- Post datetime: 2010-01-09T20:39:14+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Tosyk
>
> Dtmech wrote:Tosyk wrote:Try to do it with other files, perhaps unpacking archives was not entirely successful. See it all Do you have files with extensions. When I unpacked my archives, I have all the files have no extension and I now have to rename every file manually. Try just mod2max copy the files in the folder, then run mod2max, inscribe the name of the file and press Enter (ie, not via drag-and-drop).

Didn't work. :/

The archives i need to extract are in nativepc/rom/enemy/ ?

I can not say for sure right now. Put my file model and my copy mod2max. I just tried - everything works fine.

ps: it seems the files with the models should be in the directory \ demo, at least, with the main characters

Well your file works fine , but my files , just don't , what did you exactly do when you extracted the arc files?
## Post #245
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-01-09T23:31:25+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Dtmech
>
> Well your file works fine , but my files , just don't , what did you exactly do when you extracted the arc files?
I do not remember exactly how extract archives, it has been a long time, at least in the past year.    Try Dmc4Extract or RE5ArcTool v095. But I did not do anything unusual, the same thing as everyone else.
## Post #246
- Username: Dtmech
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 14, 2009 8:32 pm
- Post datetime: 2010-01-09T23:41:09+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Tosyk
>
> Dtmech wrote:Well your file works fine , but my files , just don't , what did you exactly do when you extracted the arc files?
I do not remember exactly how extract archives, it has been a long time, at least in the past year.    Try Dmc4Extract or RE5ArcTool v095. But I did not do anything unusual, the same thing as everyone else.

Maybe you can send the two extraction tools over a pm?
## Post #247
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-01-10T01:04:14+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Dtmech
>
> Tosyk wrote:Dtmech wrote:Well your file works fine , but my files , just don't , what did you exactly do when you extracted the arc files?
I do not remember exactly how extract archives, it has been a long time, at least in the past year.    Try Dmc4Extract or RE5ArcTool v095. But I did not do anything unusual, the same thing as everyone else.

Maybe you can send the two extraction tools over a pm?

For some reason I have in the program archive virus appears  , not only were infected mod2max and dmc4tex  , I have not used them for a month, as the games that are already extracted and waiting in the wings. So send them not see the point. However, you can find the same tools in this topic.
## Post #248
- Username: ddt
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 09, 2010 8:22 pm
- Post datetime: 2010-01-10T09:48:49+00:00
- Post Title: Re: [PC] Devil May Cry 4

2 Surveyor .
sorry, I'm a new one.
I 'd recomply ( also modifyed ) your code Dmc4ModelScr.
and I simply use:
LPVDEC		VDecBIO5=0;
D3DVERTEXELEMENT9 DecBIO5[] = {
{ 0, 0, D3DDECLTYPE_SHORT4N, D3DDECLMETHOD_DEFAULT, D3DDECLUSAGE_POSITION, 0 },
{ 0, 8, D3DDECLTYPE_UBYTE4, D3DDECLMETHOD_DEFAULT, D3DDECLUSAGE_BLENDINDICES, 0 },
{ 0, 12, D3DDECLTYPE_UBYTE4N, D3DDECLMETHOD_DEFAULT, D3DDECLUSAGE_BLENDWEIGHT, 0 },
{ 0, 16, D3DDECLTYPE_UBYTE4N, D3DDECLMETHOD_DEFAULT, D3DDECLUSAGE_NORMAL, 0 },
{ 0, 20, D3DDECLTYPE_UBYTE4N, D3DDECLMETHOD_DEFAULT, D3DDECLUSAGE_TANGENT, 0 },
{ 0, 24, D3DDECLTYPE_FLOAT16_2, D3DDECLMETHOD_DEFAULT, D3DDECLUSAGE_TEXCOORD, 0 },
{ 0, 28, D3DDECLTYPE_FLOAT16_2, D3DDECLMETHOD_DEFAULT, D3DDECLUSAGE_TEXCOORD, 1 },
{ 255, 0, D3DDECLTYPE_UNUSED, D3DDECLMETHOD_DEFAULT, D3DDECLUSAGE_POSITION, 0 },
};
to Create the Vertex Declaration.
and get the result below.
It look crazy, the UV coord seens like single dimenstion.
and I don't understand why.

the code here:

void CMOD::Draw(LPDEV pDev)
{
	qVDec(VDecBIO5);
	cObject* p = m.pObject;
	_for( a, 0, m.ObjectNum )
	{
		int id = m.pMaterial[ p->MatId ].Layer0 - 1;
		if( id >= 0 )
			qTEX(0, TX[id]);

		qDrawIdxUP( triangle_strip, m.VertexNum, p->Count, m.pIndex+p->Start, (byte*)(m.pVertex) + p->Base1, 32 );
		p++;
	}
}

btw, the OBJ format output, I see this:
	for(unsigned int a = 0; a < m_uiVertexNum; a++)
		fprintf(pFile, "vt %f %f %f\n", pUF[a], 1.0f - pVF[a], 0.5f);
UV coord why is 3 member, what dose 3rd member ( .5f ) means?
[bio5_ShebaNormal2_UV_coord_dont_understand.jpg](https://xentaxbackup.github.io/file/2709_bio5_ShebaNormal2_UV_coord_dont_understand.jpg)
## Post #249
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-01-11T08:57:25+00:00
- Post Title: Re: [PC] Devil May Cry 4

0.5f is the W component but can be skipped also reread the surveyor source code to see that re5 models have 2 uv layers to be able to fix yourmodel viewer....
## Post #250
- Username: ddt
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 09, 2010 8:22 pm
- Post datetime: 2010-01-12T03:08:37+00:00
- Post Title: Re: [PC] Devil May Cry 4

Thanks shadowmoy.
I'd completely reread the code. (stupid)
and now it's work.

btw
struct cObject
{
 u16  Id;
 u16  MatId;
 byte  Flag[16];
 uint  Base1;   //this member seens like the offset when
	//the game call SetStreamSource's 3rd parameter
 uint  Zero;
 uint  Start;
 uint  Count;
 uint  Base;
 uint  Inconnu[3];
};
and also found that the game
just simply Create VertexBuffer and copy
whole pVertex's buffer
[bio5_ShebaNormal2_UV_coord_good.jpg](https://xentaxbackup.github.io/file/2714_bio5_ShebaNormal2_UV_coord_good.jpg)
## Post #251
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2010-01-13T09:41:42+00:00
- Post Title: Re: [PC] Devil May Cry 4

About joining meshes each having its own skin modifier.

I have found this script that joins meshes with different skin modifiers. I tested it and it works perfectly... as long as the meshes do not share the same bones. If vertices on different objects share the same bone, the bone weights of those vertices are lost. Can anyone improve this script? 
Here it is:

```
category:"AndreyK"
(
fn fnMergeSkinObjects objectsList refFrame =
(
ObjSkinVertices = #()
bonesList = #()

struct sSkinVertex (bonesCount,bonesID,bonesWeight)

--1
setCommandPanelTaskMode #modify

bonesOffset = 0
for obj in objectsList do
(
select obj

skinMod = undefined
for i=1 to obj.modifiers.count do
(
if (classof obj.modifiers[i] == Skin) do skinMod = obj.modifiers[i]
)

if(skinMod != undefined) then
(
--modPanel.setCurrentObject skinMod
vertices_count = skinOps.GetNumberVertices skinMod

for i = 1 to vertices_count do
(
newSkinVertex = sSkinVertex 0 #() #()
newSkinVertex.bonesCount = skinOps.getVertexWeightCount skinMod i
for j = 1 to newSkinVertex.bonesCount do
(
Append newSkinVertex.bonesID ((skinOps.getVertexWeightBoneID skinMod i j)+bonesOffset)
Append newSkinVertex.bonesWeight ( skinOps.getVertexWeight skinMod i j )
)
append ObjSkinVertices newSkinVertex
)

bones_count = skinOps.GetNumberBones skinMod
bonesOffset += bones_count

for i = 1 to bones_count do
(
appendifunique bonesList (skinOps.GetBoneName skinMod i 0)
)
)-- if(skinMod != undefined)
else deleteItem objectsList (findItem objectsList obj)
)--for obj in objectsList

--2
at time refFrame
(
skinobj = box prefix:"skinobj_"
convertto skinobj editable_poly
polyop.deleteVerts skinobj #{1..8}

for newElement in objectsList do
(
polyop.attach skinobj newElement
)

--3
skinMod = skin()
addModifier skinobj skinMod
skinMod.bone_limit = 4 --todo - find maximum bone_limit in all objects
skinMod.weightAllVertices = false

select skinobj
setCommandPanelTaskMode #modify
--modPanel.setCurrentObject skinMod


for BoneName in BonesList do
(
skinOps.addbone skinMod (GetNodeByName(BoneName)) 1
)

skinOps.Invalidate skinMod 0

skinOps.SelectBone skinMod 1

--4
vertices_count = skinOps.GetNumberVertices skinMod

for i = 1 to vertices_count do
(
skinOps.SetVertexWeights skinMod i ObjSkinVertices[i].bonesID[1] 1
skinOps.SetVertexWeights skinMod i ObjSkinVertices[i].bonesID ObjSkinVertices[i].bonesWeight
)
)--at time refFrame
)--fn fnMergeSkinObjects

on execute do
(
objectsList = selection as array

if(objectsList.count>0) do
try
(
fnMergeSkinObjects objectsList 0
)
catch()
)
)--macroscript 
```

Save it as *.mcr, put it into \ui\macroscripts. Now create a toolbar with the button (category AndreyK -> mergeSkinObjects). Select multiple objects with skin modifiers, press the button to merge those objects.

I know, there is an SMD plugin solution, but it is more like a workaround. And it has its drawbacks. Is anyone here good at MaxScript willing to improve this script?
## Post #252
- Username: ddt
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 09, 2010 8:22 pm
- Post datetime: 2010-01-13T13:52:28+00:00
- Post Title: Re: [PC] Devil May Cry 4

Today learn effect.
I fool again.
Is there someone help me!
what is going on in the effect file ?
sampler s0 : register(s0);

#if 1
row_major float3x4 mJoint[32];
#else
float3x4 mJoint[32];
#endif

float4x4 mPV;
float4x4 mW;

void vs( 
  float3 ipos    :POSITION,
  float2 itex    :TEXCOORD0,
  float2 itex1    :TEXCOORD1,
  float4 weight  : BLENDWEIGHT0,
  float4 bone    : BLENDINDICES0,
  out float4 opos :POSITION,
  out float2 tex  :TEXCOORD0,
  out float2 tex1  :TEXCOORD1)
{
  float3 pos = 0;
  if( 1 )
  {
    pos = mul( ipos, mJoint[ bone.x ] )*weight.x + mul( ipos, mJoint[ bone.y ] )*weight.y;
    if( weight.z )      pos += mul( ipos, mJoint[ bone.z ] )*weight.z + mul( ipos, mJoint[ bone.w ] )*weight.w;
  }
  else
  {
    pos = mul( mJoint[ bone.x ], ipos )*weight.x + mul( mJoint[ bone.y ], ipos )*weight.y;
    if( weight.z )      pos += mul( mJoint[ bone.z ], ipos )*weight.z + mul( mJoint[ bone.w ], ipos )*weight.w;
  }

  opos = mul( float4(pos, 1), mW );
  opos = mul( opos, mPV );
  tex = itex;
  tex1 = itex1;
}

float4 ps( float2 t0  :  TEXCOORD0, float2 t1  :  TEXCOORD1 ):COLOR0
{
  float u = ( t1.x < 0 ) ? t0.x : t1.x;
  float v = ( t1.y < 0 ) ? t0.y : t1.y;
  return float4( tex2D( s0, float2( u, v ) ).xyz, 1 );
}

technique Bio5{
   pass P0{
      vertexShader = compile vs_2_0 vs();
      pixelShader  = compile ps_2_0 ps();
   }   
}

I'm so sure I'd pass the right BoneMatrix(m3x4) data,
and call peff->CommitChanges();
just don't know what the diffent between:
 "row_major float3x4" and "float3x4" ?
how to calc then with "mul"
[bio5_ShebaNormal2_Skin_with_effect_No_work.jpg](https://xentaxbackup.github.io/file/2720_bio5_ShebaNormal2_Skin_with_effect_No_work.jpg)
## Post #253
- Username: rogueclarkey
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 22, 2008 11:01 pm
- Post datetime: 2010-02-04T19:13:26+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi All,

A quick nod to all the work previous work done by others in this thread. Great work 

I'm trying to make sense of some anomalies I'm coming across in the face data when I'm looking at the dante model data.
(model\game\pl006\pl006.mod)

The code I've written is based on the Dmc4Model source posted on this forum. Cheers Surveyor.

From previous posts in the cObject class:

usFlag[6]  - start Vertex index
usFlag[5] - end Vertex index
usFlag[4] - vertexCount

uiCount - number of tris in the triangle strip

For the very first object in pl006.mod, uiCount = 4 so there should be 6 indices for this triangle strip. This seems to tie up correctly because uiStart for the second object is 6.

If I print out the above fields and all the indices within that strip I get the following:

Object 0: usFlag[6]: 0 usFlag[5]: 2 usFlag[4]: 3
uiCount+2: 6 // number of indices
0: 0
1: 1
2: 2
3: 2
4: 2
5: 3


I'm a little confused if the usFlag[6] is 0 and usFlag[5] is 2, why the last index that makes up the triangle strip is 3. i.e. A number outside this range.

I think I must be misinterpreting something and I hope someone with a bit more familiarity with the format might be able to shed some light on this.
## Post #254
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2010-03-03T18:43:56+00:00
- Post Title: Re: [PC] Devil May Cry 4

can dantes office be extracted thru the extractor provided? or do i have to extract the models seperately and put them back togehter in max?
## Post #255
- Username: oBadboyo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 12, 2010 1:32 pm
- Post datetime: 2010-03-12T07:42:38+00:00
- Post Title: Re: [PC] Devil May Cry 4

can you tell me what exactly i need to do to import RE5 model.
I imported the ms then exported to smd ( should i delete the low LOD ?)
open the smd with notepad, replace all the \ with /, still error when importing.
And BTW, why the model is so blocky with useless line +part, and when i give the meshsmooth it appear sort of not smooth at all. Mod2obj import it smoothly but sadly no bone
## Post #256
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2010-04-03T00:08:24+00:00
- Post Title: Re: [PC] Devil May Cry 4

So I read through this thread, and I'm still kind of lost.

How do I get stuff from Lost Planet into Max or whatever?
## Post #257
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-03T00:35:47+00:00
- Post Title: Re: [PC] Devil May Cry 4

the key is you need to find that planet which is lost.

but seriously just download the lost planet arc extractor then use the converters ported to import them.
## Post #258
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2010-04-03T00:43:05+00:00
- Post Title: Re: [PC] Devil May Cry 4

Alright. So dmc4model is the one that converts the extracted model files into normal model formats, right? 

Also, I wasn't able to download the texture converter. Any chance of a reupload?

EDIT: I get a Trojan warning when downloading the package with the texture converter in it.

EDIT EDIT: I seriously need the pack with the texture converter, I'm still unable to download it because of that stupid virus warning and I have no way of ignoring it (library computer).
## Post #259
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2010-04-24T09:53:20+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from TehDave
>
> Also, I wasn't able to download the texture converter. Any chance of a reupload?
It won't change anything. Turn off the antivirus software.
## Post #260
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2010-05-08T00:14:59+00:00
- Post Title: Re: [PC] Devil May Cry 4

Well, I managed to download it, but thanks anyways.

Is there anyway to fix the loose vertexes without using vertex weld and loosing the model's smoothing?

Also, any plans to support Lost Planet 2 when it comes out in a couple of days?
## Post #261
- Username: Demiurge
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 17, 2010 6:34 am
- Post datetime: 2010-07-17T11:42:24+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hey Surveyor, thanks for the great tools!

For all the other...have you used dmc4extract under windows7 ? Even without antivirus, it won't start...

Thanks!
## Post #262
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-07-17T11:47:22+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Demiurge
>
> Hey Surveyor, thanks for the great tools!

For all the other...have you used dmc4extract under windows7 ? Even without antivirus, it won't start...

Thanks!
I'm using dmc4extract without any problem on my Win7 x64 Ultimate (with turn-off my anti-virus).
## Post #263
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-07-18T02:06:21+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Demiurge
>
> Hey Surveyor, thanks for the great tools!

For all the other...have you used dmc4extract under windows7 ? Even without antivirus, it won't start...

Thanks!

DMC4extract is to rename the files with the correct extensions, no to extract the files from the arc.
## Post #264
- Username: fleshtheworld
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 01, 2008 11:16 am
- Post datetime: 2010-07-28T08:23:14+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi, iv skimmed through this thread, but im not sure which tools to get or where. It seems like all the tools are made by different authors.

Can someone give an overview of the achievement of this thread and the tools used.

From what i gather, you can get the models from DMC4 into a 3d modeling software. All i want to accomplish is get the models and textures into a 3d software. What about previous DMC series? Any links to learn about older DMC extracting?
## Post #265
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-07-28T08:56:13+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from fleshtheworld
>
> Hi, iv skimmed through this thread, but im not sure which tools to get or where. It seems like all the tools are made by different authors.

Can someone give an overview of the achievement of this thread and the tools used.

From what i gather, you can get the models from DMC4 into a 3d modeling software. All i want to accomplish is get the models and textures into a 3d software. What about previous DMC series? Any links to learn about older DMC extracting?
This tutorial i created for me, bu perhaps you can find it useful:

> 1. After installation all files you need are in 
>
> root/nativePC/rom 
>
> 
>
> 2. To decompress .arc files using a script for QuickBMS 
>
> http://aluigi.altervista.org/papers/bms/dmc4.bms
>
> 
>
> 3. Model files and textures after unpacking you can find in the model (model/demo) folder 
>
> 
>
> 4. Each type of model (characters/enemy/weapon) corresponds to its origin folder names, for example 
>
> 
>
> em001, where em - mark enemies, 001 - serial number 
>
> 
>
> pl000, where pl - characters/players, 000 - serial number 
>
> 
>
> wp005, where wp - weapons, 005 - serial number 
>
> 
>
> 5. On default all files are without extension, it can be corrected by Dmc4Extract tool (though I have detected a virus in it, but it work fine, or you can rename each file manually). It must be copied into a folder, for example in em001 and run. Dmc4Extract will automatically rename all files in current folder by it headers. 
>
> 
>
> 5. Model format .mod and the texture format .tex opened and converted by Noesis 
>
> http://oasis.xentax.com/index.php?content=downloads
## Post #266
- Username: fleshtheworld
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 01, 2008 11:16 am
- Post datetime: 2010-07-28T18:03:06+00:00
- Post Title: Re: [PC] Devil May Cry 4

Step 1 to me is out of the blue, but i assume your talking about the game content location?

So, it looks like i only need 3 tools? QuickBMS to extract files, Dmc4Extract to fix QuickBMS inability to process something relating to multiple files and extension issues?, and noesisv to convert the files into easier formats to work with.

For identifying the extracted file extensions i would have to have forknowledge of what they may be? But apparently Dmc4Extract helps with that. This brings me to a related question, isnt their tools that can detect the proper extension of a file bu looking up its 'raw code'/header something.

Thanks for sharing the tut
## Post #267
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-07-28T23:25:13+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from fleshtheworld
>
> Step 1 to me is out of the blue, but i assume your talking about the game content location?
 yes

> Reply from fleshtheworld
>
> isnt their tools that can detect the proper extension of a file bu looking up its 'raw code'/header something
Dmc4Extract doing this nicely on the 5 step
## Post #268
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-08-03T22:18:21+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi!!
I messed with animations a little and I've been able to play gameplay anims, the demo scenes still act weird...
The pic below shows nero playing a guitar and comitting suicide, I'll post the program soon.
[Motions.JPG](https://xentaxbackup.github.io/file/3294_Motions.JPG)
## Post #269
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-08-04T03:15:00+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> Hi!!
I messed with animations a little and I've been able to play gameplay anims, the demo scenes still act weird...
The pic below shows nero playing a guitar and comitting suicide, I'll post the program soon.
It's juuuust great
## Post #270
- Username: Jodan
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 02, 2010 11:12 am
- Post datetime: 2010-08-04T04:23:54+00:00
- Post Title: Re: [PC] Devil May Cry 4

Surveyor, thank you for this new soon to be released tool... very cool...
## Post #271
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2010-08-04T17:59:31+00:00
- Post Title: Re: [PC] Devil May Cry 4

Admin edit: tool was shared without permission. Removed by request. Don't do it again.

This is the tool to Extract and Repack (with compression) the .ARC files of Devil May Cry 4.
See the "how to use" inside the .rar to guide you.

Enjoy
## Post #272
- Username: gics
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Dec 19, 2009 4:12 pm
- Post datetime: 2010-08-04T21:20:36+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Surveyor
>
> Hi!!
I messed with animations a little and I've been able to play gameplay anims, the demo scenes still act weird...
The pic below shows nero playing a guitar and comitting suicide, I'll post the program soon.

Great work man...
I can't wait that program.
## Post #273
- Username: Xenior
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 09, 2010 10:31 am
- Post datetime: 2010-08-10T02:55:24+00:00
- Post Title: Re: [PC] Devil May Cry 4

How can I edit the model? I use Noesis ,but I don't know how to save...
## Post #274
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2010-08-14T16:16:18+00:00
- Post Title: Re: [PC] Devil May Cry 4

Wow, just found out that MHF Benchmark uses this format as well. Then posting a new thread and googling two minutes afterwards I stumble upon this one - I love this place   
Keep it up, cannot wait
## Post #275
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2010-08-15T13:48:11+00:00
- Post Title: Re: [PC] Devil May Cry 4

@Herdell: Did that tool come from the DMC4 translation project? Anyway, thanks, I can think of a few uses for it.
@eycaramba: MHF's format is not the same, we've been able to extract dmc 4 .arcs for ages. I wish we could extract MHF's too though...
## Post #276
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2010-08-16T10:36:44+00:00
- Post Title: Re: [PC] Devil May Cry 4

I said MHF BENCHMARK  
But yeah... I wonder why they use this strange, multi-containered pac format. At least the textures are easily extracted :O
But I want to know what is it about the content of the JKR archives >_>
## Post #277
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2010-08-16T18:59:45+00:00
- Post Title: Re: [PC] Devil May Cry 4

> I said MHF BENCHMARK
You're gonna tell me now that they use different formats in the benchmark? Don't think so.
## Post #278
- Username: Rygdea
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Aug 16, 2010 7:27 pm
- Post datetime: 2010-08-16T20:43:09+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hey, nice work everyone, but I got a question, does the "normal" Dante model always have the top of his Devil trigger there?

[http://i37.tinypic.com/x5oayp.jpg](http://i37.tinypic.com/x5oayp.jpg)

I get this in both em_dante.arc and uPlayerDante.arc

I didn't have this problem with Nero (In fact his devil trigger had a separate folder.)

Would I need to remove it myself from the Main Body with a 3D editing program myself since it looks like the original body is there. (Minus the cape and head, which are seperate) or is there a Model in game that doesn't include it?

If it matters I'm not using the Demo, but the actual game (Steam version). Thanks for any help.
## Post #279
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2010-08-17T08:59:27+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from omni
>
> You're gonna tell me now that they use different formats in the benchmark? Don't think so.
Well, then tell me how I got this nice T-Posed Berukyulos? (plus it's MHF PAC file is strange encrypted)
## Post #280
- Username: Rygdea
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Aug 16, 2010 7:27 pm
- Post datetime: 2010-08-17T13:44:06+00:00
- Post Title: Re: [PC] Devil May Cry 4

> 1. After installation all files you need are in
>
> root/nativePC/rom
>
> 
>
> 2. To decompress .arc files using a script for QuickBMS
>
> http://aluigi.altervista.org/papers/bms/dmc4.bms
>
> 
>
> 3. Model files and textures after unpacking you can find in the model (model/demo) folder
>
> 
>
> 4. Each type of model (characters/enemy/weapon) corresponds to its origin folder names, for example
>
> 
>
> em001, where em - mark enemies, 001 - serial number
>
> 
>
> pl000, where pl - characters/players, 000 - serial number
>
> 
>
> wp005, where wp - weapons, 005 - serial number
>
> 
>
> 5. On default all files are without extension, it can be corrected by Dmc4Extract tool (though I have detected a virus in it, but it work fine, or you can rename each file manually). It must be copied into a folder, for example in em001 and run. Dmc4Extract will automatically rename all files in current folder by it headers.
>
> 
>
> 5. Model format .mod and the texture format .tex opened and converted by Noesis
>
> http://oasis.xentax.com/index.php?content=downloads

I did this and it works fine for the model, but the textures seem to fail to import in 3DS Max 



If I try to add them myself after though there is no UV Mapping.   

If I try another method trough Mod2Max the Model gets all "Blocky" (I don't know the word for this)



Any Help at all?

> Reply from Herdell
>
> This is the tool to Extract and Repack (with compression) the .ARC files of Devil May Cry 4.
See the "how to use" inside the .rar to guide you.

Enjoy

I tried this, but it crashes on the first file it tries to extract.
## Post #281
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2010-08-17T16:27:43+00:00
- Post Title: Re: [PC] Devil May Cry 4

@eycaramba: So they DO use different formats? Funny.
Anyway, when i said this: "MHF's format is not the same, we've been able to extract dmc 4 .arcs for ages."
I meant the benchmark XD

@Rygdea: Yeah, that DMC 4 unpacker/repacker doesn't unpack at all. It seems to repack fine though.
## Post #282
- Username: Jodan
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 02, 2010 11:12 am
- Post datetime: 2010-08-19T01:31:15+00:00
- Post Title: Re: [PC] Devil May Cry 4

I would like to replace dmc4 and re5 models with different models; is there a tool or plugin to export a file in max into a *.mod?  The goal  here is the rig a new model on top of the games default bones and export it out to be used in game.


I also have a question about importing a smd file, I had made in max (with export)... I can export the file fine, but if I import the smd (with the mesh, bones import without any issues), I get a "Error: Unparsable node data (line 3)."  Any ideas as to what might be causing the problem with the mesh? Any ideas would be appreciated.
## Post #283
- Username: jenner
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 21, 2010 5:10 am
- Post datetime: 2010-08-21T13:38:00+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from omni
>
> @Herdell: Did that tool come from the DMC4 translation project? Anyway, thanks, I can think of a few uses for it.

Yes, it came from GameVicio ([http://www.gamevicio.com.br](http://www.gamevicio.com.br)) brazilian portuguese translation and the user is sharing my tool without permission.
## Post #284
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2010-08-21T22:29:38+00:00
- Post Title: Re: [PC] Devil May Cry 4

I'm sure he'll be sorry once he sees your post but, since it's done already, how about giving us permission to share it? Who knows, someone might put it to good use eventually. And while you're at it you could post some general info about your tool.
## Post #285
- Username: jenner
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 21, 2010 5:10 am
- Post datetime: 2010-08-22T00:55:56+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from omni
>
> I'm sure he'll be sorry once he sees your post but, since it's done already, how about giving us permission to share it? Who knows, someone might put it to good use eventually. And while you're at it you could post some general info about your tool.

He will not be sorry for sure, he did it because he was banned from our site. But this sad episode became a good oportunity to show one of our tools to translate games, this simple one was developed with NSIS (Nullsot Install System). All you have to do is put the tool in the same folder containing the arc file you want to mod.

- First option => The tool will create a new arc.gv file using the original one and the modified extracted files
- Second option => The tool wil extract all content from the arc file to a folder with the same name

The tool is instable sometimes and crash with many already modified files.
## Post #286
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2010-08-22T12:05:54+00:00
- Post Title: Re: [PC] Devil May Cry 4

@Jodan: Missed your post there but we can't import models for these games yet.
@jenner: Cool, thanks ^_^.
Quick question, for the first option, do the modified files need to have their proper extensions (.mod etc.)?
## Post #287
- Username: jenner
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 21, 2010 5:10 am
- Post datetime: 2010-08-22T12:48:31+00:00
- Post Title: Re: [PC] Devil May Cry 4

The tool 
> Reply from omni
>
> @Jodan: Missed your post there but we can't import models for these games yet.
@jenner: Cool, thanks ^_^.
Quick question, for the first option, do the modified files need to have their proper extensions (.mod etc.)?

Do not change names or extensions of the extracted files, rename your modified files accordingly. You can delete all the untouched files, the tool will inject the files that are in the folder into the new arc file.
## Post #288
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2010-08-23T21:40:35+00:00
- Post Title: Re: [PC] Devil May Cry 4

Thanks.
As I said in a previous post, I can't seem to extract using your tool, it crashes but leaves the process open (Same happens to another user and to a friend of mine). I'll assume from what you said that files extracted with your tool have the proper extensions.
## Post #289
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-08-24T06:47:52+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi,
Here's the dmc4 motion exporter, so how do we use this thing? There is a text file attached with the program, you'll use that, it is self explanatory: write the path of the lmt file you want to process, the model file it belongs to and an output path (where the scripts will be created), don't use spaces in you paths because the program uses the fscanf() function so "program files/capcom" is very bad!!! (notice the space between the m & f)
The program requires a model exported using the mod2max.exe (see earlier posts), once you open it under max, drag and drop any script on top of that model and it will bind the animation to the bones. This model must be in ref pose, you can't drag and drop multiple scripts into the same model. so far the program works only on gameplay animations so don't try to use it on "models/demo" models.
I think that's all you need to know about the exporter which is in very early dev stages so expect bugs and crazy poses!!
Enjoy!!
[Dmc4Motion.zip](https://xentaxbackup.github.io/file/3365_Dmc4Motion.zip)
## Post #290
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2010-08-24T15:39:49+00:00
- Post Title: Re: [PC] Devil May Cry 4

Thanks a lot for your work. Btw, we're trying to swap animations but it usually get's screwed up because they're crammed together. Is there any way we can switch/extract/insert especific animations between packages?
## Post #291
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2010-08-28T18:31:40+00:00
- Post Title: Re: [PC] Devil May Cry 4

Sorry for the double post ( I think I'm justified), but did you guys know there's a debug mode in DMC 4? And that you can use it to play with Dante whenever you want? And that it's only available in an obscure version of the game, but we made a patch to make it work in all of them?

Read all about it here: [http://s1.zetaboards.com/InfernalWorks/topic/3745063/1/](http://s1.zetaboards.com/InfernalWorks/topic/3745063/1/)
## Post #292
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2010-08-29T11:19:20+00:00
- Post Title: Re: [PC] Devil May Cry 4

Thanks alot surveyor!
You are the best
## Post #293
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-08-31T10:24:43+00:00
- Post Title: Re: [PC] Devil May Cry 4

> did you guys know there's a debug mode in DMC 4? And that you can use it to play with Dante whenever you want? And that it's only available in an obscure version of the game, but we made a patch to make it work in all of them?
Thanks man, that's good to know.

> Btw, we're trying to swap animations but it usually get's screwed up because they're crammed together
The guys at capcom say their MTFramework engine has a unified animation scheme which means you can plug any animation with any model and still work fine (to some extent)

> Is there any way we can switch/extract/insert especific animations between packages?
Now look at this pic: on the left you have a nero model captured from the game using 3DRipperDX, just after, a nero model is rigged using the dmc4motion extractor and the same animation is applied to gloria model. The unified scheme thing seems true but even though the poses look similar they aren't the same, the difference (between game and dmc4motion) is most visible in the devil arm and this is due to the fact that there's some unclear/custom rad2degrees conversion function that isn't linear and this is the best I could achieve. The work is in progress and demo animations start to show up too.
[GloriaNeroed.jpg](https://xentaxbackup.github.io/file/3389_GloriaNeroed.jpg)
## Post #294
- Username: gics
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Dec 19, 2009 4:12 pm
- Post datetime: 2010-08-31T16:14:13+00:00
- Post Title: Re: [PC] Devil May Cry 4

@Surveyor

Can you tell me where i can download dmc4motion extractor? Please...
## Post #295
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2010-09-03T06:01:45+00:00
- Post Title: Re: [PC] Devil May Cry 4

[download/file.php?id=3365](http://forum.xentax.com/download/file.php?id=3365)

> Reply from gics
>
> @Surveyor

Can you tell me where i can download dmc4motion extractor? Please...
## Post #296
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2010-09-05T06:26:07+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi Surveyor
I tried import anim, but MAX (2011 x64, 2009 x86) stoped with error  
[Clipboard01.jpg](https://xentaxbackup.github.io/file/3406_Clipboard01.jpg)
## Post #297
- Username: Jodan
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 02, 2010 11:12 am
- Post datetime: 2010-09-08T05:03:24+00:00
- Post Title: Re: [PC] Devil May Cry 4

omni, if we can export the files and obtain the bone data now, would creating a max2mod or a mod exporter plugin for max be difficult to implement or something now plausible? i ask because this seems to be the last piece of the puzzle toward adding custom models into re5.
## Post #298
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2010-09-11T18:46:40+00:00
- Post Title: Re: [PC] Devil May Cry 4

Guys who made translations of the game...
In which files there are texts, fonts etc? I want to translate this game.
## Post #299
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2010-09-11T20:50:26+00:00
- Post Title: Re: [PC] Devil May Cry 4

New debug mode patch released, check the forum if you want it.

@Surveyor: What I meant was that, when we swap .lmt files, the motion swap is buggy because the animations are in packages as opposed to one file for each animation. So I'm asking if we can, let's say, swap Dante's running animation with Nero's somehow.

@Jodan: I could make an educated guess, but If you take a look through this thread you'll see plenty of people more suited to answer that XD

@GamerSuper: Subtitles for cutscenes are in each cutscene's .arc file in nativepc\rom\demo. Text for menus are in each menu's file, try nativepc\rom\id.
## Post #300
- Username: smoker29
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 17, 2010 11:32 am
- Post datetime: 2010-09-18T17:12:28+00:00
- Post Title: Re: [PC] Devil May Cry 4

hey, thanks for the download link. I will start downloading this and hope it is a virus free.
## Post #301
- Username: Carampucilo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 12, 2010 4:00 am
- Post datetime: 2010-09-19T20:59:29+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from omni
>
> 
@GamerSuper: Subtitles for cutscenes are in each cutscene's .arc file in nativepc\rom\demo. Text for menus are in each menu's file, try nativepc\rom\id.

Please do not answer this idiot. It the known Russian clown who tries to get the information at foreign forums because in the homeland of it each person hates. And all probably already saw "the first PSP game started on PS3" from this stupid liar which has certainly appeared a fake. I ask do not answer its questions.

Yours faithfully from mother Russia
## Post #302
- Username: Nexus Elite ns
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2009 1:11 am
- Post datetime: 2010-10-19T01:10:26+00:00
- Post Title: Re: [PC] Devil May Cry 4

Any chance on looking up at lost planet 2 files? it's the same arc but different format inside i think.
## Post #303
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2010-10-20T14:45:35+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Nexus Elite ns
>
> Any chance on looking up at lost planet 2 files? it's the same arc but different format inside i think.

Using some of the tools for dmc, re5 and the first lp have extracted fine for lp2. But the file extensions are unknown to me. Going to start a lp2 thread.
## Post #304
- Username: Nexus Elite ns
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2009 1:11 am
- Post datetime: 2010-10-21T02:50:52+00:00
- Post Title: Re: [PC] Devil May Cry 4

The contents of this post was deleted because of possible forum rules violation.
## Post #305
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-11-04T12:20:29+00:00
- Post Title: Re: [PC] Devil May Cry 4

Now we can model swap dmc 3 weapon model not just reskin,we can import new weapon model to dmc 3



Thanks to our friend n3xus
from
[http://s1.zetaboards.com/InfernalWorks/topic/3820468/3/](http://s1.zetaboards.com/InfernalWorks/topic/3820468/3/)
its gonna be great if we can import a new model player 
If anyone know about programming and 3d modeling please  go here
[http://s1.zetaboards.com/InfernalWorks/topic/3820468/3/](http://s1.zetaboards.com/InfernalWorks/topic/3820468/3/)
and contact n3xus 

Its gonna be great if we can mod dmc3,its gonna be the first mod able dmc series 
If someone know about programming and 3d modeling please help
## Post #306
- Username: apeanut
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 08, 2010 12:13 pm
- Post datetime: 2010-12-01T05:36:52+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi,I'm a freshman here.There exist some bug when Dante's mod changes into Gilgamesh.I will show some photos of my discovery.

[http://img.ph.126.net/gwuWQx-KWl70gQpVR ... 362470.bmp](http://img.ph.126.net/gwuWQx-KWl70gQpVRg8DWw==/3701677418722362470.bmp)
[http://img.ph.126.net/FKXeXIn6rjZ7DRys5 ... 201937.bmp](http://img.ph.126.net/FKXeXIn6rjZ7DRys5Sow4g==/3057944146985201937.bmp)
[http://img154.ph.126.net/jq3MA8BpgSwbyy ... 249382.bmp](http://img154.ph.126.net/jq3MA8BpgSwbyybRKlLU6w==/1485906402057249382.bmp)



Clip the website below to see more pictures. 
[http://www.dmcry.cn/viewthread.php?tid= ... omuid=4053](http://www.dmcry.cn/viewthread.php?tid=4903&fromuid=4053)

 My Blog：[http://617929052.blog.163.com](http://617929052.blog.163.com)
## Post #307
- Username: happytimes
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 02, 2011 6:52 am
- Post datetime: 2011-06-04T08:43:59+00:00
- Post Title: Re: [PC] Devil May Cry 4

Did anyone look into the sound effects?

They appear to be .spac files with no known audio format. The .sreq files might be the header files.

Changing model works fine, but can the sound effects be altered or at least decoded into .wav?
## Post #308
- Username: ntlam
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 06, 2011 12:18 pm
- Post datetime: 2011-06-20T04:57:34+00:00
- Post Title: Re: [PC] Devil May Cry 4

hi everyone , i'm newbie. 
I use dmc4motion to extract animation and convert to md5anim and i use [noesis v3.3](http://oasis.xentax.com/index.php?content=downloads) to extract model and bone to md5mesh.
But when i combine 2 file and play animation the model look so bad :


I write the code to load md5 model and animation in c# 
anyone fix that ?
## Post #309
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2012-02-05T01:40:43+00:00
- Post Title: Re: [PC] Devil May Cry 4

The DMC4Motion is in early stage of developing, so its exported function dont work properly
## Post #310
- Username: sobhannina
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Dec 29, 2011 3:25 am
- Post datetime: 2012-03-08T14:30:20+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi all

thanks for your all efforts making tools

i have a request and a question 

i just want to edit the textures of 2 / 3 girls in the game (Characters) and then Inject them to the original .arc file where they belongs .

so the question is , Which Tools i have to Use ? 

and  do you know how can access the movies that shown in game ? i mean in game Movies like Nero & Dante's Fight in the First Level of game ! i'd like to edit both TEXTURES and Movies of the game and then Replace the Edited ones with Original ones (Inject Them).

Does any one know how can i do these things ?
## Post #311
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-08T18:49:33+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from sobhannina
>
> Hi all

thanks for your all efforts making tools

i have a request and a question 

i just want to edit the textures of 2 / 3 girls in the game (Characters) and then Inject them to the original .arc file where they belongs .

so the question is , Which Tools i have to Use ? 

and  do you know how can access the movies that shown in game ? i mean in game Movies like Nero & Dante's Fight in the First Level of game ! i'd like to edit both TEXTURES and Movies of the game and then Replace the Edited ones with Original ones (Inject Them).

Does any one know how can i do these things ?

You'll have to unpack the highpoly models.

Check this forum:

[http://s1.zetaboards.com/InfernalWorks/index/](http://s1.zetaboards.com/InfernalWorks/index/)
## Post #312
- Username: sobhannina
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Dec 29, 2011 3:25 am
- Post datetime: 2012-03-08T19:54:06+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Darko
>
> sobhannina wrote:Hi all

thanks for your all efforts making tools

i have a request and a question 

i just want to edit the textures of 2 / 3 girls in the game (Characters) and then Inject them to the original .arc file where they belongs .

so the question is , Which Tools i have to Use ? 

and  do you know how can access the movies that shown in game ? i mean in game Movies like Nero & Dante's Fight in the First Level of game ! i'd like to edit both TEXTURES and Movies of the game and then Replace the Edited ones with Original ones (Inject Them).

Does any one know how can i do these things ?

You'll have to unpack the highpoly models.

Check this forum:

http://s1.zetaboards.com/InfernalWorks/index/

would you please be more Clear on that ?!!!! 
i couldn't find the Things am looking for !
i want to extract and  edit Game Character  which are shown in the Demos ! like Lady , Gloria , ..... Textures and then Repack them again 

i find that 90% of demos in the Game are Real-time Demos (Cut Scenes) so i had to Edit the Original models i read whole 21 pages in this Topic/Form , but am confused ! Tell me Which Tools i have to use and how ?

Thanks
and
## Post #313
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2012-04-20T18:37:39+00:00
- Post Title: Re: [PC] Devil May Cry 4

does anyone know where the file with coordinates of font's char
## Post #314
- Username: Portagas
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 17, 2014 11:03 pm
- Post datetime: 2014-07-19T15:03:27+00:00
- Post Title: Re: [PC] Devil May Cry 4

Hi.
Dmc 4 MSG2Editor How can I use .

Edit:I got it
## Post #315
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-08-31T14:05:14+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from Thief1987
>
> does anyone know where the file with coordinates of font's char

I have same question with him! Thanks!
## Post #316
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2014-11-24T02:08:25+00:00
- Post Title: Re: [PC] Devil May Cry 4

> .. the 1st exports the mesh data and when I'm done with mesh modifications the 2nd script comes to set the bones and skinning. If somebody has an idea about this then I'd like to hear it..

In 3DSmax you can copy and paste a skin from one model to another, provided the models are similar.
This isn't entirely flawless, and you always have to check the pasted skin & adjust where necessary.
It works best for models that have their legs not too close to each other.

If you like I can explain more about this.
## Post #317
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2015-07-01T16:01:26+00:00
- Post Title: Re: [PC] Devil May Cry 4

any update for special edition?
## Post #318
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2016-03-12T07:56:25+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from evin
>
> I'm almost done with the MSG2 editor program. Only the default character-set supported (english, german, french etc.) by reading. The writer part support the most ASCII characters, yet.
Maybe not this is the best program, but at least works fine with the most msg2 file.
.NET 2.0 required.

(The ARC file injector is under development. I can't handle the "arc-compress", that's why will the program only append the new uncompressed data to the end of file.)

Could you share me your source code in private? I need update in PS3 version.

My table in PS3 version:

```
00002024=[tab]
00001004=[begin]
000011040000060400000604=[end]
00000104=¶\n\r
0000200403002004=[COLOR=GREEN]
0000200402002004=[COLOR=RED]
00002104=[/COLOR]
00004D00=0
00022E00=1
00044400=2
00064400=3
00084B00=4
000A4600=5
000C4800=6
000E4200=7
00104800=8
00124900=9
00141700=!
00163C00=?
00182500=(
001A2500=)
001C2800= 
001E5F00=&
00201600=:
00221600=;
00241600=,
00261700=.
00282900="
002A1700='
002C3B00=~
002E2000=-
00304500=+
00324700=/
00343B00=@
00363B00=$
00386100=A
003A5300=B
003C5200=C
003E5B00=D
00405100=E
00424D00=F
00445B00=G
00464F00=H
00481E00=I
004A4700=J
004C5400=K
004E4B00=L
00506F00=M
00525A00=N
00546300=O
00564800=P
00586A00=Q
005A5100=R
005C4D00=S
005E5100=T
00605100=U
00625400=V
00647D00=W
00667D00=X
00685000=Y
006A3B00=Z
006C3D00=a
006E4700=b
00704000=c
00724500=d
00744100=e
00762B00=f
00784300=g
007A4500=h
007C1D00=i
007E1800=j
00804600=k
00821C00=l
00846D00=m
00864400=n
00884500=o
008A4600=p
008C4400=q
008E2C00=r
00903B00=s
00922800=t
00944600=u
00964100=v
00985F00=w
009A4100=x
009C4300=y
009E3700=z
00A85F00=®
```


I use Atlas and Cartographer to extract and repack, but if I have a program, it will be faster. Thanks!
## Post #319
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-12T09:22:32+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from shadowlonely1989
>
> Could you share me your source code in private?Seriously?
Your quotation is from  Thu Jul 16, 2009 8:07 am, evin's last post is from one year ago.
(Just in case you didn't know.  )

Use forum search:
[viewtopic.php?f=10&t=8972&p=78012&hilit=msg2#p78012](http://forum.xentax.com/viewtopic.php?f=10&t=8972&p=78012&hilit=msg2#p78012)
From what I see it's about 
> (DR, RE5, DMC4, LP, MvC, DD, etc) so you might check it
or search for the source of PHP's MSG2 Editor, if any.

(I found the C# source of the RE5 MSG2 editor mentioned in the above linked thread.)

btw: what are the (main) differences between PC and PS3 versions of msg2 files?
## Post #320
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2016-03-13T04:51:00+00:00
- Post Title: Re: [PC] Devil May Cry 4

> Reply from shakotay2
>
> shadowlonely1989 wrote:Could you share me your source code in private?Seriously?
Your quotation is from  Thu Jul 16, 2009 8:07 am, evin's last post is from one year ago.
(Just in case you didn't know.  )

Use forum search:
viewtopic.php?f=10&t=8972&p=78012&hilit=msg2#p78012
From what I see it's about (DR, RE5, DMC4, LP, MvC, DD, etc) so you might check it
or search for the source of PHP's MSG2 Editor, if any.

(I found the C# source of the RE5 MSG2 editor mentioned in the above linked thread.)

btw: what are the (main) differences between PC and PS3 versions of msg2 files?

I checked, but I am not good C#, maybe this code need update beacause It is so long. Per char have 4 byte:
Example:
04004400=2 //first 2 byte is id char
06004400=3 //last 2 byte is w of char, number 2 and 3 have same width
Between PS3 and PC have some diffirent in:
1. id char:
Example:
04004400=2 // PC
=>
00044400=2 // PS3
2. Lenght of file:
Example:
I have 1.msg2 file with size=0C1C
- PC version at 8h with size: 1C0C
- PS3  version at 0Ah with size: 0C1C
## Post #321
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-13T12:34:32+00:00
- Post Title: Re: [PC] Devil May Cry 4

If you uploaded two small msg2 files (one for PC, one for PS3) I could have a look at maybe next weekend.
