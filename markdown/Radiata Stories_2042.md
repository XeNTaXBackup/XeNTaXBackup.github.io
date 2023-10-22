## Post #1
- Username: Melly
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 18, 2006 6:57 am
- Post datetime: 2006-08-17T23:06:01+00:00
- Post Title: Radiata Stories

I came here to request Radiata Stories and inserted the game into my DVD drive... but the only files that came up are:

IOPRP300.IMG (269 KB)
SLUS_212.62 (506 KB)
SYSTEM (57 bytes)

So I have no archive for an example of the Radiata Stories files... 

Any info on how to find the real files so I can do this request?
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-08-17T23:26:06+00:00
- Post Title: Radiata Stories

looks a ps2 structure
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-08-18T00:31:24+00:00
- Post Title: Radiata Stories

Yeah, it is. the IMG file is the one to most likely contain compressed files. You may want to look into it though, thoughts are that there may be hidden files.
## Post #4
- Username: Melly
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 18, 2006 6:57 am
- Post datetime: 2006-08-18T03:11:27+00:00
- Post Title: Radiata Stories

Yeah there would have to be hidden files since the DVD is over 4 gigs... I have no clue how to find them, though.


I attached a zip file of the file SLUS_212.62 from the DVD.  My zip of all the DVD's files is too big for attachment
[SLUS_212.62.zip](https://xentaxbackup.github.io/file/792_SLUS_212.62.zip)
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-08-18T06:08:58+00:00
- Post Title: Radiata Stories

Control Panel>Tools>Folder Options

From there go to the view tab, look for the thing that says "Hidden files and folders" and check "Show hidden files and folders"

Click ok then tell me if anything changes.
## Post #6
- Username: Melly
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 18, 2006 6:57 am
- Post datetime: 2006-08-18T16:51:47+00:00
- Post Title: Radiata Stories

> Reply from Darkfox
>
> Control Panel>Tools>Folder Options

From there go to the view tab, look for the thing that says "Hidden files and folders" and check "Show hidden files and folders"

Click ok then tell me if anything changes.

Nope... already had that enabled, which is why I'm confused nothing shows up.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-18T18:09:23+00:00
- Post Title: Radiata Stories

Here's some info:

The SLUS file is an ELF file, a PS2 executable file. 
Looking at the file itself also reveals it is much like an exeutable. 
So, there's probably no need to find more files, all you need is there. The executable and some data files.  

Try PS2Dis (Playstation 2 disassembler) to open the SLUS and also the other files, I noticed PS2Dis could also open .IMG files. 

[http://www.geocities.com/SiliconValley/ ... 69/ps2dis/](http://www.geocities.com/SiliconValley/Station/8269/ps2dis/)

And this may also interest you:

[http://forums.ngemu.com/pcsx2-official- ... -bios.html](http://forums.ngemu.com/pcsx2-official-forum/65034-dumping-your-ps2-bios.html)
## Post #8
- Username: Jaggedge
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 18, 2009 1:00 am
- Post datetime: 2009-07-20T04:39:25+00:00
- Post Title: Radiata Stories

Hi Mr Mouse, I'm new to game archive research, but very interested to start learning. I've recently gone through your definitive guide to exploring file formats and decided to run field tests on one of my favorite games, Radiata Stories.

I've tried PS2Dis as well as Hex Workshop on the SLUS file, but I'm still missing the data files you mentioned. So all I have at the moment are the SLUS ( 507kb ) and the IMG  ( 270kb ). I've tried the "Show hidden files and folders" option too. Could you share how you got them to appear? That's a wall for me at the moment, I think I can proceed once I see them.
