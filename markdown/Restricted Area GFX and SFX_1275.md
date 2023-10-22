## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-05-25T12:27:47+00:00
- Post Title: Restricted Area GFX and SFX

Help extract GFX and SFX in game Restricted Area  
[GroundLayer GFX.rar](https://xentaxbackup.github.io/file/253_GroundLayer GFX.rar)
## Post #2
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-05-25T12:28:23+00:00
- Post Title: Restricted Area GFX and SFX

This SFX pak file  
[MiniShip SFX.rar](https://xentaxbackup.github.io/file/254_MiniShip SFX.rar)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-25T13:34:56+00:00
- Post Title: Restricted Area GFX and SFX

Ok, thanks, downloaded them. Will take a look at them soon.
## Post #4
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-05-25T14:25:52+00:00
- Post Title: Restricted Area GFX and SFX

Good... Big thx Mr.Mouse
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-25T14:54:11+00:00
- Post Title: Restricted Area GFX and SFX

```
SavePos ST 0 ;
GoTo EOF 0 ;
SavePos END 0 ;
GoTo ST 0 ;
Set Num Long 0 ;
Do ;
Get UCS Long 0 ;
SavePos CSO 0 ;
Get CS Long 0 ;
SavePos FO 0 ;
SavePos J 0 ;
GetDString ID 2 0 ;
SavePos UCSO 0 ;
Set FN String FILE ;
String FN += Num ;
String FN += JC ;
Log FN FO CS 0 CSO ;
Math Num += 1 ;
Math J += CS ;
GoTo J 0 ;
While J < END ;

```


Fixed a script in my tea-break, wasn't so hard. However, the files are compressed. Haven't figured out what was used. They do have a tag "JC". 
So I made sure they were saved as JC files. They have no filenames normally. 

It's just a list of "JC" files

[uint32] uncompressed size
[uint32] compressed size (size in archive)
[uint32] filedata (starts with "JC" followed by a [uint32] Uncompressed size )
[pak.zip](https://xentaxbackup.github.io/file/255_pak.zip)
## Post #6
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-05-25T15:11:18+00:00
- Post Title: Restricted Area GFX and SFX

Super Scripts  Working Thx Mr.Mouse 
Mr. Mouse I likely have already tortured you
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-26T03:36:40+00:00
- Post Title: Restricted Area GFX and SFX

I came up with something very similar...

```
| Restricted Area *.pak |
+-----------------------+

// Unknown compression is used in this archive

// for each file
  4 - Decompressed File Length
  4 - File Length (not including this 8-byte header)
  
  // Compressed File Data
    2 - Compression Header (JC)
    4 - Decompressed File Length
    X - Compressed File Data
```


I don't know what the compression is either, which is disappointing 

I will have a Game Extractor plugin soon if you want it. Otherwise the MexCom script Mr Mouse posted will do the same job 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-26T13:34:56+00:00
- Post Title: Restricted Area GFX and SFX

Attached is a Game Extractor (full version) plugin for this archive format - unzip into your plugins/ directory (make the directory if it doesn't already exist). I didn't bother making this plugin for the Basic Version because all the files in the archive are unusable anyway due to the unknown compression. 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_PAK_16.zip](https://xentaxbackup.github.io/file/260_Plugin_PAK_16.zip)
