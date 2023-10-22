## Post #1
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-04-29T13:21:37+00:00
- Post Title: Quick BMS

Hi,
i'm using Quick BMS for repack some files. Quick BMS doesn't support repack bigger file original.
Is there some way how repack bigger files than original ?
Or reduce files what i want repack ?
Sorry for my bad english.
THX
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-29T13:49:31+00:00
- Post Title: Quick BMS

the auto function wont let you put back bigger files.
you can code your own script to repack any file but you have to know what you are doing in quickbms.
he has provided a few examples of how to do it.
## Post #3
- Username: COOLak
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Aug 14, 2012 2:19 am
- Post datetime: 2012-08-17T15:25:26+00:00
- Post Title: Quick BMS

Then can someone please rewrite the script for me so it could re-import files bigger than original?

```

# signature 0x1234
IDString "\x34\x12\x00\x00"

Get TOC Long
GoTo TOC

# signature 0x5768
IDString "\x78\x56\x00\x00"

Get FileCount Long
Get TOCPkSize Long
# 256+4+4+4=268
Math TOCUnSize = FileCount
Math TOCUnSize *= 268
SavePos TOC
# skip deflate magic bytes
Math TOCPkSize -= 2
Math TOC += 2
# workaround fix for big TOC in some archives
Math TOCUnSize *= 2

# unpack TOC
ComType deflate
Clog MEMORY_FILE TOC TOCPkSize TOCUnSize
ComType copy

For I = 1 To FileCount
  GetDString FileName 256 MEMORY_FILE
  Get FileOffs Long MEMORY_FILE
  Get FilePack Long MEMORY_FILE
  Get FileSize Long MEMORY_FILE
# skip deflate magic bytes
  Math FileOffs += 2
  Math FilePack -= 2

  ComType deflate
  Clog FileName FileOffs FilePack FileSize
  ComType copy
Next I
```


Many thanks in advance.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-17T18:42:23+00:00
- Post Title: Quick BMS

Pretty sure the restriction that the filesize cannot be bigger than the original is program limitation, not a script limitation.
## Post #5
- Username: COOLak
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Aug 14, 2012 2:19 am
- Post datetime: 2012-08-17T19:24:42+00:00
- Post Title: Quick BMS

> Reply from finale00
>
> Pretty sure the restriction that the filesize cannot be bigger than the original is program limitation, not a script limitation.

Well, I'm considering these words:

> Reply from chrrox
>
> the auto function wont let you put back bigger files.
you can code your own script to repack any file but you have to know what you are doing in quickbms.
he has provided a few examples of how to do it.

And if this is still not possible, then I will be greatful for the way that can provide me such functionality. Because I know it is possible. Some modders have repacked this game's archives and they didn't care about filesize, they have exceeded it when localized the game, but it works.

Examples of files: [http://narod.ru/disk/59467538001.12b045 ... 1.res.html](http://narod.ru/disk/59467538001.12b0457626e4b0f4e766e20ffae4ccdb/data1.res.html)
[http://narod.ru/disk/59467548001.f5aa85 ... 3.res.html](http://narod.ru/disk/59467548001.f5aa85c668d56512d0935d50e8aeccf5/data3.res.html)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-17T20:17:31+00:00
- Post Title: Quick BMS

the words of chrrox mean only that if you want to use bigger files you must code a repacker from scratch, and in that case a bms script is not a good solution because it doesn't grant the flexibility and the complexity needed for a repacker/rebuilder.

in short if the script is valid for reinjection (files <= originals, no crc/hash checks performed by the game and so on) then you have the perfect solution for replacing the modified files with no effort of the programmer who wrote the script and you.

if you want or need to write a repacker then you need the maximum effort which includes not only the programming work but also the reversing of the additional fields that you can ignore in extraction/reinjection work.

that's why the reinjection mode of quickbms is so incredibly cool for you (users) and moreover for me and other scripters who need to do zero work for the reinjection :)
## Post #7
- Username: COOLak
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Aug 14, 2012 2:19 am
- Post datetime: 2012-08-17T20:25:19+00:00
- Post Title: Quick BMS

> Reply from aluigi
>
> the words of chrrox mean only that if you want to use bigger files you must code a repacker from scratch, and in that case a bms script is not a good solution because it doesn't grant the flexibility and the complexity needed for a repacker/rebuilder.

in short if the script is valid for reinjection (files <= originals, no crc/hash checks performed by the game and so on) then you have the perfect solution for replacing the modified files with no effort of the programmer who wrote the script and you.

if you want or need to write a repacker then you need the maximum effort which includes not only the programming work but also the reversing of the additional fields that you can ignore in extraction/reinjection work.

that's why the reinjection mode of quickbms is so incredibly cool for you (users) and moreover for me and other scripters who need to do zero work for the reinjection

I understand this. But I still need to repack the archive with bigger files. The thing is that in 2001 Russian pirates have published this game here and they have localized it and overwrote these archives with bigger files with no problem. And Russian pirates are not some guru, they are just ordinary scripters. I just want to transfer their localization to patch 1.2 of this game (Cabela's 4x4 Off-Road Adventure 1), but I can't do it because of this problem. If you can help me, then please do it. I'm sorry for the trouble, but I really need this.
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-17T21:02:57+00:00
- Post Title: Quick BMS

I no longer create stand-alone repackers, so I can't help.
