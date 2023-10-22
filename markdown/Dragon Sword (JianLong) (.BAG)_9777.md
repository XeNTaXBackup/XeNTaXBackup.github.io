## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-22T22:23:36+00:00
- Post Title: Dragon Sword (JianLong) (*.BAG)

Official Site: [Here](http://lj.netease.com)
Download Client: [Here (about 8GB)](http://lj.163.com/download/)
Download Unpacker - v0.0.5 r11 Hot Fix: [Here](https://www.sendspace.com/file/y622g4)
Preview Screen: [Here](http://img4.cache.netease.com/photo/0031/2012-07-06/85ODKLQS0RBT0031.jpg)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-22T23:47:54+00:00
- Post Title: Dragon Sword (JianLong) (*.BAG)

I figured out something
the size value in the file area_01.bag
it starts at offset 8 in the table
C8 E5 4F 4E
you xor it with 0xD0e54f4e
and you get 
18 00 00 00
the next one is 0xC bytes down
5C E5 4D 4E
you xor this with the last xor - C 0xc4e54f4e
and you get 98 00 02 00 
the next one 20654F4E
you again xor it with the last xor key - c 0xb8e54f4e
and you get
98 80 00 00


so the fiel table seems to go

hash name long
offset long
size long
and the first file is always offset 0x24
and size 0x18
so you can use those to generate the xor key 

it has something to do with the offset you read the value at i think
because around every 0x100 the 2nd number besides the - c changes
here is the values for area_01

> F0C6616C CFF95153 C8E54F4E - d0e54f4e
>
> CB4D616C F3F95153 5CE54D4E - c4e54f4e
>
> B4D66F6C 17F95353 20654F4E - b8e54f4e
>
> 893E736C EB785353 34654F4E - ace54f4e
>
> 5DC0756C 5FF85253 69E54F4E - a0e54f4e
>
> 6C017C6C 32FB5253 0C654F4E - 94e54f4e
>
> 4D027F6C D67A5253 10654F4E - 88e54f4e
>
> 
>
> 4E60416C 8AFB5553 E4E44D4E - 7ce44f4e
>
> 374B4C6C 1EFC5753 20CF4F4E - 70e44f4e
>
> F6C6596C BAD75753 B4E64F4E - 64e44f4e
>
> 1C4D5F6C D6CA5753 C0E4474E - 58e44f4e
>
> 1541256C 6ACB5F53 D4E4474E - 4ce44f4e
>
> 1E0D276C 9ECB4753 D8644F4E - 40e44f4e
>
> 4B732C6C 424C4753 64CF4F4E - 34e44f4e
>
> 2F022F6C 8E274753 B0E4474E - 28e44f4e
>
> 8BA43B6C 42184F53 84A44F4E - 1Ce44f4e
>
> offset 1F20FD
>
> 4D620C6C E6D84E53 DAE44F4E - 10e44f4e
>
> C6E9EF6C B8D94E53 54CF4F4E - 04e44f4e
>
> B558F26C 14B44E53 60644F4E - f8e44f4e
>
> 1F02F26C 68354E53 74E4474E - ece44f4e
>
> 7E0DF86C DC367653 78E44D4E - e0e44f4e
>
> 4482CB6C 00367853 4CE44D4E - d4e44f4e
>
> 24D3CC6C 84377A53 98CF4F4E - c8e44f4e
>
> offset 2BFAC7
>
> 1DAFD16C 00027A53 BDA64E4E - bce44f4e
>
> DCD7D06C 13C47C53 28E44D4E - b0e44f4e
>
> 94A3D06C FFC57E53 3C644F4E - a4e44f4e
>
> 8307D06C 6B457E53 00644F4E - 98e44f4e
>
> 23F9D36C E7C66153 14E44D4E - 8ce44f4e
>
> 8EA3D86C 83C76353 18644F4E - 80e44f4e
>
> 814BDD6C CF446353 ECE74D4E - 74e74f4e
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-23T12:34:16+00:00
- Post Title: Dragon Sword (JianLong) (*.BAG)

Hm.
[char.bag_table.rar](https://xentaxbackup.github.io/file/5916_char.bag_table.rar)
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-24T00:20:23+00:00
- Post Title: Dragon Sword (JianLong) (*.BAG)

the ZZZ files are compressed with COMP_LZO1X
mabee there needs to be some slight change to the algorithm?
the data looks mostly right but it may be a bit off.
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-03T17:02:46+00:00
- Post Title: Dragon Sword (JianLong) (*.BAG)

Ok i continued make tool for unpack files. Well function for decrypt table has been done.
I have one problem. On my first PC with Win7 Home Edition game does not work (just closing without errors or msg).
On second PC game will not work because lost one 512mb / 1024mb (yup broken). If chrrox can explain where stored info about hash offsets size (in table) i can write extractor.
## Post #6
- Username: Ekey
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-02-04T04:10:04+00:00
- Post Title: Dragon Sword (JianLong) (*.BAG)

its getting late you can probably finish this.
This seems to work on the first archive of each name but fails on the archives like char0 char1 ext.
ill look into why if you do not beat me to it.



```
#
# Written by Ekey (h4x0r) / a little from chrrox
# http://www.progamercity.net
#
# script for QuickBMS http://quickbms.aluigi.org
comtype lzo1x

get PAKSIZE asize
get ID long

if ID == 0x62616731
    set TotalFiles_Key "0xe7356461"
    set TableOffset_Key "0xcb449442"
    set UNK1_Key "0x698346bd"
    set UNK2_Key "0x867389fe"
    set UNK3_Key "0xabedc59d"
else ID == 0x62616732
    set TotalFiles_Key "0x27252421"
    set TableOffset_Key "0x3b343432"
    set UNK1_Key "0x5953565d"
    set UNK2_Key "0x6663696e"
    set UNK3_Key "0x7b7d757d"
endif

filexor TotalFiles_Key
get FILES long
math FILES - 1
filexor TableOffset_Key
get TABLEOFFSET long
filexor ""

set TABLESIZE = PAKSIZE
math TABLESIZE -= TABLEOFFSET
math TABLESIZE -= 4

goto TABLEOFFSET

for i = 0 < FILES
filexor UNK1_Key
get HASH long
filexor UNK2_Key
get OFFSET long
filexor UNK3_Key
get SIZE long
math HASH ^ TABLEOFFSET
math OFFSET ^ TABLEOFFSET
math SIZE ^ TABLEOFFSET
filexor ""
log MEMORY_FILE OFFSET SIZE
goto 0x18 MEMORY_FILE
math SIZE -= 0x18
if SIZE > 0
get tmp long MEMORY_FILE
if tmp = 0x5A5A5A5A
get TSIZE long MEMORY_FILE
math SIZE - 0x8
clog "" 0x20 SIZE TSIZE MEMORY_FILE
else
log "" 0x18 SIZE MEMORY_FILE
endif
else
log "" OFFSET 0x18
endif
math TABLEOFFSET += 12
next i

```
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-04T12:50:17+00:00
- Post Title: Dragon Sword (JianLong) (*.BAG)

Ok thanks for script, left to find hash func.
## Post #8
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-10-20T03:35:48+00:00
- Post Title: Dragon Sword (JianLong) (*.BAG)

> Reply from Ekey
>
> Ok thanks for script, left to find hash func. With formating hash
Code: Select all# Dragon Sword (JianLong) (BAG format) (IN PROGRESS)
#
# Written by Ekey (h4x0r) / a little from chrrox
# http://www.progamercity.net
#
# script for QuickBMS http://quickbms.aluigi.org

comtype lzo1x

get PAKSIZE asize
get ID long

if ID == 0x62616731
    set TotalFiles_Key "0xe7356461"
    set TableOffset_Key "0xcb449442"
    set UNK1_Key "0x698346bd"
    set UNK2_Key "0x867389fe"
    set UNK3_Key "0xabedc59d"
else ID == 0x62616732
    set TotalFiles_Key "0x27252421"
    set TableOffset_Key "0x3b343432"
    set UNK1_Key "0x5953565d"
    set UNK2_Key "0x6663696e"
    set UNK3_Key "0x7b7d757d"
endif

filexor TotalFiles_Key
get FILES long
math FILES - 1
filexor TableOffset_Key
get TABLEOFFSET long
filexor ""

set TABLESIZE = PAKSIZE
math TABLESIZE -= TABLEOFFSET
math TABLESIZE -= 4

goto TABLEOFFSET

for i = 0 < FILES
filexor UNK1_Key
get HASH long
filexor UNK2_Key
get OFFSET long
filexor UNK3_Key
get SIZE long
math HASH ^ TABLEOFFSET
math OFFSET ^ TABLEOFFSET
math SIZE ^ TABLEOFFSET
filexor ""
string NAME p= "%08X" HASH
log MEMORY_FILE OFFSET SIZE
goto 0x18 MEMORY_FILE
math SIZE -= 0x18
if SIZE > 0
get tmp long MEMORY_FILE
if tmp = 0x5A5A5A5A
get TSIZE long MEMORY_FILE
math SIZE - 0x8
clog NAME 0x20 SIZE TSIZE MEMORY_FILE
else
log NAME 0x18 SIZE MEMORY_FILE
endif
else
log NAME OFFSET 0x18
endif
math TABLEOFFSET += 12
next i

client-1.1.2 release，The script does not work。
[20131020113459.jpg](https://xentaxbackup.github.io/file/6715_20131020113459.jpg)
## Post #9
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-10-23T03:49:27+00:00
- Post Title: Dragon Sword (JianLong) (*.BAG)

client-1.1.2 Downloads: 

[http://ds.gdl.netease.com/ds-1.1.2.exe](http://ds.gdl.netease.com/ds-1.1.2.exe)
[http://ds.gdl.netease.com/ds-1.1.2.r00](http://ds.gdl.netease.com/ds-1.1.2.r00)
[http://ds.gdl.netease.com/ds-1.1.2.r01](http://ds.gdl.netease.com/ds-1.1.2.r01)
[http://ds.gdl.netease.com/ds-1.1.2.r02](http://ds.gdl.netease.com/ds-1.1.2.r02)
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-07T14:39:47+00:00
- Post Title: Dragon Sword (JianLong) (*.BAG)

W.I.P.. Now filenames can be detected!
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-08T15:27:08+00:00
- Post Title: Dragon Sword (JianLong) (*.BAG)

Done. First post updated. Tested on 1.1.62.
## Post #12
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2014-07-11T03:03:50+00:00
- Post Title: Dragon Sword (JianLong) (*.BAG)

hi~Ekey How to use pass？
## Post #13
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-11T05:23:24+00:00
- Post Title: Dragon Sword (JianLong) (*.BAG)

> Reply from Ekey
>
> Download Unpacker: Here
## Post #14
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-07-11T19:31:30+00:00
- Post Title: Dragon Sword (JianLong) (*.BAG)

first of all, big thanks to Ekey for the unpacker.
I Try it on char.bag (chient 1.1.62) and got 15551 of unknown items!!!
I did research on this 3D format sometime ago. (It's similiar to Legendary Champions)

.model is the whole model information (includes animation detail, lod etc)
.visual is material and bones
.primitives is the basic 3D data
.animation is actual animation data
.dds is texture

But in my unpacked char.bag, there is not .primitives files!?
I checked the unknown data. 
eg: 0E35ED36 , 33DAD878 , 679ABB60 etc. are dds files
06D70ED7 , 1568AC0C , C7515A2F , DCD80DCE etc are primitives files
03662545 , 0C013CE5 , 2A82F48E , FB4BB6FB etc are animation files

Is there any chance to update the hash list!?

Thanks
## Post #15
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-13T13:44:25+00:00
- Post Title: Dragon Sword (JianLong) (*.BAG)

Well i tryed writting logger, but in game have like CRC checksum and every time playing about 5 min crashing :\ Anyway you can find file names inside unknown files.
For example :

Original path: gui/gui2/Common/Kuang1ti1/circle_icons_select.wap
gui/ means this file inside gui.bag, delete it and you can get only gui2/Common/Kuang1ti1/circle_icons_select.wap
Replace slashes / to \ -> tolower -> gui2\common\kuang1ti1\circle_icons_select.wap

I will update unpacker later with automatic reverse slashes, make paths with lowercase and detecting extensions for unknown files. About filelist > maybe
## Post #16
- Username: troll1981
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 10, 2014 2:28 am
- Post datetime: 2014-07-17T19:04:24+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

hy Ekey!

is the unpacker updated ?   you write at 13.7 you will make an update ?
## Post #17
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-18T07:46:16+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

Not yet
## Post #18
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-09-18T18:09:08+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

> Reply from Ekey
>
> Not yetno news about that? you done a aweseme work before, is good you finish it to got it or if you are interested in got file names PM, if you explain a bit I can run client and play here to got it, ok many thanks and hope you can do it, see ya.
## Post #19
- Username: yitian
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 10, 2014 5:24 pm
- Post datetime: 2015-02-28T18:22:19+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

Anyone can reupload unpacker? please!!
## Post #20
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-03-02T15:10:04+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

Reuploaded.
## Post #21
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-03-02T16:04:33+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

> Reply from Ekey
>
> Reuploaded.HI Ekey, Thank you very much updated the tool
## Post #22
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-06-15T15:53:54+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

Unpacker is updated to 0.0.5 r10

```
- Added decryption for some files
- Base with file names is updated to 100% - Full list for latest game client
```


Download: 1st post
## Post #23
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-06-15T19:35:42+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

> Reply from Ekey
>
> Unpacker is updated to 0.0.5 r10
Code: Select all- Added newest compression algorithm
- Added decryption for some files
- Base with file names is updated to 100% - Full list for latest game client

Download: 1st post

what ploblem sir Client frome 1st post
## Post #24
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-06-15T20:38:16+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

Archive name? Or you got this error on app startup?

Try > Make properties for JLBAGUnpacker.exe and unlock file.
## Post #25
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-06-15T20:50:22+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

> Reply from Ekey
>
> Archive name? Or you got this error on app startup?

Try > Make properties for JLBAGUnpacker.exe and unlock file.

same
## Post #26
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-06-15T21:34:36+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

That is strange because i tested tool on WinXP, Win7 x64, Win10 and it works perfect.
## Post #27
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-06-16T04:00:44+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

> Reply from Ekey
>
> That is strange because i tested tool on WinXP, Win7 x64, Win10 and it works perfect.

i can't reply u in Message

Yes  u online
u have  Facebook or Twisrter or Skype ?
## Post #28
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-06-16T12:53:55+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

Fixed in r11
## Post #29
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2016-11-22T03:21:39+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

> Reply from Ekey
>
> Fixed in r11

Can you reupload the unpacker?
## Post #30
- Username: jackolo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 07, 2016 9:55 pm
- Post datetime: 2016-12-07T14:03:09+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

If this gets updated, will it work on other Netease games that uses .BAG files?
That would be sweet
## Post #31
- Username: jackolo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 07, 2016 9:55 pm
- Post datetime: 2016-12-21T08:35:42+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

> Reply from Ribales
>
> Hmm download doesn't work for me. What am I doing wrong?

Auto deleted by filehoster for inactivity, it also probably is outdated doesn't work anymore as well... :/ 


PS. for anyone out there who can help;
Here's another Netease game(WildFire Online) that uses .bag files, and is updated every 2 weeks.
Sample: [https://mega.nz/#!PFVTzQBY!uODqrJAP6Gvu ... RAYTTYAhRA](https://mega.nz/#!PFVTzQBY!uODqrJAP6GvuOxajIvJ8nY2XrkqbbvVlFRAYTTYAhRA)

Using [http://aluigi.org/bms/1gab_2gab_bag.bms](http://aluigi.org/bms/1gab_2gab_bag.bms) to attempt to unpack it yield this error message: [http://i.imgur.com/WaO5afc.png](http://i.imgur.com/WaO5afc.png)
## Post #32
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2017-01-11T12:23:30+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

any other mirror links of this tool?
## Post #33
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2017-08-09T17:10:21+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

@Ekey 

Could you re-upload the unpacker v.0.0.5 r11? link is dead
## Post #34
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2018-12-02T15:35:40+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

@Ekey  link is dead!help!
## Post #35
- Username: banlu
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 21, 2015 5:15 am
- Post datetime: 2019-10-15T05:02:25+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

could someone please reupload ekey's unpacker
## Post #36
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2019-10-17T10:06:56+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

[https://www19.zippyshare.com/v/jRM7swM4/file.html](https://www19.zippyshare.com/v/jRM7swM4/file.html)
## Post #37
- Username: banlu
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 21, 2015 5:15 am
- Post datetime: 2019-10-22T18:35:38+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

> Reply from Ekey ↑Thu Oct 17, 2019 6:06 pm at Thu Oct 17, 2019 6:06 pm
>
> 
https://www19.zippyshare.com/v/jRM7swM4/file.html

thank you sir !
## Post #38
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-04-12T23:33:43+00:00
- Post Title: Re: Dragon Sword (JianLong) (*.BAG)

@Ekey
can u reup the Unpack Tool?

PS: Is any importer for 3ds max exist?

Thanks!
