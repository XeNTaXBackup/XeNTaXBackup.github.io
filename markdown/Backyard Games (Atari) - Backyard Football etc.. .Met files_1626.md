## Post #1
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-20T08:18:27+00:00
- Post Title: Backyard Games (Atari) - Backyard Football etc.. .Met files

There is so many of these games.. And extractor/script could be nice..

4.2mb cut file included! The filenames are in the center of this file.. Big header or sumthing. i dunno 


[http://rapidshare.de/files/9496461/fb2006.met.rar](http://rapidshare.de/files/9496461/fb2006.met.rar)
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-20T12:39:46+00:00
- Post Title: Backyard Games (Atari) - Backyard Football etc.. .Met files

I have downloaded the file and will look at it soon.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2005-12-23T03:25:56+00:00
- Post Title: Backyard Games (Atari) - Backyard Football etc.. .Met files

Ive hexxed out part of an MP3 file from that archive.
not much of information. just showing that there are files 
of value in the archive though.
[hsghah.zip](https://xentaxbackup.github.io/file/503_hsghah.zip)
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-24T05:31:48+00:00
- Post Title: Backyard Games (Atari) - Backyard Football etc.. .Met files

Yeah this is the specs I have so far...

```
| Backyard Football *.met |
+-------------------------+

// Some files have length=0

// ARCHIVE HEADER
  4 - Files Directory Offset (28)
  4 - Files Directory Length
  4 - Number Of Files
  4 - Filename Directory Offset
  4 - Filename Directory Length
  4 - First File Offset
  4 - File Data Length

// FILES DIRECTORY
  // for each file
    4 - Unknown (usually null)
    4 - Filename Offset?
    4 - Unknown
    4 - File Offset
    4 - File Length

// FILENAME DIRECTORY
  1 - null
  
  // for each file
    X - Filename
    1 - null Filename Terminator
    
// FILE DATA
  // for each file
    X - File Data
```


I will be writing a plugin soon, and put it on the wiki once I have check that this spec is correct.

Thanks mate.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-28T10:31:18+00:00
- Post Title: Backyard Games (Atari) - Backyard Football etc.. .Met files

OK, the plugin is in the latest Game Extractor - [http://www.watto.org/extract/download.html](http://www.watto.org/extract/download.html)

Have fun - let us know if you have any problems.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-29T06:56:21+00:00
- Post Title: Backyard Games (Atari) - Backyard Football etc.. .Met files

tnx watt!
## Post #7
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-29T06:56:56+00:00
- Post Title: Backyard Games (Atari) - Backyard Football etc.. .Met files

btw
checked with 2 others.. seems it works with all backyard games!
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-29T08:02:41+00:00
- Post Title: Backyard Games (Atari) - Backyard Football etc.. .Met files

Not a problem - thanks for the update 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-31T06:32:28+00:00
- Post Title: Backyard Games (Atari) - Backyard Football etc.. .Met files

Are there more examples of MET files?
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-01T21:13:28+00:00
- Post Title: Backyard Games (Atari) - Backyard Football etc.. .Met files

Never mind, I downloaded a demo. Here's the MultiEx BMS:

```
Get HeaderSize Long 0 ;
Get DataSize Long 0 ;
SavePos COff 0 ;
Do ;
SavePos FOO 0 ;
Get FO Long 0 ;
If FO <> 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get NSize Long 0 ;
GetDString FName NSize 0 ;
SavePos COff 0 ;
Log FName FO FS FOO FSO ;
Else ;
Set COff Long HeaderSize ;
EndIf ;
While COff < HeaderSize ;
```


See the [viewtopic.php?t=1086&start=60](http://forum.xentax.com/viewtopic.php?t=1086&start=60) manual by Kornet how to add it to MultiEx Commander yourself. 

Below the BMS file. 

It also allows importation, however, I would make backups of the MET files first, because the game may not react too cool to it. Who knows though! 


[met.zip](https://xentaxbackup.github.io/file/532_met.zip)
