## Post #1
- Username: DarkAngel
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jan 23, 2011 12:12 pm
- Post datetime: 2011-01-23T04:18:01+00:00
- Post Title: (PC) Dead Space 2 (.dat)

Please help me unpack the game files  Dead Spece 2. files do not suggest that because they are big.
## Post #2
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2011-01-23T11:27:20+00:00
- Post Title: (PC) Dead Space 2 (.dat)

here a split 150mb and in atachment 35 kb split
[http://www.multiupload.com/YEDH3GSJJ8](http://www.multiupload.com/YEDH3GSJJ8)
[Untitled1.rar](https://xentaxbackup.github.io/file/3834_Untitled1.rar)
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-01-23T15:06:38+00:00
- Post Title: (PC) Dead Space 2 (.dat)

Its actually the same as all visceral games on the 360 version just splitted and with different extensions.

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring BIGH
get VIV_SIZE long
endian big
get FILES long
get HEADER_SIZE long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get NAME_CRC long
    log NAME_CRC OFFSET SIZE
next i
```


Unfortunately it will extract without names making it very hard to identify anything, so it is very tedious and disappointing.
## Post #4
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2011-01-23T17:23:36+00:00
- Post Title: (PC) Dead Space 2 (.dat)

okay well in one file i found things like this

```
3slo........COHS....RDHS+7.z....|..9...O...O...O^.|.....brute_merged.sbk.shared\audio\docref_banks\0xb6159c6\brte_base_audio_ref\brute_merged.sbk.SBK...COHSh...kapRX......?..sbnk....X...............
```
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-01-23T17:27:15+00:00
- Post Title: (PC) Dead Space 2 (.dat)

Yes i find those but i think those are imbedded devs assets rather then a file folder structure.
## Post #6
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2011-01-23T19:09:33+00:00
- Post Title: (PC) Dead Space 2 (.dat)

> Reply from OrangeC
>
> Its actually the same as all visceral games on the 360 version just splitted and with different extensions.
Code: Select all# Dante's Inferno
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring BIGH
get VIV_SIZE long
endian big
get FILES long
get HEADER_SIZE long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get NAME_CRC long
    log NAME_CRC OFFSET SIZE
next i

Unfortunately it will extract without names making it very hard to identify anything, so it is very tedious and disappointing.

This doesn't work for the Xbox 360 version.
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-01-23T20:50:17+00:00
- Post Title: (PC) Dead Space 2 (.dat)

Strange, worked for me
## Post #8
- Username: DarkAngel
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jan 23, 2011 12:12 pm
- Post datetime: 2011-01-24T19:36:07+00:00
- Post Title: (PC) Dead Space 2 (.dat)

anyone ever get unpacked so that the structure of files and folders was normal
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-01-24T21:19:17+00:00
- Post Title: (PC) Dead Space 2 (.dat)

That would be neat.
## Post #10
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-01-30T13:27:53+00:00
- Post Title: (PC) Dead Space 2 (.dat)

is there any way to unpack that file?
edit:I also try dragon unpacker,winrar, 7-zip and it's not working

edit: 31/01/2011 1.45 p.m, yes i i have open it with the quickbms and using dantes inferno script, after i extact it (pc version) i m using hex editor i open the file's name "-736893235" the files size is 9,0b7 kb. the first line is 03 00 00 08 68 D0 01 00 20 00 00 00 00 00 00 00 when i turn it into binary using scientific calculator,  
03=0 00=0 00=0 08=0 68=1101000 D0=11010000 01=0 00=0 20=100000 00=0 00=0 00=0 00=0 00=0 00=0 00=0

is it correct?
## Post #11
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-01-31T20:11:03+00:00
- Post Title: (PC) Dead Space 2 (.dat)

I'm actually poking around with Dead Space 2 now (PC version), and have a nearly complete file list for DS2DAT6.DAT/DS2DAT7.DAT/DS2DAT8.DAT (missing one file name), complete list for DS2DAT9.DAT. Very incomplete lists for DS2DAT0.DAT/DS2DAT1.DAT (sound files).

Need to clean up my code a bit more before I push it to my repository.
[ds2.png](https://xentaxbackup.github.io/file/3858_ds2.png)
## Post #12
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-02-01T03:54:16+00:00
- Post Title: (PC) Dead Space 2 (.dat)

hi rick, I'm new to hex editing, is it correct the way i read it
the one of the screenshot, is it you made it?
## Post #13
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-01T05:30:04+00:00
- Post Title: (PC) Dead Space 2 (.dat)

> Reply from Rick
>
> I'm actually poking around with Dead Space 2 now (PC version), and have a nearly complete file list for DS2DAT6.DAT/DS2DAT7.DAT/DS2DAT8.DAT (missing one file name), complete list for DS2DAT9.DAT. Very incomplete lists for DS2DAT0.DAT/DS2DAT1.DAT (sound files).

Need to clean up my code a bit more before I push it to my repository.

WHOA! 

how did you figure out the Structure?
## Post #14
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-02-01T11:34:21+00:00
- Post Title: (PC) Dead Space 2 (.dat)

> Reply from Rick
>
> I'm actually poking around with Dead Space 2 now (PC version), and have a nearly complete file list for DS2DAT6.DAT/DS2DAT7.DAT/DS2DAT8.DAT (missing one file name), complete list for DS2DAT9.DAT. Very incomplete lists for DS2DAT0.DAT/DS2DAT1.DAT (sound files).

Need to clean up my code a bit more before I push it to my repository.

I hope this will work with Dante's Inferno files too. (Same engine, same deveoper team)
This will contain repack function too?
## Post #15
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-01T12:00:04+00:00
- Post Title: (PC) Dead Space 2 (.dat)

> Reply from evin
>
> I hope this will work with Dante's Inferno files too. (Same engine, same deveoper team)
This will contain repack function too?It probably uses the same hash function for files, you'd have to build a custom file list for that game. I do have the PS3 version so I'll look at that.

> Reply from OrangeC
>
> WHOA! 

how did you figure out the Structure?What, the BigFile structure? That's dead simple. If you mean file names, well, the game doesn't use hardcoded hash references (except in some places), so I just pulled all of the names from available locations.
## Post #16
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-02-01T12:06:52+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

so, have you release the tool yet?
## Post #17
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-02-01T12:29:10+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Rick
>
> evin wrote:I hope this will work with Dante's Inferno files too. (Same engine, same deveoper team)
This will contain repack function too?It probably uses the same hash function for files, you'd have to build a custom file list for that game. I do have the PS3 version so I'll look at that.

Great.  I'll try out on the X360 version.
## Post #18
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2011-02-01T17:39:30+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Nice work. I wait for release of the tool.
## Post #19
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-01T18:41:37+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Same here
## Post #20
- Username: pipirisnaki
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 02, 2011 6:17 am
- Post datetime: 2011-02-01T22:20:33+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Hi rick, how is going on with the tool? Just wanted to know if this will be usefull with ps3 game data, cuz there are only 3 big files
## Post #21
- Username: Skymmer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 25, 2010 8:50 am
- Post datetime: 2011-02-01T23:01:13+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Rick, judging the filenames of DAT files I presume you have the Multi6 edition. Right?
I'm curious if your tool will work for DAT files from Multi3 edition. Actually all of the DAT files from Multi3 edition are differ to Milti6, except a two (as far as I remember).
## Post #22
- Username: pipirisnaki
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 02, 2011 6:17 am
- Post datetime: 2011-02-01T23:15:47+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Ok, for example, i've used the previous script for quick bms for dead space 2 ps3 version. I've opened a random file and i've got that hex on the image. How exactly do i know from what offset to other offset the files from that folder are located?
[Sin título.gif](https://xentaxbackup.github.io/file/3860_Sin título.gif)
## Post #23
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-02-01T23:19:26+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Waiting and anxious...
## Post #24
- Username: pipirisnaki
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 02, 2011 6:17 am
- Post datetime: 2011-02-01T23:20:54+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

nevermind, i'm reading a tutorial xD
## Post #25
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-01T23:43:24+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

I have built up a fairly complete list of files for Dante's Inferno (PS3), excluding sound files.

> Reply from Skymmer
>
> Rick, judging the filenames of DAT files I presume you have the Multi6 edition. Right?
I'm curious if your tool will work for DAT files from Multi3 edition. Actually all of the DAT files from Multi3 edition are differ to Milti6, except a two (as far as I remember).Yes, I think so. My copy is from EA's download service.

It's trivial to get file lists for the 'data' data files (ie, not sounds). That's not really an issue.

If you want, cut the file table header from each dat and upload them somewhere (16+(file count * 12) bytes from start of file), and I can check.

> Reply from pipirisnaki
>
> Ok, for example, i've used the previous script for quick bms for dead space 2 ps3 version. I've opened a random file and i've got that hex on the image. How exactly do i know from what offset to other offset the files from that folder are located?I'm not sure what you're asking here.
[di.png](https://xentaxbackup.github.io/file/3861_di.png)
## Post #26
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-01T23:47:26+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

So there are no filenames for music/sounds at all?

shame, its what i really wanted to extract.
## Post #27
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-01T23:49:30+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from OrangeC
>
> So there are no filenames for music/sounds at all?

shame, its what i really wanted to extract.There are filenames, they are just not easy to get, currently my archive viewer can identify most of them by checking some header bytes in the file (looking for 03 00 00). They have an extension of '.exa.snu' (in Dead Space 2 at least).
## Post #28
- Username: pipirisnaki
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 02, 2011 6:17 am
- Post datetime: 2011-02-01T23:56:44+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Rick
>
> I have built up a fairly complete list of files for Dante's Inferno (PS3), excluding sound files.
Skymmer wrote:Rick, judging the filenames of DAT files I presume you have the Multi6 edition. Right?
I'm curious if your tool will work for DAT files from Multi3 edition. Actually all of the DAT files from Multi3 edition are differ to Milti6, except a two (as far as I remember).Yes, I think so. My copy is from EA's download service.

It's trivial to get file lists for the 'data' data files (ie, not sounds). That's not really an issue.

If you want, cut the file table header from each dat and upload them somewhere (16+(file count * 12) bytes from start of file), and I can check.
pipirisnaki wrote:Ok, for example, i've used the previous script for quick bms for dead space 2 ps3 version. I've opened a random file and i've got that hex on the image. How exactly do i know from what offset to other offset the files from that folder are located?I'm not sure what you're asking here.

I was asking how to do [viewtopic.php?f=29&t=3545](http://forum.xentax.com/viewtopic.php?f=29&t=3545) this tutorial, xD, but nvm, i'm reading the tutorial right now, so i can get at least a "sort of" file structure xD. omg, this thing its difficult for me
## Post #29
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-02-02T23:43:50+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

So Rick, when you will release this great tool?
## Post #30
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-02T23:48:40+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Not to be rude but let the man some time to work on it, it must be very complex and he might have a life also
## Post #31
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-03T03:20:41+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

You are welcome to check out my code in my repository:

[http://svn.gib.me/public/visceral/trunk/](http://svn.gib.me/public/visceral/trunk/)

I am not providing binaries at this time.
## Post #32
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-03T05:24:41+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Skymmer
>
> Rick, judging the filenames of DAT files I presume you have the Multi6 edition. Right?
I'm curious if your tool will work for DAT files from Multi3 edition. Actually all of the DAT files from Multi3 edition are differ to Milti6, except a two (as far as I remember).Looking at localetable.txt, it shows English, French, and Spanish for my version of the game. So mine would be Multi3.
## Post #33
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-02-03T11:24:53+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Ok, i'm ultra n00b in programming things, so I can't compile this source?
Cause I tried to complite it in VS2010 and it give me some errrors and files missing.

Help?
## Post #34
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-03T11:53:34+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

If no one compiles it bye this afternoon ill go for it when i get home.
## Post #35
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-03T20:22:09+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Rick
>
> You are welcome to check out my code in my repository:

http://svn.gib.me/public/visceral/trunk/

I am not providing binaries at this time.

Is this source fully working or WIP?
## Post #36
- Username: pipirisnaki
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 02, 2011 6:17 am
- Post datetime: 2011-02-03T20:25:57+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

I think it's kinda like a working beta
## Post #37
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-03T20:39:05+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

It's working fine, but I'm the developer. I'm actively developing it which is why I prefer not to distribute binaries.

If you are missing Gibbed.RefPack, etc, you need to checkout that URL using a SVN client, it will pull in externals like Gibbed.RefPack automatically.

Edit: you are welcome to drop by irc.synirc.net #gibbed to discuss Dead Space 2 stuff with me in realtime (when I'm not busy).
## Post #38
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-03T21:40:57+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

pipirisnaki has made obvious some issues with my repository and I've corrected them, it should compile correctly now.
## Post #39
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-03T22:56:08+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Can i compile this in Cygwin?
## Post #40
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-03T23:03:56+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

It's C# code, so I doubt it.
## Post #41
- Username: StaticTheFox
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 28, 2011 11:44 am
- Post datetime: 2011-02-04T00:46:55+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Weird, I get this error when unpacking an STR file:

> Unhandled Exception: System.FormatException: unsupported build type 58B1F4D8 at
>
> Gibbed.Visceral.UnpackSTR.Program.Main<String[] args> in <path>\Gibbed.Visceral.UnpackSTR\Program.cs:line 108
## Post #42
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-04T00:49:36+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

I import the project into vs C# 2010 but it doesn't support solution folders,so i build it anyway and the archive viewer won't open,if anyone successfully compiled, please explain how, thanks.
## Post #43
- Username: StaticTheFox
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 28, 2011 11:44 am
- Post datetime: 2011-02-04T00:52:49+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from OrangeC
>
> I import the project into vs C# 2010 but it doesn't support solution folders,so i build it anyway and the archive viewer won't open,if anyone successfully compiled, please explain how, thanks.

If you're using the Express version, then solution folders won't work.
## Post #44
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-04T00:58:38+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Ahh okay then i will get the pro version then .
## Post #45
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-04T01:06:41+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Build in debug mode so it outputs binaries to ..\bin\; the project data that it loads is in there.
## Post #46
- Username: StaticTheFox
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 28, 2011 11:44 am
- Post datetime: 2011-02-04T01:38:40+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Blegh, the image converter hates me.
## Post #47
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-04T02:33:00+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

I have not properly written ConvertTG4 yet, trying to use it is a bad idea.
## Post #48
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-04T02:37:50+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Well the archive viewer successfully worked for dead space 2.

Will test it with dante's inferno.
## Post #49
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-04T05:00:05+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

@pipirisnaki

Completely repacked PC data (with different organization too) with PackBig and game works fine. Don't know why repacks didn't work for you.
## Post #50
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-04T05:15:47+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Tested Dante ps3 and 360 , most of it is unknown names, I'm assuming the code needs to be worked on for all names to appear as is in the .filelist files?
## Post #51
- Username: Kane
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 28, 2010 5:50 pm
- Post datetime: 2011-02-04T12:10:12+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

I have the en/de version and in ds2data0.dat there are 105 unknown files.
In other dat files 1.
## Post #52
- Username: Skymmer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 25, 2010 8:50 am
- Post datetime: 2011-02-04T16:26:16+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Rick
>
> @pipirisnaki

Completely repacked PC data (with different organization too) with PackBig and game works fine. Don't know why repacks didn't work for you.

Strange. How it can be? There are some files with unknown names. Or they're somehow are unpacked and packed too?
## Post #53
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-04T17:27:45+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Kane
>
> I have the en/de version and in ds2data0.dat there are 105 unknown files.
In other dat files 1.Same version as me, and that's the most progress I've made in finding the file names so far; that's fine though, the 105 files are audio files (not really important to me), and the 1 unknown in the others are some config file for building the archives (also not really important).

> Reply from Skymmer
>
> Strange. How it can be? There are some files with unknown names. Or they're somehow are unpacked and packed too?PackBig will repack files under the __UNKNOWN directory using their name as the hash value (since they get saved with a hex version of the hash as their name).
## Post #54
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-02-04T18:55:06+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

There is an .str repacker in you plans? Or this "released" tool can already do this?
## Post #55
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-04T19:05:37+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

None yet, tools still in heavy development.
## Post #56
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2011-02-04T20:21:47+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Nice work Rick.     

You code a viewer.   

Can you (re)build it to unpack AND repack the *.dat - files from Dead Space 2, too?
## Post #57
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-04T21:10:39+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

ArchiveViewer = Unpack (need to write an UnpackBig too) big (viv, dat)
PackBig = Pack big (viv, dat)
## Post #58
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-04T21:33:43+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

If you have made any improvements of the code do we simply update our project in our svn clients and it will redownload it?
## Post #59
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-04T21:41:45+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from OrangeC
>
> If you have made any improvements of the code do we simply update our project in our svn clients and it will redownload it?Yes, though I may have caused some local conflicts with my recent commits (renaming a few projects), if so, just re-checkout the code and it should checkout fine.
## Post #60
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-05T00:57:21+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

how to repack the dat file
## Post #61
- Username: JBieber
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 03, 2010 1:01 am
- Post datetime: 2011-02-05T01:35:52+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Rick how to use your tool? 
I don't understand how to use ArchiveViewer and PackBig
How to unpack, pack .dat files? Please tell me
## Post #62
- Username: Skymmer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 25, 2010 8:50 am
- Post datetime: 2011-02-05T02:33:59+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Oh my... If the people can't use simple GUI and old good conzoleee, then I probably completly f**ked up.
## Post #63
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-05T05:07:29+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

How do i get complete lists for dante's inferno ps3? i keep getting mostly unknown files.
## Post #64
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-05T08:32:40+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Strange, accidentally corrupted DS2DAT0.DAT so I redownloaded the game from EADM, and it gave me PAL data too alongside the NTSC data I got before, my local install now has data for ntsc_en_fr, pal_de_en, and pal_es_it. 

Oh well, I can make some better file lists with this I think.
## Post #65
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2011-02-05T12:01:06+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Rick
>
> ArchiveViewer = Unpack (need to write an UnpackBig too) big (viv, dat)
PackBig = Pack big (viv, dat)
Sorry, my fold. I have found out how I can unpack the *.dat - files.

Can you fill the UNKOWN files for DEAD SPACE 2, too???

And how can i REPACK modded files with your tool to an *.dat archiv???
## Post #66
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-02-05T17:18:35+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

How to import modified files back to the .dat file? 
Or how to extract and reapck the whole file?
I have some modified files here and wanna put it back in the .dat
and try out in the game.

Help...
## Post #67
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-06T00:05:31+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Each command-line tool gives instructions on its usage, if you don't have the capability to use command-line tools then I'm afraid I can't help you. BigViewer = unpack .dat/.viv, BigPack = pack .dat/.viv. StrUnpack = unpack .str, StrPack = pack .str.

Unknown files are a work in progress; for Dead Space 2 the only unknowns left are audio files which are a very low priority for me. I am not really interested in audio files.

I've committed updates to StrUnpack and committed an implementation of StrPack that I used to create a mod already (and it works) that unlocks the Conduit doors on PC version of the game.
## Post #68
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-06T00:10:15+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

To easily override content (at least in the PC version of Dead Space 2), you can do the following:

Depending on your version of the game, you may need to do some file shuffling to make this mod work.

If you have a DS2DAT0.DAT, you'll need to rename all existing DS2DAT#.DAT to one number higher, eg:

DS2DAT0.DAT -> DS2DAT1.DAT
DS2DAT1.DAT -> DS2DAT2.DAT
DS2DAT2.DAT -> DS2DAT3.DAT
DS2DAT3.DAT -> DS2DAT4.DAT
DS2DAT4.DAT -> DS2DAT5.DAT
DS2DAT5.DAT -> DS2DAT6.DAT
DS2DAT6.DAT -> DS2DAT7.DAT
DS2DAT7.DAT -> DS2DAT8.DAT
DS2DAT8.DAT -> DS2DAT9.DAT
DS2DAT9.DAT -> DS2DAT10.DAT

Then pack whatever files you want to override into a new DS2DAT0.DAT and the game will use that to override other files.
## Post #69
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-06T00:12:32+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

thanks rick
## Post #70
- Username: JBieber
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 03, 2010 1:01 am
- Post datetime: 2011-02-06T02:04:02+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Rick
>
> Each command-line tool gives instructions on its usage, if you don't have the capability to use command-line tools then I'm afraid I can't help you. BigViewer = unpack .dat/.viv, BigPack = pack .dat/.viv. StrUnpack = unpack .str, StrPack = pack .str.
[http://svn.gib.me/public/visceral/trunk/](http://svn.gib.me/public/visceral/trunk/) i can't find command line tool only strange code.
I'm ultra noob but i can use command line tool. I don't know where to put this code (for unpack, pack .dat files) or how to use.
## Post #71
- Username: iluvjesus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 06, 2011 12:08 pm
- Post datetime: 2011-02-06T04:24:09+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

can anyone help me in using this tool? can't seem to start this up in c#
## Post #72
- Username: iluvjesus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 06, 2011 12:08 pm
- Post datetime: 2011-02-06T04:54:34+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

can anyone help me on opening these?
## Post #73
- Username: StaticTheFox
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 28, 2011 11:44 am
- Post datetime: 2011-02-06T09:00:45+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Curious as to what type of data the texture and model formats use.
## Post #74
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-06T09:02:45+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from StaticTheFox
>
> Curious as to what type of data the texture and model formats use.Textures use DXT compression, not exactly DDS files but can be converted pretty easily using Squish. Have not looked at models.
## Post #75
- Username: StaticTheFox
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 28, 2011 11:44 am
- Post datetime: 2011-02-06T09:16:44+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Rick
>
> StaticTheFox wrote:Curious as to what type of data the texture and model formats use.Textures use DXT compression, not exactly DDS files but can be converted pretty easily using Squish. Have not looked at models.
Dumb question, but is it bad that I can't find an EXE to it?  I compiled everything correctly.
## Post #76
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2011-02-06T11:33:10+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Someone can attach the binaries? 
Thaaanks
## Post #77
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2011-02-06T16:13:12+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from JBieber
>
> Each command-line tool gives instructions on its usage, if you don't have the capability to use command-line tools then I'm afraid I can't help you. BigViewer = unpack .dat/.viv, BigPack = pack .dat/.viv. StrUnpack = unpack .str, StrPack = pack .str.That´s nice.   

But where i can finde the (re)packer for *.dat-files?

Sorry, but i can find it.   

Please a DIRECT-LINK.
## Post #78
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-02-06T18:30:36+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Can someone send the compiled version?
## Post #79
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-06T18:34:33+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

[http://www.sendspace.com/file/fh3lgv](http://www.sendspace.com/file/fh3lgv)

Here is the Compiled Bin folder.
## Post #80
- Username: Blank
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 05, 2010 12:05 pm
- Post datetime: 2011-02-06T18:38:23+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

I apologize for adding onto the growing list of questions from amateur video game rippers, but I've been having a bit of trouble converting the .snu audio files extracted via BigViewer. I originally thought that such files could be decoded by the program OrangeC used for the original Dead Space ([http://www.multiupload.com/9YPDMKQ79Y](http://www.multiupload.com/9YPDMKQ79Y)), but the method doesn't seem to be very effective with Dead Space 2's newer streams. Is there an alternate program or method for handling such files, and is the task of translating them feasible for a person with little understanding of the programming languages involved?

I thank you for your consideration and express my sincere appreciation towards the Xentax community for providing the tools and information that have gotten me this far.
## Post #81
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-06T18:43:24+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

I have ripped the audio files using the xbox360 version of the game because it uses EA packed XMA, So i would suggest you go on hcs tools page and grab ea_multixma to unpack the xma streams at offset 0x20. grab xma_parse to rebuild xma streams then get alpha's xmariffheader script to add headers and towav to convert the xma files.

its a bit of work but it dos the job.
## Post #82
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-02-06T18:55:40+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

I want to+ translate the game... Can someone tell	to me where is the text files?
## Post #83
- Username: Blank
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 05, 2010 12:05 pm
- Post datetime: 2011-02-06T18:57:35+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from OrangeC
>
> I have ripped the audio files using the xbox360 version of the game because it uses EA packed XMA, So i would suggest you go on hcs tools page and grab ea_multixma to unpack the xma streams at offset 0x20. grab xma_parse to rebuild xma streams then get alpha's xmariffheader script to add headers and towav to convert the xma files.

its a bit of work but it dos the job.

I actually tried that method with with the .snu files of Dante's Inferno and BFBC_res_decode_pack.7z, but I have no idea how to perform the 0x20 offset. Do I need to modify some aspect of the ea_multi_xma.exe program, or is the concept of the offset a programming technique that should be familiar to even amateurs?

I thank you for your quick response and would like to thank you for the game rips you've contributed to the Internet over the years.
## Post #84
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-06T19:37:33+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

its just a cpommand line argument

ea_multi_xma file.snu -o 0x20

enter and it demuxes the streams.
## Post #85
- Username: Blank
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 05, 2010 12:05 pm
- Post datetime: 2011-02-06T20:55:02+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from OrangeC
>
> its just a cpommand line argument

ea_multi_xma file.snu -o 0x20

enter and it demuxes the streams.

I'm embarrassed to say that I don't know what a command line argument is; do I have to place that exact statement into the Run box, or do I need to edit the properties of either ea_multi_xma.exe or the .snu files?

Moreover, because I'm guessing that I'm doing something wrong when I open ea_multi_xma.exe and get no response, how will I know if whatever configuration I end up with is the correct one for .snu conversion?

I again apologize for my lack of familiarity with basic programming; I never thought such tasks would be so difficult to calculate.

EDIT: After several incidents of trial-and-error, I think I finally understand how to use ea_multi_xma.exe. I'm toying around with the Command Prompt for the first time in my life, and putting in the file locations and your aforementioned argument seems to yield results. I'll continue such experiments with high hopes, but please accept this simple illustration as a token of my appreciation for all of your help.
## Post #86
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2011-02-07T09:23:35+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Can you tell me where are the game text files? Thanks.
## Post #87
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-08T01:38:00+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Hello rick i was wondering if you are building a filelist for BIGFILE0.viv for dante's inferno ps3? id really love to have he audio filenames.
## Post #88
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2011-02-08T11:36:45+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Very nice work Rick! Thanks for your time and effort.
## Post #89
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2011-02-08T18:04:25+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from geevious
>
> Very nice work Rick! Thanks for your time and effort.Too.  

And THX @ OrangeC for compiling die NEW Version.
## Post #90
- Username: Blank
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 05, 2010 12:05 pm
- Post datetime: 2011-02-09T01:56:14+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

I'm sure this situation has already been addressed with XMA files in general, but I'd appreciate a less complex explanation for the answer I'm anticipating. Essentially, I'm in the process of converting .snu files using the process graciously mentioned by OrangeC a few posts ago. While it works very well for most of the streams, a few only convert into short pieces of gibberish. Searches on Google have led me to believe that the issue is related to either the header configuration in the batch file or my incorrect rebuilding of the XMA stream through xma_test.exe. Does anyone happen to know how to resolve this, and is he or she willing to explain the proper process to someone relatively unfamiliar with the logic behind the executables?

Here are the files in question, as well as the associated programs and the results I've received.
[http://www.multiupload.com/9F0U8EXD28](http://www.multiupload.com/9F0U8EXD28)
## Post #91
- Username: ghf50
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 04, 2011 10:47 pm
- Post datetime: 2011-02-09T05:56:37+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from OrangeC
>
> I have ripped the audio files using the xbox360 version of the game because it uses EA packed XMA, So i would suggest you go on hcs tools page and grab ea_multixma to unpack the xma streams at offset 0x20. grab xma_parse to rebuild xma streams then get alpha's xmariffheader script to add headers and towav to convert the xma files.

its a bit of work but it dos the job.

Hi, everyone. sorry for my poor english
I have the file mx_credits_ds2.exa.snu from pc version of Dead Space 2.
is it uses EA packed XMA? How to make it decodeable.(I don't have the file of 360 version)
I am a noob, can anyone explain it in simple, I will be great thanks to him/her
## Post #92
- Username: leonkennedy4011
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 21, 2010 8:44 pm
- Post datetime: 2011-02-09T06:55:55+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Just wondering, I unpacked the STR with isaacs engineer suit, the mesh is in GEO format, what opens this? is there a 3ds max script for it?
## Post #93
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-02-09T07:10:03+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from leonkennedy4011
>
> Just wondering, I unpacked the STR with isaacs engineer suit, the mesh is in GEO format, what opens this? is there a 3ds max script for it?

once you open it, can you make a print screen of it , and what program did you use to open that file?
## Post #94
- Username: leonkennedy4011
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 21, 2010 8:44 pm
- Post datetime: 2011-02-09T07:23:42+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from sirew
>
> leonkennedy4011 wrote:Just wondering, I unpacked the STR with isaacs engineer suit, the mesh is in GEO format, what opens this? is there a 3ds max script for it?

once you open it, can you make a print screen of it , and what program did you use to open that file?
yes I know but what opens the geo file in order to even view the model?, and compiled version posted on page six, in the bin folder there are a few different exe files, save the str file from the viewer and drag it on the strunpack exe
## Post #95
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-09T10:04:58+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

.geo is likely some proprietary Visceral model format.
## Post #96
- Username: Nexus Elite ns
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2009 1:11 am
- Post datetime: 2011-02-09T10:16:08+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Rick
>
> .geo is likely some proprietary Visceral model format.
Anyways of converting it to mesh?
## Post #97
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-09T13:16:12+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from ghf50
>
> OrangeC wrote:I have ripped the audio files using the xbox360 version of the game because it uses EA packed XMA, So i would suggest you go on hcs tools page and grab ea_multixma to unpack the xma streams at offset 0x20. grab xma_parse to rebuild xma streams then get alpha's xmariffheader script to add headers and towav to convert the xma files.

its a bit of work but it dos the job.

Hi, everyone. sorry for my poor english
I have the file mx_credits_ds2.exa.snu from pc version of Dead Space 2.
is it uses EA packed XMA? How to make it decodeable.(I don't have the file of 360 version)
I am a noob, can anyone explain it in simple, I will be great thanks to him/her

EA packed xma is 360 only, however xplorer's towav can convert some dead space SNU's but not all.
## Post #98
- Username: ghf50
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 04, 2011 10:47 pm
- Post datetime: 2011-02-09T13:43:31+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from OrangeC
>
> EA packed xma is 360 only, however xplorer's towav can convert some dead space SNU's but not all.
Thanks for your reply.
I'v tried the xplorer's ToWav, it can convert Dead Space 1's exa.snu file to wav format, but not work with ds2's exa.snu.
Are there any other way to make ds2's exa.snu file decodeable ?  Oh,god. I really love the credits music
## Post #99
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-09T13:48:18+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

not at this time no atleast for pc version, but 360 decodes fine with he method i explained a few posts back.
## Post #100
- Username: FlyingShip
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 24, 2010 11:55 pm
- Post datetime: 2011-02-09T14:39:31+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

The contents of this post was deleted because of possible forum rules violation.
## Post #101
- Username: ghf50
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 04, 2011 10:47 pm
- Post datetime: 2011-02-09T16:19:06+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from OrangeC
>
> not at this time no atleast for pc version, but 360 decodes fine with he method i explained a few posts back.
a little pity.The only thing I can do now is wait for someone write a new docoder.  
But anyway, thanks for your response!
Almost forgot, Would you please upload the 360 version of mx_credits_ds2.exa.snu somewhere for me, I'll try convert it my self. In pc version, this file is in DS2DAT0.DAT:audiostreams\redits_d\mx_credits_ds2.exa.snu, and I don't know if the filename or location of this file in 360 is same as pc. sorry for my poor english
## Post #102
- Username: ghf50
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 04, 2011 10:47 pm
- Post datetime: 2011-02-09T16:20:45+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

The contents of this post was deleted because of possible forum rules violation.
## Post #103
- Username: Blank
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 05, 2010 12:05 pm
- Post datetime: 2011-02-09T16:40:05+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from ghf50
>
> OrangeC wrote:not at this time no atleast for pc version, but 360 decodes fine with he method i explained a few posts back.
a little pity.The only thing I can do now is wait for someone write a new docoder.  
But anyway, thanks for your response!
Almost forgot, Would you please upload the 360 version of mx_credits_ds2.exa.snu somewhere for me, I'll try convert it my self. In pc version, this file is in DS2DAT0.DAT:audiostreams\redits_d\mx_credits_ds2.exa.snu, and I don't know if the filename or location of this file in 360 is same as pc. sorry for my poor english

How's this?
[http://www.multiupload.com/I3RUU68C8F](http://www.multiupload.com/I3RUU68C8F)
## Post #104
- Username: ghf50
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 04, 2011 10:47 pm
- Post datetime: 2011-02-09T18:04:00+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from OrangeC
>
> I have ripped the audio files using the xbox360 version of the game because it uses EA packed XMA, So i would suggest you go on hcs tools page and grab ea_multixma to unpack the xma streams at offset 0x20. grab xma_parse to rebuild xma streams then get alpha's xmariffheader script to add headers and towav to convert the xma files.

its a bit of work but it dos the job.
Hi, OrangeC. Do you know how to use xma_parse? it has many arguments, which should I use?
I use xma_parse like this

```
xma_test.exe mx_credits_ds2.exa.snu_stream1 -r test.xma
```

after this, I use quickbms to add a xma riff header to test.xma,and docode it by towav.
but I got a 11seconds wav file,and it sounds 60times faster than in game.
which step is wrong?
## Post #105
- Username: ghf50
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 04, 2011 10:47 pm
- Post datetime: 2011-02-09T18:05:13+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Blank
>
> How's this?
http://www.multiupload.com/I3RUU68C8F
Yes! thank you!
## Post #106
- Username: renato
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 03, 2010 9:16 am
- Post datetime: 2011-02-09T21:20:35+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Could this be related to the .geo extension?
[viewtopic.php?f=16&t=4837&p=41404&hilit=.geo#p41404](http://forum.xentax.com/viewtopic.php?f=16&t=4837&p=41404&hilit=.geo#p41404)
## Post #107
- Username: leonkennedy4011
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 21, 2010 8:44 pm
- Post datetime: 2011-02-09T23:35:06+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from renato
>
> Could this be related to the .geo extension?
viewtopic.php?f=16&t=4837&p=41404&hilit=.geo#p41404
maybe but thats a older game, different build
## Post #108
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-09T23:54:26+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Maybe it use the same format but different compression
## Post #109
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-10T00:32:12+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

If it's not developed by Visceral it's very unlikely.
## Post #110
- Username: leonkennedy4011
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 21, 2010 8:44 pm
- Post datetime: 2011-02-10T04:16:16+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

btw has anyone tried model swaping? if you look in isaacs suits the hacker suit from the console is in there among the other exlusives, I tired swaping the hacker suit with the advance suit but it just made it invisible, my second attempt made the suit chaning loop over and over
## Post #111
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-02-10T04:40:48+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from leonkennedy4011
>
> btw has anyone tried model swaping? if you look in isaacs suits the hacker suit from the console is in there among the other exlusives, I tired swaping the hacker suit with the advance suit but it just made it invisible, my second attempt made the suit chaning loop over and over

what do you mean by 'invisible'?
## Post #112
- Username: leonkennedy4011
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 21, 2010 8:44 pm
- Post datetime: 2011-02-10T05:55:25+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from sirew
>
> leonkennedy4011 wrote:btw has anyone tried model swaping? if you look in isaacs suits the hacker suit from the console is in there among the other exlusives, I tired swaping the hacker suit with the advance suit but it just made it invisible, my second attempt made the suit chaning loop over and over

what do you mean by 'invisible'?
I mean invisible as in literally 
[](http://img835.imageshack.us/i/27602178.jpg/)
## Post #113
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-02-10T06:09:47+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

oooo,I see, is your game pc or console version?
## Post #114
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-10T06:24:48+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Why swap for the hacker suit?

[http://mod.gib.me/deadspace2/conduit.7z](http://mod.gib.me/deadspace2/conduit.7z) (unlocks conduit rooms on PC)
## Post #115
- Username: leonkennedy4011
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 21, 2010 8:44 pm
- Post datetime: 2011-02-10T06:33:55+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Rick
>
> Why swap for the hacker suit?

http://mod.gib.me/deadspace2/conduit.7z (unlocks conduit rooms on PC)
whats the conduit room? I was swaping cause you cant unlock the collecter edition suit, hacker suit on pc
edit: ok I see what they are now, thanks
## Post #116
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2011-02-10T19:09:22+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

@Rick i have a lot of unknow files the program only works in 3 languages right?
## Post #117
- Username: saladbeard
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 05, 2011 5:51 pm
- Post datetime: 2011-02-11T12:09:08+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Rick
>
> http://mod.gib.me/deadspace2/conduit.7z (unlocks conduit rooms on PC)

This is amazing! Thank you so much.
If anyone will be able to extract Isaac's suit models, could you share them with us please: [viewtopic.php?f=16&t=5966](http://forum.xentax.com/viewtopic.php?f=16&t=5966)
## Post #118
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2011-02-11T18:53:11+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

@ Rick

Where can i change ending/suffix before packing the modde files?????

I result ending/suffix is ALWAYS *.viv   

Or can i change the ending/suffix to *.dat, and it still work?
## Post #119
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-11T18:56:19+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Yes you can rename, or give it an output filename as whatever you wish on commandline.
## Post #120
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2011-02-12T19:08:13+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Rick
>
> Yes you can rename, or give it an output filename as whatever you wish on commandline.THX for your fast answer.    And again: You prog nice CMD-tools, also great GUI´s for it, to can get better/faster result.   

The only thing is. The filename from the "X-Box Version" are the same than for the version for pc? Because you have write the filelist for the "X-Box Version", or?
## Post #121
- Username: renato
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 03, 2010 9:16 am
- Post datetime: 2011-02-12T23:55:19+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Any clue how can open the .geo files?

by google translate
## Post #122
- Username: Aliensoldier
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 13, 2011 10:36 pm
- Post datetime: 2011-02-13T20:45:13+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from renato
>
> Any clue how can open the .geo files?

> Reply from nightFlarer
>
> Phew, ok, I am done. So it's the same deal guys with maxscripts. 
Copy the code below, open up 3DS Max, Maxscript Menu>New Script, then paste, save, Maxscript Menu>Run Script, select the script you saved.

Now it's going to ask for the mesh file, so open up a .geo in the "Mesh" folder eg. 0144_torsoupper.geo
Then it's going to ask for the UV file which is also a .geo file, but should be in the "MeshVolatile" folder eg. 0145_torsoupper.geo
Notice that the number is different, lower is the mesh and greater is the UV.
Code: Select allfname = getOpenFileName \ 
caption:"Open .geo from Mesh folder" \
types:"Dead Space 2 Mesh(*.geo)|*.geo" \
historyCategory:"DeadSpace2ObjectPresets"
f = fopen fname "rb"
gname = getOpenFileName \ 
caption:"Open .geo from MeshVolatile folder" \
types:"Dead Space 2 UV(*.geo)|*.geo" \
historyCategory:"DeadSpace2ObjectPresets"
g = fopen gname "rb"
clearlistener()
fscale=100

Face_array=#()
Vert_array=#()
UV_array=#()

fseek f 0x0380 #seek_set
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
unk1=readlong f
vertcount=readlong f
unk2=readlong f
null1=readlong f
unk3=readlong f
vertcount=readlong f
unk4=readlong f
unk5=readlong f
unk6=readlong f
face=readlong f
unk7=readlong f
faceoff=readlong f

fseek f 0x400 #seek_set
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))

	
for x = 1 to vertcount do(

vx=readfloat f
vy=readfloat f
vz=readfloat f
p=readfloat f
p=readfloat f
p=readfloat f
p=readfloat f
p=readfloat f
append Vert_array([vx,vy,vz] * fscale)
)

for u = 1 to vertcount do(
tu=readfloat g
tv=readfloat g
append UV_array[tu,tv,0]
)

Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
fseek f faceoff #seek_set

for x = 1 to face/3 do(
fa=readshort f #unsigned+1
fb=readshort f #unsigned+1
fc=readshort f #unsigned+1
append Face_array[fa,fb,fc]
)
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))

msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]

Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f
fclose g

Well, I was using ConvertTG4 with Debug and it worked, or something like that...
[http://img502.imageshack.us/i/eurostileltstdbold32.png](http://img502.imageshack.us/i/eurostileltstdbold32.png)
It's not the best result, but I think every can see the texture of the Slasher in there.
## Post #123
- Username: StaticTheFox
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 28, 2011 11:44 am
- Post datetime: 2011-02-13T23:12:44+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Aliensoldier
>
> 
Well, I was using ConvertTG4 with Debug and it worked, or something like that...

It's not the best result, but I think every can see the texture of the Slasher in there.

How'd you do that?  for me it just outright crashes.

Edit: nevermind, but the results are really... pixelated.
## Post #124
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2011-02-14T02:16:46+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

The maxscript is updated in the other thread.
## Post #125
- Username: Nexus Elite ns
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2009 1:11 am
- Post datetime: 2011-02-14T04:06:21+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

I've notice there's some missing GEO files when you extract the STR, perhaps the unpacker need some fix, because there's only certain files for the GEO, while missing other stuff from it.
## Post #126
- Username: leonkennedy4011
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 21, 2010 8:44 pm
- Post datetime: 2011-02-14T06:12:26+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

having the same problem, a lot of mesh files are missing, arms, visor ext and some validate meshes for the UV as well
## Post #127
- Username: Aliensoldier
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 13, 2011 10:36 pm
- Post datetime: 2011-02-14T15:17:49+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from nightFlarer
>
> The maxscript is updated in the other thread.

Can you post it, pls?

EDIT: Oh you ment that script. So then, don't mind about my question...
## Post #128
- Username: RedDeadRedemption
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jul 13, 2010 10:23 pm
- Post datetime: 2011-02-15T17:12:54+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Any progress to decode snu files from PC version?
## Post #129
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2011-02-15T20:36:43+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Stupid question, I know, but does the Tool work for DS1? I tried extracting the .str packages, and while it does work, I think they're either files missing or not DS1 compatible. Once again, sorry for the stupid question, I just want to make sure.
## Post #130
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-02-16T09:36:17+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Hey guys, I 've done it using 3D Ripper, but I dislike it because of its hard to find the right texture and the mesh is not clean
## Post #131
- Username: ghf50
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 04, 2011 10:47 pm
- Post datetime: 2011-02-17T15:04:33+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from RedDeadRedemption
>
> Any progress to decode snu files from PC version?
I have the same question.hope someone can write a new decode program for PC version
## Post #132
- Username: Schemer
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jun 11, 2010 10:59 pm
- Post datetime: 2011-02-18T05:59:16+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

ghf50 +1
May someon make coder\decoder ds2 snu files?
## Post #133
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-02-18T09:37:36+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

need tool for dead space 2 language file.
## Post #134
- Username: Gamma256
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 15, 2011 8:13 am
- Post datetime: 2011-02-20T02:30:06+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Does anybody know where the animation files are? I am trying to experiment around but can't seem to find those files and its confusing. Thanks in advanced.
## Post #135
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-20T07:00:58+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Gamma256
>
> Does anybody know where the animation files are? I am trying to experiment around but can't seem to find those files and its confusing. Thanks in advanced.The animation files are the *.win files inside stream sets.
## Post #136
- Username: Gamma256
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 15, 2011 8:13 am
- Post datetime: 2011-02-20T15:41:25+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Rick
>
> The animation files are the *.win files inside stream sets.
Thanks. 



helmet less mod  even thou I wasn't aiming for it
## Post #137
- Username: Aliensoldier
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 13, 2011 10:36 pm
- Post datetime: 2011-02-20T16:52:50+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Gamma256
>
> helmet less mod

lol, looks nice   

I think I've found something interesting, it looks like Visceral has made his models with "Maya"
Here's an extraction from the file "0073_slasher.hkx.win"

```

```

Maybe there is a way to "reconvert" the mesh and open it in Maya?

And Rick, you said the animations are saved inside the *.win files, is there already a way to import them into 3Ds Max?
## Post #138
- Username: Gamma256
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 15, 2011 8:13 am
- Post datetime: 2011-02-20T18:16:34+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Aliensoldier
>
> Gamma256 wrote:helmet less mod

lol, looks nice

To bad he doesn't have any facial animations when talking, other then talking to Nichole, Ellie, and the blond without his helmet on.

Also from what I seen the HKX folder controls when your looking up, down, left and right. And the BNK folder controlled the helmet being shown even though I didn't edit that specif .win file for the helmet.
## Post #139
- Username: czehntner
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 17, 2011 12:27 am
- Post datetime: 2011-02-21T05:27:15+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

can somebody please explain to me how to make it so that i can pull the nescessary advanced armor (rig) files from the dat files?

Actually. I started playing around with the unpacking/pack tools provided by rick, and i think i figured out how to open the files. However, when i try to do this i keep getting an error page saying that the file is not responding and asks me if i wish to close or troubleshoot. Help?
## Post #140
- Username: Aliensoldier
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 13, 2011 10:36 pm
- Post datetime: 2011-02-22T15:57:30+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Can somebody explain me how to pack STR-files?
Everytime I use the STR-packer the program crashes...
## Post #141
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-02-25T22:46:13+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from czehntner
>
> can somebody please explain to me how to make it so that i can pull the nescessary advanced armor (rig) files from the dat files?

Actually. I started playing around with the unpacking/pack tools provided by rick, and i think i figured out how to open the files. However, when i try to do this i keep getting an error page saying that the file is not responding and asks me if i wish to close or troubleshoot. Help?

can you teach me how tu use unpacker?
## Post #142
- Username: Gamma256
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 15, 2011 8:13 am
- Post datetime: 2011-03-02T12:46:56+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from sirew
>
> can you teach me how tu use unpacker?
Drag ANY .str file and use Gibbed.Visceral.StrUnpack.exe NOT Gibbed.Visceral.UnpackSTR.exe

Also the new Dead Space 2: Severed str files wont unpack. Dunno why, hey rick if your still here can you possibly help?
## Post #143
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-02T13:23:31+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

thank you very much,which folder contain the suit?
## Post #144
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-03-02T22:52:43+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Gamma256
>
> Drag ANY .str file and use Gibbed.Visceral.StrUnpack.exe NOT Gibbed.Visceral.UnpackSTR.exe

Also the new Dead Space 2: Severed str files wont unpack. Dunno why, hey rick if your still here can you possibly help?Can you post the first 1MB of one of the ones that don't work?
## Post #145
- Username: Gamma256
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 15, 2011 8:13 am
- Post datetime: 2011-03-03T01:05:55+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from sirew
>
> thank you very much,which folder contain the suit?
All model files for characters and weapons will be located in DATA05 if you didnt add a extra DAT file to unlock the conduct rooms. If you did it will be DATA06. They will be under global assets.

> Reply from Rick
>
> Gamma256 wrote:Drag ANY .str file and use Gibbed.Visceral.StrUnpack.exe NOT Gibbed.Visceral.UnpackSTR.exe

Also the new Dead Space 2: Severed str files wont unpack. Dunno why, hey rick if your still here can you possibly help?Can you post the first 1MB of one of the ones that don't work?
I think all str files for Severed wont unpack. Well all the character ones I tried, I tried the level .str files and they seem to unpack fine, some of the ones I unpacked. I think it's the character .str's only at the moment.

Heres one of the characters.
[http://www.mediafire.com/?f02j1i162fok5x3](http://www.mediafire.com/?f02j1i162fok5x3)
## Post #146
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-03T02:15:13+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

yes, i've found, it, and the files type is .geo, I think there's still no viewer or exporter were made
## Post #147
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2011-03-04T02:25:08+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from sirew
>
> yes, i've found, it, and the files type is .geo, I think there's still no viewer or exporter were made

We're working on it.. No bones yet! We'll keep you posted
## Post #148
- Username: czehntner
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 17, 2011 12:27 am
- Post datetime: 2011-03-04T03:12:08+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from UberBlack
>
> sirew wrote:yes, i've found, it, and the files type is .geo, I think there's still no viewer or exporter were made

We're working on it.. No bones yet! We'll keep you posted

I'm hopin that means you guys are gonna beable to post files. I've hit a snag w my laptop and can't seem to figure out how to get those .geo files for the  advanced suit to save my life.....
## Post #149
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-04T07:31:11+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from UberBlack
>
> sirew wrote:yes, i've found, it, and the files type is .geo, I think there's still no viewer or exporter were made

We're working on it.. No bones yet! We'll keep you posted

Hope I can help, IF I knew about programming
## Post #150
- Username: Aliensoldier
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 13, 2011 10:36 pm
- Post datetime: 2011-03-04T16:49:45+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

If it's possible to upack files from Servered, could somebody upload Lexine, please?  : 
I know she is in the normal archives of Dead Space 2 too, but she has no head there and I think it's a really very old model
## Post #151
- Username: Gamma256
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 15, 2011 8:13 am
- Post datetime: 2011-03-04T23:08:03+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Aliensoldier
>
> If it's possible to upack files from Servered, could somebody upload Lexine, please?  : 
I know she is in the normal archives of Dead Space 2 too, but she has no head there and I think it's a really very old model

This is all I got from the normal archives of DS2. Never hurts to do some blind modding and repacking.
## Post #152
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-05T01:49:18+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Wow,awesome,good job
## Post #153
- Username: Gamma256
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 15, 2011 8:13 am
- Post datetime: 2011-03-05T01:58:30+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from sirew
>
> Wow,awesome,good job
She still needs an acutal hair texture. Right now it's not going right. I'll put it up sometime for dl.....when I finish nightflairs request.....
## Post #154
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-05T02:08:45+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

So it's not finish yet , but it's ok for me, because, you're just a step closer to finish,
## Post #155
- Username: Aliensoldier
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 13, 2011 10:36 pm
- Post datetime: 2011-03-05T16:18:35+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Gamma256
>
> Aliensoldier wrote:If it's possible to upack files from Servered, could somebody upload Lexine, please?  : 
I know she is in the normal archives of Dead Space 2 too, but she has no head there and I think it's a really very old model  

This is all I got from the normal archives of DS2. Never hurts to do some blind modding and repacking.

Wow, nice job! How did you get the textures? Here's my version:


I just used what the unfinished TG4D-concerter gave me, also the UV-coordinates were incorrect.
Well, I think you're one looks better   but how did you get the textures and here head?
I guess TexMod would not work, right?
## Post #156
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2011-03-05T22:28:03+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Aliensoldier
>
> Gamma256 wrote:Aliensoldier wrote:If it's possible to upack files from Servered, could somebody upload Lexine, please?  : 
I know she is in the normal archives of Dead Space 2 too, but she has no head there and I think it's a really very old model  
This is all I got from the normal archives of DS2. Never hurts to do some blind modding and repacking.

Wow, nice job! How did you get the textures? Here's my version:

I just used what the unfinished TG4D-concerter gave me, also the UV-coordinates were incorrect.
Well, I think you're one looks better   but how did you get the textures and here head?
I guess TexMod would not work, right?

If you were using my maxscript, it's probably because I didn't update it yet. I've fixed it for Gamma256 and gave it to him since he had a few problems, but I forgot to update my post.

```
caption:"Open .geo from Mesh folder" \
types:"Dead Space 2 Mesh(*.geo)|*.geo" \
historyCategory:"DeadSpace2ObjectPresets"
f = fopen fname "rb"
gname = getOpenFileName \
caption:"Open .geo from MeshVolatile folder" \
types:"Dead Space 2 UV(*.geo)|*.geo" \
historyCategory:"DeadSpace2ObjectPresets"
g = fopen gname "rb"
clearlistener()
fscale=100
indices = 0

Face_array=#()
Vert_array=#()
UV_array=#()

fseek f 0x50 #seek_set
infoOff1=readlong f
r=readlong f
r=readlong f
r=readlong f
r=readlong f
r=readlong f
infoOff2=readlong f

fseek f infoOff1 #seek_set
fseek f 48 #seek_cur
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
faceInd=readlong f
fseek f 76 #seek_cur
unk01=readlong f
vertOff=readlong f
faceOff=readlong f


fseek f infoOff2 #seek_set
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
unk1=readlong f
vertcount=readlong f
unk2=readlong f
null1=readlong f
unk3=readlong f
vertcount=readlong f
unk4=readlong f
unk5=readlong f
unk6=readlong f
face=readlong f
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
unk7=readlong f
unk8=readlong f
unk9=readlong f
unk10=readlong f
unk11=readlong f
unk12=readlong f
unk13=readlong f
face2=readlong f
Print ("face2 @ 0x"+((bit.intAsHex(ftell f))as string))

fseek f vertOff #seek_set
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))

   
for x = 1 to vertcount do(

vx=readfloat f
vy=readfloat f
vz=readfloat f
p=readfloat f
p=readfloat f
p=readfloat f
p=readfloat f
p=readfloat f
append Vert_array([vx,vy,vz] * fscale)
)

