## Post #1
- Username: ashkanhsj
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Mar 17, 2010 5:42 am
- Post datetime: 2010-03-16T23:27:19+00:00
- Post Title: Doom 3 (Xbox) .GOB file

Hey guys, when I've played Xbox version of Doom 3 and D3: Resurrection of Evil, I noticed that they had some differences. but all I have to do is open the .GOB files then extract models and textures from Xbox version then convert them to PC version. so I need some tools for Xbox version to open the .GOB files and extract the contents. I want to view them in Doom 3 Editor. I need your help.

Sample files:

[http://www.2shared.com/file/12195511/93 ... _gfc_.html](http://www.2shared.com/file/12195511/938a1118/assets_english__GOB__gfc_.html)


Thanks in advance




Xbox version.jpg (177.15 KiB) Viewed 660 times
## Post #2
- Username: ashkanhsj
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Mar 17, 2010 5:42 am
- Post datetime: 2010-04-02T23:38:09+00:00
- Post Title: Doom 3 (Xbox) .GOB file

Can someone please make an extractor tool for these files?
## Post #3
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2010-04-08T03:59:55+00:00
- Post Title: Doom 3 (Xbox) .GOB file

This is the same format that Vicarious Visions used for the Xbox port of Jedi Academy and Jedi Outcast.  There are no editors out there yet, but some initial data was gathered on the formats by Watto back in December of 2005.  It'd be nice if this format was cracked.  Doom, Jedi Outcast and Jedi Academy are all very moddable on the PC and Xbox ports of these mods would really bring a lot of life back to these games.
## Post #4
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2010-04-08T23:59:37+00:00
- Post Title: Doom 3 (Xbox) .GOB file

Working on it.
## Post #5
- Username: ashkanhsj
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Mar 17, 2010 5:42 am
- Post datetime: 2010-04-10T18:41:43+00:00
- Post Title: Doom 3 (Xbox) .GOB file

> Reply from grimdoomer
>
> Working on it.

Thanks in advance. (＾∇＾)
## Post #6
- Username: Teancum
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-04-11T02:28:58+00:00
- Post Title: Doom 3 (Xbox) .GOB file

I haven't ever looked at this GOB format...but just to note, lots else was changed in the xbox ports of Jedi Knight 2/Jedi Academy, I think the biggest change was that map formats were changed a bit (JK2/JA's bsp structures wasted huge amounts of memory to support lightstyles and I believe VV corrected/changed this, probably among numerous other format changes). And of course, all game code was compiled native, so only pure-asset-driven mods could be considered for porting, and many of those assets may need a bit of reprocessing to work on Xbox. The JA port was much closer to the PC port than JK2 was (as you probably noticed, JK2MP on the consoles was totally hacked in to run in "singleplayer" mode).

I suppose if I had to guess too, I'd say the likelihood that VV kept the proc/md5mesh/md5anim text-based on their Doom 3 port is pretty low.  But it's possible.

But it would be awesome to see "Melee Mod" running on Xbox Jedi Academy.  Let me know if you run into any walls here grimdoomer, and I will look into ripping a GOB from one of my old Xbox discs to help out.
## Post #7
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2010-04-12T01:16:10+00:00
- Post Title: Doom 3 (Xbox) .GOB file

> Reply from MrAdults
>
> I suppose if I had to guess too, I'd say the likelihood that VV kept the proc/md5mesh/md5anim text-based on their Doom 3 port is pretty low.  But it's possible.
Well they did keep it  I've been working on an app and I can dump all the files and decompress them. But there are some complications. I've found the code that loads the gfc file in the xbe, but it's been a while since I worked with x86 assembly. I've been doing ppc for the last few months so reversing has been slow. The files are pretty wierd. Only a hand full have names, some are just random crap, and others have 15+ extensions that make 0 sense. I'll try to get an app that can atleast replace files, but porting modifications... I don't know how possible it will be.
## Post #8
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-04-12T22:14:59+00:00
- Post Title: Doom 3 (Xbox) .GOB file

> Reply from grimdoomer
>
> Well they did keep it
Cool. 

