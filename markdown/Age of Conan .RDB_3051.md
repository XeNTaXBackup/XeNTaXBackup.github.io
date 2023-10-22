## Post #1
- Username: aritheory
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 26, 2007 11:49 am
- Post datetime: 2008-06-03T08:28:01+00:00
- Post Title: Age of Conan *.RDB

Hello people

I need to ask you for some help figuring out the Resource Database archives for Age of Conan. They're huge (all ~1GB) *.RDB files. From what I can tell by scanning through them with a hex-editor, they're based on a key-file system where the engine uses a file called "le.idx" . I'm sure they use some sort of compression too.

Any help would be appreciated from  anybody who has AOC out there. I can try to get some more info on the headers if you need it.

Thanks

EDIT: Here are some caps of the beginnings of the possible key-file (le.idx) and the first .rdb file. As you can see, there are XML files at the beginning. I'm yet to determine how the files are laid out, hopefully this will help.

le.idx
[](http://img340.imageshack.us/my.php?image=rdb1eb8.jpg)

00.rdb
[](http://img340.imageshack.us/my.php?image=rdb2qj8.jpg)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-06-03T12:23:43+00:00
- Post Title: Age of Conan *.RDB

That idx looks a bit strange. But hard to say something only having a picture.
## Post #3
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2008-06-03T17:32:39+00:00
- Post Title: Age of Conan *.RDB

[http://www.aocdev.com/wiki/index.php?title=RDBDATA](http://www.aocdev.com/wiki/index.php?title=RDBDATA)
## Post #4
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-06-07T09:20:45+00:00
- Post Title: Age of Conan *.RDB

> Reply from nicoli_s
>
> http://www.aocdev.com/wiki/index.php?title=RDBDATAThat's very incomplete. After noticing how shitty existing tools for the RDB files were, I wrote my own -- here's the archive format that I worked out:

For le.idx:

magic : 4 bytes : RDBI
version : 4 bytes : int [current version is 4]

for version 4:

hash : 16 bytes
record count : 4 bytes : int [no more than 0x1000000 records allowed]

for each record up to record count:
- type : 4 bytes : uint
- id : 4 bytes : uint

for each record up to record count:
- flags+rdb index : 4 bytes : uint [flags = value & 0xFFFFFF00, rdb index = value & 0xFF]
- offset : 4 bytes : uint
- size : 4 bytes : uint
- hash1 : 4 bytes : uint
- hash2 : 4 bytes : uint

There is one record of type 1000010, which has a limited amount of filename <-> id lookup, it is not complete by any means though.

Anyway, to get a specific record just open the associated resource file (rdb index) and seek to that offset, most record types have a 12 byte header of varying data, generally starts with their type ID again, then two values indicating contents of that type. After that it is file data.
[rdbviewer.png](https://xentaxbackup.github.io/file/1534_rdbviewer.png)
## Post #5
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2008-06-07T20:27:01+00:00
- Post Title: Age of Conan *.RDB

have you done any work into the FCTX files? i know they are DXT data, but when you put an appropriate dds header on them, they appear slightly off, kind of tiled, i figured there was maybe a problem with the mip maps that i didnt understand
also, for me the only file in 1000010 appears to be compressed and has no plain text filenames in it
## Post #6
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-06-07T21:38:22+00:00
- Post Title: Age of Conan *.RDB

> Reply from nicoli_s
>
> have you done any work into the FCTX files?Yes, they are just DXT data without a proper header, the only exception I've come across is for the type of 'MIXD' (DXIMage) which appears to have some form of compression going on.

magic : 4 bytes : FCTX <- should be considered a part of the 'data header' like seen on other file data
unk1 : 4 bytes [always 2?] <- should be considered a part of the 'data header' like seen on other file data
unk2 : 4 bytes [always 1?] <- should be considered a part of the 'data header' like seen on other file data
width : 2 bytes : ushort
height : 2 bytes : ushort
flags : 4 bytes : uint
type : 4 bytes : char[4] [DXT1, DXT5, MIXD, etc...]
data : variable

> Reply from nicoli_s
>
> also, for me the only file in 1000010 appears to be compressed and has no plain text filenames in itIt is not.

Format is simple,

type : 4 bytes : uint
unknown : 4 bytes : uint [always 1?]
unknown : 4 bytes : uint [always 2?]
type count : 4 bytes : uint
for each type count:
- type id : 4 bytes : uint
- name count : 4 bytes : uint
- for each name count:
-- entry id : 4 bytes : uint
-- name length : 4 bytes : int
-- name : variable [name length] : char*
## Post #7
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2008-06-08T05:43:54+00:00
- Post Title: Age of Conan *.RDB

hey Rick,
good work on figuring out the fileformats! 

Do you think it would be possible to extract and reinject textures into the rdb's somehow?

I know that the patcher checks the bigfiles on startup but maybe it only checks the filesize / timestamps and no hash?

I know that theres some hash checking going on at some point (RDBHashIndex.bin ?!) but maybe thats only used for patching... atleast i hope so cause i'd love to mod some textures
## Post #8
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2008-06-08T15:55:11+00:00
- Post Title: Age of Conan *.RDB

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-06-10T01:07:04+00:00
- Post Title: Age of Conan *.RDB

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-06-10T01:07:49+00:00
- Post Title: Age of Conan *.RDB

> Reply from Itze
>
> hey Rick,
good work on figuring out the fileformats! 

Do you think it would be possible to extract and reinject textures into the rdb's somehow?

I know that the patcher checks the bigfiles on startup but maybe it only checks the filesize / timestamps and no hash?

I know that theres some hash checking going on at some point (RDBHashIndex.bin ?!) but maybe thats only used for patching... atleast i hope so cause i'd love to mod some texturesI don't know, what I would look for instead is a way to override content inside RDB via files outside on the normal filesystem.
## Post #11
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2008-06-10T04:54:43+00:00
- Post Title: Age of Conan *.RDB

yeah... done that kinda heh...

i wrote a proxy.exe for texmod so now you can actually use command lines and therefore start age of conan! 


how about blue hair?
 

a different cape?



here's the  downloadlink for the proxy: [http://www7.zippyshare.com/v/5071703/file.html](http://www7.zippyshare.com/v/5071703/file.html)

check the Readme.txt

Sourcecode is included (VB2008) (don't know any other program language) 
oh and you need the most recent .NET framework installed
## Post #12
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2008-06-10T14:52:15+00:00
- Post Title: Age of Conan *.RDB

thanks for posting your filename list rick, i still have yet to figure out the compression, but ill be spending some more time on it over the next week, and itze, which texture files are you overwriting? is it the tiled dds textures? or the png ones
## Post #13
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2008-06-10T15:55:03+00:00
- Post Title: Age of Conan *.RDB

none... im patching the texture in memory directly with texmod 
but i rip them as .dds cause thats what the unreal engines native format is
## Post #14
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-06-10T23:37:36+00:00
- Post Title: Age of Conan *.RDB

> Reply from Itze
>
> none... im patching the texture in memory directly with texmod 
but i rip them as .dds cause thats what the unreal engines native format isWhat does unreal have to do with Age of Conan?
## Post #15
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2008-06-11T09:28:49+00:00
- Post Title: Age of Conan *.RDB

I think Conan is based off the Unreal Engine 2...though there is a tiny chance it uses UNREAL ENGINE 3...but this isn't used as often as 2 as its more expensive n only seems to be used for higher end games...im sure the play station version of conan was Unreal engine 3 though. So im guessing the PC version is a port or related in someway and then yeah i suppose it might use the same engine...easier to program that way
## Post #16
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2008-06-11T09:41:18+00:00
- Post Title: Re: Age of Conan *.RDB

sorry i was wrong.

> The DreamWorld graphics engine was developed by Funcom circa 2000. Other computer games powered by DreamWorld technology include Anarchy Online and its various expansion packs. When Funcom began developing Age of Conan: Hyborian Adventures, the company reviewed its existing technology base and decided to focus on the further evolution of their proprietary DreamWorld engine as opposed to licensing a third-party engine like many online RPG companies do. As such, Funcom began to retool their engine with the overall design, pipeline and implementation process was taken into account. In light of these changes, the DreamWorld engine has been rebuilt for Age of Conan: Hyborian Adventures with new features, special effects and optimizations.
Its the dreamworks engine that was build and used for Conan, also DDS isnt a format made for UNREAL but unreal does use it but it generally prefers DXT (direct X textures).
## Post #17
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2008-06-27T07:58:52+00:00
- Post Title: Re: Age of Conan *.RDB

Hi guys

Great work! Any news on this? A working tool for AoC would be very useful and much appreciated. As you already pointed out, the other exiting tool (I know only of one) is a bit limited at the moment.

Thanks in advance

/N
## Post #18
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2008-07-07T15:43:24+00:00
- Post Title: Re: Age of Conan *.RDB

*bump*

Any news on the rdb format and perhaps Ricks' tool?

Thanks in advance

Cheers

N
