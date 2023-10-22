## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-08-20T11:28:47+00:00
- Post Title: Need help on Tales of Vesperia[X360] files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Zipslow
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 07, 2009 7:25 pm
- Post datetime: 2009-09-18T23:00:08+00:00
- Post Title: Need help on Tales of Vesperia[X360] files

Format (FPS4) might be as posted here on [gbatemp](http://gbatemp.net/index.php?showtopic=123050&st=0&p=1642444&#entry1642444) ?
## Post #3
- Username: Zipslow
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 07, 2009 7:25 pm
- Post datetime: 2009-09-22T10:11:44+00:00
- Post Title: Need help on Tales of Vesperia[X360] files

Here is an extractor for the SVO files .... [http://www.brisma.net/2008/09/15/tales- ... g-parte-1/](http://www.brisma.net/2008/09/15/tales-of-vesperia-hacking-parte-1/) .... but then you still end up with the  fatduck's mysterious .dat files.....
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-09-27T07:02:04+00:00
- Post Title: Need help on Tales of Vesperia[X360] files

Actually, you can easily "unpack" the svo file!

Here is my QuickBMS unpack script:

```
# by fatduck     Aug09
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "FPS4"
endian big
get NUMRES long
goto 0x1C

for i = 1 to NUMRES
    get RESSTART long
    get CHUNKSIZE long
    get RESSIZE long
    getdstring RESNAME 0x20    
    log RESNAME RESSTART RESSIZE
next i

```


The problem is after extract, all individual files are then compressed with a unknown method!

By the way, that link to the blog have another game I am interested, Tales of the World: Radiant Mythology (PSP).
But I can't understand, is it spinish? Coud you translate it for me? [http://www.brisma.net/2008/03/29/tales- ... ology-psp/](http://www.brisma.net/2008/03/29/tales-of-the-world-radiant-mythology-psp/)
## Post #5
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2009-09-27T12:07:30+00:00
- Post Title: Need help on Tales of Vesperia[X360] files

it's italian  it talks about the file structure of arc files (veeery simple, i made an extractor/reinserter but i lost it with my hard drive  ) and then it talks about sub-archives which are simply compressed with gzip

[edit] i found the [Unpacker](http://www.tbhreloaded.it/Vash/PspArcExtractorv09.rar) and the [Bin Dumper](http://www.tbhreloaded.it/Vash/Dumper.rar)
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-07T00:36:38+00:00
- Post Title: Need help on Tales of Vesperia[X360] files

Here is the tales of Vesperia extractor
[http://www.tbhreloaded.it/Vash/VsoEx.rar](http://www.tbhreloaded.it/Vash/VsoEx.rar)
I am close to an decompress program it is very close to lzss.
it looks like a modified version of it like the fpk format.
## Post #7
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-11-24T12:36:38+00:00
- Post Title: Need help on Tales of Vesperia[X360] files

Do you mean 8ing fpk format! I know that format but I have no cue on this one!

Any news!?
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-12-20T17:42:18+00:00
- Post Title: Need help on Tales of Vesperia[X360] files

The tool xbdecompress.exe extracts these files perfectly
## Post #9
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-12-21T07:00:42+00:00
- Post Title: Need help on Tales of Vesperia[X360] files

Chrrox

Which version of xbdecompress did you use?
I use the one aluigi post and it didn't work!?

I got the message said:
xbdecompress: error: file was compressed using an encoder with different version than the decoder
xbdecompress: warning: failed to decompress to file est_c001.res

The header in Tales of Vesperia files are 0F F5 12 EE!!!

I also tried aluigi's BMS script, but it crash!?
## Post #10
- Username: bwin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jan 01, 2010 9:31 am
- Post datetime: 2010-01-04T02:32:50+00:00
- Post Title: Need help on Tales of Vesperia[X360] files

Hi guys, I found this topic by lurking and googling, and I thought I'd add my two cents.

I've done a little bit of tampering with the files, and this is what I got:
Using files from the game:
1. Using VsoEx, I unpacked chara.svo, I then got multiple .dat files with a 0FF5 12EE header.
2. Using xbdecompress rev 6654, I uncompressed some of these .DAT files successfully (and more precisely BTL_PAT_C000_DEF.DAT)
3. I'm now stuck with FPS4 files that I can't unpack, be it with fatduck's BMS script (gives bogus files) or VsoEx (gives a segmentation fault). These files seem to contain more FPS4 files...?

Using files from the demo:
After having unpacked UI.svo, I got multiple .TXM and .TXV files, the former being, I guess, maps of the latter.
After playing a little with TileMolester, I noticed that the .TXV files were 32bpp, GRAB and swizzled images.
Using 360deswizzle, I found myself with "proper" DDS files. I then just had to switch the R G B and Alpha channels with Photoshop.

Result sample:
[Download here](http://www.mediafire.com/?tynjtoqmxzk)

So all that's left to do is, I guess, unpack the above mentioned FPS4 files.
## Post #11
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-02-05T09:30:21+00:00
- Post Title: Need help on Tales of Vesperia[X360] files

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-05T10:34:44+00:00
- Post Title: Need help on Tales of Vesperia[X360] files

```
string NAME += ".unpacked"
comtype PUYO_LZ01
get TYPE byte
get ZSIZE long
get SIZE long
savepos OFFSET
clog NAME OFFSET ZSIZE SIZE
```

for who is interested in the algorithm and in the technical stuff, it's simply lzss with an init char (the one used to fill the sliding window at the beginning) equal to 0x00 instead of 0x20.
the fact is that using comtype lzss "12 4 2 2 0" wasn't good because the decompressed data is bigger than how much specified by the header (the second 32bit value) and so the algorithm returned -1 while that PUYO_LZ01 does exactly the same but breaks at the specified output size.
## Post #13
- Username: bwin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jan 01, 2010 9:31 am
- Post datetime: 2010-02-05T11:49:52+00:00
- Post Title: Need help on Tales of Vesperia[X360] files

Nice job!

I was wondering, is there any way to deswizzle X360 Direct Draw textures that are not 32bit A8 R8 G8 B8? I found various textures that seem to be swizzled 16bit A4 R4 G4 B4 (i.e. I can only get the colors right by swapping the A and G, then R and B channels, but it's still scrambled) and also some 8bit textures. Not sure if this is relevant to the thread, but... I'd appreciate any help.

TXV files are simply big endian DDS files without header. Header information is stored in a TXM map file

TXM structure (C-like code)

```
	uint32 width;
	uint32 height;
	uint32 unknown2;
	uint32 imageformat; // ?? Not sure of that one. 0x18280186 = 32bit A8R8G8B8, 0x1A200154 = ??; 0x1828014F = 16bit A4R4G4B4
	uint32 nameoffset; // from here
	uint8 paddingentry[0x44];
} TXM_VESPER_DATA_ENTRY;

typedef struct TXM_VESPER_HEADER {
	uint32 signature; //0x20000
	uint32 filesize;
	uint32 unknown1; // 0x4 ?
	uint32 filecount;
	uint8 padding1[0x44];
} TXM_VESPER_HEADER;

typedef struct TXM_VESPER_DATA_STRUCT {
	//Header (size 0x54)
	TXM_VESPER_HEADER header;
	
	//Entries
	TXM_VESPER_DATA_ENTRY entries[header.filecount];
	
	//File List
	zstring filenames; //NULL terminated filename list
} TXM_VESPER_DATA_STRUCT;

```


Sample files (COMALL.txv contains various texture types, I also snipped the part that's 16BPP) :

[Download here](http://www.mediafire.com/download.php?wt5mmhkggym)
## Post #14
- Username: bwin
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-02-05T12:44:29+00:00
- Post Title: Need help on Tales of Vesperia[X360] files

if you create an xpr out of the images you can use unbundler.exe from the xbox sdk to deswizzle them.
## Post #15
- Username: bwin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jan 01, 2010 9:31 am
- Post datetime: 2010-02-06T01:30:10+00:00
- Post Title: Need help on Tales of Vesperia[X360] files

It worked like a charm! Thanks!
[Yuri.png](https://xentaxbackup.github.io/file/2768_Yuri.png)
## Post #16
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-02-07T14:11:27+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

Regarding XPR containers, would someone mind posting the exact structure of an XPR header needed for a texture to work with UnBundler ? I went through the SDK docs, but couldn't find the relevant info. I have some 360 DXTn textures that are "swizzled", but I'm not familiar with the XPR format.
## Post #17
- Username: Insomniac
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-02-07T15:36:28+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

just create a xpr with one file using the bundler.exe in the sdk so you know the header.
## Post #18
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-02-07T22:15:37+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

UnBundler.exe gives me a .rdf file that is in XML. How do I extract the actual files?
## Post #19
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-02-08T14:22:01+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

> Reply from chrrox
>
> just create a xpr with one file using the bundler.exe in the sdk so you know the header.
Thanks, chrrox. That was a clever suggestion, and it worked out nicely.  



> Reply from Caboose
>
> UnBundler.exe gives me a .rdf file that is in XML. How do I extract the actual files?
UnBundler usually creates the actual files alongside the RDF file. If you're only getting an empty RDF file, then perhaps the XPR file is a in a different/unusual format?
## Post #20
- Username: GlassZeppelin
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Feb 07, 2010 9:20 am
- Post datetime: 2010-02-09T04:26:53+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

> Reply from bwin
>
> TXM structure (C-like code)
Code: Select alltypedef struct TXM_VESPER_DATA_ENTRY {
	uint32 width;
	uint32 height;
	uint32 unknown2;
	uint32 imageformat; // ?? Not sure of that one. 0x18280186 = 32bit A8R8G8B8, 0x1A200154 = ??; 0x1828014F = 16bit A4R4G4B4
	uint32 nameoffset; // from here
	uint8 paddingentry[0x44];
} TXM_VESPER_DATA_ENTRY;

typedef struct TXM_VESPER_HEADER {
	uint32 signature; //0x20000
	uint32 filesize;
	uint32 unknown1; // 0x4 ?
	uint32 filecount;
	uint8 padding1[0x44];
} TXM_VESPER_HEADER;

typedef struct TXM_VESPER_DATA_STRUCT {
	//Header (size 0x54)
	TXM_VESPER_HEADER header;
	
	//Entries
	TXM_VESPER_DATA_ENTRY entries[header.filecount];
	
	//File List
	zstring filenames; //NULL terminated filename list
} TXM_VESPER_DATA_STRUCT;
I've noticed that some of the .txm files, for example all of the ITEM_*.txm files, do not seem to follow this format. I can't seem to get any information out of them...

EDIT: Although I do think I have discovered that the 0x1A200154 value for the imageformat corresponds to D3DFMT_DXT4.
## Post #21
- Username: bwin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jan 01, 2010 9:31 am
- Post datetime: 2010-02-11T15:59:55+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

@GlassZeppelin

I've made an updated, improved version of that structure descriptor, I'll post it when I get home. I'll also post the FPS4 structure used in some files that didn't work with fatduck's quickBMS script.

Also I've found here that the 0x1A200154 value meant D3DFMT_DXT5 and not D3DFMT_DXT4. And 0x1A200152 means D3DFMT_DXT1. There's, however, one value I couldn't interpret: 0x1A20017B, which you can find in common.svo/texture.dat.

... But I've yet to find the mystic arte cut-ins. If anyone got some kind of clue, don't hesitate.
## Post #22
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-09-13T07:59:22+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

I can't understand how did you do to extract those image files!  
I have the files from the complete game (not the demo), and I'm trying with the exact files you're talking about (COMALL.TXM & TXV). I also have the SDK (76451), and I've been trying to use the programs you mentioned, but I continue to receive errors. If I use COMALL.TXV with Bundler, to create the xpr file, it tells me it can't read it. If I try to deswizzle it with 360deswizzler (I'm using the right program? Is that by darvolt?), it gives me a DDS whose content is messed up and unusable (but the program asks me to give an image dimension... how can I know that? I always put a random value). I even tried with xbdecompress, but same thing as Bundler and Unbundler. I'd be interested in extracting the menu images (like the objects, the cursor, and things like those), but I'm totally noob, in all this. I'm racking my brain to understand how did you do, but I can't. Can someone explain me in detail what the heck have I to do, please? I've been trying for days and I'm starting to get irritated for not being successful.
## Post #23
- Username: bwin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jan 01, 2010 9:31 am
- Post datetime: 2010-09-13T15:46:42+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

Hey,

It has been a long time since I've done this, yay for topic reply notifications (I've got all item and recipe pictures though, I can mediafire them if you want) so I don't remember that well, but one important thing is to have the correct version of xbdecompress (6654).

I remember having spent quite a lot of time on this, and by trial and error I got some results.

For COMALL.txv/txm, you'll have to extract each image file one by one, create an xpr header for each of these based on the TXM file and then deswizzle/decompress them with unbundler IIRC (I remember coding something including a quickBMS script to automate the process but my HDD crashed since then and I don't have anything anymore).

360deswizzler only works well with RGBA8 files, and you also have to guess the dimensions based on the size of what you want to deswizzle.

Good luck.

I've also done some work on Graces and Ratatosk if you're interested.
[faces1.png](https://xentaxbackup.github.io/file/3439_faces1.png)
## Post #24
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-09-14T11:41:36+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

If you could mediafire me the objects and recipe pictures you'd do me a real favour...!!! ^_^

I think I have the 7645 version of xbdecompress... It's strange that it doesn't work... Shouldn't it be a superior version of the 6654? That's why I can't extract nothing from txv files?

For Ratatosk, I've already extracted the models and textures of the characters (it's very easy, after all), but I was searching for a way to extract the skit mugshots (I opened a topic in Graphic File Formats some weeks ago: [viewtopic.php?f=18&t=4890](http://forum.xentax.com/viewtopic.php?f=18&t=4890)) and the visual effects textures.

Thank you very much for the answer, bwin!
## Post #25
- Username: bwin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jan 01, 2010 9:31 am
- Post datetime: 2010-09-14T14:03:23+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

The contents of this post was deleted because of possible forum rules violation.
[CHR.zip](https://xentaxbackup.github.io/file/3444_CHR.zip)
## Post #26
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-09-14T21:31:58+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

I see... So basically it's all very unpredictable. I'll try when I have more time, then >< And I'll also try to find the version of xbdecompress you're saying.

Me too noticed that Graces and Vesperia have very similar formats (I was trying to decompress the content in the .se3 files in both the games, that should contain sound effects)... It's strange to see X360 formats being used on Wii... I wonder what they'll use, on the PS3 version.

Don't know why I can't download the Vesperia zip .__.'' Ratatosk works (there are many things I already ripped via Dolphin), but if I click on the link of Vesperia the dl doesn't start, or if it does it creates a 0-byte file. Can you re-upload it elsewhere? And don't worry, if I manage to do what I'm trying to I'll credit you for sure!!! **
## Post #27
- Username: bwin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jan 01, 2010 9:31 am
- Post datetime: 2010-09-14T21:46:49+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

The contents of this post was deleted because of possible forum rules violation.
## Post #28
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-09-15T06:28:50+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

Thanks a lot, bwin! Now it works, I owe you a favour!!
## Post #29
- Username: quantico
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Sep 19, 2010 6:19 pm
- Post datetime: 2010-09-23T18:44:50+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

Did anyone ever try to decompress the scenario.dat (which seems to contain all the text of the game?)
## Post #30
- Username: bwin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jan 01, 2010 9:31 am
- Post datetime: 2010-09-23T18:46:42+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

Text actually is in string.svo --> stringxx.so IIRC.
## Post #31
- Username: quantico
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Sep 19, 2010 6:19 pm
- Post datetime: 2010-09-23T18:55:13+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

The contents of this post was deleted because of possible forum rules violation.
## Post #32
- Username: ils
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Sep 25, 2010 12:36 pm
- Post datetime: 2010-10-10T16:26:13+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

The contents of this post was deleted because of possible forum rules violation.
## Post #33
- Username: harter82
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 17, 2010 11:24 pm
- Post datetime: 2010-10-17T15:29:52+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

The contents of this post was deleted because of possible forum rules violation.
## Post #34
- Username: moxmox
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 01, 2010 11:58 pm
- Post datetime: 2010-11-02T21:17:40+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

The contents of this post was deleted because of possible forum rules violation.
## Post #35
- Username: moxmox
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 01, 2010 11:58 pm
- Post datetime: 2010-11-03T15:22:09+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

> Reply from bwin
>
> Text actually is in string.svo --> stringxx.so IIRC.

Any experience what can be done with this .so file? It seems binary or compilation of many files. 

The Xbox360 undub version of Vesperia (japanese audio with english texts) have string_dic.so partly 100% exactly the same as PS3 version (for example artes part), but this part is in the different section of the file. Xbox360 english version is quite different also in artes part.
## Post #36
- Username: Lunarshine
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 08, 2010 8:24 pm
- Post datetime: 2010-11-08T15:10:15+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

thanks a ton for upping the vesperia graphics, I really needed those, as Im working on a tales trading card game. its still in developement, but if youre curious heres the first draft. (I know Richter isnt from vesperia but you get the idea)

[http://serafiend.deviantart.com/#/d31g5xs](http://serafiend.deviantart.com/#/d31g5xs)
## Post #37
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2010-11-26T13:42:55+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

He, I'm wondering if anyone has had any luck with the .SE3 files?
## Post #38
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-11-26T14:52:32+00:00
- Post Title: Re: Need help on Tales of Vesperia[X360] files

Serious necropost here, so for that I appologize.

But I've managed to unpack the svo files, and then using a BMS script managed to extract the .dat files they pump out, finally resulting in .unpacked files, not sure where to go from here, half the topic has been removed due to people sharing content.

I'm only after the world map and town textures, running this script:

```
string NAME += ".unpacked"
comtype PUYO_LZ01
get TYPE byte
get ZSIZE long
get SIZE long
savepos OFFSET
clog NAME OFFSET ZSIZE SIZE

```


I get an error about the sizes not matching.

Is this specific to noncharacter or UI textures (since it seems thats what everyone else wanted to extract).

I can upload one of the .unpacked if anyone likes.