> Reply from grimdoomer
>
> I've been working on an app and I can dump all the files and decompress them. But there are some complications. I've found the code that loads the gfc file in the xbe, but it's been a while since I worked with x86 assembly. I've been doing ppc for the last few months so reversing has been slow. The files are pretty wierd. Only a hand full have names, some are just random crap, and others have 15+ extensions that make 0 sense. I'll try to get an app that can atleast replace files, but porting modifications... I don't know how possible it will be.
Well, x86 is my most fluent assembly language (at least, behind ARM...and 65x...and...ok, maybe not the most), so feel free to call for help. 

So are the file names in the GOB itself, or in the xbe? If they're in the GOB, does the xbe completely ignore the info and use its own internal file table? That would be sad, although modifying it in the xbe for modifications would be completely reasonable. I would be curious as well if the JA/JK2 GOB format is even identical the Doom 3 one, and if so, whether it also really uses the file info in the GOB or not (this is again assuming you found it in the GOB and not the xbe).
## Post #9
- Username: vadim
- Rank: advanced
- Number of posts: 41
- Joined date: Fri Apr 09, 2010 11:15 pm
- Post datetime: 2010-04-29T18:57:58+00:00
- Post Title: Doom 3 (Xbox) .GOB file

.GOB & global.d3tfull unpacker
[RazbSbor.rar](https://xentaxbackup.github.io/file/2994_RazbSbor.rar)
## Post #10
- Username: ashkanhsj
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Mar 17, 2010 5:42 am
- Post datetime: 2010-05-06T08:00:42+00:00
- Post Title: Doom 3 (Xbox) .GOB file

> Reply from vadim
>
> .GOB & global.d3tfull unpacker

Thanks, Did it work?
## Post #11
- Username: vadim
- Rank: advanced
- Number of posts: 41
- Joined date: Fri Apr 09, 2010 11:15 pm
- Post datetime: 2010-05-08T13:14:41+00:00
- Post Title: Doom 3 (Xbox) .GOB file

> Reply from ashkanhsj
>
> vadim wrote:.GOB & global.d3tfull unpacker

Thanks, Did it work?

Yes works can unpack.GOB archives and extract\rebuild .dds files from global.d3tfull
## Post #12
- Username: ashkanhsj
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Mar 17, 2010 5:42 am
- Post datetime: 2010-05-12T08:40:37+00:00
- Post Title: Doom 3 (Xbox) .GOB file

> Reply from vadim
>
> ashkanhsj wrote:vadim wrote:.GOB & global.d3tfull unpacker

Thanks, Did it work?

Yes works can unpack.GOB archives and extract\rebuild .dds files from global.d3tfull

Hey, good job my friend. It works great. I'm very grateful. it's so useful for moders. thanks in advance.  (^_^)
## Post #13
- Username: ashkanhsj
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Mar 17, 2010 5:42 am
- Post datetime: 2010-05-19T16:53:50+00:00
- Post Title: Doom 3 (Xbox) .GOB file

How can I make some custom maps on the Xbox version of Doom 3 just like Halo 1 & 2 on the Xbox
## Post #14
- Username: doomero
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 21, 2010 4:02 am
- Post datetime: 2010-08-20T22:18:14+00:00
- Post Title: Doom 3 (Xbox) .GOB file

hi i am new, i tested that gob. unpacker  and it doesnt work and appear a error, the reazon was those gob files are not like the star wars dark forces gob file....maybe id software make some changes in the gob format...
## Post #15
- Username: ashkanhsj
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Mar 17, 2010 5:42 am
- Post datetime: 2010-08-23T20:38:54+00:00
- Post Title: Doom 3 (Xbox) .GOB file

> Reply from doomero
>
> hi i am new, i tested that gob. unpacker  and it doesnt work and appear a error, the reazon was those gob files are not like the star wars dark forces gob file....maybe id software make some changes in the gob format...

I tasted it already and its worked great!
## Post #16
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2011-07-24T15:47:07+00:00
- Post Title: Re: Doom 3 (Xbox) .GOB file

Sorry for the necropost, but I feel like this is related. -- Is there any chance of a Jedi Academy-compatible version of this app? It crashes for me with JA gob files.
## Post #17
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2013-04-04T02:40:04+00:00
- Post Title: Re: Doom 3 (Xbox) .GOB file

Necroposting yet again, but the specs for the .GFC/.GOB files have been inadvertently released. With the closing of LucasArts Raven Software released the source code to Jedi Outcast and Jedi Academy. Vicarious Visions' code for these container files, along with all Xbox-specific code, was there.

Jedi Outcast code: [http://sourceforge.net/projects/jedioutcast/](http://sourceforge.net/projects/jedioutcast/)
Jedi Academy code: [http://sourceforge.net/projects/jediacademy/?source=dlp](http://sourceforge.net/projects/jediacademy/?source=dlp)

The code can be found in \[gamename]\code\goblib. Hopefully this helps with import/extraction tools. Heck, that same C++ code probably could be directly integrated to some degree if someone were feeling froggy enough to make a dedicated tool.
## Post #18
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2013-04-07T14:48:46+00:00
- Post Title: Re: Doom 3 (Xbox) .GOB file

Here are the two files from the Jedi Academy source code that handle the .GOB/.GFC container system. It's C++ code. [http://www.mediafire.com/?slrtgroox1xv8km](http://www.mediafire.com/?slrtgroox1xv8km)

Some notes from the header file:
goblib.h

```
 * GOB File System
 *
 * Purpose: Provide fast, efficient disk access on a variety of platforms.
 * Implementation:
 *		The GOB system maintains two files -- GOB and GFC.  The GOB file is actually
 *		an archive of many files split into variable size, compressed blocks.  The GFC,
 *		GOB File Control, contains 3 tables -- a block table, basic file table, and
 *		extended file table.  The block table is analogous to a DOS FAT.  The basic
 *		file table contains a minimal set of file information to handle basic reading
 *		tasks.  The extended file table is optionally loaded and contains additional
 *		file information.  File names are case insensitive.
 *		  
 *		Files can be read in a normal manner.  Open, read, seek and close
 *		operations are all provided.  Files can only be written in a single
 *		contiguous chunk of blocks at the end of an archive.  Reads are processed
 *		through a configurable number of read ahead buffers to in an effort to
 *		minimize both reads and seeks.  Other operations including delete, verify, 
 *		access, and get size are also supported on files inside an archive.
 *
 *		The system supports read profiling.  By supplying a file read callback 
 *		function, the library will output the block number of each read.  This can 
 *		be used rearrange block in the archive to minimize seek times.  The 
 *		GOBRearrange sorts files in an archive.
 *
 *		Supports block based caching.  Primarily aimed at caching files off a DVD/CD
 *		to a faster hard disk.

#define GOB_MAGIC_IDENTIFIER		0x8008
#define GOB_MAX_FILE_NAME_LEN		96
#define GOB_MAX_FILES				(16*1024)
#define GOB_MAX_BLOCKS				32767
#define GOB_BLOCK_SIZE				(64*1024)
#define GOB_BLOCK_ALIGNMENT			2048
#define GOB_MEM_ALIGNMENT			64
#define GOB_COMPRESS_OVERHEAD		1024
#define GOBMARKER_STARTBLOCK		('L' | 'B' << 8 | 'T' << 16 | 'S' << 24)
#define GOBMARKER_ENDBLOCK			('L' | 'B' << 8 | 'N' << 16 | 'E' << 24)

```
## Post #19
- Username: Phobos90
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 22, 2018 2:57 pm
- Post datetime: 2019-07-04T03:10:07+00:00
- Post Title: Re: Doom 3 (Xbox) .GOB file

> Reply from vadim ↑Fri Apr 30, 2010 2:57 am at Fri Apr 30, 2010 2:57 am
>
> 
.GOB & global.d3tfull unpacker

Sorry to bring back this old thread, but I wish to know what's the proper usage of this tool to open Doom 3 Xbox .gob and global.d3tfull files.


I just don't know what to do with this exe.
