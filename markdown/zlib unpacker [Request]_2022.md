## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-08-04T10:03:30+00:00
- Post Title: zlib unpacker [Request]

Somebody knows where found or can make a zlib unpacker like 7zip.exe or similar in console mode?

I found one (created by a japanese ppl) but canÂ´t unpack correct a data compressed with zlib 1.2.x
## Post #2
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-08-04T11:55:19+00:00
- Post Title: zlib unpacker [Request]

ummm

[http://www.zlib.net/](http://www.zlib.net/)

can give you a dll that you can incorporate into a program.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-04T12:09:45+00:00
- Post Title: zlib unpacker [Request]

I guess he rather would like a command-line driven tool like :

```
zlib c:\allmyzlibbedfiles\*.zlb c:\mytargetfolder 
```


Which, consequently, shouldn't be too difficult to create.
## Post #4
- Username: GARID
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2006-12-19T23:40:56+00:00
- Post Title: zlib unpacker [Request]

I attached my command line zlib tool.
Usage:
zlibc -k input  output [level]
for compression
or
zlibc -d input output
for decompression

level from 0 (don't compress) to 9 (highest compression)

Edit:
Get new version below.
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-14T20:24:53+00:00
- Post Title: zlib unpacker [Request]

Thanks!!!
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-03-18T23:42:50+00:00
- Post Title: zlib unpacker [Request]

Rheini: is it okay if make use of this commandline tool in jaeder naub?
(i would make a specific GUI within my ripper that makes you select a file
to be decompressed). that would be awesome ) *i love it*
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-03-19T11:08:46+00:00
- Post Title: zlib unpacker [Request]

Yeah of course.
I attach the exe compiled with static linking of the CRT. This eliminates the necessity of the CRT dlls.
[zlibc.rar](https://xentaxbackup.github.io/file/1094_zlibc.rar)
## Post #8
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-03-20T11:04:26+00:00
- Post Title: zlib unpacker [Request]

The current tests ive made with jaeder/zlibc is great!!!

my bruteforce Zlib technique works like a charm currently.

however, i have little little request  i need a version of this program
that doesnt make any screen output at all, infact, not even opening up a screen.

the reason is that under the bruteforce stage the access to the program
is very intense, and everytime it opens up a window everything else will
lose focus. ....so, its impossible to do anything else while the
scanner is accessing zlibc.exe all the time ;D

The bruteforcer works this way: jaederstorm.exe is the first one
to scan the file for signatures, it will then report back to the mainframe
with everything it has found. the mainframe will filter it out and
send chunks to zlibc.exe for decoding, which then the mainframe
will pack together in one big chunk.raw file, that can later be scanned
normally by jaedernaub for filesignatures.

currently just tested on one file from CSI-Miami, but it worked =X
[zlibc.gif](https://xentaxbackup.github.io/file/1097_zlibc.gif)
## Post #9
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-03-20T11:34:33+00:00
- Post Title: zlib unpacker [Request]

If you use a bruteforce approach, it probably would be the best idea to implement zlib directly in your program.
Then you could also use in-memory decompression.
I used some ideas from [here](http://www.dogma.net/markn/articles/zlibtool/zlibtool.htm) for my program.
## Post #10
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-03-20T11:40:06+00:00
- Post Title: zlib unpacker [Request]

the funny thing here is that this approach was actually faster
than it may seem. as your program allready decompresses zlib
chunks in a lightspeed way , so this isnt really a bottleneck 

but i may consider it, if i have time ;D
## Post #11
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-03-20T14:44:05+00:00
- Post Title: zlib unpacker [Request]

I think the honor goes to the zlib authors
## Post #12
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-03-20T15:59:16+00:00
- Post Title: zlib unpacker [Request]

tons of games are using zlib..so i may only wait for your bruteforce to discover hidden things,looks great ripper as usual in jaeder 

greets!
## Post #13
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-20T18:49:14+00:00
- Post Title: zlib unpacker [Request]

Mainly games that are intended to be moddable at the least moderately use ZLIB correct? I know games such as Age of Empires use ZLIB. Same with AOE2 and etc. I'm rather fond of ZLIB.
## Post #14
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-09-03T22:08:07+00:00
- Post Title: zlib unpacker [Request]

Sorry to bump this old post!
But Rheini, could you add a parameter of an offset value switch to your zlibc.exe so when decompress a file, it go to the offset first and then start the decompression.

Or could you send me a source code of your zlibc so I can modifity it myself!?

I need this function/switch badly!
Thanks
## Post #15
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-04T13:51:18+00:00
- Post Title: zlib unpacker [Request]

Good idea. I'm on it.
## Post #16
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-09-04T14:26:45+00:00
- Post Title: Re: zlib unpacker [Request]

Thanks, by the way, could this offset value support hex input as well(eg: 0x10C). Because most of the time when we looking at the hex data, we use hex offset!

Thanks once again!
## Post #17
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-04T18:02:52+00:00
- Post Title: Re: zlib unpacker [Request]

The idea isn't bad, but I won't implement that (maybe later) since every good hex editor provides both hex and decimal offsets, furthermore this version of the tool is meant to be also used in automatic processing.

Might take some time til it's finished since I'm completely rewriting the tool in another programming language ([D](http://www.digitalmars.com/d/))

I still have some file scanner code lying around here, another possible feature would be an automatic extraction of all zlibbed files contained in an archive. But this is just a thought atm
## Post #18
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2008-09-20T21:15:13+00:00
- Post Title: Re: zlib unpacker [Request]

Here is a command line unpacker for ZLIB compressed data files.

Syntax:
```
INFLATE <compr_file> [decompr_file | [0x]offset [decompr_file]]
```


compr_file:	Container file which consists of jointed ZLIB data streams. Must be given on the command line.
decompr_file:	Name of the decompressed file. Optional.
offset:		Offset within compr_file where the ZLIB stream starts. Optional.

Example:

```
INFLATE data.dat
```
		Extracts the first ZLIB stream at offset 0 from DATA.DAT and names it DATA.DXX.

```
INFLATE data.dat 17
```
		Extracts the ZLIB stream from offset 0x11 (11hex, 17dez) from DATA.DAT and names it DATA.DXX.

```
INFLATE data.dat extr.zlb
```
	Extracts the first ZLIB stream at offset 0 from DATA.DAT and names it EXTR.ZLB.

```
INFLATE data.dat 0x111 extr.zlb
```
	Extracts the ZLIB stream from offset 0x111 (273dec) from DATA.DAT and names it EXTR.ZLB

Error codes:	0 - OK
		1 - wrong parameters
		2 - error opening input file
		3 - error opening output file
		4 - error ZLIB-initialization
		5 - error during decompression
		6 - error writing destination file
		7 - given offset not in file range

(updated Sep 29, 2008)
[inflate.zip](https://xentaxbackup.github.io/file/1663_inflate.zip)
## Post #19
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-09-28T17:55:04+00:00
- Post Title: Re: zlib unpacker [Request]

Hi asmxtx, I found a little problem with your tool here! 
If I set the offset to 0x08, your tool won't deflate the file. But when I cut out the first 8 bytes and deflate with your tool, it works, it works!(even thought it said data error)

And I yes, I can use other tools (like zlibc, offzip) to deflate it without error!
[error_file.zip](https://xentaxbackup.github.io/file/1660_error_file.zip)
## Post #20
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2008-09-29T03:56:58+00:00
- Post Title: Re: zlib unpacker [Request]

The problem should be solved now.
I didn't subtract the offset from the input size. This let ZLIB read random data beyond the input buffer if the compressed source was a not terminated stream like in your file. (Download link updated.)
## Post #21
- Username: deve
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 22, 2009 4:56 pm
- Post datetime: 2009-05-16T17:21:54+00:00
- Post Title: Re: zlib unpacker [Request]


## Post #22
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-16T18:21:36+00:00
- Post Title: Re: zlib unpacker [Request]

zlibc is not meant to be an archiver.
It is designed to de-/compress raw zlib streams.
## Post #23
- Username: i404401
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 03, 2012 8:14 am
- Post datetime: 2012-05-03T00:25:30+00:00
- Post Title: Re: zlib unpacker [Request]

@ Rheini : Thank you for your tool, it saved up my time.
Thanks to others who share their ideas here too.
