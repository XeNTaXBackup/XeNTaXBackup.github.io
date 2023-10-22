## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-25T21:07:52+00:00
- Post Title: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Gibbed Tiger Unpacker (rev117) / Rick
Download: [here](http://forum.xentax.com/viewtopic.php?p=84229#p84229)
Usage:

> Gibbed.TombRaider9.Unpack "szTIGERarchive" "szOutputFolder"
Example:

> Gibbed.TombRaider9.Unpack "c:\Tomb Raider\title.000.tiger" "c:\Tomb Raider\unpacked\title"
DRM Dumper (1.0.1.2) / Ekey (h4x0r)
Download: [here](http://www.sendspace.com/file/ow6vqq)
Usage:

> 1) Unpack Tiger archive
>
> 2) Run DRMDumper
>
> 3) Select game path
>
> 4) Open .DRM files
>
> 5) Profit
Additional thanks to  howfie 



RenderMesh plugin for Noesis (1.5beta) / MrNightmareTM
Download: [here](https://www.dropbox.com/s/hxkw495v07c5qgj/fmt_tombraider_mesh.py)
Usage:

> 1) Download Noesis
>
> 2) Copy plugin in "plugins\python" folder
>
> 3) Profit
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-25T22:03:52+00:00
- Post Title: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

files 000 and 001 is basically 1 file cutted on to 2 pieces you script wont work on this unless you merge them
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-25T22:10:35+00:00
- Post Title: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

I can't test because I do not have these files. Anyway seems wrong extracting.

bigfile_ENGLISH.000.tiger

```
xenon-w\local\locals.bin
```

CRC32 for FileName is 0xC8B69EE7. Found in 

```
FFFF1501\C8B69EE7
```


