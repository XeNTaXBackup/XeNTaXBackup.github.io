## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-05T01:06:53+00:00
- Post Title: Exmachina - GDP

Hmmm ..... very interesting archive in this game.... 

Header PK - as in WinZip... but this is accurate not Winzip.... in whom what considerations to this archive?   

[http://rapidshare.de/files/10417081/Pack.zip.html](http://rapidshare.de/files/10417081/Pack.zip.html)
## Post #2
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-01-05T02:05:40+00:00
- Post Title: Exmachina - GDP

different headers

PKZIP header is  PK 0x03 0x04
This has a header of  PK 0x04 0x00
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-05T06:23:25+00:00
- Post Title: Exmachina - GDP

Does anyone have a better result that this? There must be some way to calculate the correct file offsets, or the first file offset, or something like that.

```
| Exmachina *.gdp |
+-----------------+

// Data is ZLib Compressed

// You can use the FileOffset field to correctly calculate the size of each file.
// When you reach the end of the directory, you will know the first file offset. You can then
// set the correct file offsets for each file.
// You can detect the end of the directory by trying to read entry field 3 - if it isn't the number
// 1 then it is the file data

2 - Header (PK)
2 - Version (4)
4 - Unknown
4 - null
4 - Version (1)
8 - CRC?
4 - null
4 - Unknown
12 - null

// for each file
  4 - Unknown
  8 - CRC?
  4 - Unknown (1)
  4 - null
  4 - File Offset [-XXXX]
  4 - Unknown
  4 - Unknown
  20 - null
  X - Filename
  2 - null Filename Terminator

X - File Data
```


WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-05T15:17:15+00:00
- Post Title: Exmachina - GDP

> Reply from Rahly
>
> different headers

PKZIP header is  PK 0x03 0x04
This has a header of  PK 0x04 0x00

Yes you the rights

> Reply from friendsofwatto
>
> Does anyone have a better result that this? There must be some way to calculate the correct file offsets, or the first file offset, or something like that.
I do hope will be plugin for Game Extractor?
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-05T22:10:20+00:00
- Post Title: Exmachina - GDP

Yes, I will be writing a plugin, but there just has to be a better way to do it - there are some things that just don't make any sence.

Plugin coming soon 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-05T22:28:37+00:00
- Post Title: Exmachina - GDP

Good... wait
