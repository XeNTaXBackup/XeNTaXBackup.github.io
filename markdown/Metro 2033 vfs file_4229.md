## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-03-16T12:15:54+00:00
- Post Title: Metro 2033 vfs file

Hello i have tried other vfs tools but to no avail.

i have provided a cut out of the 1gig file.

[http://www.megaupload.com/?d=TA5YJCMI](http://www.megaupload.com/?d=TA5YJCMI)
## Post #2
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2010-03-18T06:54:47+00:00
- Post Title: Metro 2033 vfs file

> Reply from OrangeC
>
> but to no avail.

"quick&dirty" BMS-script for unpack any .fvs0, .vfs1 files (need content.vfi in archive folder, tested with QuickBMS 0.3.14c):

```
# (only unpacker, not decrypter. hhrhhr@gmail.com 03-2010)
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get source FILENAME
open FDSE "content.vfi" 1
get max_size asize 1
get ffff long 1
get chunk_size long 1
savepos data_pos 1
math offset = data_pos
math offset += chunk_size
set exit_while byte 0
do
	goto offset 1
	get num long 1
	get chunk_size long 1
	savepos data_pos 1
	math offset = data_pos
	math offset += chunk_size
	get num0 long 1
	get strlen_filesize long 1
	get file_name string 1
	get file_size long 1
	if file_name == source
		log MEMORY_FILE data_pos chunk_size 1
		get mem_max_size asize MEMORY_FILE
		math mem_max_size -= 12
		get mem_num0 long MEMORY_FILE
		get mem_strlen_filesize long MEMORY_FILE
		get mem_file_name string MEMORY_FILE
		get mem_file_size long MEMORY_FILE
		get mem_num1 long MEMORY_FILE
		get mem_size long MEMORY_FILE
		do
			get current_xor byte MEMORY_FILE
			get mem_tmp threebyte MEMORY_FILE #????
			get mem_file_offset long MEMORY_FILE
			get mem_file_size_unp long MEMORY_FILE
			get mem_file_size_pak long MEMORY_FILE
			get mem_full_path_size long MEMORY_FILE
			filexor current_xor MEMORY_FILE
			getdstring mem_full_path mem_full_path_size MEMORY_FILE
			string mem_full_path -= 1
			filexor 0 MEMORY_FILE
			log mem_full_path mem_file_offset mem_file_size_pak
			savepos mem_data_pos MEMORY_FILE
		while mem_data_pos < mem_max_size
		set exit_while byte 1
	endif
	if offset >= max_size
		set exit_while byte 1
	endif
while exit_while != 1

```
## Post #3
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-03-18T15:47:46+00:00
- Post Title: Metro 2033 vfs file

i think headerles dds are inside
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-03-18T15:50:27+00:00
- Post Title: Metro 2033 vfs file

> Reply from hhrhhr
>
> OrangeC wrote:but to no avail.

"quick&dirty" BMS-script for unpack any .fvs0, .vfs1 files (need content.vfi in archive folder, tested with QuickBMS 0.3.14c):
Code: Select all# Metro 2033 (03-2010 hhrhhr@gmail.com v1.0 only unpacker, not decrypter)
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get source FILENAME
open FDSE "content.vfi" 1
get max_size asize 1
get ffff long 1
get chunk_size long 1
savepos data_pos 1
math offset = data_pos
math offset += chunk_size
set exit_while byte 0
do
	goto offset 1
	get num long 1
	get chunk_size long 1
	savepos data_pos 1
	math offset = data_pos
	math offset += chunk_size
	get num0 long 1
	get strlen_filesize long 1
	get file_name string 1
	get file_size long 1
	if file_name == source
		log MEMORY_FILE data_pos chunk_size 1
		get mem_max_size asize MEMORY_FILE
		math mem_max_size -= 12
		get mem_num0 long MEMORY_FILE
		get mem_strlen_filesize long MEMORY_FILE
		get mem_file_name string MEMORY_FILE
		get mem_file_size long MEMORY_FILE
		get mem_num1 long MEMORY_FILE
		get mem_size long MEMORY_FILE
		do
			get current_xor byte MEMORY_FILE
			get mem_tmp threebyte MEMORY_FILE #????
			get mem_file_offset long MEMORY_FILE
			get mem_file_size_unp long MEMORY_FILE
			get mem_file_size_pak long MEMORY_FILE
			get mem_full_path_size long MEMORY_FILE
			filexor current_xor MEMORY_FILE
			getdstring mem_full_path mem_full_path_size MEMORY_FILE
			string mem_full_path -= 1
			filexor 0 MEMORY_FILE
			log mem_full_path mem_file_offset mem_file_size_pak
			savepos mem_data_pos MEMORY_FILE
		while mem_data_pos < mem_max_size
		set exit_while byte 1
	endif
	if offset >= max_size
		set exit_while byte 1
	endif
while exit_while != 1

Doesn't work, says 0 files copied.
## Post #5
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2010-03-18T16:45:09+00:00
- Post Title: Metro 2033 vfs file

do you have content.vfi in game folder? do you have unlocked game? if no - no unpack.
if yes - try this (key -l disable real unpack, only screen output):

```
quickbms.exe -l metro2033.bms path_to_game\videos.vfs0 .
```

sample output:

```
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open input file e:\Games\Metro2033\videos.vfs0
- open script metro2033.bms

  offset   filesize   filename
------------------------------
- enter in folder G:\tmp
- open input file e:\Games\Metro2033\content.vfi
  00000008 260462370  content\outro_bad.ogv
  0f86572a 210030614  content\outro_good.ogv

- 2 files found in 0 seconds
```
## Post #6
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2010-03-19T05:55:40+00:00
- Post Title: Metro 2033 vfs file

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2010-03-19T16:38:08+00:00
- Post Title: Metro 2033 vfs file

.upk unpacker:

```
# (only unpacker, not decrypter. hhrhhr@gmail.com 03-2010)
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

# data section
get num0 long
get data_size long
savepos pos
math pos += data_size
goto pos

# filelist section
get num1 long
get list_size long
savepos pos
do
	get current_xor byte
	get tmp threebyte #???
	get offset long
	get size_unp long
	get size_pak long
	get strlen_filename long
	filexor current_xor
	getdstring name strlen_filename
	filexor 0
	string name -= 1
#	print "%offset% %size_unp% %size_pak% %name%"
	log name offset size_pak
	savepos list_pos
	math list_pos -= pos
while list_pos < list_size 0

# dummy section (02 00 00 00 04 00 00 00 00 00 00 00)
get num2 long
get size long
savepos pos
math pos += size
goto pos

# guid section
get num3 long
get guid_size long
savepos pos
get upk_name FILENAME
string upk_name += ".guid"
log upk_name pos guid_size

```


p.s.
i need bbcode tag [spoiler][/spoiler] ;)
## Post #8
- Username: filipmosner
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 30, 2008 2:17 am
- Post datetime: 2010-03-20T15:37:28+00:00
- Post Title: Metro 2033 vfs file