Who can look [this](http://www.sendspace.com/file/gwzb81) file ? Seems divided into blocks and compressed?

```
4 bytes - Nulls
4 bytes - Nulls
4 bytes - Nulls
4 bytes - Uncompressed Size (Endian Little) ?
```

[Screen v1](http://img856.imageshack.us/img856/9962/15230321.png)

Or

```
4 bytes - Nulls
4 bytes - Nulls
4 bytes - Nulls

select block by size

4 bytes - Nulls
4 bytes - Size with header
4 bytes - Uncompressed Size
4 bytes - Nulls

next block

```

[Screen v2](http://img803.imageshack.us/img803/3347/16431491.png)
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-02-25T22:57:35+00:00
- Post Title: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

When you unpack it you should end up with a bunch of files which are mainly CDRM files. Which stand for Compressed DRM those are compressed and contain models, textures etc..
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-25T23:21:15+00:00
- Post Title: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Yeah i know about DRMs. I found much files as local.bin divided into blocks and compressed. XMem or ?

PS: third post updated.
## Post #6
- Username: sephiroth99
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-02-25T23:53:36+00:00
- Post Title: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

in your file you posted
40 00 01 00 =
0x40 * 0x80 = 0x2000
this is the number at the end
00 00 00 00 00 00 08 10 00 00 20 00
then the 2nd section
2C 00 01 00 = 
0x2C * 0x80 = 0x1600
this is the number at the end
00 00 00 00 00 00 08 10 00 00 36 00
then the 3rd section
28 00 01 00 = 
0x28 * 0x80 = 0x1400
this is the number at the end
00 00 00 00 00 00 08 10 00 00 4A 00
so you can see this first short is the uncompressed data size that you multiply * 0x80
and the number at the end is the placeholder the file is at after decompression.
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-02-26T01:07:09+00:00
- Post Title: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

PC and ps3 version leaked already too? PC version use zlib?
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-02-26T01:09:47+00:00
- Post Title: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> PC and ps3 version leaked already too? PC version use zlib?
No PC leak or PS3. However, PS3 leak is imminent since there are several unboxing videos.

Just a little note Ekey, I made an unpacker a while ago but mine is doing something slightly different. I'm not sure why you are adding/subtracting 0x2010 it's resulting in files having missing data since i compared with my files. I don't think you should be doing that? I'm not certain but I was just letting you know.

~Waiting for PC.
## Post #9
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-02-26T02:40:26+00:00
- Post Title: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

tomb raider for the 360 has been leaked
## Post #10
- Username: sephiroth99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 24, 2011 3:23 am
- Post datetime: 2013-02-26T03:28:23+00:00
- Post Title: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

I had a look too at the new archives. Here's what I found and my current interrogations.

Does any one know if "TAFS" is a known format? My guess is that it's proprietary (as is everything in every TR games...). Is it "TAFS" like "TA" file system, or "FATS" like File Allocation Table "S"??

I used the work done by Rick on DX3 and TR for the following. I made a copy of his code here: [https://github.com/sephiroth99/gibbedtr](https://github.com/sephiroth99/gibbedtr)

About the format of the archive, it's pretty basic, looks a lot like TRU. The thing that is different is how the DRM files are built. Before, in TRU, there was the main DRM file (compressed "CDRM") and you had some pointers to data elsewhere (what Rick called "Resolvers", see : [HERE](https://github.com/sephiroth99/gibbedtr/blob/master/Gibbed.TombRaider.FileFormats/DRM/Resolver.cs)

Now, for TR9, it looks like the DRM file entry in the bigfile is only an index file of those kind of "Resolvers" and the "real" data is elsewhere in the bigfile. But that "real" data is not in the index of the bigfile. I made a basic extractor, and indeed you only extract like 900MB out of the 2.7GB of the bigfile. see [HERE](https://github.com/sephiroth99/gibbedtr/tree/master/Gibbed.TombRaider.UnpackTiger) for my shitty extractor that doesn't work.

I also started looking for filenames, you can see what I have here: [https://github.com/sephiroth99/gibbedtr ... n%29/files](https://github.com/sephiroth99/gibbedtr/tree/master/bin_tr/projects/Tomb%20Raider%209%20%28Xenon%29/files)

So I guess we need to find a way to generate/extract the full DRM file. And after that, see if the format of the mesh, textures, etc ... changed compared to TRU.


Edit: Looks like the DRM file is more similar to the TRU version than I thought. Still, the part about having hidden data in the bigfile stays true I think.

The new DRM Header has the following format:

```
    u32 version; // 0x16 for TR9
    u32 unknown[5]; // all zero? must check all DRM files
    u32 SectionCount;
    u32 UnknownCount;

(Total length: 32 bytes)

```


It looks like the following parts (section header, resolvers, data) are the same as TRU (the section header anyway, can't say for the resolvers).

to be continued...
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-26T06:32:36+00:00
- Post Title: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Sadly, Rebuilder for filelists dont work with TIGER. Anyway here updated filelist. Added ~ 118 filenames.

Paths

```
%sDesign\Image Resources\%s.drm
local\localization\movies\%s.sch
%s\objectlist.txt
%s\objlist.dat
%saudio\streams\
%scinstream\
%s\symbol.ids

```

[bigfile.rar](https://xentaxbackup.github.io/file/6222_bigfile.rar)
## Post #12
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2013-02-26T09:44:12+00:00
- Post Title: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

damn you guys are fast... keep up the good work! 

wish i had the game already but im waiting for the pc version
## Post #13
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-26T18:52:39+00:00
- Post Title: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Simple Language Editor (TR9 Xbox) ... Need tests



1) Unpack Tiger BIGs
2) Open local.bin
3) Select string
4) Edit string
5) Save or Continue editing
6) Test it 
[CrapBinEditor.rar](https://xentaxbackup.github.io/file/6224_CrapBinEditor.rar)
## Post #14
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-26T20:13:29+00:00
- Post Title: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

going to test it right away  Thx man i dont need to do it anymore  Can you please do it export <-> import to TXT to bin pls ?
## Post #15
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-26T20:42:35+00:00
- Post Title: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from sephiroth99
>
> I had a look too at the new archives. Here's what I found and my current interrogations.

Does any one know if "TAFS" is a known format? My guess is that it's proprietary (as is everything in every TR games...). Is it "TAFS" like "TA" file system, or "FATS" like File Allocation Table "S"??

I used the work done by Rick on DX3 and TR for the following. I made a copy of his code here: https://github.com/sephiroth99/gibbedtr

About the format of the archive, it's pretty basic, looks a lot like TRU. The thing that is different is how the DRM files are built. Before, in TRU, there was the main DRM file (compressed "CDRM") and you had some pointers to data elsewhere (what Rick called "Resolvers", see : HERE

Now, for TR9, it looks like the DRM file entry in the bigfile is only an index file of those kind of "Resolvers" and the "real" data is elsewhere in the bigfile. But that "real" data is not in the index of the bigfile. I made a basic extractor, and indeed you only extract like 900MB out of the 2.7GB of the bigfile. see HERE for my shitty extractor that doesn't work.

I also started looking for filenames, you can see what I have here: https://github.com/sephiroth99/gibbedtr ... n%29/files

So I guess we need to find a way to generate/extract the full DRM file. And after that, see if the format of the mesh, textures, etc ... changed compared to TRU.


Edit: Looks like the DRM file is more similar to the TRU version than I thought. Still, the part about having hidden data in the bigfile stays true I think.

The new DRM Header has the following format:
Code: Select allDRM Header
    u32 version; // 0x16 for TR9
    u32 unknown[5]; // all zero? must check all DRM files
    u32 SectionCount;
    u32 UnknownCount;

(Total length: 32 bytes)


It looks like the following parts (section header, resolvers, data) are the same as TRU (the section header anyway, can't say for the resolvers).

to be continued...

Does your pack work OK mate pls or does it work at all?
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-26T21:30:50+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from michalss
>
> going to test it right away  Thx man i dont need to do it anymore  Can you please do it export <-> import to TXT to bin pls ?
That function there is just disabled. Edit 1-3 rows and check it in game. I do not have the opportunity.
## Post #17
- Username: sephiroth99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 24, 2011 3:23 am
- Post datetime: 2013-02-27T04:51:55+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> Sadly, Rebuilder for filelists dont work with TIGER. Anyway here updated filelist. Added ~ 118 filenames.

Paths
Code: Select all%sDesign\Runnables\%s.drm
%sDesign\Image Resources\%s.drm
local\localization\movies\%s.sch
%s\objectlist.txt
%s\objlist.dat
%saudio\streams\
%scinstream\
%s\symbol.ids
Nice, hopefully we find the missing ones soon! What is "Rebuilder" and why it wouldn't work with tiger files?

> Reply from michalss
>
> Does your pack work OK mate pls or does it work at all?
Packer for TR9? I don't think we are at this point, we don't even know the format of the TAFS format yet.


OK so update. I went in search (manually) of the "hidden" files... and I found CDRM files! yay! But they have a new block format. boo. So we need to reverse that, but that's another discussion (new thread?) (another note for the new thread, there was an uncompressed CDRM [yeah I know...] and the underlaying DRM format had the same "version number" as DX3... Interesting to confirm if the new CDRM files are the same.)

Anyway, for the TAFS/tiger files, I noticed something. In the alignment padding between files, there are blocks called "NEXT" and they seem to only have one value (a jump offset? an index?) My guess is that goes with the new DRM format (the "version 22"). 

So next step is to find a way to make sense of those 3 data points (the TAFS format, the new DRM format and the NEXT blocks)
## Post #18
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-27T05:30:51+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> michalss wrote:going to test it right away  Thx man i dont need to do it anymore  Can you please do it export <-> import to TXT to bin pls ?
That function there is just disabled. Edit 1-3 rows and check it in game. I do not have the opportunity.

Sure i will do it this is not a problem. Can you please enable it ?
## Post #19
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-27T06:42:40+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from sephiroth99
>
> 
Nice, hopefully we find the missing ones soon! What is "Rebuilder" and why it wouldn't work with tiger files?
I mean Gibbed.TombRaider.RebuildFileLists

> Reply from michalss
>
> going to test it right away  Thx man i dont need to do it anymore  Can you please do it export <-> import to TXT to bin pls ?
Well maybe sephiroth add support TR9 bins for translatr project. Format easy

```
4 Bytes - Version? (0x36 Always)
4 Bytes - Total Records
216 Bytes - 0xFF
4 Bytes - Null

Next values - strings offsets

for (uint i = 0; i < count; i++)
  {
    Here, some cool operations with strings :)
  }

```
## Post #20
- Username: sephiroth99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 24, 2011 3:23 am
- Post datetime: 2013-02-28T04:47:30+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> Who can look this file ? Seems divided into blocks and compressed?
That's a MUL file. If so, it would then be XMA audio. We'll have to see if they still use a modified ADPCM codec for the PC version.

One thing, it's definitely not the locals.bin file.

> Reply from Ekey
>
> I mean Gibbed.TombRaider.RebuildFileLists
If you look at my github, I there is the format BigFileV3 (for TR9/tiger/TAFS). If you replace in RebuildFileLists the bigfile variable for that new type, it will work. 
I also added your new filenames to my git if you don't mind 


OK I made a new thread for the new CDRM files, see here: [viewtopic.php?f=21&t=10183](http://forum.xentax.com/viewtopic.php?f=21&t=10183)

I haven't looked more at the TAFS files though. Is anyone else researching that?
## Post #21
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-28T05:20:14+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> sephiroth99 wrote:
Nice, hopefully we find the missing ones soon! What is "Rebuilder" and why it wouldn't work with tiger files?
I mean Gibbed.TombRaider.RebuildFileLists
michalss wrote:going to test it right away  Thx man i dont need to do it anymore  Can you please do it export <-> import to TXT to bin pls ?
Well maybe sephiroth add support TR9 bins for translatr project. Format easy
Code: Select all4 Bytes - Language ID (0xFFFFE0 -> %0.2x) - (0x05 - DUTCH) , (0x08 - PORTUGUESE)
4 Bytes - Version? (0x36 Always)
4 Bytes - Total Records
216 Bytes - 0xFF
4 Bytes - Null

Next values - strings offsets

for (uint i = 0; i < count; i++)
  {
    Here, some cool operations with strings :)
  }

Thx mate big file is not a problem, but subtitles and other ingame text is not in local.bin, this is what sephiroth99 trying to find...  i hope you guys manage ti do it
## Post #22
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-28T06:50:56+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from michalss
>
> this is what sephiroth99 trying to find...  i hope you guys manage ti do it
In MUL files all subtitles and SCH (simple text file) for movies
## Post #23
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-28T08:04:17+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> michalss wrote:this is what sephiroth99 trying to find...  i hope you guys manage ti do it
In MUL files all subtitles and SCH (simple text file) for movies

So it is simple texts, i did not find any file where i can simple edit text all packed in mul files not simple text at all? Nice is there anyway to identify in what all files is it in please, i guess it is in all of them ? So unleas there is packer then it is impossible to do localization and not even test with edited text
## Post #24
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-02-28T18:52:03+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

Where to find filenames and how to compare them with there offsets?
## Post #25
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-28T20:21:05+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

For Xbox dump memory regions while you playing game. 

BTW: See file 10466CE1.unknown (symbos.ids ???) he contained interesting info : Dev paths for files, labels and ect.

```
3978,object/sfx/audio_graph/audio_graph_forest/audio_graph_forest
3980,object/sfx/audio_graph/audio_graph_oniden/audio_graph_oniden
3982,object/sfx/audio_graph/audio_graph_spawner/audio_graph_spawner
4044,object/physical/storage/barrels/barrel_exploding_spawner/barrel_exploding_spawner
4046,object/physical/storage/barrels/barrel_exploding_ww2sos/barrel_exploding_ww2sos

```


Just need add in the end strings .drm or .mul and found correct initial path + replace / on \ ... I found all the audio files for DXHR using by this 
Seems sephiroth found 3k files by using B2C36492.unknown (it's objects.dat or objectlist.txt)
## Post #26
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-02-28T21:58:33+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

I have an xbox aslo.

What tools did you use? do you need a jtagged box?
## Post #27
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-01T17:21:42+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

About compress found strings :

```
GFxZlibState - Seems for ScaleForm SWFs
edgezlib_inflate_raw_data.cpp (1.2.3.0-SPU-EDGE)

```


next files need check paths:

```
xenon-w\objlist.dat
xenon-w\unitlist.txt
\tras\game\xenon\tras.arg
\tras\xenon-w\objectlist.txt
\tras\xenon-w\objlist.dat
\tras\xenon-w\unitlist.txt
\tras\local\localization\movies\%.sch - Where % Movie filename without extension

```
## Post #28
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-01T21:07:21+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

awesome that ps3 uses zlib... means PC version will most likely use it as well. 3 more days!
## Post #29
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-01T22:15:58+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

Yeah but after decompressing with ZLIB, files have new compression. You can see here [examples](http://forum.xentax.com/viewtopic.php?p=83423#p83423) (_dec.dat) . Compressed data begin from offset 0x24. 

```
4 Bytes - Compressed Size (Without Header (size 0x24) - Endian Big)
4 Bytes - Decomrpessed Size ? (Endian Big)
4 Bytes - Unknown (Endian Little)
4 Bytes - Unknown (Endian Little)
4 Bytes - Unknown (Endian Little)
4 Bytes - Unknown (Endian Little)
8 Bytes - Nulls
```


I check comtype_scan2 but without results.

> Reply from OrangeC
>
> I have an xbox aslo.

What tools did you use? do you need a jtagged box?
Read [this](http://www.xpgamesaves.com/topic/32897-xbox-360-memory-dumping-realtime-editing/) for example.
## Post #30
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-03-01T22:51:19+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

Okay i see i need to get a jtag. However i am going to be working from pc version and im having trouble finding a good realtime memory dumper.
## Post #31
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-02T19:57:10+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

Updated filelists for PS3: Added names for Patch 1.01
[TR9_PS3_v2.rar](https://xentaxbackup.github.io/file/6234_TR9_PS3_v2.rar)
## Post #32
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2013-03-03T10:52:24+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> Yeah but after decompressing with ZLIB, files have new compression. You can see here examples (_dec.dat) . Compressed data begin from offset 0x24. 
Code: Select all4 Bytes - PS3T (Always)
4 Bytes - Compressed Size (Without Header (size 0x24) - Endian Big)
4 Bytes - Decomrpessed Size ? (Endian Big)
4 Bytes - Unknown (Endian Little)
4 Bytes - Unknown (Endian Little)
4 Bytes - Unknown (Endian Little)
4 Bytes - Unknown (Endian Little)
8 Bytes - Nulls

It's DXT compressed texture (PS3T = PS3 texture?)
[](http://i52.fastpic.ru/big/2013/0303/7c/34f4911b3275fc75d7d50708180cd77c.jpg)

DXT5 with mipmaps in Untitled5_dec (main texture) and DXT1 with mipmaps in Untitled6_dec (normal map)
## Post #33
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-03T13:52:53+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

huh nice 

BTW: they are divided i just join all into one (anyway offzip unpacked by blocks)
## Post #34
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-03-04T23:35:10+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

patch.000.tiger in PC version has ~111MB of dead/unused data. 

Edit: this can't be right... if it is, PC version has 4GB+ of dead/unused data.
## Post #35
- Username: sephiroth99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 24, 2011 3:23 am
- Post datetime: 2013-03-05T00:25:58+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Rick
>
> patch.000.tiger in PC version has ~111MB of dead/unused data. 

Edit: this can't be right... if it is, PC version has 4GB+ of dead/unused data.

If you only check the header, yes there is a lot of dead data. but if you look inbetween the gaps of the files listed in the bigfile header, you will find files. It also doesn't make sense that the main model (laracroft.drm) is only 161KB (xbox version).

Here's my guess with what is currently known. The main, indexed entry is the new drm format (version 22), which only contains pointers to data in the bigfile, which is of the new format too. My other guess is that the "NEXT" blocks indicate the chain ("linked list") of pointed entries, so the drm only points to the first file.

But my main guess is that it's completely wrong lol, and it's way more simple than that. It always is.
## Post #36
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-05T01:37:22+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

This is how the Bigfile works I think, sorry I should have posted this earlier when I figured it out.

1. What you do is, you read the entries normal like File Hash, Locale, Size, Offset.
2. You subtract 0x80 from the offset which will point you to the actual file.
3. This will take you to another file however, it may not be a file table, I recommend reading the first Int which is 0x16 for the file table. It's just some identifier. So if you are at a file table you....
4. Goto 0x17 (relative from start) which is the amount of entries in the file table, there is information about the offsets (you still minus 0x80). Most importantly, these point to the CDRM container offsets etc.
5. Now you need to figure out the size of the .CDRMs i haven't had a look into it I'm currently playing the PC version.

It just uses offsets pointing to a sub file table kind of thing where you can then unpack the CDRMS.

Blah *Goes back ingame*
## Post #37
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-05T05:32:04+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Rick
>
> patch.000.tiger in PC version has ~111MB of dead/unused data. 

Edit: this can't be right... if it is, PC version has 4GB+ of dead/unused data.

Hi Rick,

I did check your repository and i can see you update it with TR9, are you also considering to make packer for PC,X360 please ?
## Post #38
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-03-05T10:12:31+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from michalss
>
> Hi Rick,

I did check your repository and i can see you update it with TR9, are you also considering to make packer for PC,X360 please ?Packer will not be possible until the DRM stuff is understood.
## Post #39
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-05T13:15:07+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

Would be great for a repacker, it seems that no Crystal Dynamics Tomb Raider game has no modding community or any tools to unpack, repack the files because they are so big. I hope that with this game, we get the chance to do this kind of stuff.
## Post #40
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-05T13:38:46+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Rick
>
> michalss wrote:Hi Rick,

I did check your repository and i can see you update it with TR9, are you also considering to make packer for PC,X360 please ?Packer will not be possible until the DRM stuff is understood.

Most likely asking about BIG file only for repack at least something, coz i guess you know structure since you have unpacker done   Thx Just my humble guess
## Post #41
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-05T21:37:23+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

Well game completed. Here PC filelists update (copy in bin_tr9\projects\Tomb Raider 9\files)

```
bigfile_english - +1066
patch - +56
title - +58
pack8 - +10
```

[tr9_projects.rar](https://xentaxbackup.github.io/file/6240_tr9_projects.rar)
## Post #42
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-05T22:22:32+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

So is there an unpacker yet?
## Post #43
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2013-03-05T23:23:28+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

Somebody gonna do model extractor for new TR(PC version)?
## Post #44
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-06T00:38:30+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

model format looks really easy
models start with 0x0600000
stages start with 0x0300000
textures all start with PCD9 + DXT1/DXT3/DXT5
i'm sure somebody will do it since it don't look hard at all

however, you guys must wait for rick and ekey to figure out how the data is organized as I ran Rick's tool today and it doesn't get all the data. There's like 68,000 CDRM sections in bigfile.002 lol. when all the data is decompressed the amount of extracted CDRM data is around 10 GB. There's like 7,341 texture files and they are absolutely lovely (on PC only).
## Post #45
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-07T07:23:53+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

ekey, if you don't mind me asking, how did you get the filenames? did you peek in the exe or did you grab them from the second section of the first bigfile (the sections that have items that start with 0x16 can have a list of strings in between the file offsets and size data, but i parsed all the strings and a lot of names that appear in your list are not in my list).

he he he is this how older TR games were too? the big files are just a list of data sections and you construct files by combining one or more of these sections (many of these sections can be used in more than one file as well)? big files are kind of like files that are composed of one or more hard links to data, right?

the reference count appears to me to be very high... there are 171,698 data sections, but combining files (which are in the second section of the first big file) i get a total of 1,860,361 files .

if you don't get what i mean (cuz i mumble lol), here's code I used to go through all the data in the big files.

```
{
 uint32 temp;
 ifile.read((char*)&temp, sizeof(temp));
 return temp;
}

int main()
{

 //
 // READ TABLE
 //

 using namespace std;
 ifstream ifile("bigfile.000.tiger", ios::binary);
 if(!ifile) return error("shit");

 // skip all the useless shit
 ifile.seekg(0x1A800);
 
 uint32 n_files = 0;

 struct TABLESUBENTRY1 {
  uint32 p01;
  uint32 p02;
  uint32 p03;
  uint32 p04;
  uint32 p05;
 };
 struct TABLESUBENTRY2 {
  uint32 p01;
  uint32 p02;
  uint32 p03;
  uint32 p04;
 };

 struct TABLEENTRY {
  uint32 p01; // 0x16
  uint32 p02;
  uint32 p03;
  uint32 p04;
  uint32 p05;
  uint32 p06;
  uint32 p07; // number of entries
  uint32 p08;
  deque<TABLESUBENTRY1> sub1;
  boost::shared_array<char> namelist;
  deque<TABLESUBENTRY2> sub2;
 };
 deque<TABLEENTRY> entrylist;
 set<uint32> fileset;

 for(;;)
    {
     uint32 currpos = (uint32)ifile.tellg();
     cout << "Table Entry #0x" << hex << entrylist.size() << " at 0x" << currpos << dec << endl;

     TABLEENTRY entry;
     entry.p01 = LE_read_uint32(ifile);
     entry.p02 = LE_read_uint32(ifile); // string length part 1
     entry.p03 = LE_read_uint32(ifile); // string length part 2
     entry.p04 = LE_read_uint32(ifile);
     entry.p05 = LE_read_uint32(ifile);
     entry.p06 = LE_read_uint32(ifile);
     entry.p07 = LE_read_uint32(ifile); // number of sections this file is composed of
     entry.p08 = LE_read_uint32(ifile);
     if(entry.p01 != 0x16) break;
     n_files += entry.p07;

     for(uint32 i = 0; i < entry.p07; i++) {
         TABLESUBENTRY1 se;
         se.p01 = LE_read_uint32(ifile);
         se.p02 = LE_read_uint32(ifile);
         se.p03 = LE_read_uint32(ifile);
         se.p04 = LE_read_uint32(ifile);
         se.p05 = LE_read_uint32(ifile);
         entry.sub1.push_back(se);
        }

     // there can be strings here, they are already null terminated
     // wtf? why did they do this retarded ass shit lol?
     uint32 len = entry.p02 + entry.p03;
     if(len) {
        boost::shared_array<char> name(new char[len]);
        LE_read_array(ifile, name.get(), len);
        entry.namelist = name;
        cout << " ";
        for(uint32 i = 0; i < len; i++) {
            if(name[i] == 0) cout << " ";
            else cout << name[i];
           }
        cout << endl;
       }

     for(uint32 i = 0; i < entry.p07; i++) {
         TABLESUBENTRY2 se;
         se.p01 = LE_read_uint32(ifile);
         se.p02 = LE_read_uint32(ifile); // offset + bigfile index
         se.p03 = LE_read_uint32(ifile); // size of section
         se.p04 = LE_read_uint32(ifile);
         entry.sub2.push_back(se);
         fileset.insert(se.p02); // add offset and bigfile index to set of files
        }

     entrylist.push_back(entry);

     // move to next 0x800-aligned position
     uint32 position = ifile.tellg();
     position = ((position + 0x7FF) & (~0x7FF));
     ifile.seekg(position);
     if(ifile.fail()) return error("Seek failure.");
    }
 ifile.close();

 cout << "Number of entries = 0x" << hex << entrylist.size() << dec << endl;
 cout << "Number of files = 0x" << hex << n_files << dec << endl;
 cout << "Number of unique files = 0x" << hex << (uint32)fileset.size() << dec << endl;

 // WORKS GREAT!
 // now let's read all these entries
 ifstream filelist[4];
 filelist[0].open("bigfile.000.tiger", ios::binary);
 filelist[1].open("bigfile.001.tiger", ios::binary);
 filelist[2].open("bigfile.002.tiger", ios::binary);
 filelist[3].open("bigfile.003.tiger", ios::binary);
 
 for(uint32 i = 0; i < entrylist.size(); i++)
    {
     cout << "Table Entry #0x" << hex << i << dec << endl;
     
     for(uint32 j = 0; j < entrylist[i].sub2.size(); j++)
        {
         // file offset and size of data
         uint32 offset = (entrylist[i].sub2[j].p02 & 0xFFFFFF00);
         uint32 size = entrylist[i].sub2[j].p03;
 
         // big file index
         uint32 bigfile = (entrylist[i].sub2[j].p02 & 0xFF);
         if(bigfile > 3) return error("Invalid bigfile index.");
 
         // move to offset
         filelist[bigfile].seekg(offset);
         if(filelist[bigfile].fail()) return error("Seek failure.");
 
         // read CDRM
         uint32 magic = LE_read_uint32(filelist[bigfile]);
         if(filelist[bigfile].fail()) return error("Read failure.");
         if(magic != 0x4D524443) return error("Not a CDRM section.");
        }
    }

 return 0;
}

```
## Post #46
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-07T12:37:29+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> ekey, if you don't mind me asking, how did you get the filenames?
Writed simple logger. Works like this looping call to hash func and read value from registers (in this case, EAX)
## Post #47
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-07T16:05:47+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> Well game completed. Here PC filelists update (copy in bin_tr9\projects\Tomb Raider 9\files)
Code: Select allbigfile - +391
bigfile_english - +1066
patch - +56
title - +58
pack8 - +10

I was trying to unpack it but do you have fresh latest repo for unpacker somehwhere pls ?
## Post #48
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-07T21:04:58+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

lol you guys want an unpacker that unpacks everything but generates 180,000 files + 1.8 million symoblic links with no filenames ? at least the data in the 5,491 symbolic link directories appear to be organized... man this is crazy, there are some files that are linked to over 1,000 times, which kind of sucks cuz windows has a limit on the number of hard links to a file so i had to use symbolic links. kind of useless without meaningful extensions for the symbolic links but oh well...
## Post #49
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-03-07T21:49:03+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> howfie wrote:ekey, if you don't mind me asking, how did you get the filenames? 
Writed simple logger. Works like this looping call to hash func and read value from registers (in this case, EAX)

Do you mind sharing the logger here?
## Post #50
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-08T04:04:08+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> lol you guys want an unpacker that unpacks everything but generates 180,000 files + 1.8 million symoblic links with no filenames ? at least the data in the 5,491 symbolic link directories appear to be organized... man this is crazy, there are some files that are linked to over 1,000 times, which kind of sucks cuz windows has a limit on the number of hard links to a file so i had to use symbolic links. kind of useless without meaningful extensions for the symbolic links but oh well...
Why do you want to extract the symbolic links? Nobody needs the same file 1000 times, so you need to extract every mesh only once and skip all symbolic links for this file. Inside the game its just a reference to a specific mesh used on different locations. There is no need to extract the references/symbolic links.
## Post #51
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-08T05:51:07+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

heres the problem... files are not referenced by names. some of laras textures are shared amoung the various versions of her models. when processing a mesh, youll see like a number, 17. what texture is that and what directory is it in? stages also use the same tree, light, and statue models. given mesh 5, what model is that? answer: you dont know. but if all data thats used is listed using numeric links, you know. this way automatic texturing should be easy. youll see in an hour when i release my texture tool. hopefully someone else can do the models.
## Post #52
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-08T06:23:33+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

Unpacker for PC version.
[http://www.sticklove.com/content/tr9unpack.7z](http://www.sticklove.com/content/tr9unpack.7z)

Instructions:
1. Copy tiger files into a new, empty directory. It is very important that this directory be initially empty (see photo below).
2. Place ripper.exe and zlib1.dll in this directory as well.
3. Run ripper.exe.
4. Go somewhere for and hour or so and come back.



There will be 4 new directories when done.
bigfile.000\ will contain DRM files. Do not delete these; they are referenced by the files in the link directory.
bigfile.001\ will contain DRM files. Do not delete these; they are referenced by the files in the link directory.
bigfile.002\ will contain DRM files. Do not delete these; they are referenced by the files in the link directory.
bigfile.003\ will contain DRM files. Do not delete these; they are referenced by the files in the link directory.

symbolic_links\ will contain 5,000 or so directories, with each directory containing symoblic links to files in the bigfile directories. symbolic links suck, and i prefer hard links, but windows only allows 1,024 hard links per file linked too.



for example, open up symbolic_links/3358. lara croft is there and more textures for her are in the following directories. 3358 contains a mildly grunged up version of lara. there is also one model file in here, probably a partial lara model (it's only 98 KB so this model is probably an accessory for this version of lara that the other laras don't have.



if you think any one of these symlink files are important (most are shaders and references to scripts), but i believe i renamed all the meshes and texture files, let me know so i can modify it.

as usual, code is [here](http://code.google.com/p/sticklove/source/browse/trunk/source/xentax/ripper/pc_tr2013.cpp).

one note about symbolic links for those who don't know or never heard of them. they are like shortcuts that you can rename like regular files. they are not Windows lnk shortcut files. so for example those dds files in the image... each dds file if you click on properties you see it is 0 bytes lol. double click on it and it will load in your image viewer. Windows treats it as a DDS file even though the actual data for that file is actually in another file (in a DRM file in one of the bigfile directories). deleting the DRM file, renaming the DRM file, or even moving the DRM file, will sever the link. this doesn't happen with hard links but i couldn't use hard links for reasons mentioned above.

have fun, there's like 7,000+ really nice textures. chris... you already working on or finished a mesh converter? you are usually always 5 steps ahead of me .
## Post #53
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-08T07:27:42+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

Updated filelist. Added ~ 1300 names.

> Reply from OrangeC
>
> Do you mind sharing the logger here?
maybe
[tr9_projects_1257.rar](https://xentaxbackup.github.io/file/6246_tr9_projects_1257.rar)
## Post #54
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-03-08T09:07:02+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

Decompressing files... please wait.
Decompressing files for link directory #0x0.
There are 1 symbolic links to this file.
Warning: failed to create hard link to G:\4\bigfile.000\0x2a6fd800.drm.
[report.rar](https://xentaxbackup.github.io/file/6248_report.rar)
## Post #55
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-08T09:11:11+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

what system are you on? if i recall right symbolic links work on vista or higher, but the api is available on XP. do you have the "4/symbolic_links" directory present?

also, if you are running it a second time and already have a symbolic_links directory, delete the symbolic_links directory before running it again. windows does not let you overwrite existing symbolic links.

if you still get error, download it again. i updated the program to print an error code. let me know what your error code is. the 0xb7 (ERROR_ALREADY_EXISTS) i show below means that I didn't delete the symbolic_links directory before running it again. but i tried it right now in a C:\4\ directory and it worked great. don't use wine and if that doesn't work, if G is an external drive, try C (not sure how windows like links on external drives).

another common error is 0x522 (ERROR_PRIVILEGE_NOT_HELD), which means you need to log in as someone with administrator privileges.

```
Decompressing files for link directory #0x0.
There are 1 symbolic links to this file.
Warning: failed to create symbolic link to C:\4\bigfile.000\0x2a6fd800.drm. GetLastErrorCode() returned 0xb7.

```
## Post #56
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-03-08T10:07:37+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

I use Win7 x64. symbolic_links have, but empty(5 492 folders).

0x2a6fd800.drm have 495 bytes.

This is repeats when delete all and start second time too.
## Post #57
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-08T10:10:48+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

ok, get me that error code; as i am on x86, not x64. that file is indeed 495 bytes so looks like it's working just the CreateSymbolicLink function is failing for some odd reason, and that error code would help me out.

also, if anybody else run it and it works (or doesn't work), let me know .
## Post #58
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-03-08T11:17:52+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

I attach .txt with it - error messages not reports, because I run it throught command line.

Decompession process starts if run command line with administrator rights. Tool uses functions, which avaliable under administrator, right?
## Post #59
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-08T13:40:39+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> heres the problem... files are not referenced by names. some of laras textures are shared amoung the various versions of her models. when processing a mesh, youll see like a number, 17. what texture is that and what directory is it in? stages also use the same tree, light, and statue models. given mesh 5, what model is that? answer: you dont know. but if all data thats used is listed using numeric links, you know. this way automatic texturing should be easy. youll see in an hour when i release my texture tool. hopefully someone else can do the models.

Thx for the explanation and your unpacker - works fine for me with Win7 x64 (but needs admin-privilegs). 
I thought we talk just about simple unpacking first, before we go to further features like automatic texture-linking. 

I have looked at various .drm files for the PC-version with my hexeditor.

* There are uncompressed dds-Textures - just needed to be renamed to .dds.
* Unknown Mesh-Files
* Some DirectX-Shader-Files
* Some kind of "FSB4"-Audio-Files
* And many other unknown stuff.

Maybe you can scan more file headers inside your unpacker and rename the files directly instead giving all the same .drm-extension? Its easier to analyze if we could seperate meshes,textures, audios, shaders etc

Btw: The FX-Audio-Files can be converted&renamed to mp3 with [FSB-Extractor](http://aezay.dk/aezay/fsbextractor/FsbExtractor13.02.11.rar). But you have to remove the first bytes (44AC0000000000000000000064000000) until "FSB4" to make it work.
## Post #60
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2013-03-08T15:41:08+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> what system are you on? if i recall right symbolic links work on vista or higher, but the api is available on XP. do you have the "4/symbolic_links" directory present?
Windows XP SP3... "The procedure entry point CreateSymbolicLinkA could not be located in the dynamic link library KERNEL32.dll."

Look forward to a complete extract tool that is Windows XP compatible!
## Post #61
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-03-08T16:35:00+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

bigfile.000 (26 743)
Small part(25 303) - 350 MB (367 334 721 bytes)
Big part(1 440) - 2,76 GB (2 965 174 296 bytes)
FSBs - 273, 4,88 MB (5 126 016 bytes)

bigfile.001 (68 129)
Small part(66 605) - 573 MB (601 041 438 bytes)
Big part(1 522) - 2,58 GB (2 771 429 888 bytes)
FSBs - 1976, 19,6 MB (20 576 480 bytes)

bigfile.002 (66 687)
Small part(64 906) - 648 MB (680 275 109 bytes)
Big part(1 780) - 2,33 GB (2 509 617 208 bytes)
FSBs - 2 745, 34,4 MB (36 110 880 bytes)

bigfile.003 (10 141)
Small part(9 888) - 138 MB (145 369 764 bytes)
Big part(253) - 419 MB (439 840 496 bytes)
FSBs - 64, 1,43 MB (1 502 144 bytes)

Most files is textures in DDS format.
Fast method found audio data(dont sure what the game use fmod only) will be not bad.
## Post #62
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-08T17:29:28+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

can you tell me a filename of a symlink for a mesh file i missed. previous games used 0x3c05 for meshes and i got all those. there maybe a new mesh type. also give name of audio file and i will write program that just renames files.
## Post #63
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2013-03-08T18:29:31+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

I am just curious if you guys are also checking out the additional files, I wonder if they may contain additional goodies, these are some of the ones I noticed on my PC Steam copy:

bigfile_ENGLISH.000.tiger
title_ENGLISH.000.tiger
title.000.tiger
patch.000.tiger

PACK4.000.tiger (dlc)
PACK8.000.tiger (dlc)
## Post #64
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-08T18:42:38+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

+ ~1100

Edited: ops. reattached
[tr9_projects_2451.rar](https://xentaxbackup.github.io/file/6252_tr9_projects_2451.rar)
## Post #65
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-03-08T22:39:56+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

Why would you create actual symbolic links?
## Post #66
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-08T23:32:30+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

because if i copied all the files it would be 100 GB; there is massive data sharing. some CDRM sections are referred to by the file table over 1000 times . what i'd like to know is that there's 180,000 + CDRM chunks, but only 6,000 some names? are MUL files archives with shared CDRM chunks? in the second section of the big file is a bunch of 0x16 entries; each entry contains a list of items that reference a CDRM section and if you count all these items, it comes out to a total of 1.8 million items . copying would have taken forever LOL! i did it the quick and dirty way just to get the textures and mesh files out there so that people can start working on the model format while you and ekey crank it out the hard way .
## Post #67
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-08T23:54:29+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

huh XP support pl0x
## Post #68
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-08T23:58:24+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

hahahahahahahahahahaha for that i would have to copy the data ekey... do you know how long it takes to copy 1.8 million files ?
## Post #69
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-09T00:12:42+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

I have pc with win7 but I'm lazy to copy game. Anyway offzip rullez
## Post #70
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-03-09T04:01:22+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

I think, add in symlink name file name, which linked - very hard to do it manually. And modify\add code for change .symlink extension to another by header(dds, mech, etc)(search\scan in first 64 bytes) also.
## Post #71
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-09T06:20:45+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Researchman
>
> I think, add in symlink name file name, which linked - very hard to do it manually. And modify\add code for change .symlink extension to another by header(dds, mech, etc)(search\scan in first 64 bytes) also.
I agree with the first one. The second one is already done for .dds and .mesh. He can add the fsb-audio files. I think all other files are useless for us at the moment.
But he should rename the .drm files in the bigfile-folders, too. Would be easier to view the unique textures instead of going through thousands of symlink-folders and found millions of duplicates.
## Post #72
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-09T07:29:08+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

that can be done i see what i can do.

btw anyone want to work on the model format? ill only work on it if no one else wants to do it. me lazy lol.
## Post #73
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-03-09T11:06:13+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

I don't have the game so feel free.
## Post #74
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2013-03-09T11:58:40+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

@howfie
thanks for the work on the ripper 

is it possible to "easily" reinject modified textures or is it possible at all?


EDIT:
actually seems simple enough since you already name the file after the correct offset in the bigfiles...

"just" generate a new cdrm file and overwrite the data in the bigfile with that... i guess :X
## Post #75
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-09T13:37:59+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> that can be done i see what i can do.
Would be nice if you can change your hard-coded tiger-filenames to a scandir(*.tiger)-method or something.
So we can extract additional content like title.000.tiger, title_ENGLISH.000.tiger, patch.000.tiger and DLC-Content (PACK4.000.tiger, PACK8.000.tiger) etc (=over 1,5 GB extra data)
Or you could add a console-parameter to specify this filenames seperatly to reduce the extract time.  

> Reply from howfie
>
> btw anyone want to work on the model format? ill only work on it if no one else wants to do it. me lazy lol.
I only know the mesh-format start with 0x0600000.  
Tomb Raider has over 9800 meshes and over 7300 textures.

I really want to know how the textures are connected to the meshes. Some symlink-folders have one or more meshes and mostly multiple dds-textures. 
It could be hard to determine the correct textures for specific parts of the model without any filenames or something inside the mesh-file. Any idea how they are connected, howfie?
## Post #76
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-09T17:35:44+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

about reinjecting textures, scan bigfiles for pcd9. if i recall some were uncompressed. if number afiter pcd9 is 15 it is abrg 32-bit. if changes show, it works. backup files b4 tryin though.
## Post #77
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-03-09T17:39:22+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

^ Wouldn't be possible the game to read the files outside of big files? Like having them in the right directory? Giving an example /meshes/characters/lara/head_diffuse.dds inside the BIG file, but outside of just create the folder from the main directory leading to /lara/ and convert the modded texture to the right DDS version that game use.
## Post #78
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-09T17:43:00+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

lemme try modding a texture right now... lets see how kind crystal dynamics wuz to us.
## Post #79
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2013-03-09T18:02:23+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

good luck.
## Post #80
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-09T18:53:41+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

ok, i modified some unknown small texture in the bigfile and the game ran and didn't complain.
so this is what imma going to do....

pick a texture and i will try to move it to the end of the bigfile.003.tiger by changing all the links that refer to it. is there a zlib compressor anywhere?
## Post #81
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-03-09T19:03:40+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> because if i copied all the files it would be 100 GB; there is massive data sharing. some CDRM sections are referred to by the file table over 1000 times . what i'd like to know is that there's 180,000 + CDRM chunks, but only 6,000 some names? are MUL files archives with shared CDRM chunks? in the second section of the big file is a bunch of 0x16 entries; each entry contains a list of items that reference a CDRM section and if you count all these items, it comes out to a total of 1.8 million items . copying would have taken forever LOL! i did it the quick and dirty way just to get the textures and mesh files out there so that people can start working on the model format while you and ekey crank it out the hard way .No I mean versus having an extra file for any that reference other files, say somefile.drm.resources, .resources would point to the actual (unique) files, instead of using this dumb system that uses real symlinks (and taxes the system for no reason at all -- bad design).

A better tool would be one that allows live browsing of data without extracting it, then export a base DRM with its dependencies through that, instead of unpacking everything.
## Post #82
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-09T19:09:33+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

oh i see now... that would be a great idea but would require writing a more complex tool though
i don't know C# or know the FCL very well and a tool written using my native platform sdk to browse data would take me a few thousand lines of code.
i haven't written an actual windows program in years 
we're supposed to be lazy rick 
400 lines of code, a couple hours worth of work to dump everything
more time to spend with the girlfriend at medieval times last night...
more time to have lots and lots of sex
and sex is more important than saving my hard drive
## Post #83
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2013-03-09T21:02:06+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

@howfie awesome... how about the island map? should be easy to spot any changes to it:

bigfile.002:
0x30b1f000.drm and 0x31489800.drm 

i haven't found the "innocent lara" textures yet... that would be even better cause you could directly check the model @ extras in the main menu :X
## Post #84
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-09T21:26:28+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

ok let me check it out lol
## Post #85
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-09T23:20:01+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

~500+
[tr9_projects_2984.rar](https://xentaxbackup.github.io/file/6255_tr9_projects_2984.rar)
## Post #86
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-10T09:30:24+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

Who has a licensed steam version PM me.
## Post #87
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-10T09:42:05+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

whatcha mean by licensed?
## Post #88
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-10T10:06:36+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> ok, i modified some unknown small texture in the bigfile and the game ran and didn't complain.Nice - now all the nerds are waiting again for the nude-texture-patch.   

But it would be more interesting to figure out the mesh-format to convert them to .obj or something. Was there any progress made?
## Post #89
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-03-10T10:12:49+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

Nude patches by texture edit is so 2000...we need to be able to replace meshes  But, aside from that, yea any progress in getting a readable obj format or even exporting the mesh rigged.
## Post #90
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-10T10:28:35+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

no, i am not working with meshes yet... hoping someone else will take it up. i think mariokart said he was interested in doing this so...

i am just messing around, have to rewrite some zlib code to recompress textures

the format of the items in a CDRM section is pretty easy...

XXYYYYYY - ZZZZZZZZ
XXYYYYYY - ZZZZZZZZ

XX (one byte)
01 - means uncompressed
02 - means zlib

YYYYYY (three bytes)
uncompressed size (when XX is 01, YYYYYY = ZZZZZZZZ)

ZZZZZZZZ (four bytes)
compressed size

texture format is a different story.

PCD9
15000000 or DXT1 or DXT5
unknown #1 (either 0, 1, 2)
size of data
width
height
flag byte (always 01)
flag byte (always 00)
flag byte (00 if DXT, bits per pixel if not DXT)
flag byte (number of mipmaps)
unknown #2 (0, 4, 7)
texture type (1 for color, specular, 3 for unknown, 4 for normal map)

if someone can help me figure out those unknowns...
## Post #91
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-10T10:52:25+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

About [PCD9](http://svn.gib.me/public/crystaldynamics/trunk/Gibbed.DeusEx3.FileFormats/PCD9File.cs) from Rick svn
## Post #92
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-10T11:27:14+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from CMihai
>
> Nude patches by texture edit is so 2000...we need to be able to replace meshes  But, aside from that, yea any progress in getting a readable obj format or even exporting the mesh rigged.
I found [a site](http://gamevixenzone.ryonani.com/hot-stuff-21/tomb-raider-2013-raiding-style-709/) for TR 2013 texture modding via TexMod (including see-through-shirts, lol...)

[](http://postimage.org/image/b9kv83k7h/)
## Post #93
- Username: kekko
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Nov 01, 2008 9:26 pm
- Post datetime: 2013-03-10T14:18:49+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

I haven't checked yet by myself, but I guess TR9 CDRM format should be similar to TRU one.
There's already a nice tool for that and sources are freely available
[http://www.tombraiderforums.com/showthread.php?t=142318](http://www.tombraiderforums.com/showthread.php?t=142318)
Binary: [http://www.volny.cz/pavlicd/UnpackTRU/UnpackTRU3.96.zip](http://www.volny.cz/pavlicd/UnpackTRU/UnpackTRU3.96.zip)
Sources: [http://www.volny.cz/pavlicd/UnpackTRU/U ... .96Src.zip](http://www.volny.cz/pavlicd/UnpackTRU/UnpackTRU3.96Src.zip)
## Post #94
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-10T15:24:14+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

So when can we get the proper extensions, I just can't go through millions of files without knowing what they are all we need is the .mesh,.fsb .tex/dds stuff for now.
## Post #95
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-10T16:30:26+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

ok i take care of that today lol
k i see people use dx9 hacks for texture mods so screw texture replacement.
you guise should tell me sooner so i dont waste all of yesterday writing zlib code and going through 7,000 textures lol. the formats have changed slightly.
just sound right? and then dont save other data right ?
## Post #96
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-10T16:37:43+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> ok i take care of that today lol
just sound right? and then dont save other data right ?
Would love to grab the sound, also it'd be great if you could strip of the first couple of bytes so that it can be used in fsb extractor without having to remove it for all files. The file should start with FSB4. Cheers.
## Post #97
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-10T16:42:22+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

can you find one sample fsb filename?
## Post #98
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-10T16:44:13+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> can you find one sample fsb filename?
0x45a79000.drm is a fsb
## Post #99
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-10T17:00:31+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

thx will be done soon.
## Post #100
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2013-03-10T17:11:20+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> Simple Language Editor (TR9 Xbox) ... Need tests



1) Unpack Tiger BIGs
2) Open local.bin
3) Select string
4) Edit string
5) Save or Continue editing
6) Test it
Delphi 7...
Could you share the source code?
## Post #101
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-10T17:48:04+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

k done.. how do you play FSB files? 
gotta make sure they work
## Post #102
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-10T17:52:17+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> k done.. how do you play FSB files? 
gotta make sure they work
[http://aezay.site11.com/aezay/fsbextractor/](http://aezay.site11.com/aezay/fsbextractor/)

this worked for me
## Post #103
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-10T17:59:12+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

i get a "This sample could not be extracted as the data offset points outside file boundaries."
## Post #104
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-10T18:03:50+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> i get a "This sample could not be extracted as the data offset points outside file boundaries."
worked perfectly fine for me sample:
[0x45a79000.zip](https://xentaxbackup.github.io/file/6257_0x45a79000.zip)
## Post #105
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-10T18:17:19+00:00
- Post Title: Re: Tomb Raider (2012) (PC) (PS3) (XBOX) (*.000.tiger)

ok i see why lol; it doesn't work on the symlink FSB files... actually have to rename the ones in the bigfile folders. almost done.
## Post #106
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-10T18:42:15+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

try this lemme know if it works
gotta step out for today though will fix tonight if something's wrong

just delete previous directories or rename them before running
i advise renaming unless you want to wait an hour to delete the symlink directory lol

this version renames file extension in the other directories and ignores unimportant files (so there are a lot fewer than 1.8 million symlinks this time lolololol). i torture your computer as i have tortured mines. love you guise bunches :* ha hahah ahahahahahahhahhahahha
[TR9TextureRipper.7z](https://xentaxbackup.github.io/file/6258_TR9TextureRipper.7z)
## Post #107
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-10T19:07:05+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> (so there are a lot fewer than 1.8 million symlinks this time lolololol)


Useless files lol
## Post #108
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-10T21:04:32+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

i just noticed need to remove empty directories. do that tonight then work on model format.
## Post #109
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-10T21:17:33+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> you guise should tell me sooner so i dont waste all of yesterday writing zlib code and going through 7,000 textures lol.I have found this site only today, sry 
But be sure, we need a tiger-packer sooner or later   


New ripper works fine, thx howfie.

> Reply from howfie
>
> ...then work on model format.Yeah  The last TR game had a DRM index inside the .mesh for the textures&materials. Take a look at kekkos [sources](http://www.volny.cz/pavlicd/UnpackTRU/UnpackTRU3.96Src.zip) (/Unpacker/MeshParser.cs) Maybe parts of them are similar. If not, good luck to figure it out.
## Post #110
- Username: devilkkw
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Mar 10, 2013 4:21 pm
- Post datetime: 2013-03-10T21:48:25+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

For what version of game are this tool?
Pc version have .tiger file."like as bigfile.000.tiger"
working to source code to open thath,i get "out of memory error".
## Post #111
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-10T21:57:19+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

For PC. Copy in game folder and run
## Post #112
- Username: devilkkw
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Mar 10, 2013 4:21 pm
- Post datetime: 2013-03-10T22:52:02+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

yep,for texture ripper is ok, but for UnpackTRU not work...
## Post #113
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-10T23:01:23+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

UnpackTRU - for Tomb Raider: Underworld. Does not work because the format changed. [here](http://svn.gib.me/builds/crystaldynamics/tombraider9/tombraider9-r117_b74.zip) latest Rick tools.
## Post #114
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-11T00:17:44+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Interesting, anyone know how to convert the MUL files?
## Post #115
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2013-03-11T01:43:31+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> UnpackTRU - for Tomb Raider: Underworld. Does not work because the format changed. here latest Rick tools.
Thank you very much for latest compile of Rick tools.

Sorry if I don't understand, I have uncompiled with Rick tools and the result is many drm files. I understand that some should be textures, shouldn't they? Rename to .dds and cannot open them. I notice a couple people posted images in this thread showing textures, but I can't seem to view any of the files.
## Post #116
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2013-03-11T02:39:29+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from relight
>
> Ekey wrote:UnpackTRU - for Tomb Raider: Underworld. Does not work because the format changed. here latest Rick tools.
Thank you very much for latest compile of Rick tools.

Sorry if I don't understand, I have uncompiled with Rick tools and the result is many drm files. I understand that some should be textures, shouldn't they? Rename to .dds and cannot open them. I notice a couple people posted images in this thread showing textures, but I can't seem to view any of the files.

Use howfie unpacker for that.
## Post #117
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2013-03-11T07:15:34+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from rexil
>
> relight wrote:Ekey wrote:UnpackTRU - for Tomb Raider: Underworld. Does not work because the format changed. here latest Rick tools.
Thank you very much for latest compile of Rick tools.

Sorry if I don't understand, I have uncompiled with Rick tools and the result is many drm files. I understand that some should be textures, shouldn't they? Rename to .dds and cannot open them. I notice a couple people posted images in this thread showing textures, but I can't seem to view any of the files.
Use howfie unpacker for that.
Isn't "howfie unpacker" and "Rick tools" both unpacking the bigfiles? howfie's doesn't work for me, while Rick's does.

Well, I guess I'll just stay away until the tools are finished.
## Post #118
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-11T10:00:26+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Rick's unpacker only unpacks the Bigfile data
Howfie's tool only unpacks the Bigfile + some of the drm data which contains textures, models etc
## Post #119
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-03-11T13:53:54+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

I think, Howfie's tool for unpacking other .tiger archives will be actual too, because adding all other files from .tiger archives in Rick's unpacker will not soon. (not sure because of the format)
## Post #120
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-11T13:59:47+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)


## Post #121
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-03-11T14:58:38+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

.MUL is container\archive files, which store audio data.
## Post #122
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-11T16:51:38+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

~350
[tr9_projects_3239.rar](https://xentaxbackup.github.io/file/6261_tr9_projects_3239.rar)
## Post #123
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-03-11T17:47:13+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from C00L12345
>
> 

Niceee
## Post #124
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-11T17:48:06+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Finally got somewhere with the lods. Still got to test some stuff with this, if anyone knows where Lara is stored let me know thanks.
## Post #125
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2013-03-11T18:11:14+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from C00L12345
>
> Finally got somewhere with the lods. Still got to test some stuff with this, if anyone knows where Lara is stored let me know thanks.

great! but maybe i missed something.. how can you view that mesh files in noesis?
## Post #126
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-03-11T18:19:13+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Researchman
>
> .MUL is container\archive files, which store audio data.I wrote a tool for DX3 which might work (Gibbed.DeusEx3.Demux).
## Post #127
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-11T18:19:54+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from fil1969
>
> 
great! but maybe i missed something.. how can you view that mesh files in noesis?

Made a custom script which is currently a W.I.P gonna be searching for the characters as far as i'm aware:

Alex = 0x6a23c000.mesh [picture](http://i.imgur.com/pZV58Se.png)
Scavenger = 0x58c8c800.mesh [picture](http://i.imgur.com/eDzHfgZ.png)

> I wrote a tool for DX3 which might work (Gibbed.DeusEx3.Demux).

Tried last night says some form of sample rate error.
## Post #128
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-03-11T18:47:59+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> I wrote a tool for DX3 which might work (Gibbed.DeusEx3.Demux).
Dont work.

> g:\7\bin_dx3>Gibbed.DeusEx3.Demux 1.mul
>
> 
>
> Необработанное исключение: System.FormatException: Один из
>
> ементов имел недопустимый формат.
>
>    в Gibbed.DeusEx3.Demux.Program.Main(String[] args)
## Post #129
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-11T19:31:25+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from C00L12345
>
> Finally got somewhere with the lods. Still got to test some stuff with this, if anyone knows where Lara is stored let me know thanks.

try the directories around 3300 or so, where her textures are stored
## Post #130
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-11T19:42:18+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> C00L12345 wrote:Finally got somewhere with the lods. Still got to test some stuff with this, if anyone knows where Lara is stored let me know thanks.

try the directories around 3300 or so, where her textures are stored
Cannot seem to find Lara anywhere i have found:

The Dr guy, The tattoo guy, Roth, Alex, and some of the other baddies.

Is there a quicker way of finding Lara?
## Post #131
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-11T19:44:56+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

let me see... there are some strings i ignored... let me print them out again to see if they give any hints
did you get bones and weights too? how similar is the format to the old one?
## Post #132
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-11T19:52:03+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> let me see... there are some strings i ignored... let me print them out again to see if they give any hints
did you get bones and weights too? how similar is the format to the old one?
No bones, weights yet. I did work a long time ago on the TR8 mesh format but I can't really remember everything. I guess it's similar in many ways though.
## Post #133
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-11T20:00:03+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

oh ok cool. if you want to work on the model format COL, just lemme know so I won't work on it and I can go do something else lol .

laracroft is referenced in directory
4274 (there is one mesh file, it is actually a scene file though, i misnamed the extension)
the single model file in there doesn't look like a character file however
so sorry, doesn't look like the strings help any
maybe rick or ekey could provide some input since they know how the string/filename system works
## Post #134
- Username: CMihai
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-11T23:03:10+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Finally got the bones thanks to chrrox   

Roth:
## Post #135
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-11T23:08:33+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

looks good
## Post #136
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-03-11T23:18:21+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Impressive  Keep us updated!
## Post #137
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2013-03-12T04:13:05+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Wow great stuff. How hard is it to step up to animations once you know the skeletal structure
## Post #138
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-12T08:51:52+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Really nice work, C00L12345.

I hope you will share your current plugin-version with us today. 
There's no harm if it doesn't work 100% at the moment - you can update as often as you want.
## Post #139
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-03-12T09:29:28+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> C00L12345 	
>
> Banned
 
Researchman, спалился, что ты русский =)
## Post #140
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-12T09:39:00+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

COOLs status has always been like that lol; don't know why. phpbb is a free forum and it is somewhat buggy.
## Post #141
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-12T09:52:47+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> COOLs status has always been like that lol; don't know why. phpbb is a free forum and it is somewhat buggy.
So very true, very unique and interesting though lol
## Post #142
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2013-03-12T17:29:39+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

I can fix that if you want; just looks like you have the "Banned" rank for some reason.
## Post #143
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-12T17:37:14+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

+2172
[tr9_projects_5156.rar](https://xentaxbackup.github.io/file/6263_tr9_projects_5156.rar)
## Post #144
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-03-12T18:10:02+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> +2172How did you deal with the hash collision?

```
pc-w\audio\streams\vo\act_03\305_mb_monastery_b\305_mb_040_ready_room\305_mb_040_134_scavenger_a.mul
```
## Post #145
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-12T19:11:14+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Open MUL, go to offset 0x2050 and you can see real name

In this folder pc-w\audio\streams\vo\act_03\305_mb_monastery_b\305_mb_040_ready_room\ only 3 files:

```
305_mb_040_020_lara.mul
305_mb_040_030_lara.mul
```
## Post #146
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-03-12T20:04:57+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> Open MUL, go to offset 0x2050 and you can see real name

In this folder pc-w\audio\streams\vo\act_03\305_mb_monastery_b\305_mb_040_ready_room\ only 3 files:
Code: Select all305_mb_040_010_lara.mul
305_mb_040_020_lara.mul
305_mb_040_030_lara.mulI checked my commits and that name came from one of your lists at some point, so it's all good.
## Post #147
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-12T20:25:11+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

How game generate sounds path's ? I mean from where it takes 305_mb_monastery_b / 305_mb_040_ready_room ?
## Post #148
- Username: TRF
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Mar 13, 2013 4:41 am
- Post datetime: 2013-03-13T07:15:16+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> How game generate sounds path's ? I mean from where it takes 305_mb_monastery_b / 305_mb_040_ready_room ?

That probably works with the .symlink files. If we can only get rid of these 2 million files where we have no use for
## Post #149
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-13T07:22:53+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

page 8, first post silly person! 
ekey and rick are talking about something totally different.
## Post #150
- Username: TRF
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Mar 13, 2013 4:41 am
- Post datetime: 2013-03-13T08:52:50+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

I can't seem to get the ripper to work. Not even looking at the posts on page 8 with Rick doesn't ring a bell here.

I copied it into the game folder and it runs through millions directories, but not a single file is made. I did however manage to get it to work ones and have those files that needs to be made with those millions of symlink files.

Anyways, i can't get the MUL files to open with any program.
Any ideas and tutorials  or at least a little guidance?
## Post #151
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-13T11:19:13+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from TRF
>
> I can't seem to get the ripper to work. [..] I copied it into the game folder and it runs through millions directories, but not a single file is made. [..] Anyways, i can't get the MUL files to open with any program.
Download howies second ripper version (page 8, first post). Run the ripper with administrator privilegs. It extracts the correct .fsb audiofiles. This files can be converted to mp3 with [FSB-Extractor](http://aezay.site11.com/aezay/fsbextractor/).
## Post #152
- Username: TRF
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Mar 13, 2013 4:41 am
- Post datetime: 2013-03-13T11:47:15+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Sorry, but i forgot to copy the rest of the files aswell.
I only copied bigfile.000.tiger and NOT 001, 002 and 003.

It's extracting as we speak and already found fsb files.
Thanks for you help.

EDIT: Can i convert multiple FSB files using FsbExtractor13.03.09 downloaded from this forum?
## Post #153
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-13T12:45:34+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Just copy ripper in game folder and run. You can see created folder like bigfile.00x bla bla bla ect. Why do need to make an additional copy of tiger files (it's -> +8gb)? do not understand
## Post #154
- Username: TRF
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Mar 13, 2013 4:41 am
- Post datetime: 2013-03-13T12:51:12+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

I want to keep my Program Files as clean as possible, so i made a new directory for the extraction folder.
But everything is extracted succesfully.

Now i'm trying to convert the FSB with the FsbExtractor, but i don't want to do all the FSB files seperately.
Is there a way to set FSB Extractor, to convert multiple files?

I can only pick one FSB file and drag it in the program.
## Post #155
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-13T17:35:17+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from TRF
>
> Is there a way to set FSB Extractor, to convert multiple files?
With some extra lines, yes. 
Create a batchfile (fsb.bat) with the following source in the same folder together with fsbextractor.exe and the bigfile.00x-folders.
The batchfile will browse through the bigfile-folders and convert all .fsb-files to a new "audio_mp3"-folder.

```
SET OUTPUT_DIR=audio_mp3
SET BIGFOLDERS=(bigfile.000,bigfile.001,bigfile.002,bigfile.003)

IF NOT EXIST %OUTPUT_DIR% (
	MKDIR %OUTPUT_DIR%
)

FOR %%i IN %BIGFOLDERS% DO (
	ECHO Scanning folder "%%i"
	FOR %%F in (%%i\*.fsb) DO (
		ECHO Converting %%F 
		CALL "fsbextractor.exe" /C /O:%OUTPUT_DIR% "%%F"
	)
	ECHO Done!
)
```


@C00L12345
When will you release your noesis-plugin?
## Post #156
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-13T21:51:54+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

i think i know why you cant find lara... i can't find her HiRez textures... the xnalara guys have told me these textures are around 60 MB each. so she is not in the main bigfile... pretty sure she's in title.000.tiger. i'll do the other tiger files in a day or two as i kind of had started working on something else, but i'll get to it.
## Post #157
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2013-03-13T22:47:43+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> i think i know why you cant find lara... i can't find her HiRez textures... the xnalara guys have told me these textures are around 60 MB each. so she is not in the main bigfile... pretty sure she's in title.000.tiger. i'll do the other tiger files in a day or two as i kind of had started working on something else, but i'll get to it.

What? I saw her 4096x4096 textures in bigfile001. They are 10 mb, nnot 60 LOL XD
## Post #158
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-13T23:19:09+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Kamillho
>
> What? I saw her 4096x4096 textures in bigfile001. They are 10 mb, nnot 60 LOL XDMaybe he means all Lara-Textures (Head, Hair, Chest, Legs, Boots) at the same time.
## Post #159
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-13T23:36:08+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

kamil, really? what filename? i did a DDS search by size and there is only 1 10 MB texture and it is not lara. 
what folder is it in so that C00L can try to dig out the model?
if it's there my windows search filter must be having trouble searching though 1.8 million files .
## Post #160
- Username: TRF
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Mar 13, 2013 4:41 am
- Post datetime: 2013-03-13T23:40:14+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Sammie
>
> TRF wrote:Is there a way to set FSB Extractor, to convert multiple files?
With some extra lines, yes. 
Create a batchfile (fsb.bat) with the following source in the same folder together with fsbextractor.exe and the bigfile.00x-folders.
The batchfile will browse through the bigfile-folders and convert all .fsb-files to a new "audio_mp3"-folder.
Code: Select all@ECHO OFF
SET OUTPUT_DIR=audio_mp3
SET BIGFOLDERS=(bigfile.000,bigfile.001,bigfile.002,bigfile.003)

IF NOT EXIST %OUTPUT_DIR% (
	MKDIR %OUTPUT_DIR%
)

FOR %%i IN %BIGFOLDERS% DO (
	ECHO Scanning folder "%%i"
	FOR %%F in (%%i\*.fsb) DO (
		ECHO Converting %%F 
		CALL "fsbextractor.exe" /C /O:%OUTPUT_DIR% "%%F"
	)
	ECHO Done!
)

@C00L12345
When will you release your noesis-plugin?

Thanks, it worked.
Converting as we speak.
## Post #161
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2013-03-14T00:01:29+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> kamil, really? what filename? i did a DDS search by size and there is only 1 10 MB texture and it is not lara. 
what folder is it in so that C00L can try to dig out the model?
if it's there my windows search filter must be having trouble searching though 1.8 million files .

Lara head from example 0x3017800.dds xd I saw also her body with 4096 xd bigfile001 folder ofc
## Post #162
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-14T00:13:31+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

I did find one of Lara's models but it's a test one I think, is posed and has no bones. It's not her original, the textures could be for that model instead.



I couldn't even find any of the multiplayer characters but here's the list so far:

Baddies: 
0x6368f800.mesh; Guy who attacks Lara with turret.
0x58c8c800.mesh; Scavenger from the beginning of the game.
0xe228000.mesh; The guy who you kill on the boat.
0x3984e000.mesh; Mathias.
0xe8d6000.mesh; Himiko.

Goodies:
0x8e76800.mesh; Roth.
0x6a23c000.mesh; Alex.
0x77bcc800.mesh; Dr. Whitman.
0x4247e000.mesh; Jonah.

Missing:
Lara.
Sam.
Reyes.
## Post #163
- Username: TRF
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Mar 13, 2013 4:41 am
- Post datetime: 2013-03-14T00:38:34+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> kamil, really? what filename? i did a DDS search by size and there is only 1 10 MB texture and it is not lara. 
what folder is it in so that C00L can try to dig out the model?
if it's there my windows search filter must be having trouble searching though 1.8 million files .
ALL LARA TEXTURES IN BIG SIZE.

I found Lara textures with 4096 x 4096 x 24BPP
File numbers are: 

bigfile.000
0x54aa9800
0x5523d000
0x666c7000
0x78ea2000
0x79678800

bigfile.001
0x3017800
0x312ef000
0x37b3000
0x3ec9000
0x71e41000
0x725df800
0x72cd0800

bigfile.003
0x3b9ef000
0x3b251800
0x3c117800
0xca4c800
## Post #164
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-14T01:32:01+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

@C00L
I already played through the game three times.   I know this model. Lara is hanging on a hook at the beginning of a cutscene at the monastery. [[Screenshot](http://i.computer-bild.de/imgs/3/3/2/3/3/6/0/Bildergalerie-Tomb-Raider-745x419-c45300d0d7f272f8.jpg)]

> Reply from C00l12345
>
> I couldn't even find any of the multiplayer characters
There are 16 baddies & 14 goodies in the character selection. If you don't find any of them, maybe there are no "complete" characters in a single .mesh file. They can also use seperate objects for the head,  hair, chest, arms/hands, legs, boots and different clothing of lara and combine them in the game. The textures are splitted in seperated parts too. Theoretically all multiplayer-models can share the same bones from one (unknown) file. Everything is possible. But we can't help you with the search without your current plugin. So please share it with us and we can put our heads together to figure out this stuff faster.
## Post #165
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2013-03-14T08:27:05+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Kamillho
>
> howfie wrote:i think i know why you cant find lara... i can't find her HiRez textures... the xnalara guys have told me these textures are around 60 MB each. so she is not in the main bigfile... pretty sure she's in title.000.tiger. i'll do the other tiger files in a day or two as i kind of had started working on something else, but i'll get to it.

What? I saw her 4096x4096 textures in bigfile001. They are 10 mb, nnot 60 LOL XD

but when i got HD TEXTURES were 64mb each one.. once converted in png are 16mb.. take a look...
## Post #166
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-14T08:37:50+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

looking back yeah i was told 65 mb dds files were output by ninja ripper. now that i think about it,  ninja ripper must output uncompressed texture as size of 4096 x 4096 dxt1 level 0 mipmapped texture is 4096 x 4096 / 2 = 8 mb

level 1 mipmap is 2 mb so overall size should be a little over 10.5 mb.
## Post #167
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2013-03-14T08:47:17+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> looking back yeah i was told 65 mb dds files were output by ninja ripper. now that i think about it,  ninja ripper must output uncompressed texture as size of 4096 x 4096 dxt1 level 0 mipmapped texture is 4096 x 4096 / 2 = 8 mb

level 1 mipmap is 2 mb so overall size should be a little over 10.5 mb.

so ninja exported uncompressed? sorry but i don't understand
## Post #168
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-14T08:56:04+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

correct, and it is not a problem. the hunt for lara continues. c00l, tomorrow ill check the other bigfiles to see if they are there.
## Post #169
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2013-03-14T09:10:10+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> correct, and it is not a problem. the hunt for lara continues. c00l, tomorrow ill check the other bigfiles to see if they are there.

but if you search sorting by size, i presume is more easy find characters... or not?
## Post #170
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2013-03-14T09:55:39+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

drm files from smaller tiger files (title, patch, dlc) also resolves cdrm's from other tiger files
for example, pc-w\laracroft.drm (1680943a.drm):
first one from bigfile.000 (with so-called priority 0x00) resolves to cdrms in bigfile only;
next one from title update with priority 0x40 resolves to cdrms in title.000 and bigfile.000 (priorities 0x40 and 0x00)
and one from patch.000 with priority 0x41 resolves to cdrms in patch.000, title.000 and bigfile.000 (priorities 0x41, 0x40 and 0x00)
so Rick is right - complete unpacking will be very difficult - we need a tool that load info from all tiger files and can export needed drms with all related cdrms.
## Post #171
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-14T10:43:26+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

when all these cdrms are put together in their mul files, the size of the overall data must be friggin huge!
## Post #172
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-14T11:21:59+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

axsis has me thinking... i must be doing something wrong and might not be touching all the CDRM sections in the main bigfile, cuz what the other guys have marked as laracroft.drm, according to my code, resolves to a flat square mesh, some effects textures, and some sound effects. i'll check to see what i missed, and then look in the other bigfiles to see if we can figure out what the smaller ones grab from it.
## Post #173
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-14T12:20:28+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Axsis
>
> and one from patch.000 with priority 0x41 resolves to cdrms in patch.000, title.000 and bigfile.000 (priorities 0x41, 0x40 and 0x00)
> Reply from howfie
>
> cuz what the other guys have marked as laracroft.drm, according to my code, resolves to a flat square meshSounds like a simple priority-overwrite to use newer meshes published by patches, instead of using older ones. If bigfile.000 contains a lara-dummy (flat square with priority 0x00), and title.000 (0x40) overwrites this bigfile.000-dummy, and the patch.000 (0x41) overwrite the title.000-mesh, then the  only relevant mesh must be in the patch.000-file!?
## Post #174
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2013-03-14T12:45:56+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

testing my bms script for .tiger unpacking with parsing drms and unpacking related cdrms...
on smallest patch.000.tiger (212 Mb) i've extracted 15168 CDRMs, "count occurrences" of "CDRM" text in patch.000.tiger gives 15169 occurrences (same 15169 for "NEXT" text, except 5 occurrences in translation). don't know why 1 CDRM is not extracted - probably unused (or at least not referred in any drm inside patch.000.tiger itself)
bad thing is that quickbms has no option to autoskip files already on disk (only skip one by one manually or overwrite all).
i've selected "overwrite all", so every time cdrm was referenced in drm script overwrited extracted file. this leads to pretty slow extraction, but again - no duplicates on disk 

```
Press RETURN to quit
```

really extracted only 18820 files (3652 files from .tiger FAT and 15168 referenced cdrm files) other are just overwrites. and it takes 6:20 to unpack just 200 Mb, i wonder how many time it would take to unpack all bigfiles... 


Added:

> Reply from Sammie
>
> Sounds like a simple priority-overwrite to use newer meshes published by patches, instead of using older ones. If bigfile.000 contains a lara-dummy (flat square with priority 0x00), and title.000 (0x40) overwrites this bigfile.000-dummy, and the patch.000 (0x41) overwrite the title.000-mesh, then the  only relevant mesh must be in the patch.000-file!?
Yes, it seems so. And keeps patches small.

Added2:
Forgot to mention that I've only unpacked cdrms from current .tiger and skip those ones that refer to another .tiger files.
## Post #175
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-14T13:41:36+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Axsis
>
> and it takes 6:20 to unpack just 200 Mb, i wonder how many time it would take to unpack all bigfiles...

muahahahahahahahahahahaha
## Post #176
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-14T13:45:45+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Small filelist update +170

For Rick: hash collision 

```
vs
pc-w\audio\streams\vo\multiplayer\505_mp_reaction_barks\505_mp_070_jump_heavy\505_mp_070_045_rescue_pilot_12.mul
```


Invalid 

```
pc-w\audio\streams\vo\multiplayer\510_mp_generic_barks\510_mp_200_adaptation_affirmation\510_mp_200_1008_nikolai.mul
```


btw: Ripper for WinXP perhaps useful to someone /wave howfie  


[TR9_Ripper_WinXP_Projects_5332.rar](https://xentaxbackup.github.io/file/6267_TR9_Ripper_WinXP_Projects_5332.rar)
## Post #177
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-15T13:47:28+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Been making updates to the script after Chrrox suggested that the overlapped UV maps were probably due to the meshes having multiple pieces which is correct. I have updated the script and I can confirm it's right.  

Spent a while finding Jonah's textures but I couldn't find his hair ones:




Any news on finding Lara? I see her textures in Bigfile.001, I will check meshes all meshes smaller than 300kb and see if she turns up! Maybe Lara.drm is the answer.
## Post #178
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-15T14:41:37+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

And how to help you? Maybe you share script before ask like : any one find model Lara? WTF? I see only useless screens from Noesis friggin and nothing useful.
## Post #179
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-15T15:11:32+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> And how to help you? Maybe you share script before ask like : any one find model Lara? WTF? I see only useless screens from Noesis friggin and nothing useful.
lol, that's just what I was thinking the whole time. We all want to help, but we cannot if you don't share your current plugin-version, c00l.

> Reply from C00l12345
>
> I couldn't find his hair ones:
Try this hairs - all in bigfile.001
0x76721000 // brown 2048
0x769ad800 // brown 1024
0x3fef4000 // blonde 2048
0x775aa800+0x776df000  // blonde+spec 1024
0x3e946800 // brown 2048
0x45ac2000 // brown 2048
0x4a1a6800 // brown short 2048
0x4a5e3000 // darkbrown short 1024
0x4bf9f800 // blond tail
0x4ae77800 // brown tail
0x4af7e000 // brown tail
0x62cb2000 // white
0x6d44e800 // brown
0x71661000+0x716dd000 //brown 1024+specc
0x71714800+0x71aa9800 //brown 2048+specc
## Post #180
- Username: Ekey
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-15T15:56:08+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> And how to help you? Maybe you share script before ask like : any one find model Lara? WTF? I see only useless screens from Noesis friggin and nothing useful.

I was actually expecting an unpacker which unpacks the Bigfile, with their DRMs + assets in correct folder/subfolders so that this wouldn't be a problem. I don't quite understand why you find the screenshots I have posted "useless". It's showing progress with the Noesis plugin so how is it useless? The screens weren't posted in reference to the search for Lara so what's so useless?

I am more than happy to release early scripts but I honestly wanted to get everything done beforehand. As i respect people have been patient I will release the most stable script which you can grab in the attachment below. I recommend you only use this for model viewing and there may be issues so just be aware.

Look forward to see you guys add to the character finding list:

```
0x6368f800.mesh; Guy who attacks Lara with turret
0x58c8c800.mesh; Scavenger from the beginning of the game.
0xe228000.mesh; The guy who you kill on the boat.
0x3984e000.mesh; Mathias.
0xe8d6000.mesh; Himiko.
0x2ed37800.mesh; Generic Scavenger

Goodies:
0x8e76800.mesh; Roth.
0x6a23c000.mesh; Alex.
0x77bcc800.mesh; Dr. Whitman
0x4247e000.mesh; Jonah.
0x1cb6d000.mesh; Helicopter Pilot

Missing:
Lara.
Sam.
Reyes.
Grim.
Steph.
+Multiplayer Characters.

```

[TRAS PC.zip](https://xentaxbackup.github.io/file/6269_TRAS PC.zip)
## Post #181
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-15T15:58:00+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Thanks for script. Now we have biggest chances to find model lara
## Post #182
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-15T16:09:36+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> Thanks for script. Now we have biggest chances to find model lara
It's so weird. I checked every model between sizes 350kb+ (to the largest) in each bigfile and nothing. I guess you should all check files lower than 350kb.
## Post #183
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2013-03-15T16:41:53+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from C00L12345
>
> Ekey wrote:Thanks for script. Now we have biggest chances to find model lara 
It's so weird. I checked every model between sizes 350kb+ (to the largest) in each bigfile and nothing. I guess you should all check files lower than 350kb.

thanks for sharing..  i want help you.. but i have 2 questions:
1: can you open all .mesh files in noesis? cause i can open only a 10%
2: what about uvmaps?  i checked in max and every model i try has not uv's....
## Post #184
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-15T16:45:22+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from C00L12345
>
> I was actually expecting an unpacker which unpacks the Bigfile, with their DRMs + assets in correct folder/subfolders so that this wouldn't be a problem.
The problem is, that many assets where used 1000 times from different meshes, especially wood/stone textures. To prevent an indeterminately large number of duplicates its not a good idea to unpack this stuff in folders and have the same textures 1000 times on harddisc in different folders. Maybe its possible to auto-convert the mesh-files to obj while unpacking and append the unique texture-path to the obj/mtl. But I can't see in your script how you connect the textures to the meshes like in your screenshots. UVs are missing, too. Did you remove this code for us?
## Post #185
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-15T16:52:06+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

No, the latest script is not stable and has problems loading some models which I'm looking into, I passed out the latest stable one but once it's sorted I will post it up.
## Post #186
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-15T16:58:04+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Well i have simple drm index parser for get info about sections. Interesting section from (lara_mp.drm) :

```
ID       OFFSET       SIZE
--------------------------
553      4B5D4800     543831
```


CDRM - Total 4 parts (Full decompressed size = 821kb)

Seems its mesh but idk. Noesis msg - File could not be previewed. [Check it](http://www.sendspace.com/file/aaxbwi)
## Post #187
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-15T17:03:50+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> Well i have simple drm index parser for get info about sections. Interesting section from (lara_mp.drm) :
Code: Select all--------------------------
ID       OFFSET       SIZE
--------------------------
553      4B5D4800     543831

CDRM - Total 4 parts (Full decompressed size = 821kb)

Seems its mesh but idk. Noesis msg - File could not be previewed. Check it

The game appears to be using multiple different mesh formats.
## Post #188
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-15T17:53:31+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

yeah there are mesh and scene files, both i named .mesh. in latest unpacker i named them separately. away from home now but u can visit xnaaral's deviantart page in comments i gave him my latest unpacker. still gotta look into the other bigfiles...
## Post #189
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-15T17:56:40+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

btw cool if you ask rich to add you to noesis repo i can help you as well with model format
## Post #190
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-03-15T19:34:44+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

howfire can you upload your ripper on sendspace or something? Dunno why trying to get it from your posts leads me to 404 page   (Edit: Meh, restarting browser did the job..dafuq)

I'm also joining the hunt for Lara and some others as soon I finish compiling some things  

Edit: Found so far...

/bigfile.001/

Grim - 0x25a6c800.mesh
## Post #191
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-16T07:54:08+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

@howfie

Do something like this :

#1


or

#2


Better #2 

Where : 0xAAAAAAAA - It's original hash, 0xBBBBBBBB - Section number
## Post #192
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-03-16T11:04:00+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Checked today about all of big002/3 folders, and no sign of Lara, but her textures are in there, there might be a change that her model to be in one of the meshes that can't be previewed.
## Post #193
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-16T11:14:29+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

So the model in other format, plugin for Noesis that does not support it.
## Post #194
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2013-03-16T13:35:59+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

CDRM at offset 0x6BD91800 in bigfile.002.tiger
size: 784580 bytes, uncompressed: 1154664 bytes, i'm sure there is lara model (at least one of them )
it's biggest cdrm (excluding textures) referenced from "pc-w\laracroft_clean.drm". other cdrms are <16 kb
and textures referenced from "pc-w\laracroft_clean.drm" are both for clean and dirty lara 

ps: я так понимаю тут русскоговорящих много?
## Post #195
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-16T14:06:01+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Axsis
>
> CDRM at offset 0x6BD91800 in bigfile.002.tiger
size: 784580 bytes, uncompressed: 1154664 bytes, i'm sure there is lara model (at least one of them )
it's biggest cdrm (excluding textures) referenced from "pc-w\laracroft_clean.drm". other cdrms are <16 kb
and textures referenced from "pc-w\laracroft_clean.drm" are both for clean and dirty lara

Here info about sections for Lara drm's

> Reply from Axsis
>
> 
ps: я так понимаю тут русскоговорящих много?
Да я бы не сказал что много 
[Lara_sections.rar](https://xentaxbackup.github.io/file/6273_Lara_sections.rar)
## Post #196
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-16T14:13:39+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> 
Where : 0xAAAAAAAA - It's original hash, 0xBBBBBBBB - Section number
I don't understand your format. Is this a symlink-structure?
When you scan the tiger files you loop through 5492 "link-directorys".
Every link-directory contains a number of sections (howdies symlinks) - or in other words, data-offsets to the original files (the CDRM-Sections).
The CDRM-Sections are sometimes splitted in zlib-compressed data-sections, but that is irrelevant.

While looping through the link-directorys and there sections, the first appearance of the target file (mesh,dds,fsb...) is saved (filename=CDRM-Offset) in the "bigfile.00x"-folder. All other sections linked to the same offset will be skipped. So you have only one Offset-Filename per file.

So what is your 0xAAAAAAAA and 0xBBBBBBBB in this scenario and where should be the unique files stored?

> Reply from Ekey
>
> So the model in other format, plugin for Noesis that does not support it.
Yes, there are meshes starting with different bytes (c00l's plugin support only 0x06), but there are others starting with 0x04,0x03 and a few others with no specific header (bigfile.001/0x29f99800.mesh)
0x06 = 9555 files
0x04 =233 files
0x03 = 417 files
0x?? = 170 files 
---------------
Total 10375 meshes

> Reply from Axsis
>
> CDRM at offset 0x6BD91800 in bigfile.002.tiger
size: 784580 bytes, uncompressed: 1154664 bytes, i'm sure there is lara model (at least one of them ) it's biggest cdrm
You think its Lara, cuz its the biggest cdrm? I don't believe Lara is a 70 MB mesh. Maybe around ~1 MB. 
70 MB sounds like a complete scene-file or something else really big. The biggest meshes have a 0x03 starting-byte.

It makes no sense to guess where lara could be. We have to analyze the other mesh-formats, then we will found Lara.
## Post #197
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-16T15:35:35+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Sammie
>
> Ekey wrote:
Where : 0xAAAAAAAA - It's original hash, 0xBBBBBBBB - Section number
I don't understand your format. Is this a symlink-structure?
When you scan the tiger files you loop through 5492 "link-directorys".
Every link-directory contains a number of sections (howdies symlinks) - or in other words, data-offsets to the original files (the CDRM-Sections).
The CDRM-Sections are sometimes splitted in zlib-compressed data-sections, but that is irrelevant.

While looping through the link-directorys and there sections, the first appearance of the target file (mesh,dds,fsb...) is saved (filename=CDRM-Offset) in the "bigfile.00x"-folder. All other sections linked to the same offset will be skipped. So you have only one Offset-Filename per file.

So what is your 0xAAAAAAAA and 0xBBBBBBBB in this scenario and where should be the unique files stored?
I know about all struct's TIGER DRM and CDRM files. It's just template pic lol
## Post #198
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-16T16:25:52+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> I know about all struct's TIGER DRM and CDRM files. It's just template pic lol
I know, but what should howfie do with this kind of template-structure?
## Post #199
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-16T17:05:56+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

cool thx ekey ill look into it soon. took a break for a few days to extract models from metal gear rising .
## Post #200
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-16T17:35:55+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

@howfie. Okay. See pm
## Post #201
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2013-03-16T19:11:12+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Sammie
>
> You think its Lara, cuz its the biggest cdrm? I don't believe Lara is a 70 MB mesh. Maybe around ~1 MB. 
70 MB sounds like a complete scene-file or something else really big. The biggest meshes have a 0x03 starting-byte.

It makes no sense to guess where lara could be. We have to analyze the other mesh-formats, then we will found Lara.
where did you see 70 mb? 700kb compressed, 1 mb uncompressed.
and it is not just guess, as i wrote, i parsed through drm structure of laracroft_clean.drm, it have references to 515 cdrm objects, 67 of them are textures (from <100 bytes to >4 mbytes in size) and only 1 object, except textures have size more than 16 kb and type 0x0C, which is "RenderMesh" according to Rick's description of DeusEx3 DRM format description. textures are still 0x05.
anyone tried to load this mesh using current script from C00L12345?
## Post #202
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-16T19:43:26+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

axsis, in that directory (on mines symlink directory 2878, the textures are indeed lara). haven't checked the model format yet. ekey sent me some code to help me identify names i think so i can rename those folders according to the names he extracted (it contains a mix of some of rick's code and mines). will work on it soon. if you guys want, if c00l's code doesn't work on the mesh file, i can quickly hardcode the model out of there if you want it.
## Post #203
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-16T21:28:38+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Okay guys, its correct, thats lara.   

[](http://postimage.org/image/f42xrd5on/)
## Post #204
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-16T21:43:20+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

cool, how much does c00l's script extract?
## Post #205
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-16T22:01:26+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> cool, how much does c00l's script extract?
For Lara I had to remove the bones-part and set to MESH_START manually to 0x6E68 and Lara loads fine.
I think with a little rewrite at the beginning of the script to auto-detect the correct Mesh & Bones-offsets for all mesh-types it could load the other meshes, too.
Maybe c00l can fix this tomorrow and add UV-support.
## Post #206
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-16T22:06:34+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

oh ok I see, he is having trouble detecting the size of the header before the mesh. the size of the header is actually stored in the file table; i can redo the ripper to strip the headers from the mesh files if you want c00l. i left the headers in there because i thought they might be important (the header information for the texture files were important so i left these in as well, but stripped them from the audio files).
## Post #207
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-16T22:30:57+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Can you tell me which file Lara is in so I can investigate this?

Cheers.
## Post #208
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-16T22:33:44+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

CDRM header maybe contained about file types? I can not check it now because I do not at home.

> Reply from C00L12345
>
> Can you tell me which file Lara is in so I can investigate this?

Cheers.

> Reply from Axsis
>
> CDRM at offset 0x6BD91800 in bigfile.002.tiger
size: 784580 bytes, uncompressed: 1154664 bytes, i'm sure there is lara model (at least one of them )

or [here](http://www.sendspace.com/file/yr2w1z) if you lazy
## Post #209
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2013-03-16T23:59:46+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> CDRM header maybe contained about file types? I can not check it now because I do not at home.
not cdrm, but drm have object type field, that is seems to be the same as stated in [http://svn.gib.me/public/crystaldynamic ... ionType.cs](http://svn.gib.me/public/crystaldynamics/trunk/Gibbed.DeusEx3.FileFormats/DRM/SectionType.cs)
as you already know, drms have two tables - first, with records length 20 bytes, and second with 16 bytes. second dword of every record in first table is object type, in second table it's fourth byte of each record.
## Post #210
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-17T00:20:51+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

correct, there is also a subtype byte in the third dword. the codes have not changed from the previous games.

```
            if((entrylist[i].sub1[j].p03 & 0xFF) == 0x30) targext += "scene";
            else targext += "mesh";
           }

```
## Post #211
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-17T00:23:04+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Axsis
>
> Ekey wrote:CDRM header maybe contained about file types? I can not check it now because I do not at home.
not cdrm, but drm have object type field, that is seems to be the same as stated in http://svn.gib.me/public/crystaldynamic ... ionType.cs
as you already know, drms have two tables - first, with records length 20 bytes, and second with 16 bytes. second dword of every record in first table is object type, in second table it's fourth byte of each record.
Not noticed. Check it later. Thanks.
## Post #212
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-17T00:58:27+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from C00L12345
>
> Can you tell me which file Lara is in so I can investigate this?
all meshes starting with 0x59 (except the dummy with 90kb) is Lara with different outfits

```
000:55A22000
000:79FD9800
000:7BE1B000
000:7C4F9000
000:7D1C9000
001:0452D800
001:29F99800
001:31C2C800
001:69873800
001:714FF800
001:746F2800
002:6BD91800
002:6C88C000
002:7AAD9800
003:0D26B800
```
## Post #213
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-03-17T03:37:42+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Is there a working MUL demuxer yet?
## Post #214
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-03-17T04:29:12+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Sammie
>
> C00L12345 wrote:Can you tell me which file Lara is in so I can investigate this?
all meshes starting with 0x59 (except the dummy with 90kb) is Lara with different outfits
Code: Select all000:3801C000
000:55A22000
000:79FD9800
000:7BE1B000
000:7C4F9000
000:7D1C9000
001:0452D800
001:29F99800
001:31C2C800
001:69873800
001:714FF800
001:746F2800
002:6BD91800
002:6C88C000
002:7AAD9800
003:0D26B800

Are those really lara models??

When I try to open this file in noesis:

0x7aad9800.mesh

I get: File could not be previewed.
## Post #215
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-17T06:00:06+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

some files you have to go into the script and change the offset to the "Mesh"
anyways, c00l asked me if i could finish what he started so i'm taking his code and adding to it. format is pretty easy.

```
07000000 00002A00 A0060000 600F0000 00000000 00000000 00000000 000F0000 D80A0000 00000000 00000000 D20D0000
01000000 00002A00 60070000 A0430200 00000000 00000000 00000000 40430200 10010000 00000000 76290000 2F010000
07000000 00002A00 20080000 407B0200 00000000 00000000 00000000 E07A0200 F90B0000 00000000 032D0000 F8120000
04000000 00002100 E0080000 40EA0400 00000000 00000000 00000000 E0E90400 070F0000 00000000 EB650000 95140000
08000000 00002A00 80090000 20F80700 00000000 00000000 00000000 C0F70700 770B0000 00000000 AAA30000 21100000
03000000 00002A00 400A0000 A07A0A00 00000000 00000000 00000000 407A0A00 D7060000 00000000 0DD40000 F9090000
01000000 00002A00 000B0000 20FA0B00 00000000 00000000 00000000 C0F90B00 BF030000 00000000 F8F10000 F0050000
01000000 00002A00 C00B0000 60CC0C00 00000000 00000000 00000000 00CC0C00 AA010000 00000000 C8030100 73020000
01000000 00002A00 800C0000 002A0D00 00000000 00000000 00000000 A0290D00 35020000 00000000 210B0100 5F030000
02000000 00002A00 400D0000 00A60D00 00000000 00000000 00000000 A0A50D00 03010000 00000000 3E150100 2B010000
02000000 00002800 000E0000 20DF0D00 00000000 00000000 00000000 C0DE0D00 B4010000 00000000 BF180100 59020000
01000000 00001400 A00E0000 E03E0E00 00000000 00000000 00000000 803E0E00 80020000 00000000 CA1F0100 46040000

D = offset from mesh to vertex 
H = offset from mesh to vertex information
I = number of vertices
K = offset from mesh to index buffer data
L = number of triangles

```


vertex formats also easy stuff:

```
08 00 34 00 00 00 00 00 - 8 entries - 34 bytes per vertex
14 E4 F5 36 14 00 05 00 - 4-byte vector
49 61 7F 3E 18 00 03 00
C0 91 E6 48 0C 00 06 00 - blend weights
D3 D8 56 51 10 00 07 00 - blend indices
01 6F A8 64 2C 00 05 00 - 4-byte vector
2A 90 17 83 28 00 13 00
23 D8 F7 D2 00 00 02 00 - 0x00 position
C3 11 ED F1 30 00 05 00 - 4-byte vector

```


should have a batch ripper within a week (hopefully)
## Post #216
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-17T06:42:13+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Darko
>
> When I try to open this file in noesis:

0x7aad9800.mesh

I get: File could not be previewed.

c00l's script can't load them at the moment. I have made some corrections. The first byte is relevant for the correct headersize detection. So I have to optimize the "noepyCheckType"-function and the headerbyte-skipping. This version can load all regular meshes (no scene-files). Bones are still only supported for the 0x06-files. Maybe someone else can figure out this bones-stuff for the other characters and include the UVs, too.

[[Download](https://www.dropbox.com/s/hxkw495v07c5qgj/fmt_tombraider_mesh.py)]

Here the characters I have found. Duplicates are in the same line.

```
001:746F2800/001:31C2C800 Lara
001:714FF800/001:69873800 Lara
001:0452D800/002:7AAD9800 Lara
000:7D1C9000/000:79FD9800 Lara
000:7C4F9000/003:0D26B800 Lara
000:7BE1B000/000:3801C000 Lara
002:6C88C000/000:55A22000/002:6BD91800 Lara
001:4B5D4800/001:634FF800 Lara
001:476AB800 Lara

001:4ED79800/001:66993000 Alex
000:6A23C000 Alex
002:72EB5000/002:265F7800 Grim
001:4EDD2800/001:666EA800/001:666EA800 Liam
001:50EA6000/001:4863D000/001:4863D000 Roth
001:8E76800 Roth
001:3C6DA000/001:49AF6800 Samantha
001:423B7800 Samantha2
001:758F1800 Samantha3
001:305FA000 Samantha4
001:0ED99800 Samantha4 (lod)
001:46CB4800/001:48490800 Reyes
001:43E08800 Reyes2
001:4247E000 Jonah
000:29F22000/001:355DB800 Zac
001:19A20000 Steph
001:60B3C800/001:634A7000 Pilot
001:4BF20800/001:494B5800 Whitman
001:77BCC800 Whitman
000:0F078800/002:2CD9D000/001:7CDF7800 Victor
002:2C938000 Fisherman

Baddies:
001:5FA09000/001:6359B800 Fixer
001:5DC4E000/001:66301000 Smoker
002:2ADC9000 Smoker
001:5CEDD800/001:60DBE000 Mathias
001:5CFF1000/001:5FC7F800 Father Mathias
001:0EC4B800 Father Mathias2
002:185C8800 Father Mathias3
001:4EBF3800/001:4ECD4800 Scavenger
001:4F171000/001:7EDA4000 Scavenger Bandit
001:4EEFD800/002:0CE36800 Scavenger Archer
001:391B1800/002:0D72F000 Scavenger Scout
001:5CF96800/001:5DEBC000 Saboteur
001:5D180000/001B6E000 Bruiser
001:4EEAB800/001:66C1F800 Executioner
001:635E6000/001:6088E000 The General
001:5D99E000/001:4EE5F800 Vlad
001:5E10A800/002:04DB9800 Creeper
001:71425800 Creeper Arrow
001:64014000/002:572F9800 Soldier
002:16A3A000 Soldier2
001:655C8800/001:66454000 Archer
001:11482000 Archer Warrior

Others:
000:7B0DF800 Himiko 
001:0ED5A000 Himiko Lod
000:3592D800 Unknown Guy
001:49627000 Pirat
001:65621800 Pirat2
001:0D486800 Iron Guy
002:1C620000 Warrior
002:7CDEE800 Massiv Metal Guy
002:566D7000 Shield Warrior
002:566EF000 Sword Warrior
002:774A3800 Arrow Guy
002:00879800 Pilot on parachute
```
## Post #217
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-17T07:58:10+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

dang sammie, you must really love this game lol. i only finished half of it so far (too busy working on other things but maybe after this is all done i'll finish the game). almost caught up to where c00l is at... bones should be no problem. format is going to be a custom 3D model format that can be loaded in blender 2.49b using a python script. anybody know in what file type the animation data is stored?
## Post #218
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-03-17T09:31:15+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

so no interest in the mul files?
## Post #219
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2013-03-17T10:11:09+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

for uv support (only tested on lara sample ) :
just add :

```
rapi.rpgBindUV1BufferOfs(VBUFFER, noesis.RPGEODATA_SHORT, MESH_VERT_STRIDE, 40)

```


also the mesh format may also contain a group descriptor as the mesh actually is wrongly grouped in the current noesis script.
## Post #220
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2013-03-17T10:42:46+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from shadowmoy
>
> for uv support (only tested on lara sample ) :
just add :
Code: Select allrapi.rpgBindPositionBufferOfs(VBUFFER, noesis.RPGEODATA_FLOAT, MESH_VERT_STRIDE, 0)
rapi.rpgBindUV1BufferOfs(VBUFFER, noesis.RPGEODATA_SHORT, MESH_VERT_STRIDE, 40)


also the mesh format may also contain a group descriptor as the mesh actually is wrongly grouped in the current noesis script.

sorry, where i have to add that lines? at what point of the script? thx!
## Post #221
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-17T11:09:05+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

I think you are continuing the old script. Of course, I will feed out the last script i worked on with partial uv map support. Good luck and thanks for the continuation howfie ;] I look forward to it!

@OrangeC, I'm also interested in the MUL files. ^^
@Shadowmoy, you are correct. I think I gave you a newer script where it was fixed but I'm unsure.

You can see the newer script errors an error in the struct.pack and please mind the test stuff. Hope it helps.
[TRAS PC.zip](https://xentaxbackup.github.io/file/6275_TRAS PC.zip)
## Post #222
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2013-03-17T12:00:06+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from C00L12345
>
> I think you are continuing the old script. Of course, I will feed out the last script i worked on with partial uv map support. Good luck and thanks for the continuation howfie ;] I look forward to it!

@OrangeC, I'm also interested in the MUL files. ^^
@Shadowmoy, you are correct. I think I gave you a newer script where it was fixed but I'm unsure.

You can see the newer script errors an error in the struct.pack and please mind the test stuff. Hope it helps.

Wow and now 90% models can't be loaded :/
## Post #223
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2013-03-17T12:05:23+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Kamillho
>
> C00L12345 wrote:I think you are continuing the old script. Of course, I will feed out the last script i worked on with partial uv map support. Good luck and thanks for the continuation howfie ;] I look forward to it!

@OrangeC, I'm also interested in the MUL files. ^^
@Shadowmoy, you are correct. I think I gave you a newer script where it was fixed but I'm unsure.

You can see the newer script errors an error in the struct.pack and please mind the test stuff. Hope it helps.

Wow and now 90% models can't be loaded :/

right! but there is partial uv's support!! Anyway i'm sure they will fix this holy script!

for the correct uv's  layout---> flip vertical and mirror orrizontal
## Post #224
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-17T14:03:35+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Filelist updated (patch 1.0.722.3) Added 233 names.
[tr9_projects_5565.rar](https://xentaxbackup.github.io/file/6276_tr9_projects_5565.rar)
## Post #225
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2013-03-17T16:53:31+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> Filelist updated (patch 1.0.722.3) Added 233 names.
may be a dumb question but what is this filelist for and how do i use it ?
## Post #226
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-17T17:00:56+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

bigfiles are archives that don't appear to contain filenames. we're not sure how they're generated from the bigfile so ekey snags the filenames from the EXE by trapping the contents of eax register from the function that generates filenames. it's really only important if you need names (i don't).
## Post #227
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-17T17:16:47+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from shadowmoy
>
> Ekey wrote:Filelist updated (patch 1.0.722.3) Added 233 names.
may be a dumb question but what is this filelist for and how do i use it ?
Download [this](http://svn.gib.me/builds/crystaldynamics/tombraider9/tombraider9-r117_b75.zip). Unpack. Copy updated filelists in bin_tr9\projects\Tomb Raider 9\files\
## Post #228
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-17T21:23:25+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Found game menus (not all) and converted to [SWFs](http://www.sendspace.com/file/7oo0u6)
Any decompilers work fine... [Example 1](http://pastebin.com/A03XSQ1J) , [Example 2](http://pastebin.com/ySRtELP5)
## Post #229
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-18T16:22:01+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

you're a pretty silly guy c00l. i just went through all 9,985 mesh files and you know, other than the blend weights (uint08/255.0f) and blend indices (uint08), and the fact that there are two different types of UV formats (type 13 = sint16/2048 which you got and type 1 = real32 which you didn't); you were pretty friggin almost done with your noesis plugin lol.  do you want to finish it? i can wait for the models lol.

each vertex buffer is prefaced with a vertex information structure (whose offset is specified in the part list).

-- 0x30-byte vertex
45 3F E1 98 E8 C9 CB 30
06 00 30 00 00 00 00 00
14 E4 F5 36 0C 00 05 00
49 61 7F 3E 10 00 03 00
01 6F A8 64 28 00 05 00
2A 90 17 83 20 00 01 00 -- texture coordinates (2A 90 17 83) vertex offset (20 00) format (01 00 = real32)
23 D8 F7 D2 00 00 02 00
C3 11 ED F1 2C 00 05 00

-- 0x34-byte vertex
AB 18 5F 71 BB 5E E1 31
08 00 34 00 00 00 00 00 - 8 entries - 34 bytes per vertex
14 E4 F5 36 14 00 05 00 - 4-byte vector
49 61 7F 3E 18 00 03 00
C0 91 E6 48 0C 00 06 00 - blend weights
D3 D8 56 51 10 00 07 00 - blend indices
01 6F A8 64 2C 00 05 00 - 4-byte vector
2A 90 17 83 28 00 13 00 -- texture coordinates (2A 90 17 83) vertex offset (28 00) format (13 00 = sint16/2048.0f)
23 D8 F7 D2 00 00 02 00 - 0x00 position
C3 11 ED F1 30 00 05 00 - 4-byte vector
## Post #230
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-18T16:44:13+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> you're a pretty silly guy c00l. i just went through all 9,985 mesh files and you know, other than the blend weights (uint08/255.0f) and blend indices (uint08), and the fact that there are two different types of UV formats (type 13 = sint16/2048 which you got and type 1 = real32 which you didn't); you were pretty friggin almost done with your noesis plugin lol.  do you want to finish it? i can wait for the models lol.

each vertex buffer is prefaced with a vertex information structure (whose offset is specified in the part list).

-- 0x30-byte vertex
45 3F E1 98 E8 C9 CB 30
06 00 30 00 00 00 00 00
14 E4 F5 36 0C 00 05 00
49 61 7F 3E 10 00 03 00
01 6F A8 64 28 00 05 00
2A 90 17 83 20 00 01 00 -- texture coordinates (2A 90 17 83) vertex offset (20 00) format (01 00 = real32)
23 D8 F7 D2 00 00 02 00
C3 11 ED F1 2C 00 05 00

-- 0x34-byte vertex
AB 18 5F 71 BB 5E E1 31
08 00 34 00 00 00 00 00 - 8 entries - 34 bytes per vertex
14 E4 F5 36 14 00 05 00 - 4-byte vector
49 61 7F 3E 18 00 03 00
C0 91 E6 48 0C 00 06 00 - blend weights
D3 D8 56 51 10 00 07 00 - blend indices
01 6F A8 64 2C 00 05 00 - 4-byte vector
2A 90 17 83 28 00 13 00 -- texture coordinates (2A 90 17 83) vertex offset (28 00) format (13 00 = sint16/2048.0f)
23 D8 F7 D2 00 00 02 00 - 0x00 position
C3 11 ED F1 30 00 05 00 - 4-byte vector

Sorry, I'm just too dumb to do it. I bet you could do even better! I just can't do it unfortunately ;(
## Post #231
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-18T16:50:04+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Too dumb???!!! I got stuck and HAD TO LOOK AT YOUR CODE LOL!!!  I don't know what that make me then  . OK, I'll finish it up for ya, if shadowmoy or someone else who knows Rich's Noesis Python API doesn't take your noesis script and add like the 10 lines of code needed to finish it .

ninja edit: codeman! i see you on here... you want to finish this up for c00l?
## Post #232
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-18T16:56:40+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from howfie
>
> Too dumb???!!! I got stuck and HAD TO LOOK AT YOUR CODE LOL!!!  I don't know what that make me then  . OK, I'll finish it up for ya, if shadowmoy or someone else who knows Rich's Noesis Python API doesn't take your noesis script and add like the 10 lines of code needed to finish it .

Main issue is the struct.pack line or the code before it. Not sure why it seems to be erroring for some models. So yeah, I gave up on that one unfortunately if the problem is fixed I will continue it but i just can't seem to figure that one out so I gave up. If Codeman wants to help it'd be cool but I'm sure he has a lot of other stuff to do which is way more interesting
## Post #233
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-18T18:02:37+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

When Ekey finish updating file list, can i extract language files of Tomb Raider 9?
## Post #234
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-18T20:01:29+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from turkgamer
>
> When Ekey finish updating file list, can i extract language files of Tomb Raider 9?
Well in progress. 20579/22828 (90%) . But you can found localization files in next files:

bigfile.000.tiger - Subtitles for movies (Folder default\local\localization\movies\)
bigfile_XXXXXX.000.tiger - Subtitles for movies and Main Text (XXXXXX language name - ENGLISH, RUSSIAN and ect.) (Folders default\local\localization\movies\ , pc-w\local\locals.bin - Main Texts)
## Post #235
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-18T20:32:09+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from Ekey
>
> turkgamer wrote:When Ekey finish updating file list, can i extract language files of Tomb Raider 9?
Well in progress. 20579/22828 (90%) . But you can found localization files in next files:

bigfile.000.tiger - Subtitles for movies (Folder default\local\localization\movies\)
bigfile_XXXXXX.000.tiger - Subtitles for movies and Main Text (XXXXXX language name - ENGLISH, RUSSIAN and ect.) (Folders default\local\localization\movies\ , pc-w\local\locals.bin - Main Texts)

So, can i extract "bigfile.000.tiger,bigfile_XXXXXX.000.tiger" for now ? How can i extract? We are translation group from Turkey, how can we translate this game? Please help us
## Post #236
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2013-03-19T11:15:14+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

> Reply from C00L12345
>
> howfie wrote:Too dumb???!!! I got stuck and HAD TO LOOK AT YOUR CODE LOL!!!  I don't know what that make me then  . OK, I'll finish it up for ya, if shadowmoy or someone else who knows Rich's Noesis Python API doesn't take your noesis script and add like the 10 lines of code needed to finish it .

Main issue is the struct.pack line or the code before it. Not sure why it seems to be erroring for some models. So yeah, I gave up on that one unfortunately if the problem is fixed I will continue it but i just can't seem to figure that one out so I gave up. If Codeman wants to help it'd be cool but I'm sure he has a lot of other stuff to do which is way more interesting
hum if i got time i will take a look but i didn't promise anything
## Post #237
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-19T11:56:33+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

@C00l: its not a good idea to re-index the faces-numIndex on self-contained models - you will run into negative numbers as soon as the last vertices are building faces with the first vertices. 
First of all you have to bind the whole vertices for the mesh and then you can set the triangles-data. Anyway good work to figure out all this stuff.  

I updated my plugin-version with your UV-stuff. [[Download](https://www.dropbox.com/s/hxkw495v07c5qgj/fmt_tombraider_mesh.py)]

And of course we need a method to auto-detect the correct textures per material.

Edit: Bones added for non-0x06 meshes
## Post #238
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-19T15:33:57+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

Here is the latest TR9 unpacker (With latest file lists)
[Latest TR9.rar](https://xentaxbackup.github.io/file/6279_Latest TR9.rar)
## Post #239
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-19T19:27:00+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

So how can i edit "locals.bin" ? Is there any editor or converter? ("Locals.bin" in the attachemend)
[locals.rar](https://xentaxbackup.github.io/file/6280_locals.rar)
## Post #240
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-19T19:35:38+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.000.tiger)

not bad sammie, not bad 
remember, there is an alternative UV type (not all models use scaled signed shorts)
also, don't forget blend weights and blend indices. i described you how to get them in a previous post.
## Post #241
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-19T20:01:10+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> not bad sammie, not bad 
remember, there is an alternative UV type (not all models use scaled signed shorts)
Normally the scaled one should be the regular UVs for the diffuse-texture (itemOffset=0x8317902A /  itemType=19)
The alternative UV (itemOffset=0x8E54B6F3 / itemType=19) is probably for normalmaps or lightmaps. I have only tested the diffuse-textures on 3-4 models.
Let me know if you find a mesh only with the second UV-type without the first one.
## Post #242
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-19T21:46:41+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from turkgamer
>
> So how can i edit "locals.bin" ? Is there any editor or converter? ("Locals.bin" in the attachemend)
Useless idea. Because game have new ugly archive format and that means = No Packing tools. And hardly appears
## Post #243
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-20T05:59:26+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

ekey, isnt it theoretically possible to redirect links from any bigfile to the end of the last bigfile? i was going to try it earlier but then deemed texture modding uneccesary.
## Post #244
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-20T06:04:40+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> ekey, isnt it theoretically possible to redirect links from any bigfile to the end of the last bigfile? i was going to try it earlier but then deemed texture uneccesary.

This is possible i guess, i was able to do localization for X360, but it was really pain and texts are 3 different formats in 3 different files...  really bad BTW. i did it without extraction, however i'm able to only translate 98% of the all texts. All texts have own ID mark in big file that you can use it as start point for each text, however you can only find 98% of all texts, and repack is not needed since all texts are under each other, however true is i did not try longer text then original, but i guess it would work if u cut language under you currectly translating ..... but as i said not on PC but X360.
## Post #245
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-20T07:59:10+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> ekey, isnt it theoretically possible to redirect links from any bigfile to the end of the last bigfile? i was going to try it earlier but then deemed texture modding uneccesary.
Well GL
## Post #246
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-20T11:17:09+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> ekey, isnt it theoretically possible to redirect links from any bigfile to the end of the last bigfile? i was going to try it earlier but then deemed texture modding uneccesary.
I was going to post that but I stopped posting it. Some guy who wanted to make an injector for Tomb Raider Underworld had the same idea to create additional bigfile volumes or to inject it into a patch file so that it still can be loaded. Seems possible.
## Post #247
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-20T18:24:34+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

almost done, parses all 9,800+ models with no errors. a couple days to check to make sure and i'll release a preview (still haven't worked on auto-texturing yet). your code really helped out c00l .
## Post #248
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-03-20T19:15:44+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Thanks for that, and nice to see you got them with weights and everything. About textures, it's meh for me, I can look for them on my own. Just glad that I don't have to rig them and weight paint them as the ones from FC3...
## Post #249
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-20T19:54:02+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> almost done, parses all 9,800+ models with no errors. a couple days to check to make sure and i'll release a preview (still haven't worked on auto-texturing yet). your code really helped out c00l .
Excellent work
## Post #250
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-21T03:51:16+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Updated the noesis plugin to v1.5beta. [[Download](https://www.dropbox.com/s/hxkw495v07c5qgj/fmt_tombraider_mesh.py)]
Added some new parsing-functions for UVs, Normals and Boneweights.

[](http://postimage.org/image/mrirx6udz/)
## Post #251
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-21T04:03:37+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

nice! i see you made the changes to parse the vertex format . pretty easy right ? might as well let ya finish it and i can move on to the new one piece.
## Post #252
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-21T08:36:22+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Very nice work )
## Post #253
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-21T11:43:00+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Well something like that 



File types are identical from DXHR
## Post #254
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-21T15:05:41+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

names!!!!! ha ha ha ha ha go ekey go ekey go!!!!
## Post #255
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-03-21T15:40:40+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Lol Noesis works with symbolic links xD
## Post #256
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-21T15:57:11+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> names!!!!! ha ha ha ha ha go ekey go ekey go!!!!




BTW: I noticed that my logger captures not all names
## Post #257
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-21T16:26:58+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

regarding packer...
go rick go rick go!
## Post #258
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-21T17:32:59+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Picture-Spamming-Time? Okay - Tomb Raider pic of the day
## Post #259
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-21T17:54:56+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)


## Post #260
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-21T19:37:17+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)


## Post #261
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-21T20:08:26+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> 


> Reply from howfie
>
>
## Post #262
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-03-22T09:05:37+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

What's going on
## Post #263
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-22T10:55:55+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from CMihai
>
> What's going on
Nothing. Just for fun 

[see below](http://forum.xentax.com/viewtopic.php?p=84192#p84192) DRM dumper (Tested WinXP, Win7... About Win8 dunno).. Included video how to.

PS: There are bugs... Tool work only with content from bigfile.00x.tiger
## Post #264
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-22T13:38:58+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Nice tool Ekey! Ha ha ha ok, nobody use my ripper tool anymore! We've got filenames and selective extraction now . Did you write that in C# or native Windows SDK?
## Post #265
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-22T13:50:35+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

GUI Delphi / Library MSVS2010

btw: your ripper updated to rev424... upload binary version. i'm lazy to compile
## Post #266
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-22T14:04:23+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

there is no need to update it anymore!  nice work ekey!

the only thing i'm going to do, if sammie doesn't do it, is get the models that he/she couldn't get (quite a few meshes crash noesis).



PS.

Delphi? LOL? You old school man.... you old school . I didn't even know it was still around since Borland/Inprise went under many years ago. Are you using the Embarcadero version now?
## Post #267
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-22T14:08:53+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> there is no need to update it anymore!  nice work ekey!

the only thing i'm going to do, if sammie doesn't do it, is get the models that he/she couldn't get (quite a few meshes crash noesis).



PS.

Delphi? LOL? You old school man.... you old school . I didn't even know it was still around since Borland/Inprise went under many years ago.
Nah i'm just learning Pascal
## Post #268
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-22T14:10:20+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Ekey
>
> Nah i'm just learning Pascal

Advice: Stop .
## Post #269
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-22T14:13:33+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Why  ?
## Post #270
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-22T14:17:47+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

because Borland sucks . most developers i know abandoned the Borland bandwagon many many years ago. they used to have an awesome set of developer tools, but everything went to shit after microsoft bought out all of borland's developers, including Anders Hejlsberg.
## Post #271
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-22T14:20:55+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Dunno. For example on Delphi writed game : [Space Rangers HD: A War Apart (2013)](http://spacerangershd.com) and on BCB writed Act of War series. I do not think it sucks
## Post #272
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-22T14:28:24+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

i didn't say delphi sucks , it's just that the guy who created delphi no longer works on it. he works on C# now . were you programming when borland became inprise for a few years a decade or so ago? some people stuck with them but a lot of people, including myself, abandoned ship on anything Borland lol.
## Post #273
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-22T14:41:59+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Oh okay... Well maybe you right  ... Go write packer on C#  ?
## Post #274
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-22T14:43:56+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

be my guest my fellow programming buddy .











Nah... let Rick do it.
## Post #275
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-22T14:45:49+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> be my guest my fellow programming buddy .











Nah... let Rick do it.
## Post #276
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-22T14:53:11+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)


## Post #277
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-22T14:55:57+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

BTW, for those who come in here and see nothing but picture spam, Ekey posted a nice file extractor a page back or so lol.
## Post #278
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-22T14:57:45+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> 
Okay...

See Below : updated tool. Nothing special, just game path saved in ini settings
## Post #279
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-22T15:04:21+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> the only thing i'm going to do, if sammie doesn't do it, is get the models that he/she couldn't get (quite a few meshes crash noesis).
Can you tell me 2-3 filenames?
## Post #280
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-22T15:10:08+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

sorry sammie, now that ekey posted his extractor, i deleted all of my files. though i do have some notes saved on the files that crashed.

some of the models have a special parts list. normally the three values are 

#1 index buffer start for part
#2 number of triangles in part
#3 number of vertices in part

but in these ones they are something else:

```
                                             --------
                                                 2
2C8B1BBD A6527940 B6E009BE 0000803F 00000000 E0120000 C0250000 B2020000 00000000 00000000 00000000 00000000 00000000 00000000 00000000 FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF
F216BC3E 5A7489C0 99650BC0 0000803F C0250000 80090000 00130000 B2020000 00000000 00000000 01000000 00000000 00000000 00000000 00000000 FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF
5F4EC2BF 09274F41 93045FC1 0000803F C0380000 A0120000 40250000 B2020000 00000000 00000000 02000000 00000000 00000000 00000000 00000000 FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF
031E633F 54544D40 400631C1 0000803F 005E0000 20020000 40040000 B2020000 00000000 00000000 03000000 00000000 00000000 00000000 00000000 FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF

```


it's like

#1 index buffer start for part
#2 number of indices used in part / 2
#3 number of indices used in part
## Post #281
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-22T17:25:58+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Thx howfie, I found the model (003:3CBA8000).. looks like wisps of hair of lara. I can include a [workaround](https://www.dropbox.com/s/hxkw495v07c5qgj/fmt_tombraider_mesh.py), but I think it's not a "real" mesh, cuz if there is only one "face" between two vertices (number of indices / 2), then its not a real face/triangle. The "faceCount" in the facegroups is not divisible by 3, but by 2. So its not a triangle and the reason why rpgCommitTriangles fails. Its more like a spline or something else for hair-dynamics. Just like a start+endpoint of each hair and the "face"-info is the connection between both.

[](http://postimg.org/image/kpe40x181/)

But now we know Lara has 12576 single hairs
## Post #282
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-22T17:37:06+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Fixed strange bug on Win7: "Out of Memory" - while decompression.   

see below
## Post #283
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2013-03-22T17:47:42+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

is it me or lara have 2 skeletons ?

file :0x6bd91800.mesh

what i see :
one skeleton for ingame
one skeleton for facial anims

it is problematic to export it to smd and reimport in max

any clue on this ?
## Post #284
- Username: kekko
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Nov 01, 2008 9:26 pm
- Post datetime: 2013-03-22T18:22:45+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hi, I didn't follow the whole discussion, could someone please point me to the tools that have been developed to unpack the meshes?
Thanks
## Post #285
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-22T18:28:58+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

codeman, it's all under one skeleton for me.



BTW, Ekey, you own the first post, why not update the first post with your tools and link to Rick's SVN binaries as well?
## Post #286
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-22T19:26:36+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> BTW, Ekey, you own the first post, why not update the first post with your tools and link to Rick's SVN binaries as well?
## Post #287
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-22T19:39:30+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

hahahahahaha
## Post #288
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-03-22T20:09:04+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Uhm I'm lost, which importer works with Lara now?  And Ekey unpacker, get filenames and directories?
## Post #289
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-22T21:46:38+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Sammie
>
> But now we know Lara has 12576 single hairs

i'm absolutely envious, that's more hair than i have on my head lol.
## Post #290
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-22T21:55:25+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from CMihai
>
> Uhm I'm lost, which importer works with Lara now?  And Ekey unpacker, get filenames and directories?
1. Unpack (.drm-filenames+directories) with Rick's Tool. 
[http://svn.gib.me/builds/crystaldynamic ... 17_b75.zip](http://svn.gib.me/builds/crystaldynamics/tombraider9/tombraider9-r117_b75.zip)

2. Load .drm-container into Ekey's tool and extract the content
[http://www.sendspace.com/file/dymgkn](http://www.sendspace.com/file/dymgkn)

3. Goto RenderMesh-Folder and load a .mesh-file via noesis-plugin
[https://www.dropbox.com/s/hxkw495v07c5q ... er_mesh.py](https://www.dropbox.com/s/hxkw495v07c5qgj/fmt_tombraider_mesh.py)
## Post #291
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-03-22T22:03:32+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Gratitude
## Post #292
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-23T00:39:06+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Filelist updated. Added ~1000 - 21692/22828 (95%)
[tr9_projects_6781.rar](https://xentaxbackup.github.io/file/6282_tr9_projects_6781.rar)
## Post #293
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-23T14:52:19+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

TR9 unpacker with latest file list (%95)
[tombraider9-r117_b74.rar](https://xentaxbackup.github.io/file/6284_tombraider9-r117_b74.rar)
## Post #294
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-23T15:05:27+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

We are a translation group from Turkey. We want to translate Tomb Raider to Turkish. Now only decompressing files is possible but in the end I think compression will also be possible. So I want to translate the game until a decomp. tool is available. For that reason I need a tool to translate the files in the attachment.
[locals.rar](https://xentaxbackup.github.io/file/6285_locals.rar)
## Post #295
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-03-23T15:28:33+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

This topic is awesome!
The Unpacker doesn't appear to work on these bigfiles
bigfile.001
bigfile.002
bigfile.003
Works fine on all the others though.

Do all the big files contain the same things just in various languages etc?
## Post #296
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-23T16:04:18+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Well DRMs from DLC / PATCH supported.



Can't open models from PACK8

```
Section 596.mesh
Section 599.mesh
```


Other meshes work fine



Download: See Below
## Post #297
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-23T17:43:08+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from lionheartuk
>
> This topic is awesome!
The Unpacker doesn't appear to work on these bigfiles
bigfile.001
bigfile.002
bigfile.003
Works fine on all the others though.
bigfile.000.tiger-bigfile.003.tiger is technically one large file, but splitted in 2GB Parts. You only need to unpack the 000 file to auto-unpack all the additional data in 001-003.

@Ekey
Can you upload some non-working DLC-meshes for me?
## Post #298
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-23T18:12:32+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Sammie
>
> @Ekey
Can you upload some non-working DLC-meshes for me?
Yeah [here](http://www.sendspace.com/file/xkv5ua)
## Post #299
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-23T18:42:15+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Ekey
>
> Yeah here
0x03 header = SceneMesh, not supported
## Post #300
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-23T18:47:55+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Okay. Planned to support?
## Post #301
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-23T18:53:48+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

ekey can you rename those mesh files to .scene? the 4 byte code for meshes is 0xC yeah but the next 4 bytes in the low byte there is a number, it is 0x30 for scenes if i recall right.
## Post #302
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-23T18:56:43+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Ekey
>
> Okay. Planned to support?
Hmmm not at the moment.. some scene files are really large (up to 70mb).
I'm afraid that this files can load very very long with noesis. 

Maybe you want to put the SceneFiles in a different folder in your drm-Dumper . Its easy to find them. Take a look @ [howfies post](http://forum.xentax.com/viewtopic.php?p=83976#p83976).
## Post #303
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-23T20:18:22+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Well okay. Scene files will be in the same folder where .mesh just with extension .scene

Download: [Here](http://www.sendspace.com/file/ow6vqq)
## Post #304
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-25T12:55:59+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

[here](http://www.sendspace.com/file/ix8d97) mesh can't be loaded from main_menu_1_sp_mainmenu_background
## Post #305
- Username: Heartache
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 21, 2010 4:30 am
- Post datetime: 2013-03-25T14:00:16+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

can somebody tell me how i can convert the .mul files into wave/mp3 files? howies ripper isnt working. it seems it doesnt work on windows xp. so atm i dont see a chance to get the .fsb files
## Post #306
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-25T15:57:47+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Currently no tools for convert
## Post #307
- Username: SuperShadic2017
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 01, 2012 8:50 am
- Post datetime: 2013-03-25T17:01:20+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

How do you export the tiger files?
## Post #308
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-26T06:27:55+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

For packing no tools too
## Post #309
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-26T09:25:47+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hope this doesn't die. Tomb Raider has never had a modding scene due to there being no tools available to repack. Such a shame.
## Post #310
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-03-26T13:52:22+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from C00L12345
>
> Hope this doesn't die. Tomb Raider has never had a modding scene due to there being no tools available to repack. Such a shame.
I'm pretty sure the entire XNALARA community would dissagree.. they've been moding skins and stuff in the games for every game since TRIV, pretty successful too.

As for the .mul files, from a quick glance its difficult to tell if the mul files are entire tracks or just certain instruments for tracks, ie: acoustic file is played along side the ambient file for example.
## Post #311
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-26T17:15:20+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from lionheartuk
>
> C00L12345 wrote:Hope this doesn't die. Tomb Raider has never had a modding scene due to there being no tools available to repack. Such a shame.
I'm pretty sure the entire XNALARA community would dissagree.. they've been moding skins and stuff in the games for every game since TRIV, pretty successful too.

As for the .mul files, from a quick glance its difficult to tell if the mul files are entire tracks or just certain instruments for tracks, ie: acoustic file is played along side the ambient file for example.

The only possible modding is texture reskins via using a program called "TexMod". This has been used on all Crystal Dynamics Tomb Raider Games to do character reskins but sadly, there have been no repack tools for those games. The modding scene is incredibly small I mean that would die out very fast. As for the older games Tomb Raider IV had official tool sets released and the formats were pretty simple anyway but those are old.
## Post #312
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-26T18:18:52+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from C00L12345
>
> The modding scene is incredibly small I mean that would die out very fast. As for the older games Tomb Raider IV had official tool sets released and the formats were pretty simple anyway but those are old.The question is, what do you want to modify in such a game? Model & Texture-replacement is useless.  I dont want a redhair-Lara or a big-boobs-Lara. The only interesting thing would be a leveleditor  to create own worlds (DLCs) and share this stuff with other users. But we are not able to do this without knowning everything about all the other data, especially scripts (KI, Triggers, Events) and all kind of de/encryption. Surely, its not impossible to figure this out, but it would be time wasting. And Crystal Dynamics wouldn't support that. ^^
## Post #313
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-26T19:29:37+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

I do not think that will be more tools. Main objective is complete. Archives unpacked (models, textures, text ect)
## Post #314
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-03-26T19:38:26+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Ekey
>
> I do not think that will be more tools. Main objective is complete. Archives unpacked (models, textures, text ect)

Lol The target of all of this is the xna lara/xps community??
## Post #315
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-26T20:03:46+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

localization is good example why repack is needed. I mean repack of archive not models or other useless things.... Think about it models gonna use only a few people but make it possible for localization it will use millions of people, so for me main task it always to get localization possible and rest thing later on, i guess this is should me main task for every game... Coz with that you gonna help millions of people around the worlds where they can translate the game to their own language..  This is my opinion and trust me there will me lots of ppl feel it same way
## Post #316
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2013-03-26T23:16:59+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Darko
>
> Ekey wrote:I do not think that will be more tools. Main objective is complete. Archives unpacked (models, textures, text ect) 

Lol The target of all of this is the xna lara/xps community??

The target was to unpack archives. What people do with those archives is their own call whether xnalara or games that are modding friendly/possible.
## Post #317
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-26T23:56:57+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Sammie
>
> C00L12345 wrote:The modding scene is incredibly small I mean that would die out very fast. As for the older games Tomb Raider IV had official tool sets released and the formats were pretty simple anyway but those are old.The question is, what do you want to modify in such a game? Model & Texture-replacement is useless.  I dont want a redhair-Lara or a big-boobs-Lara. The only interesting thing would be a leveleditor  to create own worlds (DLCs) and share this stuff with other users. But we are not able to do this without knowning everything about all the other data, especially scripts (KI, Triggers, Events) and all kind of de/encryption. Surely, its not impossible to figure this out, but it would be time wasting. And Crystal Dynamics wouldn't support that. ^^
Yeah, I really needed a TR8 repacker because I wanted to attempt to port the Xbox 360 exclusive maps to see how it'd run but there are no such tools. I guess you are right, not much can be modded i this game but i wouldn't mind importing different music, playing with triggers, adding enemies etc.
## Post #318
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-27T06:39:54+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from C00L12345
>
> Sammie wrote:C00L12345 wrote:The modding scene is incredibly small I mean that would die out very fast. As for the older games Tomb Raider IV had official tool sets released and the formats were pretty simple anyway but those are old.The question is, what do you want to modify in such a game? Model & Texture-replacement is useless.  I dont want a redhair-Lara or a big-boobs-Lara. The only interesting thing would be a leveleditor  to create own worlds (DLCs) and share this stuff with other users. But we are not able to do this without knowning everything about all the other data, especially scripts (KI, Triggers, Events) and all kind of de/encryption. Surely, its not impossible to figure this out, but it would be time wasting. And Crystal Dynamics wouldn't support that. ^^
Yeah, I really needed a TR8 repacker because I wanted to attempt to port the Xbox 360 exclusive maps to see how it'd run but there are no such tools. I guess you are right, not much can be modded i this game but i wouldn't mind importing different music, playing with triggers, adding enemies etc.
BIGFileTool can pack for TRU
## Post #319
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-27T13:48:42+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Never heard of such tools, can you point me to them?

Thanks.
## Post #320
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-27T14:28:17+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

[Here](http://www.tombraiderforums.com/showthread.php?t=181335)
## Post #321
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-27T15:46:39+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

I want to localize this game, is there any packer ?
I found this link : [http://www.tombraiderforums.com/showthr ... 335&page=4](http://www.tombraiderforums.com/showthread.php?t=181335&page=4)
But download link is not avaible. Can anybody send a new link ?
Is this tool can pack ?
## Post #322
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-27T16:08:07+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from michalss
>
> localization is good example why repack is needed. I mean repack of archive not models or other useless things.... Think about it models gonna use only a few people but make it possible for localization it will use millions of people, so for me main task it always to get localization possible and rest thing later on, i guess this is should me main task for every game... Coz with that you gonna help millions of people around the worlds where they can translate the game to their own language..  This is my opinion and trust me there will me lots of ppl feel it same way
I agree you. We are translation group from Turkey and we want to translate this game too. We need a packerrrrrrrrr !
## Post #323
- Username: kekko
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Nov 01, 2008 9:26 pm
- Post datetime: 2013-03-27T20:35:31+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

[modders_only]
in theory, with a packer, it could be even possible to modify meshes, to an extent, even without fully know the DRM format.
we can't freely edit a mesh, because we can't pack it back in its original format, but we might be able to change only the chunks of data we know (i.e. vertex, faces), while ensuring that the size and the relative position of every chunk remains the same of the original DRM mesh.
This way we might just leave the unknown chunks as they are and change the ones we know.
Which kind of changes can be done?
- moving a vertex; a vertex will occupy the same space in terms of bytes if moved, while it wouldn't if deleted
- "removing" a vertex, making the triangles that points to it in the face index point somewhere else
- "removing" a face/triangle, by making all its vertices point to the same vertex
- similar approaches would apply for changing uv mapping

an "average" artist would consider these options enough for modding, considering also that the textures are much freely modifiable.

the edited meshes might either replace the original mesh in the bigfile, or might just be added at end of the last bigfile (changing the pointer to the mesh in the bigfile FAT).

[/modders_only]
## Post #324
- Username: shrek
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Aug 14, 2012 3:07 pm
- Post datetime: 2013-03-28T12:36:24+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Ekey
>
> Here

...was uploaded on fileserve and is not available anymore unfortunately...
## Post #325
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-28T12:47:12+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Does somebody know why the .mul-Files in bigfile_ENGLISH have so many different Locals (FFFFFFF7,FFFFDD41,FFFFDD51,FFFFDD61,FFFFDD63,FFFFDDF,FFFDDC1,FFFFDDCF,FFFFDDDF,FFFFDDE7,FFFFDDFF and many more) while other languages have only one Locale for all .mul-Files?
## Post #326
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-03-28T14:53:02+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Eskey for ps3 names what memory dumper did you use?
## Post #327
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-03-29T03:33:39+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Sammie
>
> Does somebody know why the .mul-Files in bigfile_ENGLISH have so many different Locals (FFFFFFF7,FFFFDD41,FFFFDD51,FFFFDD61,FFFFDD63,FFFFDDF,FFFDDC1,FFFFDDCF,FFFFDDDF,FFFFDDE7,FFFFDDFF and many more) while other languages have only one Locale for all .mul-Files?It's bitflags for supported locale.
## Post #328
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2013-03-29T03:54:29+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Ekey
>
> Filelist updated. Added ~1000 - 21692/22828 (95%)
> Reply from Ekey
>
> I do not think that will be more tools. Main objective is complete. Archives unpacked (models, textures, text ect)
Really appreciate the work everyone has done on this game... many thanks 

Hope that you'll consider updating filelists when patches are updated (latest patch is 268,727,080 bytes) and that you'll also consider updating when new DLC packs are released... pretty please with cherries on top
## Post #329
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-29T06:36:03+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Nothing special updated for 730 patch ~30 names.
[tr9_projects_6826.rar](https://xentaxbackup.github.io/file/6298_tr9_projects_6826.rar)
## Post #330
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-29T16:13:06+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Rick
>
> Sammie wrote:Does somebody know why the .mul-Files in bigfile_ENGLISH have so many different Locals (FFFFFFF7,FFFFDD41,FFFFDD51,FFFFDD61,FFFFDD63,FFFFDDF,FFFDDC1,FFFFDDCF,FFFFDDDF,FFFFDDE7,FFFFDDFF and many more) while other languages have only one Locale for all .mul-Files?It's bitflags for supported locale.
Okay, let me rephrase my question...

I have downloaded some language-files
all .mul files in title_FRENCH have FFFF0002 and all .mul files in bigfile_FRENCH have FFFF1102 
all .mul files in title_GERMAN have FFFF0004 and all .mul files in bigfile_GERMAN have FFFF1104 
all .mul files in title_ITALIAN have FFFF0008 and all .mul files in bigfile_ITALIAN have FFFF1108
...
2,4,8 bitflags.. okay
But all .mul files in title_ENGLISH have FFFFDD41. Why not FF0001?
And all .mul files in bigfile_ENGLISH have many different locals (FFFFFFF7,FFFFDD51,FFFFDD61,FFFFDD63,FFFFDDF,FFFDDC1,FFFFDDCF,FFFFDDDF,FFFFDDE7,FFFFDDFF)
Of course I see, all have 0x1 bitmask, but why are there so many different locals in the english file and only one locale in the other language-files? What's the rest of this locale-stuff in the english files? Any idea?
## Post #331
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-29T16:18:01+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

game contains 3 different text formats
## Post #332
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-29T19:00:10+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Too many of people wants translate this game, please someone help us, work on packer
## Post #333
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-30T09:45:11+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Sammie
>
> all .mul files in title_ENGLISH have FFFFDD41. Why not FF0001?
And all .mul files in bigfile_ENGLISH have many different locals (FFFFFFF7,FFFFDD51,FFFFDD61,FFFFDD63,FFFFDDF,FFFDDC1,FFFFDDCF,FFFFDDDF,FFFFDDE7,FFFFDDFF)
Of course I see, all have 0x1 bitmask, but why are there so many different locals in the english file and only one locale in the other language-files? What's the rest of this locale-stuff in the english files?
Okay, I see the english files are primary for multiple languages. Most of the .mul-files (95%) have bitmasks for english, czech, portugese, polish, korean and chinese.
Some other files have 1-2 additional bitflags for spanish, italian, french, german or arabian.. doesn't make real sense - thats the reason for the different locals. This is just a jumble. 
All other Language-Packs (French, German, Russian ..) are separated and have only her own locale-flag. 

The language-slots for hungrian and englishUK are unused, but not integrated (game starts in regular english-mode). But for japanese the game is trying to load the locals.bin and can't find them (errormsg+crash ^^). So it should be possible to inject another language in the japanese locale slot. I don't think its hard to modify the patch-file. Theoretically we could create a new bigfile|title_<lang> files with modied .muls and append (or replace) a new locals.bin to the patch-file. But I have no time to test it within the next 4 weeks. My holiday is over.
## Post #334
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2013-03-30T12:26:55+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

MUL demuxing to FSB:
[viewtopic.php?f=17&t=10217&p=84446#p84446](http://forum.xentax.com/viewtopic.php?f=17&t=10217&p=84446#p84446)
## Post #335
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-30T20:09:18+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

You are being a little bit selfish here. There are so many groups waiting for this tool to translate this game. Please consider this. So many people are waiting for this packing tool.
## Post #336
- Username: fonglee
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-30T22:54:29+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from turkgamer
>
> You are being a little bit selfish here. There are so many groups waiting for this tool to translate this game. Please consider this. So many people are waiting for this packing tool.
Don't run your mouth, nobody is being selfish. It's simply because the tool doesn't exist to share. If your "group" care so much about it they should stop being lazy ass leeches and learn to make tools to extract, repack so they wouldn't have to rely on others. Yes, there are many people who want a repack tool but it doesn't seem to be happening anytime soon so get over it or try make a repacker yourself. It's not nice to put pressure on people.
## Post #337
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2013-03-31T03:55:21+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

I'm curious if anyone has found data in the game relating to all the icons?

Skill icons, weapon icons, etc. Any icon in the game, I'm interested in it!
## Post #338
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-31T08:15:08+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from relight
>
> I'm curious if anyone has found data in the game relating to all the icons?

Skill icons, weapon icons, etc. Any icon in the game, I'm interested in it!

All ui graphics in GFx files (DTPData)

```
pc-w\main_menu_multiplayer.drm
pc-w\main_menu_options.drm
```
## Post #339
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-03-31T14:39:50+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

mmm... I'm curious, has any one tried to capture the model with the tressfx on?? Is there a way to get hair mesh with that effect??
## Post #340
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-03-31T17:30:00+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

What do you mean with all effects? There's a mesh for TressFX hair in files.
## Post #341
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-04-01T02:25:55+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Darko
>
> mmm... I'm curious, has any one tried to capture the model with the tressfx on?? Is there a way to get hair mesh with that effect??There is no "real" mesh for the TressFX hairs. Take a look at my [screenshot](http://forum.xentax.com/viewtopic.php?p=84191#p84191). (Its just a fake visualisation, cuz there are no real polygons)
This meshfile contains only start- & endpoints for each of Lara's 12576 single hairs. The gameengine is calculating thin colored lines between these points.
TressFX has no polygons and no textures, its just GPU-accelerated physics calculation (gravity, wind, collision, laras movement).

If you want to render this stuff in a 3D application, you have to script something to parse the points out of the meshfile and render colored splines with this data or connect the data with a hair-plugin or a fibermesh. Depends on your application and your knowledge.  Some of the Lara's meshes have an additional lowpoly-mesh inside the regular mesh. I think this lowpoly-mesh is a dummy for the collision-calculation and can be used for you own collision detection. Autodesk has some simple [hair tutorials](http://download.autodesk.com/us/maya/2010help/index.html?url=Creating_a_basic_hairstyle_Styling_the_hair.htm,topicNumber=d0e45408) for Maya.
## Post #342
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-04-01T02:57:19+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Sammie
>
> Darko wrote:mmm... I'm curious, has any one tried to capture the model with the tressfx on?? Is there a way to get hair mesh with that effect??There is no "real" mesh for the TressFX hairs. Take a look at my screenshot. (Its just a fake visualisation, cuz there are no real polygons)
This meshfile contains only start- & endpoints for each of Lara's 12576 single hairs. The gameengine is calculating thin colored lines between these points.
TressFX has no polygons and no textures, its just GPU-accelerated physics calculation (gravity, wind, collision, laras movement).

If you want to render this stuff in a 3D application, you have to script something to parse the points out of the meshfile and render colored splines with this data or connect the data with a hair-plugin or a fibermesh. Depends on your application and your knowledge.  Some of the Lara's meshes have an additional lowpoly-mesh inside the regular mesh. I think this lowpoly-mesh is a dummy for the collision-calculation and can be used for you own collision detection. Autodesk has some simple hair tutorials for Maya.

So It's something simikar to the hair modifiers in 3ds max.

Tnaks.
## Post #343
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2013-04-04T20:09:44+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Sammie
>
> Darko wrote:mmm... I'm curious, has any one tried to capture the model with the tressfx on?? Is there a way to get hair mesh with that effect??There is no "real" mesh for the TressFX hairs. Take a look at my screenshot. (Its just a fake visualisation, cuz there are no real polygons)
This meshfile contains only start- & endpoints for each of Lara's 12576 single hairs. The gameengine is calculating thin colored lines between these points.
TressFX has no polygons and no textures, its just GPU-accelerated physics calculation (gravity, wind, collision, laras movement).

If you want to render this stuff in a 3D application, you have to script something to parse the points out of the meshfile and render colored splines with this data or connect the data with a hair-plugin or a fibermesh. Depends on your application and your knowledge.  Some of the Lara's meshes have an additional lowpoly-mesh inside the regular mesh. I think this lowpoly-mesh is a dummy for the collision-calculation and can be used for you own collision detection. Autodesk has some simple hair tutorials for Maya.

Hey is there a possibility to just have a file with these vertices? I'd like to create a decent detailed hair mesh based on this ><
## Post #344
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-04-05T12:10:35+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from o0Crofty0o
>
> Hey is there a possibility to just have a file with these vertices? I'd like to create a decent detailed hair mesh based on this ><
There is a possibility, but you have to do it by yourself.   

But common, its not so complicated.. all necessary tools are on the first page.. extract the meshes with Ricks Tool, search for files 3CBA8000.drm in bigfile.003.
Extract the .drm with Ekeys Tool and load the extracted mesh into Noesis.. 

Here you have the choice.. you can modify the pyhton plugin to print out the mesh.vertBuff & mesh.vertIdx after line 291 in a arbitrarily format. (One Idx connects two vertices [Start+Endpoint of every hair]). Or you can try to export the mesh as .obj and parse the vertices from the obj-file (its ascii-format). Good luck.
## Post #345
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-04-06T00:54:36+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Have there been any bigfile list updates?
## Post #346
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-04-06T08:38:45+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from C00L12345
>
> Have there been any bigfile list updates?I think Ekey will post new lists, if he had new data.
I'm waiting too 


At the moment I analyze the XBox/PS3 Files. Respectively compare the data between the versions. 
After the xbox-decompression I got regular files, Big Endian Meshes, FSB-data.. everything okay.
But I can't convert the xbox textures. Something seems buggy with the DTX rawdata.

The textures have different headers, PCD9 (PC), PS3T (Playstation) & X360 (XBox). PC&PS3 are easy. I read the DXT format, width, height, mipmapCount and append the DXT rawdata. No problem.
But the xbox-textures looking weird.

I have uplodaded an example (PS3 + XBOX) including raw-data after decompression and the final dds-texture.
Playstation is correct, Xbox not. Both have the same dds-filesize. Looks like a stupid shifting or something.

[http://www.sendspace.com/file/m1gv32](http://www.sendspace.com/file/m1gv32)

Any ideas how to fix that?
## Post #347
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-04-06T12:51:44+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Is it possible to support the .scene files at all?
Some are huge, whilst others are anywhere between 10 and 24MB, whilst others are like 200+, though if someone has a good enough PC they should (in theory) be able to open and export the scenes, unless of course Noesis hits its own memory limit.
## Post #348
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-04-06T15:21:05+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Sammie
>
> C00L12345 wrote:Have there been any bigfile list updates?I think Ekey will post new lists, if he had new data.
I'm waiting too 


At the moment I analyze the XBox/PS3 Files. Respectively compare the data between the versions. 
After the xbox-decompression I got regular files, Big Endian Meshes, FSB-data.. everything okay.
But I can't convert the xbox textures. Something seems buggy with the DTX rawdata.

The textures have different headers, PCD9 (PC), PS3T (Playstation) & X360 (XBox). PC&PS3 are easy. I read the DXT format, width, height, mipmapCount and append the DXT rawdata. No problem.
But the xbox-textures looking weird.

I have uplodaded an example (PS3 + XBOX) including raw-data after decompression and the final dds-texture.
Playstation is correct, Xbox not. Both have the same dds-filesize. Looks like a stupid shifting or something.

http://www.sendspace.com/file/m1gv32

Any ideas how to fix that?
All Tomb Raider Underworld textures used the Xbox swizzle algo. It's most likely that Tomb Raider (2013) uses the same method.
## Post #349
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-04-07T11:34:18+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Packer?
## Post #350
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-07T16:42:22+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

No Packer.
## Post #351
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-04-08T01:12:39+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

xbox textures are swizzled. save them as xpr and use chris' noesis plugin.
## Post #352
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-04-08T04:44:51+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> xbox textures are swizzled. save them as xpr and use chris' noesis plugin.
I have already unswizzled the images, thx.  Its for my private unpacker.  

You mean [this script](http://forum.xentax.com/viewtopic.php?f=18&t=8102), right?
Can't load them with this plugin, cuz TR has a different "X360"-header (28 bytes)
But it's no problem to modify the plugin (see link below).

BigEndian Header:

```
unkFlag1 = input.ReadUByte(); // Unknown Flag
unkFlag2 = input.ReadUByte(); // Unknown Flag
unkFlag3 = input.ReadUByte(); // Unknown Flag
formatbyte = input.ReadUByte(); // Texture-type
dataLength = input.ReadUInt32(); // RawData-Length
junk = input.ReadUInt32(); // Nulls
imageWidth = input.ReadUInt16(); // width
imageHeight = input.ReadUInt16(); // height
mipMapCount = input.ReadUInt16(); // MipMapCount
unkFlag4= input.ReadUByte(); // Unknown Flag
unkFlag5= input.ReadUByte(); // Unknown Flag
unkFlag6= input.ReadUByte(); // Unknown Flag
unkFlag7= input.ReadUByte(); // Unknown Flag
+DXTdata
```

But there is one unknown texture-type (0x02)
Header begins with: 58 33 36 30 - 28 00 01 02

[http://www.sendspace.com/file/wq5cob](http://www.sendspace.com/file/wq5cob) <= Noesis plugin + 5 Testimages.. 
First four are okay, last one (0x02) not. Would be nice to know the correct settings for this imagetype. 

> Reply from chrrox
>
> if you find a xpr file that does not work just upload it somewhere and let me know ill add support for it.Its your job, chrrox.  

Edit: Maybe its some kind of 8bit Raw-Image (A8?). I think the byte on offset 0x16 is bitsPerPixel. Its usually 0x00 for DXT1/3/5 Images and only set for RawImages like a8r8g8b8 or something.
## Post #353
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-04-14T18:31:52+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Is anybody working on packer?
## Post #354
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2013-04-16T17:28:11+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from C00L12345
>
> Have there been any bigfile list updates?
There are a number of new files now, including updates to the patch file, a second patch file and the DLC map pack, with more DLC map packs on the way.

I would be more than happy to keep the file lists up to date if the method of doing so could be shared. I am also willing to provide any assistance needed to those creating the file lists. Just let me know if I can help in some way.
## Post #355
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-04-18T13:09:29+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

up up
## Post #356
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-18T13:33:07+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Nobody make packer
## Post #357
- Username: BiggestSmile
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 03, 2012 1:01 am
- Post datetime: 2013-04-20T12:30:11+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hey ekey, how do you actually extract file names for packs? Mind sharing sources of your tools related to TR?   
Pretty long time ago i've read something about reversing TR executable to catch these filenames
## Post #358
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-20T14:55:00+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Just simple logger nothing special
## Post #359
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-04-20T15:55:00+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Didn't the Tomb Raider Underworld tool have hash generation based on the names? I assume that it's the same probably.
## Post #360
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2013-04-21T19:34:40+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Ekey
>
> Just simple logger nothing special
It's special for us who are not familiar with this type of work 

However, I did follow your tip with a small amount of homework for the .gfx data with excellent results, thank you
## Post #361
- Username: Level NextGen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 14, 2013 1:02 am
- Post datetime: 2013-04-22T15:25:17+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hello everyone! 
I'm new here and I've just downloaded these packages from the first post.
I've tried to unpack the TR9 tiger files but it seems there's something wrong.

It tells "Unhandled Exception". I don't know what to do?

Btw I bought the game on steam, is this a problem?

Thank you in advance
## Post #362
- Username: timkango
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 12, 2011 4:16 pm
- Post datetime: 2013-04-23T01:09:24+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from relight
>
> Ekey wrote:Just simple logger nothing special
It's special for us who are not familiar with this type of work 

However, I did follow your tip with a small amount of homework for the .gfx data with excellent results, thank you

I'm not familiar with logging file names from an executable, either. Would you mind sharing the process or perhaps direct me in the right direction?
## Post #363
- Username: SoniKalien
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 13, 2011 11:02 am
- Post datetime: 2013-05-13T12:42:25+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Sorry to bother you guys 

I've been trying to extract mesh. All is well up until Noesis. I dropped the python script into the directory, but getting errors from this line:

```
    mat = open("G:\Tombraider\jonah_mp\Material\Section 3335.cdrm", 'rb').read()
IOError: [Errno 2] No such file or directory: 'G:\\Tombraider\\jonah_mp\\Material\\Section 3335.cdrm'
```


Sorry if I'm stating the obvious here, but of course there's no such directory. My extracts are in a different folder. I know I could just change the script to point to my folder but what's bugging me is this:

1- Section 3335.cdrm is actually in the Laracroft\Animations folder, not jonah_mp\material
2- Should the file be different for each model?

So what can I do? manually hunt down the right mat file for each model and change the script each time? Pass on that thanks  So i'd thought I'd ask here as I'm not big on python scripting - what should the following line actually be?:

```

	mat = open("G:\Tombraider\jonah_mp\Material\Section 3335.cdrm", 'rb').read()

```


Thanks
## Post #364
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2013-05-13T18:54:15+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Comment these two lines in noepyCheckType

```
#bsx = NoeBitStream(mat)
```

you can see the model but I don't know how to assign textures.
## Post #365
- Username: SoniKalien
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 13, 2011 11:02 am
- Post datetime: 2013-05-13T22:27:52+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from deepshit
>
> Comment these two lines in noepyCheckType
Code: Select all#mat = open("G:\Tombraider\jonah_mp\Material\Section 3335.cdrm", 'rb').read()
#bsx = NoeBitStream(mat)
you can see the model but I don't know how to assign textures.

Thanks, that got it. 

I managed to manually assign textures in 3DSMax so normals etc are all fine.
## Post #366
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-05-19T11:59:13+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

TR9 unpacker with latest files lists (%95)

[https://www.dropbox.com/s/xvfbk0s8ph0t9 ... 17_b74.rar](https://www.dropbox.com/s/xvfbk0s8ph0t9hp/tombraider9-r117_b74.rar)
## Post #367
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2013-05-20T16:12:22+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Do these unpackers recognize the new DLC costumes? Someone on TRF revealed their MD5 hashes or sth.. dunno if itz useful.. i couldn't find them so far
MD5 hashes:

PACK4.000.tiger: ee1aa894727bc44d8c3a1dd539ad783f
PACK8.000.tiger: 0166352986292a3d92792fbe4922119e
## Post #368
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2013-06-05T13:54:31+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

has any progress been made for MUL files?
## Post #369
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2013-06-14T18:37:16+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Is there any way to get DRM Dumper to dump ALL .drm files without having to go through each .drm manually?
## Post #370
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-07-14T11:38:32+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Unusual error here:

So I extracted bigfile.000, then with the DRM dumper I went into the folder containing all the .drm files, regardless of what I select to load I get the following error:

Any ideas?

Its the same install as before, nothing has changed, it worked before, however I deleted the tools etc and this is a month or 2 later and I'm trying again with the tools but no luck.
[error.jpg](https://xentaxbackup.github.io/file/6520_error.jpg)
## Post #371
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-07-14T14:43:06+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

I guess you did not specify the correct path to the game. Just click on text box where > C:\Tomb Raider for change.
## Post #372
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-07-15T20:07:44+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Ekey
>
> I guess you did not specify the correct path to the game. Just click on text box where > C:\Tomb Raider for change.
Ah, thats for game... for some reason I'd understood it to be the files location. Huge fail on my part there...

Thanks Ekey.
## Post #373
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-07-16T09:06:26+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from SoniKalien
>
> Sorry to bother you guys 

I've been trying to extract mesh. All is well up until Noesis. I dropped the python script into the directory, but getting errors from this line:
Code: Select all File "D:\Tomb Raider rip\tools\noesisv4081\plugins\python\fmt_tombraider_mesh.py", line 25, in noepyCheckType
    mat = open("G:\Tombraider\jonah_mp\Material\Section 3335.cdrm", 'rb').read()
IOError: [Errno 2] No such file or directory: 'G:\\Tombraider\\jonah_mp\\Material\\Section 3335.cdrm'

Thanks
You trying to open invalid models format. Supported only files with extension .mesh
## Post #374
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-09-19T23:05:24+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hey, I also hope we can get a little more out of the formats.
I'm interested in doing a blender importer script with cycles materials (blender 2.68)

However, without the textures loading modeles is not much, did anyone found some pointers to how meshes load their own materials and textures?

I don't see anything similar here to my experience with other formats, if anyone discovered something, it will be appreciated.
## Post #375
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-20T01:34:26+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

i know how texturing works. similar format to models. each material file begins with a code that determines type of material and number of offsets to data in material file. one of offsets is to a list of file identifiers, usually at bottom of file.

however, you cant use ricks and ekeys dumper because image files are referenced by hexidecimal identifiers. also, whether an image is a diffuse, spec, or normal map is located in the pcd files, which you must keep around

translation: its a lot of work to implement auto texturing, and you must also write a new file dumper.
## Post #376
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-09-20T18:01:15+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Oh, ok howfie, that sounds way beyond my level of skill. However, maybe it's just hard work and not "difficult" work? If you have some code already for the file dumpers that I can take a look and more details about what I have to do I really want to give it a shot.
Thanks!
## Post #377
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-20T21:30:10+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Very sorry I stopped releasing and sharing my code on an open-source repository. While convenient, recently somebody recompiled my code for a recent game I was working on for which I was holding back a release until the game stopped updating (for reasons learned from Playstation All-Stars). I don't have notes from TR2013 anymore but I still have notes from Deus Ex: HR, which is a similar material format. Another problem is that there are also two different material file types, and these files always come in pairs but rick's and ekey's tools don't differentiate between them (I called them mtrl_a and mtrl_b in my Deus Ex rip). You will need to rename these files with different extensions because they use the same hexadecimal identifier for the filename.

You're right, it is not hard work, but more or less tedious work. So tedious I kind of stopped working on Deus Ex: HR because of it. You will also have to reverse the scene file format to rebuild full stages/maps.

For Deus Ex and TR2013 as well, the material files look like:

```
-- main\bigfile\00d3\000002c7.mtl_a
-- In this example, the mtrl_a files starts with 0x15. This material does not use any texture files (it is some kind of material for color effects or something who knows).
-- So in this case, you just skip loading materials when you see this.

-- the first 0x14 bytes is a header
15 00 00 00 -- number of offset pairs to read
00 00 00 00 
00 00 00 00 
00 00 00 00 
09 00 00 00

-- the next data after header is a list of offset pairs
[0x00]: 4C 00 00 00 - 90 06 00 00
[0x01]: C8 06 00 00 - 90 00 00 00
[0x02]: CC 06 00 00 - C0 00 00 00 
[0x03]: D0 06 00 00 - 30 01 00 00
[0x04]: 50 00 00 00 - F0 06 00 00
[0x05]: 28 07 00 00 - 80 01 00 00
[0x06]: 2C 07 00 00 - B0 01 00 00 
[0x07]: 30 07 00 00 - 20 02 00 00
[0x08]: 58 00 00 00 - 50 07 00 00
[0x09]: 88 07 00 00 - 70 02 00 00
[0x0A]: 8C 07 00 00 - A0 02 00 00 
[0x0B]: 90 07 00 00 - 10 03 00 00 
[0x0C]: 5C 00 00 00 - B0 07 00 00 
[0x0D]: E8 07 00 00 - 60 03 00 00 
[0x0E]: EC 07 00 00 - 90 03 00 00 
[0x0F]: F0 07 00 00 - 00 04 00 00 
[0x10]: 68 00 00 00 - 10 08 00 00 
[0x11]: 48 08 00 00 - 50 04 00 00 
[0x12]: 4C 08 00 00 - F0 04 00 00 
[0x13]: 50 08 00 00 - D0 05 00 00 
[0x14]: 6C 00 00 00 - 50 07 00 00

```


```
-- There are two offset pairs. It is suffice to use the textures from the first pair. 
-- Here is an example of the offsets. In this case pair index 0x09 and 0x13 point
-- to a list of texture information.

[0x00]: 4C 00 00 00 - 10 0A 00 00
[0x01]: 48 0A 00 00 - 90 00 00 00
[0x02]: 4C 0A 00 00 - E0 00 00 00 
[0x03]: 50 0A 00 00 - 60 01 00 00 
[0x04]: 50 00 00 00 - 70 0A 00 00 
[0x05]: A8 0A 00 00 - D0 01 00 00 
[0x06]: AC 0A 00 00 - 20 02 00 00 
[0x07]: B0 0A 00 00 - A0 02 00 00 
[0x08]: 58 00 00 00 - D0 0A 00 00 
[0x09]: E8 0A 00 00 - 90 0C 00 00 (offsets to filenames A)
[0x0A]: F0 0A 00 00 - F0 0B 00 00 
[0x0B]: 08 0B 00 00 - 10 03 00 00 
[0x0C]: 0C 0B 00 00 - F0 03 00 00 
[0x0D]: 10 0B 00 00 - 00 05 00 00 
[0x0E]: 5C 00 00 00 - 30 0B 00 00 
[0x0F]: 68 0B 00 00 - F0 05 00 00 
[0x10]: 6C 0B 00 00 - 40 06 00 00 
[0x11]: 70 0B 00 00 - C0 06 00 00 
[0x12]: 68 00 00 00 - 90 0B 00 00 
[0x13]: A8 0B 00 00 - 10 0D 00 00 (offsets to filenames B)
[0x14]: B0 0B 00 00 - 70 0C 00 00 
[0x15]: C8 0B 00 00 - 30 07 00 00 
[0x16]: CC 0B 00 00 - 10 08 00 00 
[0x17]: D0 0B 00 00 - 20 09 00 00 
[0x18]: 6C 00 00 00 - D0 0A 00 00

-- 8 part A textures
8B 0F 00 00 00 00 00 00 00 00 00 00 20 00 01 00 -- 00000F8B is texture ID, 0x20 is color/spec maps, 0x80 is normal map, 0x2C i think is lightmap, and 0x00 is texture index.
8A 0F 00 00 00 00 00 00 00 00 00 00 20 01 01 00 -- 00000F8A is texture ID, 0x01 is texture index
54 00 00 00 00 00 00 00 00 00 00 00 20 02 01 00  -- 0x02 is texture index
16 0C 00 00 00 00 00 00 00 00 00 00 20 03 01 00 
8A 0F 00 00 00 00 00 00 00 00 00 00 20 04 01 00 
9E 0F 00 00 00 00 00 00 00 00 00 00 80 05 01 00 
19 0C 00 00 00 00 80 BF 00 00 00 00 80 06 01 00 
5D 00 00 00 00 00 00 00 00 00 00 00 2C 07 02 00 -- 0x2C i think is lightmap or something, 0x07 is texture index

-- 3 part B textures
19 0C 00 00 00 00 80 BF 00 00 00 00 80 00 01 00 
9E 0F 00 00 00 00 00 00 00 00 00 00 80 01 01 00 
8B 0F 00 00 00 00 00 00 00 00 00 00 20 02 01 00

```
## Post #378
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2013-09-21T13:48:26+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> 

You're right, it is not hard work, but more or less tedious work. So tedious I kind of stopped working on Deus Ex: HR because of it. You will also have to reverse the scene file format to rebuild full stages/maps.

Is it possible to get a whole scenery working through these .scene files? o_O
## Post #379
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-09-21T23:10:00+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

I did work on a script to partially parse the .scene mesh but I totally just stopped because I just feel that the game itself and the way it loads the files and how they are split is just ridiculous and it would take too long just to do everything.

The way it references objects from different sections of the DRM is out of control.

I'd love a DRM rebuilder for Tomb Raider Underworld and Tomb Raider (2013) because you can't actually replace anything and modding is just so limited.

Only if someone had the godly patience to do it.
## Post #380
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-09-22T00:56:20+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Gh0stBlade
>
> I did work on a script to partially parse the .scene mesh but I totally just stopped because I just feel that the game itself and the way it loads the files and how they are split is just ridiculous and it would take too long just to do everything.

The way it references objects from different sections of the DRM is out of control.

I'd love a DRM rebuilder for Tomb Raider Underworld and Tomb Raider (2013) because you can't actually replace anything and modding is just so limited.

Only if someone had the godly patience to do it.

maybe they did it on purpose to avoid reverse engineering?   
Anyway if you can post any WIP you have maybe someone in the future will have the energy to continue it.

Thanks howfie for you analysis of the material! I might ask you some questions via pm if you don't mind.
## Post #381
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-22T07:23:18+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

you may have partial source code (only TR2013 related). sorry can't include full source, but you can look at the logic.
[pc_tr2013.7z](https://xentaxbackup.github.io/file/6631_pc_tr2013.7z)
## Post #382
- Username: ClintonM0
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 28, 2014 7:16 am
- Post datetime: 2014-02-28T01:52:20+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Seems like it's been a while since anyone posted anything here, but I'm wondering if it's possible to get .fsb files out of bigfile_ENGLISH.000.tiger. All I could get are .mul files
## Post #383
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2014-03-25T22:57:25+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

All I get are .mul files... everything else shows up as "unknown"... does anyone have a fix for this?

I have the latest version of the unpacker, and I tried unpacking the bigfile.000.tiger... I've seen other people get actual models out of it, and I get nothing.
## Post #384
- Username: CrashAngel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 21, 2012 4:55 am
- Post datetime: 2014-04-07T11:04:55+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hi, I Can Extract .Tiger Files via Script....

More when i try open .Mesh in Noesis, I not preview Materials from .Mesh files in All Files....

Detected file type: Tomb Raider 2013 [PC]
Reading 'C:\Users\Administrador\Desktop\Unpack - TombRaider 2013\ac_rock_ledge_breakable_piece_a\RenderMesh\\Material_0'...Failed.

How can I open the files. Mesh with materials included ... 

Is there any script for Maya, Blender or 3D Studio?
## Post #385
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-04-07T11:28:42+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from CrashAngel
>
> Hi, I Can Extract .Tiger Files via Script....

More when i try open .Mesh in Noesis, I not preview Materials from .Mesh files in All Files....

Detected file type: Tomb Raider 2013 [PC]
Reading 'C:\Users\Administrador\Desktop\Unpack - TombRaider 2013\ac_rock_ledge_breakable_piece_a\RenderMesh\\Material_0'...Failed.

How can I open the files. Mesh with materials included ... 

Is there any script for Maya, Blender or 3D Studio?

1. You extract the .DRM headers from the .tiger file using GIBBED Unpacker.
2. Dump the DRM data by opening the corresponding .DRM file in TRAS DRM Dumper it will require configuration of the bigfile.tiger paths.
3. Open the .mesh files in Noesis using the Noesis import script.

I'm not sure what error you are getting, if you mean it's not building material files/ textures are not applied to meshes then that's because it isn't implemented. To my knowledge there is no Maya, Blender, 3DS Max scripts to import into those applications. Can't you just export from Noesis then import the files into them anyway?

I have rebuilt the script form scratch recently which looks a whole lot better, materials assigned to meshes properly. I haven't added support for parsing the material file fully until I crack what's happening in the previous game. Tomb Raider: Underworld.

I have a basic working script for Tomb Raider: Underworld too. Parses the material files perfectly all that is left is diffuse colour, diffuse texture detections. Sadly, all this information is stored within the shaders and I have not yet figured out which value(s) are defining the texture ID to use from the list in the within the material file. Until that is found it will be forever unknown therefore, auto texturing is just not possible.

I wrote a partial shader parser for Tomb Raider: Underworld but I really don't see where the information regarding which texture is diffuse, normal is stored. If anyone is interested in solving the mystery then let me know.

You are free to manually rename the textures are Noesis will just load it from the names you see in the debug box.

Edit: I think Howfie worked on a Blender script, not sure if it was completed though!
## Post #386
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-04-08T18:26:53+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Yes, I have a working unpacker and model extractor for TR2013, but it doesn't do auto-texture either. I'm too lazy and as you know:

> Reply from Gh0stBlade
>
> The way it references objects from different sections of the DRM is out of control.

Though I did have a great idea at one time to combat this, which I may try on Deus Ex: HR Director's Cut soon. So you go ahead and have all that fun with TR  .
## Post #387
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-04-08T19:50:00+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from howfie
>
> Yes, I have a working unpacker and model extractor for TR2013, but it doesn't do auto-texture either. I'm too lazy and as you know:
Gh0stBlade wrote:The way it references objects from different sections of the DRM is out of control.

Though I did have a great idea at one time to combat this, which I may try on Deus Ex: HR Director's Cut soon. So you go ahead and have all that fun with TR  .

Yeah, that was an issue before. But it's not anymore, I just made a new unpacker for both Tomb Raider: Underworld and Tomb Raider. It extracts all files with their hash names so they can just be loaded like that.

Tomb Raider: Underworld supports repacking of the sections so I know that the info for the textures is stored in the shaders because when the shader hash ID is changed, so does the ID for which texture is diffuse, normal etc.

The real issue is the IDs coming from the shader. Until that's sorted auto texturing won't happen. I did write a partial shader parser which spits out some string information and values tied to it but it's useless because I have no idea where the information is stored and can find no relation.

But if anyone is interested in helping out or has experience with such a things as shaders then it'd be of help. I've never seen a game to store such information within the shaders.

I'm not sure how far you got with Deus Ex but I guess the format is very similar to one of the Tomb Raider games so I can definitely help if needed, but it looks like the shader issue is likely to be present in that game too.

All we really need is the correct texture ids and material colour index and it'll all be good to go and the mystery will be solved...

Cheers.
## Post #388
- Username: PaniKlolwer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 26, 2014 4:35 am
- Post datetime: 2014-10-25T20:58:29+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hey, I'm new here so I'm not sure if I should write here in this topic, but I have a problem.
I downloaded a Gibbed Tiger Unpacker and it doesn't work. When I'm trying open a file "Gibbed.TombRaider9.Unpack" it's just turning on and disappears after one second. I really want to unpack these files, but I don't know why I can't  I hope that somebody will help me
## Post #389
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2014-11-11T22:51:22+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from PaniKlolwer
>
> Hey, I'm new here so I'm not sure if I should write here in this topic, but I have a problem.
I downloaded a Gibbed Tiger Unpacker and it doesn't work. When I'm trying open a file "Gibbed.TombRaider9.Unpack" it's just turning on and disappears after one second. I really want to unpack these files, but I don't know why I can't  I hope that somebody will help me

It's a command line application, you don't have to double click it.
Open cmd and type what it says in the first post:
Gibbed.TombRaider9.Unpack "szTIGERarchive" "szOutputFolder"

You might need to write the full path for the executable, e.g. C:\Users\path-to-the-exe\Gibbed.Tombraider9.UNpack.exe
## Post #390
- Username: Davidebre
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 20, 2015 11:33 pm
- Post datetime: 2015-07-21T13:26:52+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hi, it's possible to get the .fsb files out of bigfile_ENGLISH.000? I'm really interested in the voice actor sound.
A guy has done it, I want to do the same thing but with the Italian language. I asked him how he did but it's says has been far too long, and he doesn't remember.
Can someone help me, please? Sorry for my english...
## Post #391
- Username: ferex
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 04, 2015 6:06 am
- Post datetime: 2015-09-01T14:00:48+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hello.Someone send me extract and repack tool program for TR 2013 PS3 with p.m?we want to translate subtitle.
we need tiger tool program.I was send message ekey.he dont answer me.He told me I can upload only unpacker program.someone else may be able to help
## Post #392
- Username: 0x02
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 15, 2015 3:46 pm
- Post datetime: 2015-11-15T08:54:31+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Guys how do you unpack tiger files for PS3
## Post #393
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2015-11-15T10:45:31+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from ferex
>
> Hello.Someone send me extract and repack tool program for TR 2013 PS3 with p.m?we want to translate subtitle.
we need tiger tool program.I was send message ekey.he dont answer me.He told me I can upload only unpacker program.someone else may be able to help
[http://svn.gib.me/builds/](http://svn.gib.me/builds/)
## Post #394
- Username: 0x02
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 15, 2015 3:46 pm
- Post datetime: 2015-11-15T16:52:47+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Paliha
>
> ferex wrote:Hello.Someone send me extract and repack tool program for TR 2013 PS3 with p.m?we want to translate subtitle.
we need tiger tool program.I was send message ekey.he dont answer me.He told me I can upload only unpacker program.someone else may be able to help
http://svn.gib.me/builds/

i use the latest version but i keep getting an unsupported file error everytime i drop it on unpack
## Post #395
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2015-11-15T19:22:34+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

i use the latest version but i keep getting an unsupported file error everytime i drop it on unpack     [/quote]
Ок...))
But surprisingly unpacker  Tomb Raider (2013) can be found on YouTube
EXTRACT AND CONVERT TOMB RAIDER 2013 MODELS WITH BONES SUPPORT [https://www.youtube.com/watch?v=sR0WOdXIAVU](https://www.youtube.com/watch?v=sR0WOdXIAVU)
Tools [url]http://www.mediafire.com%2F%3Fat984gad6dqbs26&redir_token=PS-x1EAsWPPO2PuMPlfKptzbzzp8MTQ0NzcwMTYyNkAxNDQ3NjE1MjI2[/url]
Project folder (put it in your TR 2013 directory" [url]http://www.mediafire.com%2F%3Fofssgs4jo0to3un&redir_token=PS-x1EAsWPPO2PuMPlfKptzbzzp8MTQ0NzcwMTYyNkAxNDQ3NjE1MjI2[/url]
Included is Steven's Ripper, works in one click
## Post #396
- Username: 0x02
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 15, 2015 3:46 pm
- Post datetime: 2015-11-16T01:23:01+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Paliha
>
> i use the latest version but i keep getting an unsupported file error everytime i drop it on unpack
Ок...))
But surprisingly unpacker  Tomb Raider (2013) can be found on YouTube
EXTRACT AND CONVERT TOMB RAIDER 2013 MODELS WITH BONES SUPPORT [https://www.youtube.com/watch?v=sR0WOdXIAVU](https://www.youtube.com/watch?v=sR0WOdXIAVU)
Tools [url]http://www.mediafire.com%2F%3Fat984gad6dqbs26&redir_token=PS-x1EAsWPPO2PuMPlfKptzbzzp8MTQ0NzcwMTYyNkAxNDQ3NjE1MjI2[/url]
Project folder (put it in your TR 2013 directory" [url]http://www.mediafire.com%2F%3Fofssgs4jo0to3un&redir_token=PS-x1EAsWPPO2PuMPlfKptzbzzp8MTQ0NzcwMTYyNkAxNDQ3NjE1MjI2[/url]
Included is Steven's Ripper, works in one click[/quote]


NOT FOR PS3... did you read my post ??? i need one for ps3
## Post #397
- Username: 0x02
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 15, 2015 3:46 pm
- Post datetime: 2015-11-16T22:18:27+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

bump
## Post #398
- Username: sophia097
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 17, 2015 4:57 pm
- Post datetime: 2015-11-17T09:04:15+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

The result looks like not bad [etuicoquesamsung.com](http://www.etuicoquesamsung.com/category-etui-coque-film-chargeur-sony-xperia-z5-compact-704.html) [www.etuicoquesamsung.com](http://www.etuicoquesamsung.com/category-coques-samsung-galaxy-j1-598.html)
## Post #399
- Username: Cghde
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 19, 2015 5:41 pm
- Post datetime: 2015-11-19T09:51:37+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

All looks very good! [housse silicone galaxy a5](http://www.coquegsm.com/category-accessoires-samsung-galaxy-a5-18.html) [etui samsung galaxy a5](http://www.coquegsm.com/category-accessoires-samsung-galaxy-a5-18.html)
## Post #400
- Username: ferex
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 04, 2015 6:06 am
- Post datetime: 2015-11-19T12:03:05+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Paliha
>
> i use the latest version but i keep getting an unsupported file error everytime i drop it on unpack
Ок...))
But surprisingly unpacker  Tomb Raider (2013) can be found on YouTube
EXTRACT AND CONVERT TOMB RAIDER 2013 MODELS WITH BONES SUPPORT [https://www.youtube.com/watch?v=sR0WOdXIAVU](https://www.youtube.com/watch?v=sR0WOdXIAVU)
Tools [url]http://www.mediafire.com%2F%3Fat984gad6dqbs26&redir_token=PS-x1EAsWPPO2PuMPlfKptzbzzp8MTQ0NzcwMTYyNkAxNDQ3NjE1MjI2[/url]
Project folder (put it in your TR 2013 directory" [url]http://www.mediafire.com%2F%3Fofssgs4jo0to3un&redir_token=PS-x1EAsWPPO2PuMPlfKptzbzzp8MTQ0NzcwMTYyNkAxNDQ3NjE1MjI2[/url]
Included is Steven's Ripper, works in one click[/quote]
I cant download.can you put (codecode) all links.thanks
## Post #401
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2015-11-19T13:05:37+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Reassure foreigners...
Go to youtube the movie looked :
[https://www.youtube.com/watch?v=sR0WOdXIAVU](https://www.youtube.com/watch?v=sR0WOdXIAVU)
Next2:
[http://www.mediafire.com/download/at984 ... tr2013.rar](http://www.mediafire.com/download/at984gad6dqbs26/tools+tr2013.rar)
Next3:
[http://www.mediafire.com/download/ofssg ... ojects.rar](http://www.mediafire.com/download/ofssgs4jo0to3un/projects.rar)
======
## Post #402
- Username: ferex
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 04, 2015 6:06 am
- Post datetime: 2015-11-19T13:49:53+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Paliha
>
> Reassure foreigners...
Go to youtube the movie looked :
https://www.youtube.com/watch?v=sR0WOdXIAVU
Next2:
http://www.mediafire.com/download/at984 ... tr2013.rar
Next3:
http://www.mediafire.com/download/ofssg ... ojects.rar
======
thanks paliha.so can we use on the ps3 file this tool?do you know?
## Post #403
- Username: rajasrijan
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 04, 2014 11:31 pm
- Post datetime: 2015-11-23T04:11:22+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hi all
I'm trying to create packer for TR, this is what i'm doing.

Unpacking:
1) Read the SFAT header, get entries pointing to DRM.
2) Read the DRM header, get pointers to CDRM.
3) Extract CDRM

Packing:
1) Create new bigfile.004.tiger, increment file count in SFAT header .
2) Read content from disk, zip it if needed.
3) Store it in new bigfile at the end.
3) Modify the offset in DRM header.

This is working for textures (didn't test on meshes). I tried replacing textures in game start menu and its working.

I'm stuck at finding all the CDRM entries, as there are a lot of CDRM entries which cannot be reached from headers.
Anyone figure out this problem?

I'll put code in github when i have a working not crashing code   or by sat
## Post #404
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2016-01-26T08:40:56+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from rajasrijan
>
> Hi all
I'm trying to create packer for TR, this is what i'm doing.

Unpacking:
1) Read the SFAT header, get entries pointing to DRM.
2) Read the DRM header, get pointers to CDRM.
3) Extract CDRM

Packing:
1) Create new bigfile.004.tiger, increment file count in SFAT header .
2) Read content from disk, zip it if needed.
3) Store it in new bigfile at the end.
3) Modify the offset in DRM header.

This is working for textures (didn't test on meshes). I tried replacing textures in game start menu and its working.

I'm stuck at finding all the CDRM entries, as there are a lot of CDRM entries which cannot be reached from headers.
Anyone figure out this problem?

I'll put code in github when i have a working not crashing code   or by sat

Nice! Thanks!
## Post #405
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-01-26T17:12:02+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from rajasrijan
>
> Hi all
I'm trying to create packer for TR, this is what i'm doing.

Unpacking:
1) Read the SFAT header, get entries pointing to DRM.
2) Read the DRM header, get pointers to CDRM.
3) Extract CDRM

Packing:
1) Create new bigfile.004.tiger, increment file count in SFAT header .
2) Read content from disk, zip it if needed.
3) Store it in new bigfile at the end.
3) Modify the offset in DRM header.

This is working for textures (didn't test on meshes). I tried replacing textures in game start menu and its working.

I'm stuck at finding all the CDRM entries, as there are a lot of CDRM entries which cannot be reached from headers.
Anyone figure out this problem?

I'll put code in github when i have a working not crashing code   or by sat

Nice, i was working on same thing, i have completed working repacker... problem is that it will repack only files not contains any CDRM... 

Can you please share your code ? Privately ?
## Post #406
- Username: rajasrijan
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 04, 2014 11:31 pm
- Post datetime: 2016-01-27T04:09:52+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from michalss
>
> rajasrijan wrote:Hi all
I'm trying to create packer for TR, this is what i'm doing.

Unpacking:
1) Read the SFAT header, get entries pointing to DRM.
2) Read the DRM header, get pointers to CDRM.
3) Extract CDRM

Packing:
1) Create new bigfile.004.tiger, increment file count in SFAT header .
2) Read content from disk, zip it if needed.
3) Store it in new bigfile at the end.
3) Modify the offset in DRM header.

This is working for textures (didn't test on meshes). I tried replacing textures in game start menu and its working.

I'm stuck at finding all the CDRM entries, as there are a lot of CDRM entries which cannot be reached from headers.
Anyone figure out this problem?

I'll put code in github when i have a working not crashing code   or by sat

Nice, i was working on same thing, i have completed working repacker... problem is that it will repack only files not contains any CDRM... 

Can you please share your code ? Privately ?

Sure.   
I'm little busy now  . Ill send you ASAP.
## Post #407
- Username: rajasrijan
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 04, 2014 11:31 pm
- Post datetime: 2016-02-14T06:41:44+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Repacker code uploaded on github [https://github.com/rajasrijan/TRExplorer](https://github.com/rajasrijan/TRExplorer).

Unpacker is working correctly but there a lot of bugs in packer. Feel free to have a look. Ill put binary when its stable enough.

Please backup game before using tool.
## Post #408
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-02-14T08:54:46+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from rajasrijan
>
> Repacker code uploaded on github https://github.com/rajasrijan/TRExplorer.

Unpacker is working correctly but there a lot of bugs in packer. Feel free to have a look. Ill put binary when its stable enough.

Please backup game before using tool.

Thx, but is this for 2016 or 2013 ?
## Post #409
- Username: rajasrijan
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 04, 2014 11:31 pm
- Post datetime: 2016-02-14T09:49:43+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from michalss
>
> rajasrijan wrote:Repacker code uploaded on github https://github.com/rajasrijan/TRExplorer.

Unpacker is working correctly but there a lot of bugs in packer. Feel free to have a look. Ill put binary when its stable enough.

Please backup game before using tool.

Thx, but is this for 2016 or 2013 ?

It's 2013. I don't have 2016 yet. 
But format should be similar. I dought they will completely reinvent format.
## Post #410
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-14T13:05:25+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Repacking Tiger files should be easy if you can unpack them. What exactly is the issue?
## Post #411
- Username: rajasrijan
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 04, 2014 11:31 pm
- Post datetime: 2016-02-14T13:25:59+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Gh0stBlade
>
> Repacking Tiger files should be easy if you can unpack them. What exactly is the issue?

Complete format is not known.
## Post #412
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-14T14:02:43+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from rajasrijan
>
> Gh0stBlade wrote:Repacking Tiger files should be easy if you can unpack them. What exactly is the issue?

Complete format is not known.
Which parts are unknown? To my knowledge the entire tiger format is known. Entire CDRM format is known. DRM should be fully known except parts of the duplicated section data at the EOF (I should check that actually).
## Post #413
- Username: rajasrijan
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 04, 2014 11:31 pm
- Post datetime: 2016-02-14T14:27:25+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Gh0stBlade
>
> rajasrijan wrote:Gh0stBlade wrote:Repacking Tiger files should be easy if you can unpack them. What exactly is the issue?

Complete format is not known.
Which parts are unknown? To my knowledge the entire tiger format is known. Entire CDRM format is known. DRM should be fully known except parts of the duplicated section data at the EOF (I should check that actually).

Can you point me to the format  . I dont have the complete DRM format and there are some some CDRMs not reachable from the table at the begenning, those CDRMs are hard to replace.
## Post #414
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2016-02-15T12:07:56+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from rajasrijan
>
> Repacker code uploaded on github https://github.com/rajasrijan/TRExplorer.

Unpacker is working correctly but there a lot of bugs in packer. Feel free to have a look. Ill put binary when its stable enough.

Please backup game before using tool.

Thanks for your tool! How to use this tool?

I use this command:

> TRExplorer bigfile_ENGLISH.000.tiger UNPACK patch_ENGLISH.000.tiger

Not working! 

> F:\Program Files (x86)\Eidos Interactive\Tomb Raider GOTY Edition>TRExplorer big
>
> file_ENGLISH.000.tiger UNPACK patch_ENGLISH.000.tiger
>
> rajasrijan's tiger decoder.
>
> 
>
> Tiger Header
>
> Magic           :53464154
>
> Version         :3
>
> Parts           :1
>
> DRMs            :8618
>
> Base Path       :pc-w
>
> Loading data entries...success
>
> 
>
> Invalid operation.
>
> 
>
> F:\Program Files (x86)\Eidos Interactive\Tomb Raider GOTY Edition>pause
>
> Press any key to continue . . .
>
> Terminate batch job (Y/N)?

Thanks!
## Post #415
- Username: rajasrijan
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 04, 2014 11:31 pm
- Post datetime: 2016-02-15T12:56:47+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from shadowlonely1989
>
> rajasrijan wrote:Repacker code uploaded on github https://github.com/rajasrijan/TRExplorer.

Unpacker is working correctly but there a lot of bugs in packer. Feel free to have a look. Ill put binary when its stable enough.

Please backup game before using tool.

Thanks for your tool! How to use this tool?

I use this command:
TRExplorer bigfile_ENGLISH.000.tiger UNPACK patch_ENGLISH.000.tiger

Not working! 

F:\Program Files (x86)\Eidos Interactive\Tomb Raider GOTY Edition>TRExplorer big
file_ENGLISH.000.tiger UNPACK patch_ENGLISH.000.tiger
rajasrijan's tiger decoder.

Tiger Header
Magic           :53464154
Version         :3
Parts           :1
DRMs            :8618
Base Path       :pc-w
Loading data entries...success

Invalid operation.

F:\Program Files (x86)\Eidos Interactive\Tomb Raider GOTY Edition>pause
Press any key to continue . . .
Terminate batch job (Y/N)?

Thanks!

Try with small letters "unpack". Ill put a fix when I get home 

P.S. Updated readme
## Post #416
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-15T13:04:28+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from rajasrijan
>
> 
Can you point me to the format  . I dont have the complete DRM format and there are some some CDRMs not reachable from the table at the begenning, those CDRMs are hard to replace.

The DRM format is very close to Tomb Raider Underworld's contains the exact same components except the duplicated DRM Section info at the end of the DRM which is new. The only unknown field is the last 32-bit unsigned integer of the second DRM Section info, everything else is known. The value itself could be related to struct relocation or memory mapping.

I checked the code for your tool. I think the offset calculation is wrong. Also the game needs all hashes to be ordered in ascending order or it will crash.

Regards.
## Post #417
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2016-02-15T13:09:22+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from rajasrijan
>
> shadowlonely1989 wrote:rajasrijan wrote:Repacker code uploaded on github https://github.com/rajasrijan/TRExplorer.

Unpacker is working correctly but there a lot of bugs in packer. Feel free to have a look. Ill put binary when its stable enough.

Please backup game before using tool.

Thanks for your tool! How to use this tool?

I use this command:
TRExplorer bigfile_ENGLISH.000.tiger UNPACK patch_ENGLISH.000.tiger

Not working! 

F:\Program Files (x86)\Eidos Interactive\Tomb Raider GOTY Edition>TRExplorer big
file_ENGLISH.000.tiger UNPACK patch_ENGLISH.000.tiger
rajasrijan's tiger decoder.

Tiger Header
Magic           :53464154
Version         :3
Parts           :1
DRMs            :8618
Base Path       :pc-w
Loading data entries...success

Invalid operation.

F:\Program Files (x86)\Eidos Interactive\Tomb Raider GOTY Edition>pause
Press any key to continue . . .
Terminate batch job (Y/N)?

Thanks!

Try with small letters "unpack". Ill put a fix when I get home

Thanks! How to unpack text from bigfile_ENGLISH.000.tiger pc-w\local\locals.bin?
## Post #418
- Username: rajasrijan
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 04, 2014 11:31 pm
- Post datetime: 2016-02-15T13:25:17+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Gh0stBlade
>
> rajasrijan wrote:
Can you point me to the format  . I dont have the complete DRM format and there are some some CDRMs not reachable from the table at the begenning, those CDRMs are hard to replace.

The DRM format is very close to Tomb Raider Underworld's contains the exact same components except the duplicated DRM Section info at the end of the DRM which is new. The only unknown field is the last 32-bit unsigned integer of the second DRM Section info, everything else is known. The value itself could be related to struct relocation or memory mapping.

I checked the code for your tool. I think the offset calculation is wrong. Also the game needs all hashes to be ordered in ascending order or it will crash.

Regards.

This was working with the vanilla game, without any updates, now its not. I thought there was more CDRM sections needed in new file to stop the crash(they seem to be loading 0x8000 bytes at ones and doing some switch case logic. So I thought more sections, still learning  ).I fixed one offset calculation in NEXT section, I hope that's the one you're talking about. 

You mean the hashes in the tiger header right?
If ascending order is needed then complete file repack will be required or a binary patch if its a simple security check. What do you think?
## Post #419
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-15T13:41:06+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from rajasrijan
>
> 
So I thought more sections, still learning  ).I fixed one offset calculation in NEXT section, I hope that's the one you're talking about.

I mean the direct offset for both tiger->drm and drm->cdrm is wrong. (Try it on patch.000.tiger it's very likely your tool will crash)

> Reply from rajasrijan
>
> 
This was working with the vanilla game, without any updates, now its not.

Save yourself the trouble and work with the patched version of the game. By doing so, you can simply modify the patch.*.tiger file which is much smaller. Adding new DRM files to those means they are loaded instead of the ones in the original Bigfile.

> Reply from rajasrijan
>
> 
I thought there was more CDRM sections needed in new file to stop the crash(they seem to be loading 0x8000 bytes at ones and doing some switch case logic.

I'm not sure what you mean by this, could you explain it further please? If i recall correctly, CDRM files are not always compressed. That is very important, take a look at my tools here: [https://github.com/Gh0stblade/cdcEngineTools](https://github.com/Gh0stblade/cdcEngineTools) those are for TR8 though.

> Reply from rajasrijan
>
> 
You mean the hashes in the tiger header right?
If ascending order is needed then complete file repack will be required or a binary patch if its a simple security check. What do you think?

Yep, hashes in the tiger header must be sorted by ascending order or the engine will crash. I wrote an injector years ago and couldn't figure out why I kept getting crashes, turns out that was the problem. If you just work with the patch files then repacking will be much easier. From a technical perspective you shouldn't be altering the Bigfile.000.tiger since effectively, if you alter a file in there which has been patched in patch.000.tiger it will have no effect.

Regards.
## Post #420
- Username: rajasrijan
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 04, 2014 11:31 pm
- Post datetime: 2016-02-21T05:25:00+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hi,

> Save yourself the trouble and work with the patched version of the game. By doing so, you can simply modify the patch.*.tiger file which is much smaller. Adding new DRM files to those means they are loaded instead of the ones in the original Bigfile.

Patch files seem to contain a lot of RDEF files. Any idea what those are?

> I mean the direct offset for both tiger->drm and drm->cdrm is wrong. (Try it on patch.000.tiger it's very likely your tool will crash)

fixed. now it should work with all files

regards
## Post #421
- Username: chroiz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 19, 2016 7:21 pm
- Post datetime: 2016-03-19T11:24:56+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hey, I have a problem with the DRM Dumper. 
I extracted everything fine but when I choose to extract a DRM file the program says 



Any ideas?
## Post #422
- Username: chroiz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 19, 2016 7:21 pm
- Post datetime: 2016-03-19T13:48:35+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Duh, already got it!

And then another question, was there already the possibility to extract a model with the corresponding textures/materials extracting with it? That would save me alot of time
## Post #423
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-03-28T11:00:38+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Material strange life, a single pointer, even to the number of names graphics. 

```
95 02 00 00 00 00 00 00 01 00 00 00 20 00 02 00 
05 00 00 00 00 00 00 00 00 00 00 00 20 01 00 00 
95 02 00 00 00 00 00 00 01 00 00 00 20 00 02 00 
05 00 00 00 00 00 00 00 00 00 00 00 20 01 00 00 
95 02 00 00 00 00 00 00 01 00 00 00 20 03 02 00 
05 00 00 00 00 00 00 00 00 00 00 00 20 01 00 00 
17 00 00 00 00 00 00 00 03 00 00 00 8C 02 00 00 
06 00 00 00 00 00 00 00 00 00 00 00 2D 00 00 00 
95 02 00 00 00 00 00 00 01 00 00 00 20 00 02 00 
05 00 00 00 00 00 00 00 00 00 00 00 20 01 00 00 
95 02 00 00 00 00 00 00 01 00 00 00 20 00 02 00 
05 00 00 00 00 00 00 00 00 00 00 00 20 01 00 00

```

Stupid option parsing :

```
 uint test = 0;
 while (test != 0x00020020 && test !=0x00020120 )
          { test = MaterialStream.ReadValueU32();}
 MaterialStream.Position -=0x10;

```

Can anyone a better idea ?
## Post #424
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-03-28T13:49:05+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Paliha
>
> Material strange life, a single pointer, even to the number of names graphics. 
Code: Select all id resource                                      flag
95 02 00 00 00 00 00 00 01 00 00 00 20 00 02 00 
05 00 00 00 00 00 00 00 00 00 00 00 20 01 00 00 
95 02 00 00 00 00 00 00 01 00 00 00 20 00 02 00 
05 00 00 00 00 00 00 00 00 00 00 00 20 01 00 00 
95 02 00 00 00 00 00 00 01 00 00 00 20 03 02 00 
05 00 00 00 00 00 00 00 00 00 00 00 20 01 00 00 
17 00 00 00 00 00 00 00 03 00 00 00 8C 02 00 00 
06 00 00 00 00 00 00 00 00 00 00 00 2D 00 00 00 
95 02 00 00 00 00 00 00 01 00 00 00 20 00 02 00 
05 00 00 00 00 00 00 00 00 00 00 00 20 01 00 00 
95 02 00 00 00 00 00 00 01 00 00 00 20 00 02 00 
05 00 00 00 00 00 00 00 00 00 00 00 20 01 00 00

Stupid option parsing :
Code: Select all MaterialStream.Position = MaterialStream.Length - 0x120;
 uint test = 0;
 while (test != 0x00020020 && test !=0x00020120 )
          { test = MaterialStream.ReadValueU32();}
 MaterialStream.Position -=0x10;

Can anyone a better idea ?
I wrote a material parser for Tomb Raider: Underworld not so long ago. You're best off reading the entire format rather than skipping to the EOF. That code was adapted by Aman who made it compatible with TR2013. You could take a look at his variant of the Noesis importer.

Nevertheless, loading material files is a waste of time.

Regards.
## Post #425
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-03-28T14:22:25+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Gh0stBlade
>
> 
I wrote a material parser for Tomb Raider: Underworld not so long ago. You're best off reading the entire format rather than skipping to the EOF. That code was adapted by Aman who made it compatible with TR2013. You could take a look at his variant of the Noesis importer.

Nevertheless, loading material files is a waste of time.

Regards.
The problem is not in the table, and how to get it to start. 
In Tomb Raider: Underworld were pointers to the offset , and number of resources in the table. 
Suggest that in Rice the same story, haven't watched, but will soon undertake.

In my program I did the formats that are supported by NoeSis, but only if conservation of the resource. In NoeSis, very weak Help_SDK, and Python is almost non-typed language, not very comfortable to read such scripts, plus have not figured out how to debug using the console window, the same is not an option.
## Post #426
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-03-28T14:50:36+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Paliha
>
> Gh0stBlade wrote:
I wrote a material parser for Tomb Raider: Underworld not so long ago. You're best off reading the entire format rather than skipping to the EOF. That code was adapted by Aman who made it compatible with TR2013. You could take a look at his variant of the Noesis importer.

Nevertheless, loading material files is a waste of time.

Regards.
The problem is not in the table, and how to get it to start. 
In Tomb Raider: Underworld were pointers to the offset , and number of resources in the table. 
Suggest that in Rice the same story, haven't watched, but will soon undertake.

In my program I did the formats that are supported by NoeSis, but only if conservation of the resource. In NoeSis, very weak Help_SDK, and Python is almost non-typed language, not very comfortable to read such scripts, plus have not figured out how to debug using the console window, the same is not an option.

I'm confused and find it difficult to understand what point you are trying to make. From your previous post you suggested you wanted better ideas on how to parse the Material format and I provided you with a solution. It's not too difficult to port Python code to other languages, it took me a few minutes to port some of the mesh importers I wrote for Noesis to my engine:



What are you trying to do?
## Post #427
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-03-28T15:15:40+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Materia from Tomb Raider - Underworld 

```
int tcount = MaterialStream.ReadByte(); << !!!!
MaterialStream.Position = MaterialStream.Length - tcount * 0x10; < !!!

```

Hop...pick up the table )))
In the last three games not even a pointer to the count...)))
This is my app:
[http://www.tombraiderforums.com/showthread.php?t=214300](http://www.tombraiderforums.com/showthread.php?t=214300)
## Post #428
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2016-03-28T22:10:29+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hmm very nice things are in containers DRMRiseTR.

The materials of the even more mysterious..)))
ana_companion_0B12.matd :

```
F6 01 00 00 0F D0 0F D0 00 00 00 00 04 0B 02 00 
F7 01 00 00 0F D0 0F D0 00 00 00 00 03 14 02 00 
84 02 00 00 0F D0 0F D0 00 00 00 00 01 19 02 00 
F9 01 00 00 0F D0 0F D0 00 00 00 00 00 21 02 00 
FA 01 00 00 0F D0 0F D0 00 00 00 00 03 2C 02 00 
2A 00 00 00 0F D0 0F D0 00 00 00 00 02 31 02 00 
FB 01 00 00 0F D0 0F D0 00 00 00 00 03 3C 02 00 
07 00 00 00 0F D0 0F D0 00 00 00 00 90 01 00 00 
FB 01 00 00 0F D0 0F D0 00 00 00 00 03 0C 02 00 
84 02 00 00 0F D0 0F D0 00 00 00 00 01 11 02 00 
FA 01 00 00 0F D0 0F D0 00 00 00 00 03 1C 02 00 
F6 01 00 00 0F D0 0F D0 00 00 00 00 04 23 02 00 
F9 01 00 00 0F D0 0F D0 00 00 00 00 00 29 02 00 
F7 01 00 00 0F D0 0F D0 00 00 00 00 03 34 02 00 
2A 00 00 00 0F D0 0F D0 00 00 00 00 02 39 02 00 
07 00 00 00 0F D0 0F D0 00 00 00 00 90 01 00 00 
F6 01 00 00 0F D0 0F D0 00 00 00 00 04 0B 02 00 
F7 01 00 00 0F D0 0F D0 00 00 00 00 03 14 02 00 
84 02 00 00 0F D0 0F D0 00 00 00 00 01 19 02 00 
F9 01 00 00 0F D0 0F D0 00 00 00 00 00 21 02 00 
FA 01 00 00 0F D0 0F D0 00 00 00 00 03 2C 02 00 
2A 00 00 00 0F D0 0F D0 00 00 00 00 02 31 02 00 
FB 01 00 00 0F D0 0F D0 00 00 00 00 03 3C 02 00 
07 00 00 00 0F D0 0F D0 00 00 00 00 90 01 00

```
## Post #429
- Username: rajasrijan
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 04, 2014 11:31 pm
- Post datetime: 2017-04-23T17:58:28+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

I've made progress on packing

Screenshot of GUI. GUI can only extract and pack images. But from console you can pack all other formats(except locals) given they are already in game recognized format (FSB for audio,PDCMeshes). I'm trying to reverse more formats.






Screenshot after packing dds. Note the text was "Test" but game is mirroring texture.



> I'm confused and find it difficult to understand what point you are trying to make. From your previous post you suggested you wanted better ideas on how to parse the Material format and I provided you with a solution. It's not too difficult to port Python code to other languages, it took me a few minutes to port some of the mesh importers I wrote for Noesis to my engine:

@Gh0stBlade can you please share your script to parse meshs. I'm little stuck there. The scipt posted in first page is giving me garbage meshes.
## Post #430
- Username: shadowlonely1989
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-04-23T19:42:21+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from rajasrijan
>
> I've made progress on packing

Screenshot of GUI. GUI can only extract and pack images. But from console you can pack all other formats(except locals) given they are already in game recognized format (FSB for audio,PDCMeshes). I'm trying to reverse more formats.





Screenshot after packing dds. Note the text was "Test" but game is mirroring texture.


I'm confused and find it difficult to understand what point you are trying to make. From your previous post you suggested you wanted better ideas on how to parse the Material format and I provided you with a solution. It's not too difficult to port Python code to other languages, it took me a few minutes to port some of the mesh importers I wrote for Noesis to my engine:

@Gh0stBlade can you please share your script to parse meshs. I'm little stuck there. The scipt posted in first page is giving me garbage meshes.

Great work  The script in the main post works 100% fine on all meshes, can you show a picture of this garbage meshes and upload the sample?

Also, we already have texture/model importers thanks to Aman over at TombRaiderForums.com I hope your tool can improve usability since the current tool is commandline based.

[https://www.youtube.com/watch?v=hU70heTrmpg](https://www.youtube.com/watch?v=hU70heTrmpg)


Cheers.
## Post #431
- Username: rajasrijan
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 04, 2014 11:31 pm
- Post datetime: 2017-04-24T15:24:59+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Yup worked . I made mistake when converting to c++ code.  
Next step, edit and repack.
## Post #432
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2017-07-21T21:00:43+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from rajasrijan
>
> I've made progress on packing

Screenshot of GUI. GUI can only extract and pack images. But from console you can pack all other formats(except locals) given they are already in game recognized format (FSB for audio,PDCMeshes). I'm trying to reverse more formats.

Is this TRExplorer? Is there a GUI version downloadable? I have no idea how to handle source codes. Thanks in advance.
## Post #433
- Username: dedood2008
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 12, 2018 11:17 pm
- Post datetime: 2018-01-18T19:30:12+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from michalss
>
> files 000 and 001 is basically 1 file cutted on to 2 pieces you script wont work on this unless you merge them
well that link is dead
## Post #434
- Username: dedood2008
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 12, 2018 11:17 pm
- Post datetime: 2018-01-18T20:16:22+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Ekey
>
> 

Gibbed Tiger Unpacker (rev117) / Rick
Download: here
Usage:
Gibbed.TombRaider9.Unpack "szTIGERarchive" "szOutputFolder"
Example:
Gibbed.TombRaider9.Unpack "c:\Tomb Raider\title.000.tiger" "c:\Tomb Raider\unpacked\title"
DRM Dumper (1.0.1.2) / Ekey (h4x0r)
Download: here
Usage:
1) Unpack Tiger archive
2) Run DRMDumper
3) Select game path
4) Open .DRM files
5) Profit
Additional thanks to  howfie 



RenderMesh plugin for Noesis (1.5beta) / MrNightmareTM
Download: here
Usage:
1) Download Noesis
2) Copy plugin in "plugins\python" folder
3) Profit
whare can i download Noesis?
## Post #435
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2018-01-19T02:43:57+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from dedood2008
>
> Ekey wrote:

Gibbed Tiger Unpacker (rev117) / Rick
Download: here
Usage:
Gibbed.TombRaider9.Unpack "szTIGERarchive" "szOutputFolder"
Example:
Gibbed.TombRaider9.Unpack "c:\Tomb Raider\title.000.tiger" "c:\Tomb Raider\unpacked\title"
DRM Dumper (1.0.1.2) / Ekey (h4x0r)
Download: here
Usage:
1) Unpack Tiger archive
2) Run DRMDumper
3) Select game path
4) Open .DRM files
5) Profit
Additional thanks to  howfie 



RenderMesh plugin for Noesis (1.5beta) / MrNightmareTM
Download: here
Usage:
1) Download Noesis
2) Copy plugin in "plugins\python" folder
3) Profit

whare can i download Noesis?
[http://richwhitehouse.com/index.php?con ... ojects.php](http://richwhitehouse.com/index.php?content=inc_projects.php)

Actually googled 'noesis'
## Post #436
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-04-27T22:27:53+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

I have been searching and searching
and i can't seem to find the DRM Dumper anywhere beacuse the link here is dead    

So does anyone have the dumper laying around by any chance?  

Edit:I found i had the dumper in my drive hidden away the dumper is from 24-03-2013 but it works

But i think the Noesis Python is having issue's with weights beacuse this happens when i import it into Blender
[Alex_Cage.JPG](https://xentaxbackup.github.io/file/14283_Alex_Cage.JPG)
## Post #437
- Username: dedood2008
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 12, 2018 11:17 pm
- Post datetime: 2018-05-18T15:01:51+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

that link to the drm dumper is dead does eny one have one laying around?
## Post #438
- Username: rajasrijan
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 04, 2014 11:31 pm
- Post datetime: 2018-05-22T15:41:20+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

I've been successful in importing mesh back into game, mesh modding might be possible soon 
There are still some problems with importing bones.



I'm having same issue as @Faithfullfaun with bones (attaching screenshot) . I've used python noesis plugin to export mesh.
Since my code is based on the plugin i'm seeing same issues ingame.



Can some Pro. please take a look at the script.   
Tagging @Gh0stBlade, @Ekey (sorry for the spam)

Thanks
## Post #439
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-05-22T18:17:18+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from rajasrijan
>
> I've been successful in importing mesh back into game, mesh modding might be possible soon 
There are still some problems with importing bones.



I'm having same issue as @Faithfullfaun with bones (attaching screenshot) . I've used python noesis plugin to export mesh.
Since my code is based on the plugin i'm seeing same issues ingame.



Can some Pro. please take a look at the script.   
Tagging @Gh0stBlade, @Ekey (sorry for the spam)

Thanks

I found out that you have to export as DAE. with that the bones and weight works fine
## Post #440
- Username: rajasrijan
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 04, 2014 11:31 pm
- Post datetime: 2018-05-23T07:25:48+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Faithfullfaun
>
> rajasrijan wrote:I've been successful in importing mesh back into game, mesh modding might be possible soon 
There are still some problems with importing bones.



I'm having same issue as @Faithfullfaun with bones (attaching screenshot) . I've used python noesis plugin to export mesh.
Since my code is based on the plugin i'm seeing same issues ingame.



Can some Pro. please take a look at the script.   
Tagging @Gh0stBlade, @Ekey (sorry for the spam)

Thanks

I found out that you have to export as DAE. with that the bones and weight works fine

I'm already exporting as DAE. What is your noesis version and blender version?
The python plugin I have mentioned the version as 1.6beta.
## Post #441
- Username: rajasrijan
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-05-23T12:59:43+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Upload Lara's mesh and I'll take a look.
## Post #442
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-05-24T12:50:17+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

The Noesis plugin i use is called

fmt_TRAS_mesh_1_3_1_1-tex
## Post #443
- Username: rajasrijan
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 04, 2014 11:31 pm
- Post datetime: 2018-05-25T18:02:07+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Thanks @Gh0stBlade. Uploaded generated .dae file and original mesh. dae file is generated using noesis plugin mentioned in first page.

[https://www.dropbox.com/s/6yj62w4jtss23 ... a.zip?dl=0](https://www.dropbox.com/s/6yj62w4jtss232t/v2_lara.zip?dl=0)

@Faithfullfaun i tracked down fmt_TRAS_mesh_1_3_1_1-tex.py file. I'm getting same issue.
## Post #444
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-05-25T18:12:46+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from rajasrijan
>
> Thanks @Gh0stBlade. Uploaded generated .dae file and original mesh. dae file is generated using noesis plugin mentioned in first page.

https://www.dropbox.com/s/6yj62w4jtss23 ... a.zip?dl=0

@Faithfullfaun i tracked down fmt_TRAS_mesh_1_3_1_1-tex.py file. I'm getting same issue.

Looks like a bug with Noesis' exporter then of the importer for the app you're importing the meshes into.
## Post #445
- Username: Yikiho
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 10, 2018 8:01 pm
- Post datetime: 2018-06-10T14:56:20+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

DRM Dumper link is dead
## Post #446
- Username: T0M099
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 02, 2013 1:12 am
- Post datetime: 2018-07-03T07:52:52+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Yikiho
>
> DRM Dumper link is dead

Reupload (credits goes to the creator of dumper - Ekey)

DRM Dumper 1.0.1.2 by h4x0r (Ekey)

```
https://mega.nz/#!S8B2WIyJ!g5uqlHHNFTOFa2C0o0pz9R5bERhe7e0je0UuXxf8jm4
```
## Post #447
- Username: sergop
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Apr 21, 2017 8:47 pm
- Post datetime: 2018-11-21T17:46:07+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

I saw something about a repacker does it work and how to use it?
## Post #448
- Username: sergop
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Apr 21, 2017 8:47 pm
- Post datetime: 2018-12-12T15:47:57+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

For the people wanting to make a translation. It is possible to do so. First go to [http://tombraider.hu/letoltesek/tomb-raider](http://tombraider.hu/letoltesek/tomb-raider) and download the tool. Then extract from TR.hu.trtr with any winrar or 7zip and edit the hungarian translation. Replace the files and apply the patch. All the thanks goes to swuforce and the people behind the hungarian translation.
[https://imgur.com/a/Hf2Jw0k](https://imgur.com/a/Hf2Jw0k)
## Post #449
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2018-12-14T08:33:32+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from sergop
>
> For the people wanting to make a translation. It is possible to do so. First go to http://tombraider.hu/letoltesek/tomb-raider and download the tool. Then extract from TR.hu.trtr with any winrar or 7zip and edit the hungarian translation. Replace the files and apply the patch. All the thanks goes to swuforce and the people behind the hungarian translation.
https://imgur.com/a/Hf2Jw0k
Thanks! Can i edit font file? Because the font ingame not support my language!
## Post #450
- Username: sergop
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Apr 21, 2017 8:47 pm
- Post datetime: 2018-12-14T20:01:37+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from shadowlonely1989
>
> sergop wrote:For the people wanting to make a translation. It is possible to do so. First go to http://tombraider.hu/letoltesek/tomb-raider and download the tool. Then extract from TR.hu.trtr with any winrar or 7zip and edit the hungarian translation. Replace the files and apply the patch. All the thanks goes to swuforce and the people behind the hungarian translation.
https://imgur.com/a/Hf2Jw0k
Thanks! Can i edit font file? Because the font ingame not support my language!
I don't know mby try ask the people in zenhax cuz this method came from there. As far as i know there is no universal packer or repacker so this may not work for you. Btw what is your language.
## Post #451
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2018-12-15T00:48:13+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from sergop
>
> shadowlonely1989 wrote:sergop wrote:For the people wanting to make a translation. It is possible to do so. First go to http://tombraider.hu/letoltesek/tomb-raider and download the tool. Then extract from TR.hu.trtr with any winrar or 7zip and edit the hungarian translation. Replace the files and apply the patch. All the thanks goes to swuforce and the people behind the hungarian translation.
https://imgur.com/a/Hf2Jw0k
Thanks! Can i edit font file? Because the font ingame not support my language!
I don't know mby try ask the people in zenhax cuz this method came from there. As far as i know there is no universal packer or repacker so this may not work for you. Btw what is your language.
Thanks! My language is Vietnamese! Maybe this game support their language.
## Post #452
- Username: sergop
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Apr 21, 2017 8:47 pm
- Post datetime: 2018-12-16T11:14:26+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from shadowlonely1989
>
> 
Thanks! My language is Vietnamese! Maybe this game support their language.
Well you can try to replace all xml:lang="en'' with the chinese mark or with a mark that supports fonts for  your language (i don't know much about Vietnamese) to test if it would replace in that language. Hope it'll work.
Edit: Or maybe check in info.xml to see if you can add fonts or characters.
## Post #453
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2018-12-17T00:46:47+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from sergop
>
> shadowlonely1989 wrote:
Thanks! My language is Vietnamese! Maybe this game support their language.
Well you can try to replace all xml:lang="en'' with the chinese mark or with a mark that supports fonts for  your language (i don't know much about Vietnamese) to test if it would replace in that language. Hope it'll work.
Edit: Or maybe check in info.xml to see if you can add fonts or characters.
Can I add new font with info.xml? My file's font is fontviet.gfx!
## Post #454
- Username: sergop
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Apr 21, 2017 8:47 pm
- Post datetime: 2018-12-17T22:12:51+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from shadowlonely1989
>
> sergop wrote:shadowlonely1989 wrote:
Thanks! My language is Vietnamese! Maybe this game support their language.
Well you can try to replace all xml:lang="en'' with the chinese mark or with a mark that supports fonts for  your language (i don't know much about Vietnamese) to test if it would replace in that language. Hope it'll work.
Edit: Or maybe check in info.xml to see if you can add fonts or characters.
Can I add new font with info.xml? My file's font is fontviet.gfx!
I'd say try with a few characters and translate something to test.
## Post #455
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2019-04-02T03:28:39+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from chroiz ↑Sat Mar 19, 2016 7:24 pm at Sat Mar 19, 2016 7:24 pm
>
> 
Hey, I have a problem with the DRM Dumper. 
I extracted everything fine but when I choose to extract a DRM file the program says 



Any ideas?

I have the same issue, I wish you had given us your solution, because I can't extract any of the DRMs.
## Post #456
- Username: zakizakizaki
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 17, 2016 9:06 am
- Post datetime: 2020-04-26T21:12:21+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from Ekey ↑Tue Feb 26, 2013 5:07 am at Tue Feb 26, 2013 5:07 am
>
> 

Hello there, Ekey. 
I was modding TR9 for some time, and me and some people got the issue with DRM dumper. So, I would ask you, is there any chance that you could update unpacker that supports the patch files properly?
The thing is - DRM dumper (1.0.1.2) do not export Lara's meshes from patch file of TR9 (v1- v5 Lara's).
## Post #457
- Username: Imtiaz5683
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 15, 2020 12:05 pm
- Post datetime: 2020-06-15T04:20:11+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

DRM dumper is unable to download please upload it again.
## Post #458
- Username: gomi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 17, 2016 9:49 am
- Post datetime: 2020-06-30T22:57:29+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

yes, DRM dumper is down and can I use this tool for Rise of Tomb Raider ??? I tried but did not work.
## Post #459
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2020-07-06T20:28:37+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

You wonderful internet mother lovers are in luck, because Uncle Kingfisher13 has you covered. I found the latest versions of all the Tomb Raider 2013 extraction tools on my computer, and I have a link for you guys to use for the DRM tool. 

[https://drive.google.com/file/d/1Hc3Dwb ... sp=sharing](https://drive.google.com/file/d/1Hc3DwbHrUKr9tmMmAds8FtJ9lYSbYkC6/view?usp=sharing)

Also, for the people concerned about the latest update for the game breaking the tools, there is a solution my friends. I didn't know this was possible, but you can actually force steam to download older versions of a game you own than the current one. Google it, there are several good tutorials out there for this.
## Post #460
- Username: spamll
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 10, 2020 10:22 am
- Post datetime: 2020-07-10T05:30:01+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

> Reply from kingfisher13 ↑Tue Jul 07, 2020 4:28 am at Tue Jul 07, 2020 4:28 am
>
> 
You wonderful internet mother lovers are in luck, because Uncle Kingfisher13 has you covered. I found the latest versions of all the Tomb Raider 2013 extraction tools on my computer, and I have a link for you guys to use for the DRM tool. 

https://drive.google.com/file/d/1Hc3Dwb ... sp=sharing

Also, for the people concerned about the latest update for the game breaking the tools, there is a solution my friends. I didn't know this was possible, but you can actually force steam to download older versions of a game you own than the current one. Google it, there are several good tutorials out there for this.

Thank you for providing this download.  But as was mentioned above, "The thing is - DRM dumper (1.0.1.2) do not export Lara's meshes from patch file of TR9 (v1- v5 Lara's)".

I'm not sure if "v4_lara" and "v5_lara" are the versions that will include the Ellie (from The Last of Us - linked below) mod, but that is what I'm looking for, too.  Seems the mesh are not there.  And I can't find Ellie's textures either.  Thank you.

Anyone know the specific .drm name for Ellie's model?

[https://www.youtube.com/watch?v=ah7qcdu2a_s](https://www.youtube.com/watch?v=ah7qcdu2a_s)
## Post #461
- Username: RonaldGriggs
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 06, 2019 10:40 am
- Post datetime: 2020-07-21T10:26:20+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

This bob the robber  on hudgames summarizes my 7th grade, often playing stealth in school on hudgames
## Post #462
- Username: frkndgnr
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 10, 2020 2:13 pm
- Post datetime: 2020-10-10T06:19:24+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

"Gibbed Tiger Unpacker" how can I use this to open the language files of the game "Marvel's Avengers"?
## Post #463
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-10-11T11:35:18+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Does anyone know how to get the Gibbed Unpacker to work? For me, it only partially extracts the game's files.

Cheers
## Post #464
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-10-11T13:14:24+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

For clarity, I can extract the TIGER files, but most of the .DRM files are missing/labeled unknown.
## Post #465
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-05-23T21:10:37+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hey, sorry for the necro, but is every music file supposedly located in Bigfile.000? Because I can't find any of the cinematic music that also seems to magically cut when you just have music turned on in the game, meaning the devs made cine music read as SFX or voice overs.
## Post #466
- Username: OtosKomos
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 29, 2021 8:58 pm
- Post datetime: 2021-09-07T14:30:52+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Can I ask a basic question?
I was able to get the source code of the tools on Github and build it in Visual studio, but when I try to unpack the file with a command,  I can not do it as follows.

===-===========
D:\modsfile\TR2013\translatr\translatr-release_0.2.1\translatr\bin\Debug>translatr extract en D:\modsfile\TR2013\unpacked\GOG\bigfile.000.tiger D:\modsfile\TR2013\unpacked\GOG\patch.000.tiger

translatr 0.2.1
by sephiroth99


unhandled exception: System.IO.DirectoryNotFoundException:　Could not find part of the path 'D:\modsfile\TR2013\unpacked\GOG\bigfile.000.tiger'
   place System.IO.__Error.WinIOError(Int32 errorCode, String maybeFullPath)
   place System.IO.Directory.InternalGetFileDirectoryNames(String path, String userPathOriginal, String searchPattern, Boolean includeFiles, Boolean includeDirs, SearchOption searchOption)
   place System.IO.Directory.GetFiles(String path, String searchPattern, SearchOption searchOption)
   place translatr.Locale.getLocaleMask(String dir) 場所 D:\mods file\TR2013\translatr\translatr-release_0.2.1\translatr\Locale.cs:line 31
   place translatr.Extractor.doExtract(String[] args) 場所 D:\mods file\TR2013\translatr\translatr-release_0.2.1\translatr\Extractor.cs:line 94
   place translatr.Program.Main(String[] args) 場所 D:\mods file\TR2013\translatr\translatr-release_0.2.1\translatr\Program.cs:line 37
==============

Is this the wrong way to build? I would be grateful if anyone could tell me.
Gibbed tomraider9 unpacker with exe file could unpack.
## Post #467
- Username: kosemen76
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 05, 2019 6:05 am
- Post datetime: 2022-10-30T11:49:23+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

How can I extract the tomb raider 2013 ps3 bigfile tiger files. I couldn't find it in this forum. Can anyone post a tutorial. Please help. I want to localize the game
## Post #468
- Username: junkymana
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 05, 2017 11:01 am
- Post datetime: 2023-03-10T19:31:55+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hi guys, I just managed to make this drm dumper work again. So I will mention what worked for me.

After extracting both Gibbed Tiger Unpacker & DRM Dumper into where Tomb raider is installed, I unpacked bigfile.000.tiger by dragging it on top of TR9DRMDumper.exe and then once all was extracted I opened the file Settings.ini
Here I put the installation path of the game. First it didn't work, so I tried putting the path of the unpacked .tiger (Tomb Raider\bigfile.000_unpack\default\pc-w) and then it started working all of a sudden. I just double checkedd the path right now and it only has the game root, so it looks like DRM Dumper has changed this after working or I don't know.

I must mention that I also did downgrade my steam version of the game to the very first, you can find a tutorial here: [https://www.makeuseof.com/how-to-downgrade-steam-games/](https://www.makeuseof.com/how-to-downgrade-steam-games/)

I hope it can help anyone
You all take care.

BTW, here I share a folder with the tools to extract from the whole trilogy of the reboot TR games: [https://mega.nz/folder/5l5EEILB#JTv19I6bixwfDRUkJrB75Q](https://mega.nz/folder/5l5EEILB#JTv19I6bixwfDRUkJrB75Q)
## Post #469
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2023-08-11T15:00:26+00:00
- Post Title: Re: Tomb Raider (2013) (PC) (PS3) (XBOX) (*.tiger)

Hey, I'm wondering if someone could make the TR9 Blender import-export script to function on Blender v3.0+? It's from the TR forum covering the model modding for the game, version 0.5. It seems to only work on 2.76.

Or even v2.8 or 2.9 would be nice, but I barely can use the 2.7x versions with the old UI.

[https://www.mediafire.com/file/pxnzzs9o ... _5.py/file](https://www.mediafire.com/file/pxnzzs9o10etnkl/io_TR9_mod_tool_v0_5.py/file)