for u = 1 to vertcount do(
tu=readfloat g
tv=readfloat g
append UV_array[tu,tv,0]
)

fseek f faceoff #seek_set
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))

if (face2 > faceInd) then (
indices = face2
)else(
indices = faceInd)

if (faceInd > face) then (
indices = faceInd
)else(
indices = face)

for x = 1 to indices/3 do(
fa=readshort f #unsigned+1
fb=readshort f #unsigned+1
fc=readshort f #unsigned+1
append Face_array[fa,fb,fc]
)
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))

msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]

Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f
fclose g
```
## Post #157
- Username: Gamma256
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 15, 2011 8:13 am
- Post datetime: 2011-03-06T04:56:17+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

You updated it in the DS2 Model thread but not this on nightflair, should have mentioned that in my last post here about the new script woops. Just thought people check that thread.

Also I grabbed Isaac's face when he gets puked on....lot of trouble to make a texture you only get to see for 15 seconds really

> Reply from Aliensoldier
>
> Gamma256 wrote:Aliensoldier wrote:
I just used what the unfinished TG4D-concerter gave me, also the UV-coordinates were incorrect.
Well, I think you're one looks better   but how did you get the textures and here head?
I guess TexMod would not work, right?
I unpacked the .str file for lexine and swapped out the one textures with one of isaac's suit texture files. You just need to rename lexines textures to isaac's texture name if you want to rip the diffuse and normal right. 

Use 3ds DX Ripper to grab the textures properly.
## Post #158
- Username: Aliensoldier
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 13, 2011 10:36 pm
- Post datetime: 2011-03-06T11:30:48+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Gamma256
>
> 
I unpacked the .str file for lexine and swapped out the one textures with one of isaac's suit texture files. You just need to rename lexines textures to isaac's texture name if you want to rip the diffuse and normal right. 

Use 3ds DX Ripper to grab the textures properly.

Thanks mate, the new script works fine, you really did a great job   
But then I would need to RePack the STR-file, or did I missunderstand this?
That's the problem, it does not work. Could somebody tell me how to use the STR-packer correctly, please?  
And do you really use 3ds Ripper DX just to get the textures? I mean, if you have Lexine's texture already in the game, it would be enough to use TexMod, or not?

EDIT: Thanks mate, the new script works fine, you really did a great job
## Post #159
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-06T12:48:36+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

So do I need to use 3d max to open the model?
## Post #160
- Username: Aliensoldier
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 13, 2011 10:36 pm
- Post datetime: 2011-03-06T13:06:07+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from sirew
>
> So do I need to use 3d max to open the model?

Yes, you need 3DS Max to import the model. But then you can export it as another fileformat and edit it with other programs
## Post #161
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-06T13:30:27+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Aliensoldier
>
> sirew wrote:So do I need to use 3d max to open the model?

Yes, you need 3DS Max to import the model. But then you can export it as another fileformat and edit it with other programs

Owh and using this script? correct me if I'm wrong and thank you
## Post #162
- Username: Aliensoldier
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 13, 2011 10:36 pm
- Post datetime: 2011-03-06T16:48:39+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Yeah, go to MAXScript ---> New Script
Then paste the script in there and save it.
Then go to MAXScript ---> Run Script

And then you have to choose the GEO-files
## Post #163
- Username: Gamma256
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 15, 2011 8:13 am
- Post datetime: 2011-03-06T18:42:50+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Aliensoldier
>
> Yeah, go to MAXScript ---> New Script
Then paste the script in there and save it.
Then go to MAXScript ---> Run Script

And then you have to choose the GEO-files
Then when it wants you to choose a second GEO file its for the uvw...go to the MeshViolate folder and look for a smiliar name to that piece of GEO you choose the first time around....

also if anybody wanted to see what isaac looks like when the puker is done since you dont really get a good look since you only see it for like 4 seconds.
[http://img39.imageshack.us/img39/805/needanewface.jpg](http://img39.imageshack.us/img39/805/needanewface.jpg)
made it a url because the picture creeps the hell out of me
## Post #164
- Username: Aliensoldier
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 13, 2011 10:36 pm
- Post datetime: 2011-03-06T19:00:26+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Gamma256
>
> 

also if anybody wanted to see what isaac looks like when the puker is done since you dont really get a good look since you only see it for like 4 seconds.
http://img39.imageshack.us/img39/805/needanewface.jpg
made it a url because the picture creeps the hell out of me

Wonderfull ^^
Anyway, how did you get the UV-coordinates for the texture? Or is it ripped with 3Ds Ripper DX?
And can somebody please tell me how to use the STR-packer correctly, please? Please anybody
## Post #165
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-07T03:34:29+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

can someone upload gabe's suit, I just need the suit
## Post #166
- Username: Aliensoldier
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 13, 2011 10:36 pm
- Post datetime: 2011-03-07T06:31:17+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from sirew
>
> can someone upload gabe's suit, I just need the suit

This would mean somebody would need to import the models from the console, I'm not sure if this is possible.
I only heard about Porting from PS3.
Didn't somebody here said he was already trying to port models from Servered?
## Post #167
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-07T06:48:22+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from Aliensoldier
>
> sirew wrote:can someone upload gabe's suit, I just need the suit

This would mean somebody would need to import the models from the console, I'm not sure if this is possible.
I only heard about Porting from PS3.
Didn't somebody here said he was already trying to port models from Servered?

 owh sorry, I mean the .geo's files not the converted one
## Post #168
- Username: Gamma256
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 15, 2011 8:13 am
- Post datetime: 2011-03-10T22:36:15+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from sirew
>
> Aliensoldier wrote:sirew wrote:can someone upload gabe's suit, I just need the suit

This would mean somebody would need to import the models from the console, I'm not sure if this is possible.
I only heard about Porting from PS3.
Didn't somebody here said he was already trying to port models from Servered?

 owh sorry, I mean the .geo's files not the converted one

str unpacker isnt working with the severed files and I gave Rick a DS2: Severed str file. Have not heard from him since page 10.
## Post #169
- Username: jackycalo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 23, 2011 10:43 pm
- Post datetime: 2011-03-23T14:51:05+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

I need those gun sounds =(
Where the hell are they?
## Post #170
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-23T15:00:27+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from jackycalo
>
> I need those gun sounds =(
Where the hell are they?
HI, have you manage to get those models?
## Post #171
- Username: jackycalo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 23, 2011 10:43 pm
- Post datetime: 2011-03-23T15:07:46+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

What? no...
Found some atmosphere, background, audio_log and monster sounds.
## Post #172
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-23T22:37:45+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from jackycalo
>
> What? no...
Found some atmosphere, background, audio_log and monster sounds.
 owh you just found bg model
## Post #173
- Username: jackycalo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 23, 2011 10:43 pm
- Post datetime: 2011-03-24T10:49:08+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

bg model?

I want those gun sound files, not some model files.

found this in DS2DAT9: global_assets\global_assets\ds_assets\weapn_str
what now?
## Post #174
- Username: sirew
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jan 30, 2011 9:24 pm
- Post datetime: 2011-03-24T12:14:09+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from jackycalo
>
> bg model?

I want those gun sound files, not some model files.

found this in DS2DAT9: global_assets\global_assets\ds_assets\weapn_str
what now?

 sorry if im making you mad, i'm just asking
## Post #175
- Username: Blank
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 05, 2010 12:05 pm
- Post datetime: 2011-03-27T19:34:34+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from jackycalo
>
> bg model?

I want those gun sound files, not some model files.

found this in DS2DAT9: global_assets\global_assets\ds_assets\weapn_str
what now?

The good news? .str files can be unpacked via the Command Line using one of the programs in BigViewer (see the attached file for it). They're basically archives, so they can hold all sorts of cool stuff inside, depending on where they're located. In your case, I think that particular .str should be audio-based, but I haven't looked at Dead Space 2's directory organization in a while. Re-check the surrounding folders, just in case it's actually a model archive.

The bad news? The sound files I've found inside .str archives have been in a format called .sbk, which I don't think has been cracked open yet. Same deal with the original Dead Space files. I've already given up trying to understand the .sbk's, but I also don't know much about file formats and coding to begin with, so I wouldn't be surprised if that question's been answered already.
[BigViewerRev36.7z](https://xentaxbackup.github.io/file/4122_BigViewerRev36.7z)
## Post #176
- Username: llsabetudoll
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 17, 2011 9:43 am
- Post datetime: 2011-04-21T22:16:55+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

how to replace the files. srt?Game:dead space 2 ps3/BIGFILE2.VIV



I have a file with same name on the desktop (subtitles in Portuguese )and just need to put it into the bigfile2.ViV.



I'm from rio de janeiro Brazil and their help is very important.
## Post #177
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-04-22T07:23:02+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Unpack the viv file, replace the str file, and use the Gibbed.Visceral.BigPack.exe to repack/create the viv file. As far as I know, no replace function.
## Post #178
- Username: llsabetudoll
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 17, 2011 9:43 am
- Post datetime: 2011-04-22T14:32:45+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from evin
>
> Unpack the viv file, replace the str file, and use the Gibbed.Visceral.BigPack.exe to repack/create the viv file. As far as I know, no replace function.

this method does not work!I've done it ten times and the game crashes.send me the latest version of the tool?if i extract everything and create a new file. viv, hangs the same way.

As I use:1-extract the file bigfile2.viv with Gibbed.Visceral.BigViewer
2-I create new file .viv with Gibbed.Visceral.BigPack(I drag the folder to the Gibbed.Visceral.BigPack)
3-I see that everything is ok(file structure with Gibbed.Visceral.BigViewer)
4-I test and the game crashes when starting.

what is wrong?
## Post #179
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-04-22T17:18:31+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

We need audio files with names for dante's inferno.
## Post #180
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-04-23T07:20:59+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from llsabetudoll
>
> evin wrote:Unpack the viv file, replace the str file, and use the Gibbed.Visceral.BigPack.exe to repack/create the viv file. As far as I know, no replace function.

this method does not work!I've done it ten times and the game crashes.send me the latest version of the tool?if i extract everything and create a new file. viv, hangs the same way.

As I use:1-extract the file bigfile2.viv with Gibbed.Visceral.BigViewer
2-I create new file .viv with Gibbed.Visceral.BigPack(I drag the folder to the Gibbed.Visceral.BigPack)
3-I see that everything is ok(file structure with Gibbed.Visceral.BigViewer)
4-I test and the game crashes when starting.

what is wrong?

Try to repack from command line, not with drag&drop.
You tried this with original files? Because one of my friend just unpacked and repacked a viv file, and the game worked fine.
Latest version of Rick's tool: [http://dl.dropbox.com/u/4953836/RickVisceral110423.zip](http://dl.dropbox.com/u/4953836/RickVisceral110423.zip)  (available for a couple of weeks)
## Post #181
- Username: llsabetudoll
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 17, 2011 9:43 am
- Post datetime: 2011-04-23T14:36:17+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Try to repack from command line, not with drag&drop.
>
> You tried this with original files? Because one of my friend just unpacked and repacked a viv file, and the game worked fine.
>
> Latest version of Rick's tool: http://dl.dropbox.com/u/4953836/RickVisceral110423.zip  (available for a couple of weeks)

means that the command lines?Sorry but I learned to move alone in this tool.Yes I tried with the original file of the game without mod.Gives black screen when booting.

teach me how to do it with command line?  Thanks for help
## Post #182
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-04-23T15:24:09+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Command line: Start menu -> Run -> cmd -> Enter

Into command line: Gibbed.Visceral.BigPack.exe outputbig inputDIR
outputbig - the new viv file
inputDIR - the name of the folder, where the unpacked files are
## Post #183
- Username: llsabetudoll
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 17, 2011 9:43 am
- Post datetime: 2011-04-23T20:50:53+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

> Reply from evin
>
> Command line: Start menu -> Run -> cmd -> Enter

Into command line: Gibbed.Visceral.BigPack.exe outputbig inputDIR
outputbig - the new viv file
inputDIR - the name of the folder, where the unpacked files are

thanks! now is working with cmd

but I could not translate because the translation is different from the pc/ps3

Thank you so very very much Good Easter for y'all aew
## Post #184
- Username: Quinalha
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 04, 2011 9:26 am
- Post datetime: 2011-05-04T02:22:13+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Hey guys, i need a great help.
I extract the bigfile2.viv (ps3). Inside the folder (text_assets/text) I found the text files.
I used the tool Gibbed.Visceral.StrUnpack in the file 51d3d3e4.str (size 192kb)
After extracting, i found a folder and inside that folder the file @archive.xml and the folder (LH2). Inside the folder (LH2) there is a file 0000_deadspace2_global.en.lh2 (size 344kb).
Without modifying the file 0000_deadspace2_global.en.lh2 (size 344kb) I used the tool Gibbed.Visceral.StrPack and pack the folder with files to str, but the file 51d3d3e4.str was the same size then *HL2 (344kb). How do I get the file 51d3d3e4.str with the same size as the original (192kb)?   
I would translate the dialogue in the game for my language, but with this trouble by creating the File Bigfile2.viv the PS3 is not start the game Dead Space 2 (Black screen).   
Thanks and sorry my bad english.
## Post #185
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-05-04T06:10:25+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

You can't, The gibbed tool can't recompress. Also, as far as I know, the tool compatible with the console files, but can create pc compatible str files, only. So the problem is not the new size of the str file, I think, but the non compatible str file.
## Post #186
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-05-06T15:42:21+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

You have to download all resource through SVN. But the compiled latest version already available from this topic.
## Post #187
- Username: sergoba
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 11, 2011 3:52 pm
- Post datetime: 2011-05-07T21:22:33+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

i understand alot about modding and computors, but i cannot for the LIFE of me fathom command lines. i do however work well with bats.

What should i write in a bat file to do a mass unpack/ repack of files? please help me, there will be cake
## Post #188
- Username: hyzh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 19, 2010 10:24 am
- Post datetime: 2011-12-28T05:00:15+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

hello, I have Dead Space 2 but where I can download or extract all sounds of this game ?
## Post #189
- Username: spy007
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 06, 2012 3:02 am
- Post datetime: 2012-02-05T23:02:43+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Can somebody please extract ds or ds2 menu action sounds for me?
## Post #190
- Username: deathkitten
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 24, 2012 12:32 pm
- Post datetime: 2012-06-24T05:12:30+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

I can extract the SNU files from DAT with the RickVisceral110423 tool from this thread, but how can I convert/play them after? 

Is there any way to view the text from the game like the ingame text logs you can pick up from corpses etc, since some of the logs are not audio? I would like to see if there are any hidden/ones that I missed when playing

thanks for any help
## Post #191
- Username: Marusero
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jan 15, 2012 4:12 am
- Post datetime: 2012-06-29T04:35:18+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Sorry to revive the topic, but ... Does it have to create a compatible tool .viv DS 1 and 2 of the Xbox 360?
## Post #192
- Username: deathkitten
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 24, 2012 12:32 pm
- Post datetime: 2012-06-30T22:52:47+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

this site seems pretty dead, don't bother
## Post #193
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2012-07-14T09:28:19+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

What about changing subtitles on other language voices, like english voices/spanish subtitles?? anyone??
## Post #194
- Username: deathkitten
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 24, 2012 12:32 pm
- Post datetime: 2012-07-24T13:18:09+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

dead website
## Post #195
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-08-03T08:16:18+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

Sorry for a necro, but has anyone figured out how to open the xbox 360 exa files and if someone has, could they post the instruction on doing so below? I kinda need it
## Post #196
- Username: tormunds
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Dec 11, 2015 1:52 am
- Post datetime: 2018-12-30T01:15:02+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

I probably shouldn't necro this thread. I've got a question though. Is there a way to add new files with BigPack or it just overrides existing files? I've been messing around for a bit with this but I'm in the need to add new stuff...

I've tried packing a file with custom file names and folder, but if I try loading them ingame it crashes, so I assume it's not finding the files.

Thanks beforehand.
## Post #197
- Username: OpticalFox
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 29, 2020 1:36 am
- Post datetime: 2020-02-28T19:21:48+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

All these years later, they never finished the tools.  There's no executables to be found in the github, and there is nothing online that tells where you find said executables.
## Post #198
- Username: L33THAK0R
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jul 13, 2021 2:48 pm
- Post datetime: 2021-08-09T17:52:57+00:00
- Post Title: Re: (PC) Dead Spece 2 (.dat)

I hear you there, hopefully one day someone will figure this out and get a complete toolset out, I was always hopeful I'd be able to unpack Dante's Inferno one day, alas it seems that dream is long dead.
