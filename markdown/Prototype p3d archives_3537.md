## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-15T19:39:48+00:00
- Post Title: Prototype p3d archives

The original topic is this one about the audio format: [viewtopic.php?f=17&t=3530](http://forum.xentax.com/viewtopic.php?f=17&t=3530)

Since these files seem to be containers themselves I opened a new topic here.
They may contain vox audio data, movie subtitles, ..., even shader data.
[files.rar](https://xentaxbackup.github.io/file/2124_files.rar)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-18T14:12:11+00:00
- Post Title: Prototype p3d archives

Everything is contained in these files, also textures and some kind of configuration files it seems.
[http://ul.to/cybcyr](http://ul.to/cybcyr)

Strangefully I don't find any 3D models.

Edit: These seem to be the ones.
[http://ul.to/h7mgxk](http://ul.to/h7mgxk)

Edit2: Can't figure out any structure, sometimes it matches sometimes not.
Seems like the files are saved without a directory. I already found a filesize that matched the first block, but there were no such information for the following ones
## Post #3
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-06-19T07:33:07+00:00
- Post Title: Prototype p3d archives

I've seen mentions of that Scarface used the same format, and existing tools for Scarface work.
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-19T08:31:32+00:00
- Post Title: Prototype p3d archives

Yeah but I'm not talking about the main rcf archives.
I'm not sure though if there are working tools for those p3d archives.
## Post #5
- Username: Predatory Lootboxes
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-19T11:04:53+00:00
- Post Title: Prototype p3d archives

Oh but there is a pattern there. 

```

// HEADER

byte(4)		'P3D' + 0xFF
unint32		version?
unint32		archive size

// Resource entries

byte		pointer number A of original resource? Like in structs?
byte 		pointer number B of resource
byte 		Type ID 1
byte 		Type ID 2
unint32 	start of next section (in distance from the start of the 

first byte per resource entry!)
unint32		number of bytes still linked to this resource after this

// NOTE: if the last two variables are equal then the next resource will 

start. 


```


It seems to me that these are not really file archives, but more like storage containers of specific resource variables and data. 

Mexscript: 

```
Get D Byte 0 ;
Get version Long 0 ;
Get ArSize Long 0 ;
Set FC Long 0 ;
Do ;
SavePos S 0 ;
Set FN String "PA" ;
Get FolNum1 Byte 0 ;
String FN += FolNum1 ;
String FN += "_PB" ;
Get FolNum2 Byte 0 ;
String FN += FolNum2 ;
String FN += "_ta" ;
Get T1 Byte 0 ;
Get T2 Byte 0 ;
String FN += T1 ;
String FN += "_tb" ;
String FN += T2 ;
String FN += "_" ;
String FN += FC ;
String FN += ".bin" ;
Math FC += 1 ;
Get RS Long 0 ;
Get RSL Long 0 ;
Math S += RS ;
Math RS -= 12 ;
SavePos FO 0 ;
Log FN FO RS 0 0 ;
GoTo S 0 ;
While S < ArSize ;

```


BMS file to add to MultiEx Commander's MRF file (BMS-->>Add BMS to MRF)


 p3d.zip
(390 Bytes) Downloaded 256 times



It looks like different constructor information (structs etc) is stored in specific order in case of some p3d files.
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-19T12:27:00+00:00
- Post Title: Prototype p3d archives

Thanks for your info.
I'm not sure what exactly they are, at least every kind of data is stored in these files, 3D models, textures, scripts etc.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-19T14:27:50+00:00
- Post Title: Prototype p3d archives

Yes, such as these DDS files (in bin format only preceded by a unint32 filesize variable).

You can learn something from the order they are in the manhattan cells.p3d, as the small files are actually information files about the DDS pictures. 



PA2_PB144_ta1_tb0_18.jpg (335.92 KiB) Viewed 2350 times





PA2_PB144_ta1_tb0_10.jpg (248.16 KiB) Viewed 2342 times





PA2_PB144_ta1_tb0_2.jpg (376.53 KiB) Viewed 2335 times
## Post #8
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2009-06-19T16:08:32+00:00
- Post Title: Prototype p3d archives

Can I just say that, what you have done is really cool mr. mouse? Cause it is.
## Post #9
- Username: Drossel
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-19T19:04:01+00:00
- Post Title: Prototype p3d archives

Thanks, but there is more. 

Here's a snippet from the table of contents you can get from MultiEx Commander using the .BMS file I posted. 

```
-----------------------------------
D:\Downloads\files\manhattan_Cell_10.p3d
Number of resources: 1277
TOC Created on: 19-6-2009 at 20:30:38
-----------------------------------
Naam	Type	Grootte	Positie
PA0_PB144_ta1_tb0_0.bin	bin	61	24
PA6_PB144_ta1_tb0_1.bin	bin	53	97
PA2_PB144_ta1_tb0_2.bin	bin	174908	162
PA3_PB144_ta1_tb0_3.bin	bin	61	175082
PA0_PB144_ta1_tb0_4.bin	bin	61	175155
PA6_PB144_ta1_tb0_5.bin	bin	53	175228
PA2_PB144_ta1_tb0_6.bin	bin	349684	175293
PA3_PB144_ta1_tb0_7.bin	bin	61	524989
PA0_PB144_ta1_tb0_8.bin	bin	61	525062
PA6_PB144_ta1_tb0_9.bin	bin	53	525135
PA2_PB144_ta1_tb0_10.bin	bin	174908	525200
PA3_PB144_ta1_tb0_11.bin	bin	57	700120

```


Now, the script creates the filenames for the resources using the (unknown) pointer values I mentioned before in the DRAFT format description. So the PA<value> and the PB<value> are the two pointers A and B in the DRAFT format. By looking at these files now and examing these values, along with the resources they represent I'm positive that PA is in fact the resource subID given the context of PB (main resource type). IN the example above, there are 4 different types from the PB144 "collection". The PB144 is probably the "Texture Information" ID. The PA subtypes 0, 6 and 3 all tell some info on the texture, while PA2 represents the actual DDS file (preceded by a file size variable). 

The first type (PA0):



PA0_PB144_ta1_tb0_0.jpg (46.36 KiB) Viewed 2274 times


This tells something about the name of the texture, it's width (512) and heigth (512) and some more info.

The second (PA6)



PA6_PB144_ta1_tb0_1.jpg (38.8 KiB) Viewed 2277 times


Again some of the same info, along with other stuff, such as the DDS type variable "DXT1". 

The third (PA2) is the DDS file,not completely shown



PA2_PB144_ta1_tb0_2.jpg (43.69 KiB) Viewed 2268 times



And the last one (PA3):



PA3_PB144_ta1_tb0_3.jpg (42.59 KiB) Viewed 2256 times


This is simple the whole original file path of the DDS file that was used. 

So these are saved in that order, thus each Texture field (PB144) entails 4 subtypes that tell the game all there is to know about the texture. 

The following resources are also found in that file, that in contents look a lot like MD5 hashed values:

```
PA10_PB0_ta0_tb9_183.bin	bin	33	7603454
PA32_PB16_ta1_tb0_184.bin	bin	4	7603499
PA22_PB16_ta1_tb0_185.bin	bin	34	7603515
PA33_PB16_ta1_tb0_186.bin	bin	1	7603561
PA22_PB16_ta1_tb0_187.bin	bin	30	7603574
PA33_PB16_ta1_tb0_188.bin	bin	1	7603616
PA23_PB16_ta1_tb0_189.bin	bin	17	7603629
PA21_PB16_ta1_tb0_190.bin	bin	62	760365

```


This 'set' starts of with a PA21 subtype belonging to the PB16 Information Type, then a PA10 subtype from the PB0 type, followed by more subtypes from the PB16 Information Type (PA32, 22, 33, 22, 33, 23, 21). The sequence then repeats itself it seems. 
The PA33 are simply one byte in size (0x00) while the PA22 name the two dds used for the same texture, a "diffuse" one and a "normal" one. These DDSs you can find in the PB144 Texture Information. 

So I really think some specific user structures/types were saved in here, easy to load up back again by the game.
## Post #10
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2009-06-19T21:14:23+00:00
- Post Title: Prototype p3d archives

I'm not entirely sure I am understanding most of this but I got to the point of loading it up. Getting to the bins. To which all of the sound p3d's have been PA0_PB0_ta0_ectect.bin
I can't extract any of the files if any, inside the bins with Multiex or Dragon Unpacker. With Dragon I can see some info like possible sound efx but unable to do anything with it.

Is there some way you could help me with achieving a method to get to the sound files?
[dragonp3d.jpg](https://xentaxbackup.github.io/file/2144_dragonp3d.jpg)
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-19T21:23:02+00:00
- Post Title: Prototype p3d archives

I'm not sure what you did. Did you extract files from a specific p3d file? And then tried to open the bin files you extracted?

How did you extract them, using MultiEx Commander? 

Can you upload the .p3d file you extracted the files from, or some of the extracted .bin files somewhere?
## Post #12
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2009-06-19T21:43:38+00:00
- Post Title: Prototype p3d archives

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-20T10:53:35+00:00
- Post Title: Prototype p3d archives

These files are sound files, the same as from Rheini's  samples. I haven't looked at the format yet.
## Post #14
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-06-21T21:05:07+00:00
- Post Title: Prototype p3d archives

I need an rcf extractor for the 360? scarface doesnt work.
## Post #15
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2009-06-22T02:37:44+00:00
- Post Title: Prototype p3d archives

Perhaps EkszBox-ABX will work for you OrangeC, only thing I know of.

[http://sourceforge.net/projects/ekszbox-abx/](http://sourceforge.net/projects/ekszbox-abx/)
## Post #16
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-06-22T02:41:55+00:00
- Post Title: Re: Prototype p3d archives

> Reply from Mr.Mouse
>
> Code: Select allbyte		pointer number A of original resource? Like in structs?
byte 		pointer number B of resource
byte 		Type ID 1
byte 		Type ID 2This is wrong. It's a uint32 value, which I call "type id". Structure of data after the node header varies depending on the type id. 00019006 = TextureDDS, 00019001 = TexturePNG, 00019002 = TextureData, etc.

I'm currently working on an editor for Prototype's Pure3D (that's what p3d means) files.
## Post #17
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-06-22T12:04:13+00:00
- Post Title: Re: Prototype p3d archives

> Reply from geevious
>
> Perhaps EkszBox-ABX will work for you OrangeC, only thing I know of.

http://sourceforge.net/projects/ekszbox-abx/

I cannot get it to start up.
## Post #18
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2009-06-22T14:05:48+00:00
- Post Title: Re: Prototype p3d archives

Yeah, after checking it out myself. I was missing a bunch of files to run that version. I went to a old one. 2.0 and got it to run but on every .rcf file, it didnt find anything. Don't know of any others personally. Though like I said the scarface explorer from the thread [viewtopic.php?t=2143](http://forum.xentax.com/viewtopic.php?t=2143) worked for me.
## Post #19
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-22T15:40:19+00:00
- Post Title: Re: Prototype p3d archives

> Reply from Rick
>
> This is wrong. It's a uint32 value, which I call "type id". Structure of data after the node header varies depending on the type id. 00019006 = ImageDDS, 00019001 = ImagePNG, 00019002 = ImageData, etc.

I'm currently working on an editor for Prototype's Pure3D (that's what p3d means) files.

Well, excuse me. I was figuring out the format with a simple hex editor, after all. At such a point, one creates draft working formats and update as necessary. 

If you have more information, why not share it? You talk like you have more knowledge.
## Post #20
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-06-22T17:31:31+00:00
- Post Title: Re: Prototype p3d archives

> Reply from Mr.Mouse
>
> Well, excuse me. I was figuring out the format with a simple hex editor, after all. At such a point, one creates draft working formats and update as necessary. 

If you have more information, why not share it? You talk like you have more knowledge.I'm not trying to be offensive or demeaning, I was simply informing you that your assumption for that value was wrong, I apologize if I came off that way. I don't have an effective spec per se, but I have a bunch of code up at [http://svn.gib.me/public/prototype/trunk/](http://svn.gib.me/public/prototype/trunk/) or more specifically, [http://svn.gib.me/public/prototype/trun ... e3DFile.cs](http://svn.gib.me/public/prototype/trunk/Gibbed.Prototype.FileFormats/Pure3DFile.cs) and [http://svn.gib.me/public/prototype/trun ... ts/Pure3D/](http://svn.gib.me/public/prototype/trunk/Gibbed.Prototype.FileFormats/Pure3D/)
## Post #21
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-06-22T18:27:47+00:00
- Post Title: Re: Prototype p3d archives

> Reply from geevious
>
> Yeah, after checking it out myself. I was missing a bunch of files to run that version. I went to a old one. 2.0 and got it to run but on every .rcf file, it didnt find anything. Don't know of any others personally. Though like I said the scarface explorer from the thread viewtopic.php?t=2143 worked for me.

Yeah it didnt find anything for me either

However here is the 360 rcf file.

[http://www.megaupload.com/?d=GI7FJXD7](http://www.megaupload.com/?d=GI7FJXD7)
## Post #22
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-06-22T20:42:44+00:00
- Post Title: Re: Prototype p3d archives

> Reply from OrangeC
>
> geevious wrote:Yeah, after checking it out myself. I was missing a bunch of files to run that version. I went to a old one. 2.0 and got it to run but on every .rcf file, it didnt find anything. Don't know of any others personally. Though like I said the scarface explorer from the thread viewtopic.php?t=2143 worked for me.

Yeah it didnt find anything for me either

However here is the 360 rcf file.

http://www.megaupload.com/?d=GI7FJXD7Looks like the 360 rcf files are in big endian mode.

Edit: correction, only the header appears to be big endian.
Edit 2: double correction, if the 'big-endian' bool in the header (byte 0x22 in the file) is set to true, then the header and entry index table is in big-endian mode, but the entry name table is still in little-endian (probably because it's unused by the game itself).
## Post #23
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-06-22T23:31:57+00:00
- Post Title: Re: Prototype p3d archives

So is there anyway to unpack these?
## Post #24
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-06-29T08:28:58+00:00
- Post Title: Re: Prototype p3d archives

Hi a program called TEXmod works for extracting and adding texures to the game
## Post #25
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-06-29T20:48:12+00:00
- Post Title: Re: Prototype p3d archives

> Reply from DRAVEN
>
> Hi a program called TEXmod works for extracting and adding texures to the gameNot permanent and requires external tool to actively modify running game instance, hacky way to do it .
## Post #26
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2009-07-18T16:46:24+00:00
- Post Title: Re: Prototype p3d archives

How can I edit this file? This is subtitle file...
[NIS_0_1_FMV.rar](https://xentaxbackup.github.io/file/2205_NIS_0_1_FMV.rar)
## Post #27
- Username: Drossel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 16, 2009 5:56 pm
- Post datetime: 2009-07-19T00:22:24+00:00
- Post Title: Re: Prototype p3d archives

Perhaps this link is helpful?
[http://blog.gib.me/2009/06/21/prototype/](http://blog.gib.me/2009/06/21/prototype/)
## Post #28
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2009-07-20T06:24:06+00:00
- Post Title: Re: Prototype p3d archives

This is not working...   

> Reply from Drossel
>
> Perhaps this link is helpful?
http://blog.gib.me/2009/06/21/prototype/
## Post #29
- Username: Drossel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 16, 2009 5:56 pm
- Post datetime: 2009-07-29T22:38:34+00:00
- Post Title: Re: Prototype p3d archives

> Reply from oyunceviri
>
> This is not working...   
Drossel wrote:Perhaps this link is helpful?
http://blog.gib.me/2009/06/21/prototype/
Really? My boyfriend managed to get the CG and WOI out of it, they just have no voices. Only music. We're trying to get the voice files from all of the game but that's where we're stuck on. He doesn't understand that site's instructions. You can post on there, sometimes they answer you. Doesn't hurt to try.
## Post #30
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-07-29T23:25:23+00:00
- Post Title: Re: Prototype p3d archives

Was the music managed to be decoded?
## Post #31
- Username: Drossel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 16, 2009 5:56 pm
- Post datetime: 2009-07-30T22:34:51+00:00
- Post Title: Re: Prototype p3d archives

> Reply from OrangeC
>
> Was the music managed to be decoded?
Probably but you can easily get the music from the internet.
## Post #32
- Username: lanthas
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 15, 2009 7:43 pm
- Post datetime: 2009-10-16T22:53:15+00:00
- Post Title: Re: Prototype p3d archives

Hi,

I wrote a .p3d structure viewer: it shows the hierarchical structure contained in a p3d file and also lists names for most types of sections, but doesn't actually parse most of the sections' content. It does parse the scripting sections in detail (contained in files named *_fig.p3d: mission scripts and others) - as a coder, this is what interested me most. However, you can rightclick on any kind of section to save it as a separate file: this makes it very easy to extract e.g. textures (extract 19002 subsection and delete first 4 bytes).

In its current state it probably won't be of much use to most people, especially as it can't edit p3d files yet, only view them. But someone else might want to use it as a base for a more advanced tool. Personally I don't think I'll be developing it further much, if at all - I really just wanted to look at the mission scripts a bit .

[Screenshot](http://files.uploadffs.com/5/c64b554e/p3d.png)
[Download (sources and binary)](http://www.mediafire.com/file/onjmuj5jtyt/p3dview011.zip) - VS2008 C# project

If there is interest I can also document what I found out about the format (i.e. what is implemented in this tool) on the wiki.
## Post #33
- Username: WrappedInBlack
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Apr 27, 2012 5:51 am
- Post datetime: 2012-04-29T13:41:37+00:00
- Post Title: Re: Prototype p3d archives

Sooo.... if any of you guys still use this site can you post up a converter for p3d files? It says the other post was removed and I need a converter for Prototype 2.