Nice, but how to pack unpacked file?
## Post #9
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2010-03-20T22:54:33+00:00
- Post Title: Metro 2033 vfs file

sorry to anoy anyone in this thread, but is there anything i can just drop one of the metro files into and it will extract everything for me.

the models are tops and will finish of my fallout3mod nicely.
## Post #10
- Username: deadok
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 22, 2010 10:24 pm
- Post datetime: 2010-03-23T21:10:55+00:00
- Post Title: Metro 2033 vfs file

vfs extractor/packer (vfi actually, since vfs contains only data, not fs information)
only full-processing mode (no "extract/pack just this file")
[redist.rar](https://xentaxbackup.github.io/file/2880_redist.rar)
## Post #11
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-03-23T23:01:25+00:00
- Post Title: Metro 2033 vfs file

Thanks for the vfs tools, but i only can unpack one file (videos.vfs0) 
I do:

> ext vcontent.vfi
And the tool extracts the two files nothing else, what about the other vfs0s'?
## Post #12
- Username: deadok
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 22, 2010 10:24 pm
- Post datetime: 2010-03-24T01:24:33+00:00
- Post Title: Metro 2033 vfs file

ahem, looks like something went terribly wrong...

yeah, right, somehow i decided that it would be kewl to check if first DWORD in vfs-record = 0, and if not - abort extraction.
well, first dword is actually number of vfs...
coding after 2400 - bad, coffee doesn't halp.

fixed, reuploaded
## Post #13
- Username: dufake
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 10, 2010 11:23 pm
- Post datetime: 2010-04-11T03:42:38+00:00
- Post Title: Metro 2033 vfs file

I'm new here, but there are tools for unpacking Metro 2033.
Enjoy.

[http://metro2033forums.com/index.php?topic=739.0](http://metro2033forums.com/index.php?topic=739.0)
## Post #14
- Username: xjohnx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Mar 04, 2010 8:06 pm
- Post datetime: 2010-04-11T14:26:00+00:00
- Post Title: Metro 2033 vfs file

Used the tool but only managed to extract the sound files, getting an error on the other files (though i could be doing something wrong .
## Post #15
- Username: danidomen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 19, 2010 6:51 am
- Post datetime: 2010-04-19T07:52:22+00:00
- Post Title: Metro 2033 vfs file

Ok, I extracted correctly the file called textures.vfs0, but the file extension of the images are xxx.512 or xxx.1024 that I suppose is the texture resolution. But... How I can open this texture file?
## Post #16
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2010-07-09T07:54:57+00:00
- Post Title: Re: Metro 2033 vfs file

> Reply from danidomen
>
> Ok, I extracted correctly the file called textures.vfs0, but the file extension of the images are xxx.512 or xxx.1024 that I suppose is the texture resolution. But... How I can open this texture file?
Running into the same situation.  I opened up one of these files and found random strings / body of the file.

```
¢œÀ¶m[ß„~z€èÿµ
```

The file seem like they are headerless to me but i'm not a coder or programmer and I don't usually spend a whole lot of time around it.  Hoping to scour the net to see if there are any utilities out there that can recognize half of these files the game uses.  BTW, anyone know what GAME ENGINE this game is using?
## Post #17
- Username: Wercingetorix
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 31, 2010 4:50 pm
- Post datetime: 2010-08-18T05:56:03+00:00
- Post Title: Re: Metro 2033 vfs file

> Reply from Mirrodin
>
> BTW, anyone know what GAME ENGINE this game is using?

Its brand new 4A Engine, developed specially for Metro.
## Post #18
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-08-29T00:35:30+00:00
- Post Title: Re: Metro 2033 vfs file

I attach the tool magicdds in converts DDS to .512, .1024, .2048...and viceversa
How to use:
Convert dds to metro2033 format

> magicdds -c fileddstoconvert.dds
and
Convert Metro2033 format to DDS

> magicdds -r fileddstoconvert.512
The rar includes the source code in C
All this info is from here:
[http://metro.gameru.net/index.php?optio ... info&id=27](http://metro.gameru.net/index.php?option=com_remository&Itemid=23&func=fileinfo&id=27)
Have a nice modding  
[magicdds.rar](https://xentaxbackup.github.io/file/3383_magicdds.rar)
## Post #19
- Username: Tr1dae
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 21, 2010 2:32 am
- Post datetime: 2010-10-20T18:55:49+00:00
- Post Title: Re: Metro 2033 vfs file

Thanx for that. Finally got some usable textures from Metro. 

Can Magicdds batch convert? Doing it one by one is too slow
## Post #20
- Username: Psientist
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 17, 2011 9:27 pm
- Post datetime: 2011-03-04T15:10:18+00:00
- Post Title: Re: Metro 2033 vfs file

I used the provided QuickBMS script but I've tried converting the textures files both with magicdds and some tool a polish guy wrote to convert, but with both programs I get lots of corrupted textures (mainly the bumpmaps), is it the QuickBMS script that is the cause?
And if so, what are the alternate methods of extracting the textures? Redist crashes so I guess it's not compatible with Win7 x64?

Link to the .512 etc. to .dds converter.
[http://www.metro2033forums.com/metro-20 ... -file-765/](http://www.metro2033forums.com/metro-2033-modding-27/how-open-texture-file-765/)

Says alpha channels are the problem.

Anyone know how to salvage the bumpmaps?
## Post #21
- Username: guihighet
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Mar 12, 2011 9:00 pm
- Post datetime: 2011-03-15T13:34:03+00:00
- Post Title: Re: Metro 2033 vfs file

Anyone know what is the file containing the subtitles of the game?

Thanks
## Post #22
- Username: opti2000
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 11, 2012 8:23 am
- Post datetime: 2013-05-26T01:59:50+00:00
- Post Title: Re: Metro 2033 vfs file

Hello boys and girls!

I am so sorry to dig out this dead thread but are there any other tools to convert the .512, .1024 and .2048 texture files to dds or a useful format?

I am asking because Magicdds is not working unfortunately i dont know why. Maybe i am using it wrong. How are you guys doing it?
## Post #23
- Username: sarzamin
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Nov 19, 2010 10:19 pm
- Post datetime: 2014-06-30T14:58:53+00:00
- Post Title: Re: Metro 2033 vfs file

> Reply from deadok
>
> vfs extractor/packer (vfi actually, since vfs contains only data, not fs information)
only full-processing mode (no "extract/pack just this file")

Extractor works fine, but packer stoped working!!
## Post #24
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2014-08-29T02:12:31+00:00
- Post Title: Re: Metro 2033 vfs file

For Metro 2033 Redux tools\script?
[](http://radikal.ru/fp/29781b98b6fe4b42ba020c1970a6e52a)
[](http://radikal.ru/fp/03ff9c99c8944dfb85f38db881fe328d)[](http://radikal.ru/fp/9c8a3b48c8ae4e3da673fa522daf615d)[](http://radikal.ru/fp/9c6e4c5ab5334a63941693dca6c1351c)
