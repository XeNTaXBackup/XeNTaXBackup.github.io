## Post #1
- Username: xujozer
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 07, 2011 1:36 pm
- Post datetime: 2014-06-06T10:03:16+00:00
- Post Title: Murdered Coalesced CRC (PS3/X360)

Hi, I'm doing some tests on coalesced file, game Murdered: Soul Suspect, the tools that were available for this file works perfectly in Dump/Insert, the problem is that the game seems to use a checksum to monitor possible changes, then even I changing one byte in file, the game crashes, only the .toc was not enough to record the data.
I wonder if anyone knows a tool to make the checksum does not change (not sure if there is such a tool), or if anyone knows where the checksum recorded. The game uses U3, and all the text is in this file: Coalesced_INT.bin 

Here is the file in question: 
[https://www.dropbox.com/s/4qinsy8ql9z2q ... ED_INT.BIN](https://www.dropbox.com/s/4qinsy8ql9z2qkm/COALESCED_INT.BIN)

P.S: The PC version does not have this problem.
## Post #2
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2014-06-06T21:51:36+00:00
- Post Title: Murdered Coalesced CRC (PS3/X360)

UE3 have SHA1 crc check in executable, try to change it, for example ps3 EBOOT.ELF


ps check for ps3, it's working
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-06-07T05:41:07+00:00
- Post Title: Murdered Coalesced CRC (PS3/X360)

There is no such a thing for X360... Tested without the problem. At least no for Coalesced.bin! I have translated a few lines of code and repack it and no problem game starts.
## Post #4
- Username: xujozer
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 07, 2011 1:36 pm
- Post datetime: 2014-06-07T15:37:13+00:00
- Post Title: Murdered Coalesced CRC (PS3/X360)

> Reply from Thief1987
>
> UE3 have SHA1 crc check in executable, try to change it, for example ps3 EBOOT.ELF


ps check for ps3, it's working
Thanks, I'll test now.

> Reply from michalss
>
> There is no such a thing for X360... Tested without the problem. At least no for Coalesced.bin! I have translated a few lines of code and repack it and no problem game starts.
Oh, I thought the xbox version also had checksum, sorry.
## Post #5
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2014-06-08T17:53:54+00:00
- Post Title: Murdered Coalesced CRC (PS3/X360)

If its just a crc check you can fake the original CRC value with the attached tool

Edit: sorry just noticed you said SHA1 crc so probably won't work.
[fakecrc.rar](https://xentaxbackup.github.io/file/7453_fakecrc.rar)
## Post #6
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-07-12T08:02:31+00:00
- Post Title: Murdered Coalesced CRC (PS3/X360)

Just found out on X360 it is ok for coalesced.bin but for files like Startup_LOC_INT.xxx there is some kind of check i cannot find where please can anyone help ? Thx

In this file is fonts..
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-07-12T08:14:17+00:00
- Post Title: Murdered Coalesced CRC (PS3/X360)

never mind found it 

So X360 has not any SHA1 check in defualt.xex they have size check in TOC files instead  Pretty easy to do
## Post #8
- Username: xujozer
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 07, 2011 1:36 pm
- Post datetime: 2014-07-13T02:33:11+00:00
- Post Title: Murdered Coalesced CRC (PS3/X360)

Michaels, what is the tool you use to reinsert the files extracted from .xxx?
I never could reinsert them.
## Post #9
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-07-13T09:27:52+00:00
- Post Title: Murdered Coalesced CRC (PS3/X360)

> Reply from xujozer
>
> Michaels, what is the tool you use to reinsert the files extracted from .xxx?
I never could reinsert them.

Hex editor  010 will do the job
## Post #10
- Username: xujozer
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 07, 2011 1:36 pm
- Post datetime: 2014-07-13T13:27:33+00:00
- Post Title: Murdered Coalesced CRC (PS3/X360)

> Reply from michalss
>
> xujozer wrote:Michaels, what is the tool you use to reinsert the files extracted from .xxx?
I never could reinsert them.

Hex editor  010 will do the job

I suspected it all along!
## Post #11
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-07-13T13:46:17+00:00
- Post Title: Murdered Coalesced CRC (PS3/X360)

> Reply from xujozer
>
> michalss wrote:xujozer wrote:Michaels, what is the tool you use to reinsert the files extracted from .xxx?
I never could reinsert them.

Hex editor  010 will do the job 

I suspected it all along!

XXX files are not that bad if you want to replace for example 1 or max 3 files, doable with HEX. Once you need to do some text reimport that is complicated and for me hard, however some ppl in here are good with UPK/XXX
## Post #12
- Username: xujozer
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 07, 2011 1:36 pm
- Post datetime: 2014-07-14T04:14:20+00:00
- Post Title: Murdered Coalesced CRC (PS3/X360)

I'm trying to find where is the font size of the cutscene, I found the value to the menu in the "PS3-FateGame" file... 
Do u know where is the value to increase the font size in the cutscene of the game?
## Post #13
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-07-15T04:43:06+00:00
- Post Title: Murdered Coalesced CRC (PS3/X360)

> Reply from xujozer
>
> I'm trying to find where is the font size of the cutscene, I found the value to the menu in the "PS3-FateGame" file... 
Do u know where is the value to increase the font size in the cutscene of the game?

I'm sorry never try it.
## Post #14
- Username: tynave
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 10, 2014 2:17 am
- Post datetime: 2014-11-09T18:22:16+00:00
- Post Title: Murdered Coalesced CRC (PS3/X360)

> Reply from xujozer
>
> Thief1987 wrote:UE3 have SHA1 crc check in executable, try to change it, for example ps3 EBOOT.ELF


ps check for ps3, it's working
Thanks, I'll test now.
michalss wrote:There is no such a thing for X360... Tested without the problem. At least no for Coalesced.bin! I have translated a few lines of code and repack it and no problem game starts.
Oh, I thought the xbox version also had checksum, sorry.

Hi xojuzer,

Did you manage to get it working by hex-editing the SHA in the EBOOT?
I tried, but didn't have any luck 

Could you please help me?
I have a translated coalesced_int file, taken from the Xbox 360 game, and I'd like to get it working on PS3.

Do I have to edit the toc file too?


--- Edit: Nvm, got it working
