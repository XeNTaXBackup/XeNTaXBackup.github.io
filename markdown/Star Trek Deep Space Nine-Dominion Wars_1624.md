## Post #1
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-12-18T15:38:31+00:00
- Post Title: Star Trek: Deep Space Nine-Dominion Wars

This is a old game(2001) but I can't find any extractor for .blt archive.
Download archive sample (making with WATTO's Archive Cutter) at

[http://s6.yousendit.com/d.aspx?id=307TZ ... WDS2TAE1XG](http://s6.yousendit.com/d.aspx?id=307TZQB5NA5LQ0MVWDS2TAE1XG)
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-19T10:44:26+00:00
- Post Title: Star Trek: Deep Space Nine-Dominion Wars

OK, we will look into this for you soon.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2005-12-23T03:32:54+00:00
- Post Title: Star Trek: Deep Space Nine-Dominion Wars

try using Jaeder Naub until someone makes a archivereader for this type.
if you want to replace the files in the archive you should wait for
a real archiveparser, but for temporary extraction i think Jaeder will
do the trick on this one. ...i hope...

EDIT: you would need an BinkPlayer to view the contents of this archive,
from [http://www.radgametools.com/](http://www.radgametools.com/)
[Jaeder Naub V1.7.5f.zip](https://xentaxbackup.github.io/file/504_Jaeder Naub V1.7.5f.zip)
## Post #4
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-12-23T09:55:27+00:00
- Post Title: Star Trek: Deep Space Nine-Dominion Wars

Unfortunately  music probably stored in mp3 files because Jaeder Naub find only bik files with speech.Thank you anyway for help.
## Post #5
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2005-12-23T11:36:20+00:00
- Post Title: Star Trek: Deep Space Nine-Dominion Wars

Further analyzation of the backend of the cutted file, and i came up
with that the music is actually raw PCM data. but as I did not have a header (it was probably cut out) I dont really know what the real format is,
but here is the cutted back file when converted to a WAVE header,
and it seems to be music for me =D
[Back-ds5.zip](https://xentaxbackup.github.io/file/505_Back-ds5.zip)
## Post #6
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-12-23T21:27:02+00:00
- Post Title: Star Trek: Deep Space Nine-Dominion Wars

Ok.Let's wait unpacker.Maybe WATTO can write plugin...
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-24T05:33:20+00:00
- Post Title: Star Trek: Deep Space Nine-Dominion Wars

Specs so far...

```
| Star Trek: Deep Space Nine: Dominion Wars *.blt |
+-------------------------------------------------+

4 - Header (BOLT)
4 - Unknown
4 - Unknown
4 - Unknown
4 - Unknown
4 - Unknown
4 - Directory Offset (64)
4 - null
4 - Unknown
4 - Unknown
4 - Unknown
4 - null
4 - Unknown
4 - Unknown (2)
4 - Archive Size [+18]
4 - null

// for each file
  2 - Unknown (8)
  2 - Unknown (2816)
  4 - File Length
  4 - File Offset
  4 - Hash?
  
X - File Data
```


Will be writing a plugin for this game soon.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2005-12-24T11:19:23+00:00
- Post Title: Star Trek: Deep Space Nine-Dominion Wars

I think the File Offset value is + 4.

the first file in the archive starts at 388, but the
offset value says 384.  

or maybe im just confused =o
## Post #9
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-24T12:11:11+00:00
- Post Title: Star Trek: Deep Space Nine-Dominion Wars

hehe I think you might be right - I would be checking that alittle when I write/test the plugin. I think I remember seeing something like this in one of the archives I was looking at.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-24T17:04:52+00:00
- Post Title: Star Trek: Deep Space Nine-Dominion Wars

Actually, I think there's a little more to this format.

Are there any small archives, so we can have a complete one?
## Post #11
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2005-12-24T21:55:39+00:00
- Post Title: Star Trek: Deep Space Nine-Dominion Wars

God I love analyzing binary data!

If my mom knew that 80% of my life was hexxing strange
files at my computer she would send me to the psychward.

....now that was off topic =o  , but just a little bit.
## Post #12
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-24T22:42:13+00:00
- Post Title: Star Trek: Deep Space Nine-Dominion Wars

Hehe yeah, I wrote my own Hex-analysing program, and sometimes my mum comes over to see what I am doing and she just can't grasp it at all  - just staring at a screen full of numbers.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #13
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-12-25T00:31:04+00:00
- Post Title: Star Trek: Deep Space Nine-Dominion Wars

Upload "smallest" archive file for yours  analysis (10mb)

[http://s43.yousendit.com/d.aspx?id=39RM ... SJ3K8T0FYH](http://s43.yousendit.com/d.aspx?id=39RMRJI02P88X1YOSJ3K8T0FYH)
## Post #14
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-28T10:39:11+00:00
- Post Title: Star Trek: Deep Space Nine-Dominion Wars

I have written a plugin for this game that uses the specs I posted above - it worked on the original file you attached but let me know if you have any further problems and we will look into a more precise spec.

The plugin for this game is in the latest Game Extractor - [http://www.watto.org/extract/download.html](http://www.watto.org/extract/download.html)

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #15
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-12-28T18:41:41+00:00
- Post Title: Star Trek: Deep Space Nine-Dominion Wars

I tried new plugin and it work partially with ds9media.blt(where to be video and audio files).Archive was 227 521 kb and GameExtractor unpack only 20 files (43 mb) probably bik files [http://s35.yousendit.com/d.aspx?id=2XC8 ... Q1O8Y8V5EL](http://s35.yousendit.com/d.aspx?id=2XC8ROZ1K09371XWQ1O8Y8V5EL)
## Post #16
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-28T20:09:28+00:00
- Post Title: 

Oke oke .. no problem .... open extracted file and cut first 4 bytes ->

0000 0000 .... i am using Hex Workshop 4.2 and rename file EXT -> BIK + Install Rad Game Tools 

My result download here

[http://rapidshare.de/files/9992547/default.zip.html](http://rapidshare.de/files/9992547/default.zip.html)

Worked 100%
## Post #17
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-12-28T21:24:37+00:00
- Post Title: 

KorNet thank you for help but how you heard this bik file is only speech.The other part this archive contains music.But Game Extractor dont extract others files...
## Post #18
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-28T21:35:11+00:00
- Post Title: 

Hmmmm ... maybe Watto fixed plugin or me
## Post #19
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-12-28T21:37:18+00:00
- Post Title: 

Small addition 
Strobe's Jaeder Naub found bik files from archive without problem.
Game Extractor add for bik first 4 bytes 0000 0000
## Post #20
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-28T21:55:01+00:00
- Post Title: 

Upload please archive ( Else small archive  )
## Post #21
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-12-28T22:14:29+00:00
- Post Title: 

The contents of this post was deleted because of possible forum rules violation.
## Post #22
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-29T07:04:23+00:00
- Post Title: 

Well it looks like Mr Mouses presumption was correct - we would need to look at some more of these BLT files to correct our specs.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #23
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-31T06:33:32+00:00
- Post Title: 

Like I said, there's more to this archive format.
